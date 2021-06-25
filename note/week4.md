## 線性規劃
在數學中，線性規劃（Linear Programming，簡稱LP）特指目標函數和約束條件皆為線性的最佳化問題。
線性規劃是最佳化問題中的一個重要領域。在作業研究中所面臨的許多實際問題都可以用線性規劃來處理，特別是某些特殊情況，例如：網路流、多商品流量等問題，都被認為非常重要。目前已有大量針對線性規劃演算法的研究。很多最佳化問題算法都可以分解為線性規劃子問題，然後逐一求解。在線性規劃的歷史發展過程中所衍伸出的諸多概念，建立了最佳化理論的核心思維，例如「對偶」、「分解」、「凸集」的重要性及其一般化等。
![image](https://user-images.githubusercontent.com/47874872/123458617-d325e500-d617-11eb-9db3-205cfbcd7737.png)
## 單純形法
單純形法（simplex algorithm）在數學優化領域中常用於線性規劃問題的數值求解
下山單純形法（Nelder-Mead method）與單純形法名稱相似，但二者關聯不大。是用於優化多維無約束問題的一種數值方法，屬於更普遍的搜索算法的類別。這兩種方法都使用了單純形的概念。單純形是 {\displaystyle N}N 維中的 {\displaystyle N+1}{\displaystyle N+1} 個頂點的凸包，是一個多胞體：直線上的一個線段，平面上的一個三角形，三維空間中的一個四面體等等，都是單純形。
## Big O
Big O，又稱為漸進符號，是用於描述函式漸近行為的數學符號。更確切地說，它是用另一個（通常更簡單的）函式來描述一個函式數量級的漸近上界。在數學中，它一般用來刻畫被截斷的無窮級數尤其是漸近級數的剩餘項；在電腦科學中，它在分析演算法複雜性的方面非常有用。
## 整數規劃
要求所有的未知量都為整數的線性規劃問題叫做整數規劃或整數線性規劃問題。相對於即使在最壞情況下也能有效率地解出的線性規劃問題，整數規劃問題的最壞情況是不確定的，在某些實際情況中（有約束變量的那些）為NP困難問題。
## NP完全
NP完全或NP完備（NP-Complete，縮寫為NP-C或NPC），是計算複雜度理論中，決定性問題的等級之一。NP完備是NP與NP困難的交集，是NP中最難的決定性問題，所有NP問題都可以被快速歸化為NP完備問題。因此NP完備問題應該是最不可能被化簡為P（多項式時間可決定）的決定性問題的集合。若任何NPC問題得到多項式時間的解法，那此解法就可應用在所有NP問題上。
## 整數編程
一個整數規劃問題是一個數學優化或可行性方案，其中一些或所有的變量都限制為整數。在許多情況下，該術語指的是整數線性規劃（ILP），其中目標函數和約束（除了整數約束）是線性的。
## 泡沫排序
泡沫排序又稱為泡式排序，是一種簡單的排序演算法。它重複地走訪過要排序的數列，一次比較兩個元素，如果他們的順序錯誤就把他們交換過來。走訪數列的工作是重複地進行直到沒有再需要交換，也就是說該數列已經排序完成。這個演算法的名字由來是因為越小的元素會經由交換慢慢「浮」到數列的頂端。
## 循序搜尋法
循序搜尋法會依序比對每一筆資料，所以最大搜索時間為資料大小n，最小搜索時間為1，平均搜尋時間為(n+1)/2。所以其時間複雜度為Ο(n)。
## 優化算法
主題                | 說明
-------------------|----------------------------------------------------
爬山演算法 | 最簡單的優化算法，一直往更高的方向爬
模擬退火法 | 將爬山演算法加上溫度控制，模仿打鐵退火機制(往低的地方)
遺傳演算法 | 又稱基因演算法，模仿物競天擇，適者生存的演化機制(往高的地方)
線性規劃   | 線性規劃，可用單形法或橢圓法在多項式時間內求解
整數規劃   | 整數規劃， 難度為 NP-Complete，但還是有套件可用
## 圖形搜尋
* 圖形表示法
    * [參考資料](https://ithelp.ithome.com.tw/articles/10246151)
    * 相鄰矩陣 (Adjacency Matrix)
    ![picture](https://github.com/www-abcdefg/ai109b/blob/main/pic/%E7%9B%B8%E9%84%B0%E8%88%89%E8%AD%89.png)
    * 相鄰串列 (Adjacency List)
    ![picture](https://github.com/www-abcdefg/ai109b/blob/main/pic/%E7%9B%B8%E9%84%B0%E4%B8%B2%E5%88%97.png)
    * 相鄰多元串列 (Adjacency Multilist)
    ![picture](https://github.com/www-abcdefg/ai109b/blob/main/pic/%E7%9B%B8%E9%84%B0%E5%A4%9A%E5%85%83.png)
    * 索引表 (Index Table)
    ![picture](https://github.com/www-abcdefg/ai109b/blob/main/pic/%E7%B4%A2%E5%BC%95.png)
* 圖形搜尋
    * [參考資料](http://programmermagazine.github.io/201406/htm/focus1.html)
    * 深度優先搜尋
    ![picture](https://github.com/www-abcdefg/ai109b/blob/main/pic/%E6%B7%B1%E5%BA%A6%E5%84%AA%E5%85%88%E6%90%9C%E5%B0%8B.png)
    * 廣度優先搜尋
    ![picture](https://github.com/www-abcdefg/ai109b/blob/main/pic/%E5%BB%A3%E8%B7%AF%E5%84%AA%E5%85%88%E6%90%9C%E5%B0%8B.png)
    * 最佳優先搜尋
        * 最佳優先搜尋的實作方法與廣度優先搜尋類似，但是並不採用佇列 (queue) ，而是採用一種根據優先程度排序的結構，每次都取出最好的那個繼續進行搜尋。但是、節點的好壞通常很難評估，單純採用某種距離去評估往往會過度簡化問題，這點往往是最佳優先搜尋的困難之所在。

參考資料:[線性規劃](https://zh.wikipedia.org/wiki/%E7%BA%BF%E6%80%A7%E8%A7%84%E5%88%92)、[單純形法](https://zh.wikipedia.org/wiki/%E5%8D%95%E7%BA%AF%E5%BD%A2%E6%B3%95)、[Big O](https://zh.wikipedia.org/wiki/%E5%A4%A7O%E7%AC%A6%E5%8F%B7)、[NP完全](https://zh.wikipedia.org/wiki/NP%E5%AE%8C%E5%85%A8)
[整數編程](https://zh.wikipedia.org/wiki/%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F)、[泡沫排序](https://en.wikipedia.org/wiki/Integer_programming)、[循序搜尋法](http://spaces.isu.edu.tw/upload/18833/3/web/search.htm)
