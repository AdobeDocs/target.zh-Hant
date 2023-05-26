---
keywords: 報表；統計方法；統計計算；統計；平均值；轉換率；每位訪客帶來的收入；rpv；信賴區間；提升度；welch t-test；離線計算
description: 瞭解手動使用的統計計算 [!UICONTROL A/B測試] 中的活動 [!DNL Adobe Target].
title: 如何瞭解中使用的統計計算 [!UICONTROL A/B測試] 活動？
feature: Reports
exl-id: 5f7377b9-0567-4b6f-8968-4696b2088d0a
source-git-commit: f997b6a0ea9e0cebf7b414c029971d8520f8b95f
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 5%

---

# A/Bn 測試中的統計計算

本文記錄手動A/Bn測試中使用的詳細統計計算 [!DNL Adobe Target]. 提供的定義適用於 [!UICONTROL 轉換率]， [!UICONTROL 轉換率的信賴區間]， [!UICONTROL 提升度]， [!UICONTROL 提升度的信賴區間]、和 [!UICONTROL 信賴度].

>[!NOTE]
>
>本文資訊取代了 *Adobe Target 中 A/B 測試使用的計算* pdf 檔案 (先前可在此網站下載)。

![目標報告顯示 [!UICONTROL 轉換率]， [!UICONTROL 平均提升度和信賴區間]、和 [!UICONTROL 信賴度] A/B測試活動的摘要。](/help/main/c-reports/statistical-methodology/img/target_report.png)

## 平均績效

下節將說明上圖中使用的計算。

### 轉換率和每位訪客帶來的收入(RPV)行銷活動

下圖顯示 [!UICONTROL 轉換率]， [!UICONTROL 轉換率的信賴區間]，以及 [!UICONTROL 轉換] 在 [!DNL Target] 報告。 例如，第一行顯示對於體驗A： [!UICONTROL 轉換率] 為25.81% （含） [!UICONTROL 信賴區間] 共錄得±7.7%和32次轉換。 假設有124位訪客看過該體驗，則等於32/124 = 25.81%。

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

轉換率或 **平均值**， *μ<sub>ν</sub>*，代表每個體驗 *ν* 在實驗中，定義為量度加總與指派給該量度的單位數之間的比率， *N<sub>ν</sub>*：

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

此處，

* *Y<sub>iν</sub>* 是每個單位的量度值 *i*，已指派給特定體驗 *ν*.

* 單位總和 *i* 取決於計數方法的選擇。

   * 若 *[!UICONTROL 訪客]* 會作為計數方法使用，每個單位都是獨特訪客，定義為活動期限內的不重複活動參與者。
   * 若 *[!UICONTROL 造訪]* 當作計數方法使用，每個單位都是定義為期間體驗中的不重複參與者的不重複造訪。 [!DNL Target] 工作階段(具有唯一 `sessionId`)。 當 `sessionId` 若有變更，或訪客達到轉換步驟，則會計為新造訪。
   * 若 *[!UICONTROL 活動曝光次數]* 當作計數方法，每個單位都是定義為每次訪客載入活動的任何頁面時的唯一曝光次數。

## [!UICONTROL 平均值的信賴區間]/[!UICONTROL 轉換率]

轉換率的信賴區間在直覺上定義為與基礎資料一致的可能轉換率範圍。

執行實驗時，給定體驗的轉換率為 *預估* 「真」轉換率的10%。 若要量化此估計中的不確定性， [!DNL Target] 使用信賴區間。 [!DNL Target] 一律會報告95%信賴區間，這表示到最後，計算的95%信賴區間會包含體驗的真實轉換率。

轉換率的95%信賴區間 *μ<sub>ν</sub>* 定義為值的範圍：

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

其中平均值的標準誤差定義為

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

使用樣本標準差的無偏估計時：

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

當行銷活動是轉換率行銷活動時（即轉換量度是二進位），標準錯誤會減少為：

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## 提升度

下圖顯示 [!UICONTROL 提升度] 和 [!UICONTROL 提升度的信賴區間] 在 [!DNL Target] 報告。 數字代表提升度界限的平均值，而箭頭則反映提升度是正數還是負數。 箭頭會以灰色顯示，直到信賴度超過95%為止。 信賴度超過臨界值後，箭頭會根據提升度為正值或負值，變成綠色或紅色。

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

體驗之間的提升度  *ν*、和控制體驗 *ν<sub>0</sub>* 是轉換率中的相對「差異」，定義為

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

其中個別的轉換率如上定義。 更簡單地說，

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

如果控制體驗的轉換率 *ν<sub>0</sub>* 為0，沒有提升度。

## [!DNL Confidence Interval of Lift]

中的箱形圖 [!UICONTROL 平均提升度和信賴區間] 欄代表平均值和95% [!UICONTROL 提升度的信賴區間]. 當指定的非控制體驗的信賴區間與控制體驗的信賴區間發生任何重疊時，箱形圖就會呈現灰色。 當指定體驗的信賴區間範圍高於或低於控制體驗的信賴區間時，箱形圖就會呈現綠色或紅色。

體驗之間提升度的標準錯誤  *ν*、和控制體驗  *ν<sub>0</sub>* 定義為：

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="metric-mean"></p>

那麼提升度的95%信賴區間是：

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

此計算使用「Delta」方法，相關說明如下 [在本檔案中取得詳細資訊](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL 可信度]

最後一欄顯示 [!DNL Target] 報告。 體驗的信賴度是指在空值假設為true的情況下，獲得比觀察到的結果更少極端的結果的機率（以百分比表示）。 就p值而言，顯示的信賴度為 *1 - p值*. 直覺上，較高的信賴度表示控制體驗和非控制體驗擁有相等轉換率的可能性較低。

在 [!DNL Target]，雙尾 **韋爾奇的t檢定** 會在測試體驗和控制體驗之間執行，以測試測試方法和控制體驗是否相同。 因為我們通常不知道在執行實驗之前，兩個群組的樣本大小和變異是否相同，以及 [!DNL Target] 也允許您傳送到每個體驗的流量百分比不相等，我們並不假設每個體驗的變數相等。 因此，會選擇Welch的t檢驗，而非Student的t檢驗。

若要執行Welch的t檢驗，我們先開始計算t統計值和自由度，然後執行雙尾t檢驗來產生p值。 最後，我們會根據p值來計算可信度。

此 *t*-statistic定義為任何兩個獨立隨機變數之均值的差異， *ν* 和 *ν<sub>0</sub>*，除以標準誤差差：

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

位置 *μ<sub>v</sub>* 和 *μ<sub>v0</sub>* 是以下專案的方法： *ν*  和 *ν<sub>0</sub>* 分別是和標準誤差之間的差異 *μ<sub>v</sub>* 和 *μ<sub>v0</sub>* 提供者：

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

位置 *σ<sup>2</sup><sub>v</sub>* 和 *σ<sup>2</sup><sub>v<sub>0</sub></sub>* 是兩個體驗的差異 *ν*  和 *ν<sub>0</sub>* 分別，和 *N<sub>v</sub>* 和 *N<sub>v<sub>0</sub></sub>* 的樣本大小 *ν* 和 *ν<sub>0</sub>* （分別）。

對於Welch的t檢驗，自由度計算如下：

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

與自由度 *ν*  和 *ν<sub>0</sub>* 定義為：

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

然後p值可以從的尾部區域計算 *t*-distribution：

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

最後，可信度報告於 [!DNL Target] 定義為：

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## 離線執行計算

[下載的 CSV 報表](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)只包含原始資料，不含計算度量，例如每次造訪帶來的收入、提升度或用於 A/B 測試的信賴度。

若要計算這些統計數量，請下載 [!DNL Target] [完整可信度電腦](/help/main/assets/complete_confidence_calculator.xlsx) 用於輸入活動值的Excel檔案。
