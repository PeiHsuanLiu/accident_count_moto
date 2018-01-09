# accident_count_moto
import requests//USL擷取套件
res=resquest.get("https://www.npa.gov.tw/NPAGip/wSite/lp?ctNode=12744&CtUnit=2543&BaseDSD=7")//網站內容(內政部交通事故統計)
print(res.text)
//
from selenium import webdriver

driver = webdriver.PhantomJS(executable_path=r'路徑')  # PhantomJs
driver.get('http://pala.tw/js-example/')  // 輸入網址，交給瀏覽器 
pageSource = driver.page_source  // 取得網頁原始碼
print(pageSource)
driver.close()  //關閉瀏覽器

//取得網頁原始碼、定位元素後，交給BeautifulSoup處理，印出資料
from bs4 import BeautifulSoup
tag = input("定位元素，class前面加上.，id前面加上# ")
res = requests.get('http://pala.tw/class-id-example/')
soup = BeautifulSoup(res.text, "lxml")
for drink in soup.select('{}'.format(tag)):
    print(drink.get_text())

data=[]//資料放入陣列做統計(A1類 道路交通事故-機車)未完
count_frq=dict()
for one in data:
  if one in count_frq:
      count_frq[one]+=1
  else:
      count_frq[one]=1
print count_frq

//計數(未)

from collections import OrderedDict
//OrderedDict先進先出，當容量超出限制，刪除最前面的資料
class LastUpdatedOrderedDict(OrderedDict):
  def __init__(self, capacity):
      super(LastUpdatedOrderedDict,self).__init__()
      self.__capacity=capacity
  def __setitem__(self,key,value):
      containsKey=1 if key in self else 0
      if len(self) - containsKey >= self._capacity:
          last = self.popitem(last=False)
          print 'remove:',last
      if containsKey:
          del self[key]
          print 'set:',(key,value)
      else:
          print 'add:',(key,value)
      OrderedDict.__setitem__(self, key, value)



//google Maps APIs




