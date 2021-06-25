# 爬山演算法
* hillClimbingNumber.py
  * 執行結果

```
PS C:\Users\teemo\OneDrive\桌面>  c:; cd 'c:\Users\teemo\OneDrive\桌面'; & 'C:\Users\teemo\AppData\Local\Programs\Python\Python38-32\python.exe' 'c:\Users\teemo\.vscode\extensions\ms-python.python-2021.6.944021595\pythonFiles\lib\python\debugpy\launcher' '60398' '--' 'c:\Users\teemo\OneDrive\桌面\ai\02-optimize\01-hillclimbing\04-framework\hillClimbingNumber.py'
start:  energy(0.000)=4.000
0 : energy(-0.010)=4.000
3 : energy(-0.020)=4.000
.
.
.
394 : energy(-1.980)=0.080
395 : energy(-1.990)=0.040
396 : energy(-2.000)=0.000
solution:  energy(-2.000)=0.000
```

# 模擬退火法 (Simulated-Annealing)

## 演算法

```
Algorithm SimulatedAnnealing(s)
  while (溫度還不夠低，或還可以找到比 s 更好的解 s' 的時候)
    根據能量差與溫度，用機率的方式決定是否要移動到新解 s'。
    # (機率：溫度高時可以往上走，溫度低的時候差不多只能往下走)
    將溫度降低一些
  end
end
```
