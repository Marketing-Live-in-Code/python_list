# 基本變數－陣列List

陣列（List）是在python中常見的資料型態，是由中括號包覆起來的一個或多個資料，且不限定的格式；陣列（List）內的每個資料，以「,」符號進行分割，陣列 （List） 的起始編號為0，下一個編號為1，以此類推…。你可能會很好奇，一個變數裝一個資料就好了，為何一個變數內要裝那麼多資料？舉例來說，您肯定有搬過家，搬家時箱子（變數）是你的好夥伴，所有文具用品（資料）您會歸類在同一個箱子（變數），所有的書籍（資料）會歸類在另一個箱子（變數）；您會這樣做的目的是什麼？肯定是因為搬到新的住所時，可以快速地找到東西，以方便之後的定位吧！這也是陣列（List）這個變數被創造出來的目的。

![陣列示意圖](https://i.imgur.com/Ag5QqKp.png)

## Array和List差在哪？
> 如果不知道array是什麼，可以跳過這一段～

若您有學過Java，可能會很好奇array和list的差別是什麼？最大的差別就是array內的每個資料型態都一樣，而list則可以不同資料，因此在記憶體的安排上，array會較有效率一點。list呈現的形式如下所示：

```python!
# 陣列中的型態不限制
boxname1 = [1,2,3,4,5]
boxname2 = ['你', '好', '我', '是', '陣列']
boxname3 = [[1,2,3],4,5]
boxname4 = [1,
            '都可以放',
              [
                ['A','B'],
                [2,3]
              ]
            ]
```

## 取得陣列內的資料
取資料的方式很簡單，只需要在該變數後方，一樣使用中括號包覆慾抓取資料的編號，即可取得該資料。

```python!
>>> boxname2 = ['你', '好', '我', '是', '陣列']

>>> boxname2[2]
'我'

>>> boxname2[4]
'陣列'

>>> boxname2[5] #溢位，超出陣列範圍了
IndexError: list index out of range
```

## 資料溢位
「溢位」的意思是，超出陣列的範圍，如下舉例a變數只有5筆資料，最後一筆資料的編號為4，因此輸入a[5]要求取出編號5的內容，電腦就會回復「IndexError: list index out of range」，代表要求的編號超出了陣列。

```python!
>>> a = ['你', '好', '我', '是', '陣列']

>>> a[5] #溢位，超出陣列範圍了
IndexError: list index out of range
```

## 陣列中新增資料
利用append方法，可以在陣列的後方插入資料。

```python!
>>> a = [1, 2, 3, 4, 5]
>>> a.append(6)
>>> print(a)
[1, 2, 3, 4, 5, 6]
```

## 陣列內容排序
sort可以將陣列內的資料進行排序。

```python!
>>> a = [9, 4, 5, 3]
>>> a.sort()
>>> print(a)
[3, 4, 5, 9]
```

## 刪除陣列內容
### del刪除法
刪除陣列內容有多中方式，第一種是del方法，只要在del後輸入想刪除的陣列編號即可。由以下範例可知，輸入「del a[0]」後，除了資料遭到刪除外，整個資料的編號會「順延」，因此若重複執行「del a[0]」，最終一定會將整個陣列的資料刪光光。

```python!
>>> a = [1, 2, 3, 4, 5, 6, 7]
>>> del a[0]
>>> print(a)
[2, 3, 4, 5, 6, 7]

>>> del a[0] # 資料會順延，一直執行會一直砍掉第一個資料
>>> print(a)
[3, 4, 5, 6, 7]
```

### remove刪除法
remove方法是指定刪除資料。以下範例中輸入4，這個4並不是編號，而是指定資料是「4」就進行刪除，但並不是整個陣列中的4都刪除，只刪除「第一個找到的」。

```python=
>>> a = [1, 2, 3, 4, 5, 6, 7]
>>> a.remove(4)
>>> print(a)
[1, 2, 3, 5, 6, 7]

>>> a = [1, 2, 3, 4, 5, 4]
>>> a.remove(4)
>>> print(a)
[1, 2, 3, 5, 4]
```

### pop刪除法
pop是指定刪除編號，若沒有輸入的話，則刪除陣列最後一個資料。

```python=
>>> a = [1, 2, 3, 4, 5, 6, 7]
>>> a.pop(2) # 有指定編號2，那就刪除編號2，刪除時會顯示給你看刪除了甚麼資料
3
>>> print(a)
[1, 2, 4, 5, 6, 7]

>>> b = [1, 2, 3, 4, 5, 6, 7]
>>> b.pop() # 沒有指定任何編號，則刪除最後一個
7
>>> print(b)
[1, 2, 3, 4, 5, 6]
```
