# 傅立葉轉換在語音識別中的應用

## 目錄
* [傅立葉轉換](#傅立葉轉換)
* [語音辨識的原理](#語音辨識的原理)
* [語音辨識的應用](#語音辨識的應用)
* [實作](#實作)
* 結論

## 傅立葉轉換

傅立葉轉換是一種線性積分轉換，用於信號在時域（或空域）和頻域之間的轉換，在物理學和工程學中有許多應用。

## 語音辨識的原理

* 人類講話的聲音可以以『示波器』測量成一個隨時間變化的波形信號，這種信號對時間的關係，稱之為「時域」，在電腦對信號進行分析時，通常信號會先被轉換成在不同頻率下對應的振幅及相位，稱之為「頻域」，轉換的公式稱為「傅立葉變換」，信號經過每隔一段時間取樣，就得到可以進行分析的數位音檔，附檔名通常是 wav。

![image](https://user-images.githubusercontent.com/47874872/123516967-640cc700-d6d1-11eb-86d3-7bb780c4292a.png)

* 為了方便作語音辨識，與影像一樣，我們會對語音作特徵抽取(Feature Extraction)，目前有 FBank、MFCC(Mel frequency cepstral coefficients) 兩種，特徵抽取前須先對聲音作前置處理：
1.幀(Frame)切割：通常每幀是25ms，幀與幀之間重疊10ms，以避免邊界信號的遺漏。
2.信號加強：針對高頻信號作加強，使信號更清楚。
3.加窗(Window)：目的是消除各個幀兩端可能會造成的信號不連續性，常用的窗函數有方窗、漢明窗等。
4.去除雜訊(denoising or noise reduction)。

## 語音辨識的應用

語音辨識技術的應用包括語音撥號、語音導航、室內裝置控制、語音文件檢索、簡單的聽寫資料錄入等。語音辨識技術與其他自然語言處理技術如機器翻譯及語音合成技術相結合，可以構建出更加複雜的應用，例如語音到語音的翻譯。
語音辨識技術所涉及的領域包括：訊號處理、圖型識別、概率論和資訊理論、發聲機理和聽覺機理、人工智慧等等。

Google助理

![image](https://user-images.githubusercontent.com/47874872/123517055-c36ad700-d6d1-11eb-8aee-5d35566c360c.png)

Siri

![image](https://user-images.githubusercontent.com/47874872/123517074-d1b8f300-d6d1-11eb-94f0-f9de3ec32f03.png)

## 實作

1.install the required package using: pip install SpeechRecognitio pyaudio

2.[RunCode](https://github.com/TiaoTiao87/ai109b/blob/main/Final/VoiceToText.py)

3.Say Something

4.Result

![image](https://user-images.githubusercontent.com/47874872/123517578-56a50c00-d6d4-11eb-8c58-8aba442e9760.png)


#### 參考資料:[傅立葉轉換](https://zh.wikipedia.org/wiki/%E5%82%85%E9%87%8C%E5%8F%B6%E5%8F%98%E6%8D%A2)、[語音辨識](https://ithelp.ithome.com.tw/articles/10195763)、[code](https://gist.github.com/soja-soja/64fb66c17a59dd913d7a05d33724c306)
