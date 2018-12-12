# Project
t = 0
count = 1
while t <= 3:
    from urllib.request import urlopen
    from bs4 import BeautifulSoup

    i = str(input())
    url = 'http://jtbc.joins.com/schedule/'+i

    html = urlopen(url)
    bsObj = BeautifulSoup(html, "html.parser")
    nameList = bsObj.findAll("strong", {"class":"title"})
    b=[]
    i=0
    for name in nameList:
         words = name.get_text()
         words = words.replace(' ','')
    
         words = words.split()
         #print(words)
         #if words[1] in words:
             #del words[1]
    
         b.append(words[0])
    
    print(b[0])
    
    for i in range(2):
        for j in range(len(b[i])):
            
               if(b[i] == b[j]) count+=1
    print(count)
    t += 1



