---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: 瞭解如何使用流量估算程式，讓您知道是否有足夠的流量可讓 [!DNL Adobe Target] [!UICONTROL Multivariate Test]活動成功。
title: '[!UICONTROL Multivariate Test] (MVT)活動需要多少流量？'
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 53%

---

# 預估成功的[!UICONTROL Multivariate Test]活動所需的流量

因為多變數測試會比較多個體驗，請務必瞭解若要提供有意義的結果需要多少流量。流量估算程式會使用關於您的頁面和待測試體驗數量的統計資料，以預估讓測試成功所需的流量和測試持續時間。

流量估算程式會預測需要的樣本大小，以確保下列:

* 95%信賴度。 此統計數字表示沒有實際提升度時回報誤判的機會為5% （100% — 信賴水準）。
* 80%統計檢定力。 此統計值表示測試偵測到真正提升度25%或以上的機率為80%。
* 最低可偵測提升度為25%。 [!DNL Target]會計算80%機率偵測到25%或以上的真正提升所需的流量量。

此測試使用 Bonferroni 校正來對多個比較進行更正。此方法已知較為保守，它是利用強制執行相對大的最小可靠可偵測提升度來平衡。

流量估算程式也會提供回饋意見，讓您得知是否有足夠的流量讓您設計的測試成功。

1. 從[!UICONTROL Visual Experience Composer]，按一下&#x200B;**[!UICONTROL Traffic]**&#x200B;圖示。

   流量估算程式隨即開啟。您可以再按一下&#x200B;**[!UICONTROL Traffic]**&#x200B;圖示來隱藏流量估算程式。

   ![estimatorempty影像](assets/estimatorempty.png)

1. 提供一般轉換率、預估每日訪客人數和測試持續時間。

   * **[!UICONTROL Number of Content Combinations]**：在任何排除之後，根據要隨活動建立的體驗數量自動計算。
   * **[!UICONTROL Typical Conversion Rate]**：轉換率會根據您的估計或來自您分析系統的過去資料而以百分比表示。
   * **[!UICONTROL Estimated Visitors Per Day]**：這是根據鎖定目標條件所得到的可能檢視此頁面的訪客數量。 這可能根據您的分析資料。
   * **[!UICONTROL Test Duration]**：活動要執行的天數。

   流量估算程式會使用這些統計資料來判斷執行成功測試所需的調整。

   在接近流量估算程式頂端，您輸入的值會經過計算並顯示結果。

   ![估算影像不足](assets/estimatorinsufficient.png)

   當您變更數量時，預估即會變更。例如，如果您正在測試許多體驗，而您的轉換率和曝光率太低，流量估算器會顯示測試必須執行多久才能成功。 或者，如果您的流量很低，流量估算程式可能會建議較低數量的體驗，讓您可以執行測試達需要的天數。

   如果您沒有足夠的流量，您可以執行以下一或兩個動作:

   * 減少產品建議組合的數量和位置的數量。
   * 增加測試的持續時間。

   調整數量直到流量估算程式指出您有足夠的流量為止，然後據以設計您的測試。

   ![estimatorok影像](assets/estimatorok.png)
