## 笛摩根定律
19世紀英國數學家奧古斯塔斯·德摩根首先發現了在命題邏輯中存在著下面這些關係：

![image](https://user-images.githubusercontent.com/47874872/123464056-e8ead880-d61e-11eb-9fa1-797d9dc697a4.png)

![image](https://user-images.githubusercontent.com/47874872/123463789-8a255f00-d61e-11eb-9112-637c6751c2ce.png)
即：
* 非（p且q）等價於（非p）或（非q）
* 非（p或q）等價於（非p）且（非q）

## 謂詞邏輯
而在謂詞邏輯裏，則有「布林函數」的概念，因此其表達能力較強，例如以下是一些謂詞邏輯的範例。
* Parent(x,y) <= Father(x,y).
* Parent(John, Johnson).
* Ancestor(x,y) <= Parent(x,y).
* Ancestor(x,y) <= Ancestor(x,z) & Parent(z,y).
## 一階邏輯(First-Order Logic)
* 如果我們加上  (對於所有)∀或∃(存在) 這兩個變數限定符號，而其中的謂詞不可以是變項，而必須要是常項，這種邏輯就稱為一階邏輯。
* ∀People(x) => Mortal(x);人都會死
* people(Socrates);蘇格拉底是人
* Mortal(Socrates);所以蘇格拉底會死
## 二階邏輯 (Second-Order Logic)
* 如果一階邏輯中的謂詞，放寬成可以是變項的話 (這些變項可以加上∀與∃等符號的約束)，那就變成了二階邏輯，以下是一些二階邏輯的規則範例。

### 參考資料:[笛摩根定律](https://zh.wikipedia.org/wiki/%E5%BE%B7%E6%91%A9%E6%A0%B9%E5%AE%9A%E5%BE%8B)
