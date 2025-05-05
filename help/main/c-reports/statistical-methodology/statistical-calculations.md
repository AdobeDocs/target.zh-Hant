---
keywords: 報表；統計方法；統計計算；統計；平均值；轉換率；每位訪客帶來的收入；rpv；信賴區間；提升度；welch t測試；離線計算
description: 瞭解在 [!DNL Adobe Target]中手動[!UICONTROL A/B Test]活動中使用的統計計算。
title: 如何瞭解[!UICONTROL A/B Test]活動中使用的統計計算？
feature: Reports
exl-id: 5f7377b9-0567-4b6f-8968-4696b2088d0a
source-git-commit: bb95d160940737e23022d70cbe56567f79cbf255
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 2%

---

# A/Bn測試中的統計計算

本文記錄了[!DNL Adobe Target]中手動A/Bn測試使用的詳細統計計算。 已提供[!UICONTROL Conversion Rate]、[!UICONTROL Confidence Interval of Conversion Rate]、[!UICONTROL Lift]、[!UICONTROL Confidence Interval for Lift]和[!UICONTROL Confidence]的定義。

>[!NOTE]
>
>本文資訊取代了&#x200B;*Adobe Target Calculations for A/B Testing* pdf檔案（先前可在此網站下載）。

![顯示A/B測試活動[!UICONTROL Conversion Rate]、[!UICONTROL Average Lift and Confidence Interval]和[!UICONTROL Confidence]的目標報告。](/help/main/c-reports/statistical-methodology/img/target_report.png)

## 平均績效

下節將說明上圖中所使用的計算。

### 轉換率和每位訪客帶來的收入(RPV)行銷活動

下圖顯示[!DNL Target]報表中的[!UICONTROL Conversion Rate]、[!UICONTROL Confidence Interval of Conversion Rate]和[!UICONTROL Conversions]數目。 例如，第一行顯示對於體驗A： [!UICONTROL Conversion Rate]為25.81%，[!UICONTROL Confidence Interval]為±7.7%，且已記錄32次轉換。 假設有124位訪客看過該體驗，則等於32/124 = 25.81%。

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

實驗中的每個體驗&#x200B;*ν*&#x200B;的轉換率或&#x200B;**平均值**，*μ<sub>ν</sub>*，定義為量度總和相對於指派給該量度的單位數的比率，*N<sub>ν</sub>*：

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

此處，

* *Y<sub>iν</sub>*&#x200B;是指派給指定體驗&#x200B;*ν*&#x200B;之每個單位&#x200B;*i*&#x200B;的量度值。

* 單位&#x200B;*i*&#x200B;的總和取決於計數方法的選擇。

   * 如果使用&#x200B;*[!UICONTROL Visitors]*&#x200B;做為計數方法，則每個單位都是定義為活動終生中唯一參與者的不重複訪客。
   * 如果使用&#x200B;*[!UICONTROL Visits]*&#x200B;做為計數方法，則每個單位都是定義為在[!DNL Target]工作階段期間體驗中唯一參與者的唯一造訪（具有唯一的`sessionId`）。 當`sessionId`變更時，或訪客達到轉換步驟時，即會計為新造訪。
   * 如果使用&#x200B;*[!UICONTROL Activity Impressions]*&#x200B;做為計數方法，則每個單位都是定義為每次訪客載入活動的任何頁面時的唯一曝光數。

## [!UICONTROL Confidence Interval of Mean]/[!UICONTROL Conversion Rate]

轉換率的信賴區間在直覺上定義為與基礎資料一致的可能轉換率範圍。

執行實驗時，特定體驗的轉換率是&quot;true&quot;轉換率的&#x200B;*預估值*。 若要量化此估計中的不確定性，[!DNL Target]會使用信賴區間。 [!DNL Target]一律會報告95%的信賴區間，這表示到最後，95%的信賴區間都會包含體驗的真正轉換率。

轉換率&#x200B;*μ<sub>ν</sub>*&#x200B;的95%信賴區間定義為值的範圍：

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

其中平均值的標準誤差定義為

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

其中使用樣本標準差的無偏估計值：

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

當行銷活動為轉換率行銷活動時（即轉換量度為二進位），標準錯誤會減少為：

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## 提升度

下圖顯示[!DNL Target]報告中的[!UICONTROL Lift]和[!UICONTROL Confidence Interval of Lift]。 數字代表提升度界限的平均值，而箭頭則反映提升度是正數或負數。 箭頭會以灰色顯示，直到信賴度超過95%為止。 信賴度超過臨界值後，箭頭會根據提升度為正值或負值，變成綠色或紅色。

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

體驗&#x200B;*ν*&#x200B;與控制體驗&#x200B;*ν<sub>0</sub>*&#x200B;之間的提升度是轉換率的相對「差異」，定義為

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

其中個別轉換率定義如上。 更簡單地說，

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

如果控制體驗&#x200B;*ν<sub>0</sub>*&#x200B;的轉換率為0，則沒有提升度。

## [!DNL Confidence Interval of Lift]

[!UICONTROL Average Lift and Confidence Interval]欄中的箱形圖代表平均值和95% [!UICONTROL Confidence Interval of Lift]。 指定非控制體驗的信賴區間與控制體驗的信賴區間發生任何重疊時，箱形圖就會呈現灰色。 當指定體驗的信賴區間範圍高於或低於控制體驗的信賴區間時，箱形圖就會呈現綠色或紅色。

體驗&#x200B;*ν*&#x200B;與控制體驗&#x200B;*ν<sub>0</sub>*&#x200B;之間提升度的標準錯誤定義為：

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="量度平均值"></p>

提升度的95%信賴區間是：

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

此計算使用「差異」方法，本檔案將詳細說明[&#128279;](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL Confidence]

最後一欄顯示[!DNL Target]報表中的可信度。 體驗的信賴度是一種取得極端結果的機率（以百分比表示），當作觀察到的結果，假設null假設為true。 就p值而言，顯示的信賴度為&#x200B;*1 - p值*。 直覺上，較高的信賴度表示控制體驗和非控制體驗擁有相同轉換率的可能性較低。

在[!DNL Target]中，會在測試體驗與控制體驗之間執行雙尾&#x200B;**Welch的t檢定**，以測試測試與控制體驗的方法是否相同。 因為在執行實驗之前，我們通常不知道兩個群組的樣本大小和差異是否相同，而且[!DNL Target]也允許您傳送到每個體驗的流量百分比不相等，因此我們不假設每個體驗的差異相等。 因此，選擇Welch的t檢驗，而非Student的t檢驗。

若要執行Welch的t檢定，我們先開始計算t統計值和自由度，然後執行雙尾t檢定，以產生p值。 最後，我們會根據p值計算可信度。

*t*&#x200B;統計值定義為任何兩個獨立隨機變數&#x200B;*ν*&#x200B;和&#x200B;*ν<sub>0</sub>*&#x200B;之平均值除以差異的標準誤差：

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

其中&#x200B;*μ<sub>v</sub>*&#x200B;和&#x200B;*μ<sub>v0</sub>*&#x200B;分別為&#x200B;*ν*&#x200B;和&#x200B;*ν<sub>0</sub>*&#x200B;的均值，且&#x200B;*μ<sub>v</sub>*&#x200B;和&#x200B;*μ<sub>v0</sub>*&#x200B;之間差值的標準誤差由以下給出：

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

其中&#x200B;*σ<sup>2</sup><sub>v</sub>*&#x200B;和&#x200B;*σ<sup>2</sup><sub>v<sub>0</sub></sub>*&#x200B;分別為兩個體驗&#x200B;*ν*&#x200B;和&#x200B;*ν<sub>0</sub>*&#x200B;的變異，而&#x200B;*N<sub>v</sub>*&#x200B;和&#x200B;*N<sub>v<sub>0</sub></sub>*&#x200B;分別為&#x200B;*ν*&#x200B;和&#x200B;*ν<sub>0</sub>*&#x200B;的樣本大小。

對於Welch的t檢定，自由度計算如下：

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

*ν*&#x200B;和&#x200B;*ν<sub>0</sub>*&#x200B;的自由度定義為：

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

然後可以從&#x200B;*t* — 分佈尾部的區域計算p值：

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

最後，[!DNL Target]中報告的信賴度定義為：

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## 離線執行計算

[下載的 CSV 報表](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)只包含原始資料，不含計算度量，例如每次造訪帶來的收入、提升度或用於 A/B 測試的信賴度。

若要計算這些統計數量，請下載[!DNL Target] [完整可信度電腦](/help/main/assets/complete_confidence_calculator.xlsx) Excel檔案來輸入活動的值。
