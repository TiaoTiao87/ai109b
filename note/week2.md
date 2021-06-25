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
# 實作：爬山演算法

## 簡介

以下是「爬山演算法」 (Hill-Climbing Algorithm) 的一個簡易版本，其方法超簡單，就是一直看旁邊有沒有更好的解，如果有就移過去。然後反覆的作這樣的動作，直到旁邊的解都比現在的更差時，程式就停止，然後將那個位於山頂的解傳回，就完成了。

```
Algorithm HillClimbing(f, x)
  x = 隨意設定一個解。
  while (x 有鄰居 x' 比 x 更高)
    x = x';
  end
  return x;
end
```
