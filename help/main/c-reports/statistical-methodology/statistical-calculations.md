---
keywords: 報表；統計方法；統計計算；統計數字；平均值；轉換率；每位訪客收入；rpv；信賴區間；提升度；welch t test；離線計算
description: 了解手動中使用的統計計算 [!UICONTROL A/B測試] 活動 [!DNL Adobe Target].
title: 如何了解中使用的統計計算 [!UICONTROL A/B測試] 活動？
feature: Reports
source-git-commit: 4baa78ac1119e86002c415f09b9481ad351fdcfc
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 2%

---

# A/Bn測試中的統計計算

本文記錄了在 [!DNL Adobe Target]. 提供的定義 [!UICONTROL 轉換率], [!UICONTROL 轉換率的信賴區間], [!UICONTROL 提升度], [!UICONTROL 提升度的信賴區間]，和 [!UICONTROL 信賴度].

>[!NOTE]
>
>本文中的資訊取代 *Adobe Target A/B測試計算* 之前可在此網站下載的pdf檔案。

![顯示 [!UICONTROL 轉換率], [!UICONTROL 平均提升度和信賴區間]，和 [!UICONTROL 信賴度] A/B測試活動的區段。](/help/main/c-reports/statistical-methodology/img/target_report.png)

## 平均效能

下節將說明上圖中使用的計算。

### 每位訪客(RPV)促銷活動的轉換率和收入

下圖顯示 [!UICONTROL 轉換率], [!UICONTROL 轉換率的信賴區間]，以及 [!UICONTROL 轉換] 在 [!DNL Target] 報表。 例如，第一行顯示體驗A:the [!UICONTROL 轉換率] 為25.81%，若 [!UICONTROL 信賴區間] 記錄±7.7%和32次轉換。 鑒於124位訪客看過體驗，這等於32/124 = 25.81%。

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

轉換率或 **平均值**, *μ<sub>ν</sub>*，針對每個體驗 *ν* 在實驗中，定義為量度總和與指派給該量度的單位數之比， *N<sub>ν</sub>*:

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

此處，

* *Y<sub>iν</sub>* 是每個單位的量度值 *i*，已指派給指定體驗 *ν*.

* 單位總和 *i* 取決於計數方法的選擇。

   * 若 *[!UICONTROL 訪客]* 作為計數方法使用，每個單位都是在活動期間定義為活動中唯一參與者的獨特訪客。
   * 若 *[!UICONTROL 瀏覽]* 作為計數方法，每個單位都是獨特造訪，定義為在 [!DNL Target] 工作階段(具有唯一 `sessionId`)。 當 `sessionId` 變更，或訪客達到轉換步驟，則會計入新瀏覽。
   * 若 *[!UICONTROL 活動曝光數]* 作為計數方法，每個單位都是獨特的曝光，定義為訪客每次載入活動的任何頁面時。

## [!UICONTROL 平均值的信賴區間]/[!UICONTROL 轉換率]

轉換率的信賴區間被直觀地定義為與基礎資料一致的可能轉換率範圍。

執行實驗時，指定體驗的轉換率為 *估計* 的值。 為了量化這一估計中的不確定性， [!DNL Target] 使用信賴區間。 [!DNL Target] 一律會報告95%信賴區間，這表示從長遠來看，95%計算的信賴區間包含體驗的真正轉換率。

轉換率的95%信賴區間 *μ<sub>ν</sub>* 定義為值範圍：

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

其中平均值的標準誤差定義為

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

其中，會使用樣本標準差的無偏估計：

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

請注意，當促銷活動是轉換率促銷活動時（亦即，轉換量度為二進位），標準錯誤會降為：

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## 提升度

下圖顯示 [!UICONTROL 提升度] 和 [!UICONTROL 提升度的信賴區間] 在 [!DNL Target] 報告。 數字代表提升度界限的平均範圍，而如果提升度為正或負，箭頭會反映。 箭頭會以灰色顯示，直到信賴度超過95%為止。 信賴度超過臨界值後，箭頭會根據正或負提升度而變成綠色或紅色。

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

體驗之間的提升度  *ν*，以及控制體驗 *ν<sub>0</sub>* 是轉換率中的相對「差值」，定義為

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

個別轉換率如上所定義。 更簡單的是，

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

如果控制體驗的轉換率 *ν<sub>0</sub>* 為0，則沒有提升度。

## [!DNL Confidence Interval of Lift]

中的盒形圖 [!UICONTROL 平均提升度和信賴區間] column代表平均值，而95% [!UICONTROL 提升度的信賴區間]. 當給定非控制體驗與控制體驗的信賴區間有任何重疊時，盒形圖會呈灰色；當給定體驗的信賴區間範圍高於或低於控制體驗的信賴區間時，盒形圖會呈綠色或紅色。

體驗之間提升度的標準錯誤  *ν*，以及控制體驗  *ν<sub>0</sub>* 定義為：

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="metric-mean"></p>

提升度的95%信賴區間為：

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

此計算使用「Delta」方法，並有說明 [本檔案的更詳細資訊](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL 可信度]

最後一欄顯示 [!DNL Target] 報表。 假設空值假設為真，體驗的信賴度是取得較實際觀察到的結果低於極值的可能性（以百分比表示）。 就p值而言，顯示的信賴度為 *1 - p值*. 直覺上，較高的信賴度表示控制與非控制體驗有相同轉換率的可能性較低。

在 [!DNL Target]，雙尾 **韋爾奇的T型** 在測試體驗與控制體驗之間執行，以測試測試和控制體驗的方式是否相同。 因為在執行實驗之前，我們通常不知道兩個群組的樣本大小和變異是否相同，以及 [!DNL Target] 也可讓您擁有傳送至每個體驗的不相等流量百分比，我們不會假設每個體驗的變數相等。 因此，Welch的t檢定被選中，而不是Student的t檢定。

為了進行Welch的t檢驗，首先計算t統計量和自由度，然後運行雙尾t檢驗，生成p值。 最後，根據p值計算置信度。

此 *t*-stantitic被定義為任意兩個獨立隨機變數的方法之差， *ν* 和 *ν<sub>0</sub>*，除以差異的標準誤差：

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

where *μ<sub>v</sub>* 和 *μ<sub>v0</sub>* 是 *ν*  和 *ν<sub>0</sub>* 與標準差 *μ<sub>v</sub>* 和 *μ<sub>v0</sub>* 由提供：

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

where *σ<sup>2</sup><sub>v</sub>* 和 *σ<sup>2</sup><sub>v<sub>0</sub></sub>* 是兩個體驗的差異 *ν*  和 *ν<sub>0</sub>* 和 *N<sub>v</sub>* 和 *N<sub>v<sub>0</sub></sub>* 的樣本大小 *ν* 和 *ν<sub>0</sub>* 分別為5個。

對於Welch的t檢驗，自由度計算如下：

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

和自由度 *ν*  和 *ν<sub>0</sub>* 定義為：

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

然後，可從 *t* — 分發：

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

最後， [!DNL Target] 定義為：

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## 離線執行計算

[下載的 CSV 報表](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)只包含原始資料，不含計算度量，例如每次造訪帶來的收入、提升度或用於 A/B 測試的信賴度。

若要計算這些統計數量，請下載Target的 [完整可信度電腦](/help/main/assets/complete_confidence_calculator.xlsx) 輸入活動值的Excel檔案。