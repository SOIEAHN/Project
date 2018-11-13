#방송 편성표 예측하기
#한 요일을 지정해 이전 10주 치의 편성표를 가져와 가장 많이 방송된 프로그램을 시간대 별로 추려 다음 주 해당요일의 편성표를 예측한다.
#방송국은 jtbc로 선정하였다.
import requests
url = "http://jtbc.joins.com/schedule/20181116"
r = requests.get(url)
r.encoding = 'utf8'
data = str(r.text)
