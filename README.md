# accident_count_moto
import requests//USL擷取套件
res-resquest.get("")//網站內容(內政部交通事故統計)
print res.txt

data=[]//資料放入陣列做統計(A1類 道路交通事故-機車)
count_frq=dict()
for one in data:
  if one in count_frq:
      count_frq[one]+=1
  else:
      count_frq[one]=1
print count_frq

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







90
