## 傅立葉轉換
傅立葉轉換是一種線性積分轉換，用於信號在時域（或空域）和頻域之間的轉換，在物理學和工程學中有許多應用。因其基本思想首先由法國學者約瑟夫·傅立葉系統地提出，所以以其名字來命名以示紀念。實際上傅立葉轉換就像化學分析，確定物質的基本成分；信號來自自然界，也可對其進行分析，確定其基本成分。

## 科學計算函式庫

### matplotlib - 繪圖工具
* subplot(x,y,z) row_x乘column_y張圖中的第z張。

### NumPy - 數學矩陣運算
NumPy是Python語言的一個擴充程式庫。支援高階大量的維度陣列與矩陣運算，此外也針對陣列運算提供大量的數學函式函式庫。
* import numpy as np
* np.arange(x,y) 從起始值到上限值。
* a[x:y:z] a變數中大於等於x，小於y,一次取z單位。
* np.random.randint(0,10,6) 0~10取6個。
* np.linalg.det(x)求出x矩陣之行列式
* np.add(x,y) 兩矩陣相加。
* .shape() 回傳矩陣為幾乘幾陣列 .shape=(x,y) 重設矩陣維度。
* np.linspace(x,y,z) 從x~y分成z個。
* 可直接使用 a+b a*b a>b 等。

### SymPy - 符號運算
SymPy是一個符號計算的Python庫。它的目標是成為一個全功能的計算機代數系統，同時保持代碼簡潔、易於理解和擴展。
* x,y = symbols('x y') : 建立變數x y
* diff(x,y) : 對x做y微分
* integrate(x,y,z) 對x做積分，範圍是y~z
* factor(x) : x做因式分解
* expand(x) : 將x乘開
* simplify(x) : 如果x有同類項將其合併
* solve(x) : 求解x
* sympy.sqrt(x) :將x開根號

#### 參考資料:[傅立葉轉換](https://zh.wikipedia.org/wiki/%E5%82%85%E9%87%8C%E5%8F%B6%E5%8F%98%E6%8D%A2)、[matplotlib](https://zh.wikipedia.org/zh-tw/Matplotlib)、[NumPy](https://zh.wikipedia.org/wiki/NumPy)、[SymPy](https://zh.wikipedia.org/zh-tw/SymPy)
