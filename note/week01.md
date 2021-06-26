## 課程所使用語言
* python
## 人工智慧
* 傳統用法
  * 搜尋+優化
* 機器學習
  * 統計
  * 神經網路
# 爬山演算法
爬山演算法是一種局部擇優的方法，採用啟發式方法，是對深度優先搜尋的一種改進，它利用反饋資訊幫助生成解的決策。 爬山演算法一般存在以下問題： 局部最大 高地：也稱為平頂，搜尋一旦到達高地，就無法確定搜尋最佳方向，會產生隨機走動，使得搜尋效率降低。
## 簡易爬山演算法 -- 針對單變數函數
* hillClimbing1.py
``` 
def hillClimbing(f, x, dx=0.01):
    while (True):
        print('x={0:.5f} f(x)={1:.5f}'.format(x, f(x)))
        if f(x+dx)>f(x): # 如果右邊的高度 f(x+dx) > 目前高度 f(x) ，那麼就往右走
            x = x + dx
        elif f(x-dx)>f(x): # 如果左邊的高度 f(x-dx) > 目前高度 f(x) ，那麼就往左走
            x = x - dx
        else: # 如果兩邊都沒有比現在的 f(x) 高，那麼這裡就是區域最高點，直接中斷傳回
            break
    return x

    # 高度函數
def f(x):
    return -1*(x*x-2*x+1)
    # return -1*(x*x+3*x+5)
    # return -1*abs(x*x-4)

hillClimbing(f, 0) # 以 x=0 為起點，開始呼叫爬山演算法

    # 執行結果
PS C:\Users\teemo\OneDrive\桌面>  & 'C:\Users\teemo\AppData\Local\Programs\Python\Python38-32\python.exe' 'c:\Users\teemo\.vscode\extensions\ms-python.python-2021.6.944021595\pythonFiles\lib\python\debugpy\launcher' '62633' '--' 'c:\Users\teemo\OneDrive\桌面\ai\02-optimize\01-hillclimbing\02-var1\hillClimbing1.py'
x=0.00000 f(x)=-1.00000
x=0.01000 f(x)=-0.98010
x=0.02000 f(x)=-0.96040
.
.
.
x=0.98000 f(x)=-0.00040
x=0.99000 f(x)=-0.00010
x=1.00000 f(x)=-0.00000
```
## 實作：二維爬山演算法
### 固定調整法
如果我們《上下左右》的調整方法都試一遍，就可以將程式修改如下：

* hillClimbing2.py
```
import random

def hillClimbing(f, x, y, h=0.01):
    while (True):
        fxy = f(x, y)
        print('x={0:.3f} y={1:.3f} f(x,y)={2:.3f}'.format(x, y, fxy))
        if f(x+h, y) >= fxy:
            x = x + h
        elif f(x-h, y) >= fxy:
            x = x - h
        elif f(x, y+h) >= fxy:
            y = y + h
        elif f(x, y-h) >= fxy:
            y = y - h
        else:
            break
    return (x,y,fxy)

def f(x, y):
    return -1 * ( x*x - 2*x + y*y + 2*y - 8 )

hillClimbing(f, 0, 0)
    # 執行結果
PS C:\Users\teemo\OneDrive\桌面>  c:; cd 'c:\Users\teemo\OneDrive\桌面'; & 'C:\Users\teemo\AppData\Local\Programs\Python\Python38-32\python.exe' 'c:\Users\teemo\.vscode\extensions\ms-python.python-2021.6.944021595\pythonFiles\lib\python\debugpy\launcher' '51923' '--' 'c:\Users\teemo\OneDrive\桌面\ai\02-optimize\01-hillclimbing\03-var2\hillClimbing2.py'
x=0.000 y=0.000 f(x,y)=8.000
x=0.010 y=0.000 f(x,y)=8.020
x=0.020 y=0.000 f(x,y)=8.040
.
.
.
x=1.000 y=-0.980 f(x,y)=10.000
x=1.000 y=-0.990 f(x,y)=10.000
x=1.000 y=-1.000 f(x,y)=10.000
```
### 隨機調整法
* hillClimbing2r.py
```
import random

def hillClimbing(f, x, y, h=0.01):
    failCount = 0                    # 失敗次數歸零
    while (failCount < 10000):       # 如果失敗次數小於一萬次就繼續執行
        fxy = f(x, y)                # fxy 為目前高度
        dx = random.uniform(-h, h)   # dx 為左右偏移量
        dy = random.uniform(-h, h)   # dy 為前後偏移量
        if f(x+dx, y+dy) >= fxy:     # 如果移動後高度比現在高
            x = x + dx               #   就移過去
            y = y + dy
            print('x={:.3f} y={:.3f} f(x,y)={:.3f}'.format(x, y, fxy))
            failCount = 0            # 失敗次數歸零
        else:                        # 若沒有更高
            failCount = failCount + 1#   那就又失敗一次
    return (x,y,fxy)                 # 結束傳回 （已經失敗超過一萬次了）

def f(x, y):
    return -1 * ( x*x -2*x + y*y +2*y - 8 )

hillClimbing(f, 0, 0)
    # 執行結果
PS C:\Users\teemo\OneDrive\桌面>  c:; cd 'c:\Users\teemo\OneDrive\桌面'; & 'C:\Users\teemo\AppData\Local\Programs\Python\Python38-32\python.exe' 'c:\Users\teemo\.vscode\extensions\ms-python.python-2021.6.944021595\pythonFiles\lib\python\debugpy\launcher' '57815' '--' 'c:\Users\teemo\OneDrive\桌面\ai\02-optimize\01-hillclimbing\03-var2\hillClimbing2r.py' 
x=-0.005 y=-0.007 f(x,y)=8.000
x=0.004 y=-0.011 f(x,y)=8.004
x=0.006 y=-0.014 f(x,y)=8.029
.
.
.
x=0.999 y=-1.000 f(x,y)=10.000
x=0.999 y=-1.000 f(x,y)=10.000
x=1.000 y=-1.000 f(x,y)=10.000
```
