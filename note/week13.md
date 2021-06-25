## 反傳遞演算法
反向傳播是「誤差反向傳播」的簡稱，是一種與最優化方法（如梯度下降法）結合使用的，用來訓練人工神經網絡的常見方法。該方法對網絡中所有權重計算損失函數的梯度。這個梯度會反饋給最優化方法，用來更新權值以最小化損失函數。

反向傳播要求有對每個輸入值想得到的已知輸出，來計算損失函數梯度。因此，它通常被認為是一種監督式學習方法，雖然它也用在一些無監督網絡（如自動編碼器）中。它是多層前饋網絡的Delta規則的推廣，可以用鏈式法則對每層疊代計算梯度。反向傳播要求人工神經元（或「節點」）的激勵函數可微。

### code
* net1.py
```
net.forward()= 10
net.backwward()
x= v:1 g:2 y= v:3 g:6 o= v:10 g:1
gfx = x.g/o.g =  2.0 gfy = y.g/o.g= 6.0
```
* net2.py
```
0  =>  10
1  =>  9.216
2  =>  8.4934656
.
.
.
98  =>  0.003350901606872675
99  =>  0.003088190920893857
x= 0.01687031935884968 y= 0.050610958076549
```
## pytorch
PyTorch是一個開源的Python機器學習庫，基於Torch，底層由C++實現，應用於人工智慧領域，如自然語言處理。它最初由Facebook的人工智慧研究團隊開發，並且被用於Uber的概率編程軟體Pyro。

PyTorch主要有兩大特徵:

* 類似於NumPy的張量計算，可使用GPU加速；

* 基於帶自動微分系統的深度神經網路。

### code

* autograd0.py
```
tensor(2.)
tensor(6.)
10.0   
```

* autograd1.py
```
tensor(2.)
tensor(6.)
10.0
```

* autograd2.py
```
f= 10.0
x.grad= tensor([2., 6.])
```

* torchGd1.py
```
99 x= 0.05263785645365715 loss= 3.792219400405884
199 x= 0.4059540331363678 loss= 2.540982484817505
299 x= 0.6951667666435242 loss= 1.702589750289917
.
.
.
4899 x= 1.999867558479309 loss= 0.0       
4999 x= 1.9998914003372192 loss= 0.0      
Result: x = 1.9998916387557983 loss=0.0 
```

* torchGd2.py
```
99 parameters= [tensor(0.3926, requires_grad=True)] loss= 2.583590269088745
199 parameters= [tensor(0.6843, requires_grad=True)] loss= 1.7311391830444336       
299 parameters= [tensor(0.9230, requires_grad=True)] loss= 1.1599531173706055  
.
.
.
4899 parameters= [tensor(1.9999, requires_grad=True)] loss= 0.0
4999 parameters= [tensor(1.9999, requires_grad=True)] loss= 0.0
Result: parameters = [tensor(1.9999, requires_grad=True)] loss=0.0
```

* torchGd3.py
```
x= tensor([-0.0018, -0.0035], requires_grad=True)
```

### [反傳遞演算法](https://zh.wikipedia.org/wiki/%E5%8F%8D%E5%90%91%E4%BC%A0%E6%92%AD%E7%AE%97%E6%B3%95)、[pytorch](https://zh.wikipedia.org/wiki/PyTorch)
