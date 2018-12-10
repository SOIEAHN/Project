#방송 편성표 예측하기

t = 0
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
    
    print(b)
    #print(b[1])
    
    #a = { b[0]:1, b[1]:2, b[2]:3} 19까지
    #print(a)

    t += 1
