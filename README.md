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

//計數(未)，計算特定目錄底下的檔案以及目錄數量
import os
import sys

fileList = []
fileSize = 0
folderCount = 0
rootdir = '/usr/lib'

for root, subFolders, files in os.walk(rootdir):
    folderCount += len(subFolders)
    for file in files:
        f = os.path.join(root,file)
        fileSize = fileSize + os.path.getsize(f)
        #print(f)
        fileList.append(f)

print("Total Size is {0} bytes".format(fileSize))
print(“Total Files “, len(fileList))
print(“Total Folders “, folderCount)

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

//修改地圖模式，縮放比(未)
//加入圖示跟標記
var image ='images/beachfloag.png';
var myLatLag=new google.maps.LatLag(-33.890542, 151.274856);
var beachMarker=new google.maps.Marker({
    position:myLatLng,
    map:map,
    icon: image
});
//路，區塊(設定包含多個座標點的物件)
var flightplanCorrdinates=[
    new google.maps.LatLng(37.772323, -122.214897),
    new google.maps.LatLng(, ),
    new google.maps.LatLng(, ),
    new google.maps.LatLng(, ),
];
var flightPath = new google.maps.PolyLine({
    path:flightPathColorDinates,
    strokeColor:"#FF0000",//筆色為紅色
    strokeOpacity:1.0,//不透明度為1.0
    strokeWeught:2//筆粗2點
    });
    
 //拷貝入HTML

