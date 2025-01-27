---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: 瞭解如何使用流量估算程式，讓您知道是否有足夠的流量可讓 [!DNL Adobe Target] [!UICONTROL Multivariate Test]活動成功。
title: '[!UICONTROL Multivariate Test] (MVT)活動需要多少流量？'
feature: Multivariate Tests
hide: true
hidefromtoc: true
source-git-commit: 4805da617962e29794bd3af16138f3887ad250d0
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 21%

---

# 預估成功的[!UICONTROL Multivariate Test]活動所需的流量

因為多變數測試會比較多個體驗，請務必瞭解若要提供有意義的結果需要多少流量。[!UICONTROL Traffic Estimator]會使用您頁面的相關統計資料，以及正在測試的體驗數目，來預估流量與成功測試所需的測試持續時間。

[!UICONTROL Traffic Estimator]預測所需的樣本大小，以確保下列專案：

* 95%信賴度。 此統計數字表示沒有實際提升度時回報誤判的機會為5% （100% — 信賴水準）。
* 80%統計檢定力。 此統計值表示測試偵測到真正提升度25%或以上的機率為80%。
* 最低可偵測提升度為25%。 [!DNL Target]會計算80%機率偵測到25%或以上的真正提升所需的流量量。

此測試使用 Bonferroni 校正來對多個比較進行更正。此方法已知較為保守，它是利用強制執行相對大的最小可靠可偵測提升度來平衡。

[!UICONTROL Traffic Estimator]也提供回饋意見，讓您知道您是否擁有足夠的流量，可以順利完成您設計的測試。

1. 從[!UICONTROL Multivariate]活動中[!UICONTROL Visual Experience Composer]的[!UICONTROL Experiences]頁面，按一下[!UICONTROL Experiences]頁面左上角的&#x200B;**[!UICONTROL Traffic]**&#x200B;圖示（ ![流量估算器圖示](/help/main/assets/icons/Gauge2.svg) ）。

   [!UICONTROL Traffic Estimator]隨即開啟。

   ![流量估算器使用者介面](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   您可以再按一下圖示來隱藏[!UICONTROL Traffic Estimator]。

   在[!UICONTROL Traffic Estimator]頂端附近，會計算您輸入的值並顯示結果。

1. （依條件）提供一般轉換率、預估每日訪客人數和測試持續時間。

   * **[!UICONTROL Number of Content Combinations]**：在任何排除之後，根據要隨活動建立的體驗數量自動計算。
   * **[!UICONTROL Typical Conversion Rate]**：轉換率會根據您的估計或來自您分析系統的過去資料而以百分比表示。
   * **[!UICONTROL Estimated Visitors Per Day]**：這是根據鎖定目標條件所得到的可能檢視此頁面的訪客數量。 這可能根據您的分析資料。
   * **[!UICONTROL Test Duration]**：活動要執行的天數。

   [!UICONTROL Traffic Estimator]會使用這些統計資料來決定執行成功測試所需的調整。

   當您變更數量時，預估即會變更。例如，如果您正在測試許多體驗，而您的轉換率和曝光率太低，[!UICONTROL Traffic Estimator]會顯示測試必須執行多久才能成功。 或者，如果您的流量很低，則[!UICONTROL Traffic Estimator]可能會建議使用較少的體驗數量，讓您可以按照所需的天數執行測試。

   如果您沒有足夠的流量，您可以執行以下一或兩個動作:

   * 減少產品建議組合的數量和位置的數量。
   * 增加測試的持續時間。

   調整數字，直到[!UICONTROL Traffic Estimator]指出您有足夠的流量，然後相應地設計測試。
