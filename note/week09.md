## 神經網路
在電腦領域，神經網路是指一種模擬神經系統所設計出來的程式，用來模擬人類視覺、聽覺等等智慧行為的原理，企圖讓電腦可以具有人類智慧的一種方法。
![image](https://user-images.githubusercontent.com/47874872/123462748-4847e900-d61d-11eb-8b43-e01a4ea6061b.png)
* a1~an為輸入向量的各個分量
* w1~wn為神經元各個突觸的權值
* b為偏置
* f為傳遞函式，通常為非線性函式。一般有traingd(),tansig(),hardlim()。以下預設為hardlim()
* t為神經元輸出
### 單層神經元網路
是最基本的神經元網路形式，由有限個神經元構成，所有神經元的輸入向量都是同一個向量。由於每一個神經元都會產生一個純量結果，所以單層神經元的輸出是一個向量，向量的維數等於神經元的數目。
![image](https://user-images.githubusercontent.com/47874872/123462873-6f061f80-d61d-11eb-9ee9-8a99eaf63dbc.png)
## 梯度下降法
要使用梯度下降法找到一個函數的局部極小值，必須向函數上當前點對應梯度（或者是近似梯度）的反方向的規定步長距離點進行疊代搜索。
![image](https://user-images.githubusercontent.com/47874872/123463038-9fe65480-d61d-11eb-89f5-521349131008.png)

* diff.py
```
diff(f,2)= 12.006000999997823
```
* e.py
```
n= 100.0 e(n)= 2.7048138294215285
n= 200.0 e(n)= 2.711517122929317
n= 300.0 e(n)= 2.7137651579427837
.
.
.
n= 9900.0 e(n)= 2.718144554210053
n= 10000.0 e(n)= 2.7181459268249255
```
* gd1.py
```
import numpy as np
from numpy.linalg import norm 

# 函數 f 對變數 k 的偏微分: df / dk
def df(f, p, k, step=0.01):
    p1 = p.copy()
    p1[k] = p[k]+step
    return (f(p1) - f(p)) / step

# 函數 f 在點 p 上的梯度
def grad(f, p, step=0.01):
    gp = p.copy()
    for k in range(len(p)):
        gp[k] = df(f, p, k, step)
    return gp

# 使用梯度下降法尋找函數最低點
def gradientDescendent(f, p0, step=0.01):
    p = p0.copy()
    i = 0
    while (True):
        i += 1
        fp = f(p)
        gp = grad(f, p) # 計算梯度 gp
        glen = norm(gp) # norm = 梯度的長度 (步伐大小)
        print('{:d}:p={:s} f(p)={:.3f} gp={:s} glen={:.5f}'.format(i, str(p), fp, str(gp), glen))
        if glen < 0.00001:  # 如果步伐已經很小了，那麼就停止吧！
            break
        gstep = np.multiply(gp, -1*step) # gstep = 逆梯度方向的一小步
        p +=  gstep # 向 gstep 方向走一小步
    return p # 傳回最低點！
```
* gdGate.py
```
import numpy as np
import math
import gd3 as gd

def sig(t):
    return 1.0/(1.0+math.exp(-t))

o = [0,0,0,1] # and gate outputs
# o = [0,1,1,1] # or gate outputs
# o = [0,1,1,0] # xor gate outputs
def loss(p, dump=False):
    [w1,w2,b] = p
    o0 = sig(w1*0+w2*0+b)
    o1 = sig(w1*0+w2*1+b)
    o2 = sig(w1*1+w2*0+b)
    o3 = sig(w1*1+w2*1+b)
    delta = np.array([o0-o[0], o1-o[1], o2-o[2], o3-o[3]])
    if dump:
        print('o0={:.3f} o1={:.3f} o2={:.3f} o3={:.3f}'.format(o0,o1,o2,o3))
    return np.linalg.norm(delta, 2)

p = [0.0, 0.0, 0.0] # [w1,w2,b] 
plearn = gd.gradientDescendent(loss, p, max_loops=3000)
loss(plearn, True)
```
* gdNumber.py
```
1:p=[1.0, 3.0] f(p)=10.000 gp=[2.009999999999934, 6.009999999999849] glen=6.33721
2:p=[0.9799 2.9399] f(p)=9.603 gp=[1.9698 5.8898] glen=6.21046
3:p=[0.960202 2.881002] f(p)=9.222 gp=[1.930404 5.772004] glen=6.08625
.
.
.
35:p=[1.96547941] f(p)=0.137 gp=[-3.94095882] glen=3.94096
36:p=[2.004889] f(p)=0.020 gp=[4.019778] glen=4.01978
37:p=[1.96469122] f(p)=0.140 gp=[-3.93938244] glen=3.93938
```

#### 參考資料:[神經網路](https://zh.wikipedia.org/wiki/%E4%BA%BA%E5%B7%A5%E7%A5%9E%E7%BB%8F%E7%BD%91%E7%BB%9C)、[單層神經元網路](https://www.itread01.com/content/1546617093.html)、[梯度下降法](https://zh.wikipedia.org/wiki/%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E6%B3%95)
