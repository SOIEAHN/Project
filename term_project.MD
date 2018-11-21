#방송 편성표 예측하기
#한 요일을 지정해 이전 10주 치의 편성표를 가져와 가장 많이 방송된 프로그램을 시간대 별로 추려 다음 주 해당요일의 편성표를 예측한다.
#방송국은 jtbc로 선정하였다.
from urllib.request import urlopen
from bs4 import BeautifulSoup
html = urlopen('http://jtbc.joins.com/schedule/20181116')
bsObj = BeautifulSoup(html, "html.parser")
nameList = bsObj.findAll("strong", {"class":"title"})
for name in nameList:
    words = name.get_text()
    words = words.replace(' ', '')
    words = words.replace('3회', '')
    words = words.replace('86회', '')
    words = words.replace('362회', '')
    words = words.replace('1회', '')
    words = words.replace('105회', '')
    words = words.replace('13회', '')
    words = words.replace('14회', '')
    words = words.replace('6회', '')
    words = words.replace('29회', '')
    words = words.replace('20회', '')
    words = words.replace('15회', '')
    words = words.replace('\n', '')
    
    print(words)
