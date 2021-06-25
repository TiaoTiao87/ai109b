# 爬山演算法
* hillClimbingNumber.py(求|x^2-4|的解)

* 執行結果
```
PS C:\Users\teemo\OneDrive\桌面>  c:; cd 'c:\Users\teemo\OneDrive\桌面'; & 'C:\Users\teemo\AppData\Local\Programs\Python\Python38-32\python.exe' 'c:\Users\teemo\.vscode\extensions\ms-python.python-2021.6.944021595\pythonFiles\lib\python\debugpy\launcher' '60398' '--' 'c:\Users\teemo\OneDrive\桌面\ai\02-optimize\01-hillclimbing\04-framework\hillClimbingNumber.py'
# 2
start:  energy(0.000)=4.000
0 : energy(0.010)=4.000
1 : energy(0.020)=4.000
.
.
.
375 : energy(1.980)=0.080
378 : energy(1.990)=0.040
379 : energy(2.000)=0.000
solution:  energy(2.000)=0.000
# -2
start:  energy(0.000)=4.000
0 : energy(-0.010)=4.000
4 : energy(-0.020)=4.000
.
.
.
381 : energy(-1.980)=0.080
382 : energy(-1.990)=0.040
384 : energy(-2.000)=0.000
solution:  energy(-2.000)=0.000
```
* hillClimbingArray.py(求x^2+3y^2+z^2-x-3y-5z+8的解)

* 執行結果
```
PS C:\Users\teemo\OneDrive\桌面>  c:; cd 'c:\Users\teemo\OneDrive\桌面'; & 'C:\Users\teemo\AppData\Local\Programs\Python\Python38-32\python.exe' 'c:\Users\teemo\.vscode\extensions\ms-python.python-2021.6.944021595\pythonFiles\lib\python\debugpy\launcher' '60398' '--' 'c:\Users\teemo\OneDrive\桌面\ai\02-optimize\01-hillclimbing\04-framework\hillClimbingArray.py'
start:  energy([1, 1, 1])=1.000000
2 : energy([1, 0.99, 1])=0.970300
3 : energy([1, 0.98, 1])=0.941200
5 : energy([1.01, 0.98, 1])=0.921300
.
.
.
939 : energy([2.000000000000001, 0.49999999999999956, 2.4899999999999904])=-2.999900
941 : energy([2.000000000000001, 0.49999999999999956, 2.4999999999999902])=-3.000000
solution:  energy([2.000000000000001, 0.49999999999999956, 2.4999999999999902])=-3.000000
```
* hillClimbingEquation.py(求聯立方程式的解)
* 執行結果
```
PS C:\Users\teemo\OneDrive\桌面>  c:; cd 'c:\Users\teemo\OneDrive\桌面'; & 'C:\Users\teemo\AppData\Local\Programs\Python\Python38-32\python.exe' 'c:\Users\teemo\.vscode\extensions\ms-python.python-2021.6.944021595\pythonFiles\lib\python\debugpy\launcher' '60398' '--' 'c:\Users\teemo\OneDrive\桌面\ai\02-optimize\01-hillclimbing\04-framework\hillClimbingEquation.py'
start:  energy([[0. 0. 0.]])=2.449490
1 : energy([[-0.00609901  0.00928858  0.        ]])=2.444282
2 : energy([[-0.00599859  0.01631615  0.        ]])=2.432737
3 : energy([[-0.01386364  0.02253069  0.00673913]])=2.416567
.
.
.
5584 : energy([[-5.00051891  3.00704409  1.9969727 ]])=0.003237
5599 : energy([[-4.99964782  3.00560519  1.9969727 ]])=0.002775
5718 : energy([[-4.99964782  3.00093459  1.99935104]])=0.000443
solution:  energy([[-4.99964782  3.00093459  1.99935104]])=0.000443
```
* hillClimbingScheduling.py(排課表)
* 執行結果
```
PS C:\Users\teemo\OneDrive\桌面>  c:; cd 'c:\Users\teemo\OneDrive\桌面'; & 'C:\Users\teemo\AppData\Local\Programs\Python\Python38-32\python.exe' 'c:\Users\teemo\.vscode\extensions\ms-python.python-2021.6.944021595\pythonFiles\lib\python\debugpy\launcher' '60398' '--' 'c:\Users\teemo\OneDrive\桌面\ai\02-optimize\01-hillclimbing\04-framework\hillClimbingScheduling.py'
solution:  score=-3.880000
 A11:電子 A12:電子 A13:電子 A14:電子 A15:離散 A16:離散 A17:離散
 A21:　　 A22:工數 A23:工數 A24:工數 A25:演算 A26:演算 A27:演算
 A31:　　 A32:計概 A33:計概 A34:計概 A35:行動 A36:行動 A37:行動
 A41:　　 A42:網站 A43:網站 A44:網站 A45:視窗 A46:視窗 A47:視窗
 A51:　　 A52:軟工 A53:軟工 A54:軟工 A55:系統 A56:系統 A57:系統
 B11:　　 B12:科學 B13:科學 B14:科學 B15:網頁 B16:網頁 B17:網頁
 B21:　　 B22:網路 B23:網路 B24:網路 B25:智慧 B26:智慧 B27:智慧
 B31:　　 B32:　　 B33:動畫 B34:動畫 B35:結構 B36:結構 B37:結構
 B41:　　 B42:機率 B43:機率 B44:動畫 B45:線代 B46:線代 B47:線代
 B51:　　 B52:媒體 B53:媒體 B54:媒體 B55:嵌入 B56:嵌入 B57:嵌入
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

### 演算步驟
#### 初始化
由一個產生函數從當前解產生一個位於解空間的新解，並定義一個足夠大的數值作為初始溫度。

#### 疊代過程
疊代過程是模擬退火算法的核心步驟，分為新解的產生和接受新解兩部分：
1.由一個產生函數從當前解產生一個位於解空間的新解；為便於後續的計算和接受，減少算法耗時，通常選擇由當前新解經過簡單地變換即可產生新解的方法，如對構成新解的全部或部分元素進行置換、互換等，注意到產生新解的變換方法決定了當前新解的鄰域結構，因而對冷卻進度表的選取有一定的影響。
2.計算與新解所對應的目標函數差。因為目標函數差僅由變換部分產生，所以目標函數差的計算最好按增量計算。事實表明，對大多數應用而言，這是計算目標函數差的最快方法。
3.判斷新解是否被接受，判斷的依據是一個接受準則，最常用的接受準則是Metropolis準則：若Δt′<0則接受S′作為新的當前解S，否則以概率exp（-Δt′/T）接受S′作為新的當前解S。
4.當新解被確定接受時，用新解代替當前解，這只需將當前解中對應於產生新解時的變換部分予以實現，同時修正目標函數值即可。此時，當前解實現了一次疊代。可在此基礎上開始下一輪試驗。而當新解被判定為捨棄時，則在原當前解的基礎上繼續下一輪試驗。
模擬退火算法與初始值無關，算法求得的解與初始解狀態S（是算法疊代的起點）無關；模擬退火算法具有漸近收斂性，已在理論上被證明是一種以概率1收斂於全局最優解的全局優化算法；模擬退火算法具有並行性。
#### 停止準則
疊代過程的停止準則：溫度T降至某最低值時，完成給定數量疊代中無法接受新解，停止疊代，接受當前尋找的最優解為最終解。
#### 退火方案
在某個溫度狀態T下，當一定數量的疊代操作完成後，降低溫度T，在新的溫度狀態下執行下一個批次的疊代操作。

#### 參考資料:[維基百科-模擬退火](https://zh.wikipedia.org/wiki/%E6%A8%A1%E6%8B%9F%E9%80%80%E7%81%AB)
