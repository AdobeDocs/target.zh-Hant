---
description: 協助您改善效能、避免問題，以及修正在Adobe Target中建立和執行多變數測試活動時可能發生的已知問題。
keywords: mvt;多變數測試;多變數測試最佳做法;mvt 最佳做法;mvt 組合;mvt 報表
seo-description: 協助您改善效能、避免問題，以及修正在Adobe Target中建立和執行多變數測試活動時可能發生的已知問題。
seo-title: 多變數測試使用Adobe Target的最佳實務
solution: Target
title: 多變數測試最佳作法
topic: Standard
uuid: 4468a2eb-3fc1-4bc5-85ac-90cc02db4fbb
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 多變數測試最佳作法{#multivariate-test-best-practices}

Tips to help you improve performance, avoid issues, and correct known issues that might occur when creating and running Multivariate Test (MVT) activities in [!DNL Adobe Target].

## 計劃 {#section_4D4A1F6226F042379BF48DB753608579}

* 請注意您的頁面上可能產生顯著結果的位置。

   例如，橫幅或英雄影像可能會導致轉換多於頁尾的變更。在您的測試中包含較不具影響的位置，只會增加測試頁面上更顯著位置所需的流量和時間量。
* 請提前準備您的頁面變數。

   請注意每個選件的內容差異，並建立您預期在 MVT 測試中使用的任何影像、文字和 HTML 選件。

## 建立 {#section_C59C722CA82E48ABA58A4A7FA758F193}

* 請勿包括多於測試所需的組合。

   每個測試的組合會明顯增加達成可接受的結果所需的流量和時間量。例如，如果您有三個位置有三個選件，則有27個可能的組合(3x3x3)。個位置，其中兩個位置包含三個可能的選件，一個位置有兩個選件，提供18個選項(3x倍)。數量會隨著每個額外的位置和選件增加。

* 為位置和選件命名。

   您可以重新命名您的測試中的每個位置和選件，以使用更實用的名稱。每個位置中的選件數量會出現在位置標頭。實用的名稱將可在檢查報表時協助您識別您的選件。

* 利用預覽功能來避免不需要的內容組合。

   檢閱測試產生的所有體驗，之後再上線。請確定沒有任何組合具有對立的要求 (例如，在相同的體驗中打八折與折扣 $19) 或不相容的設計 (例如，有相同色彩的背景和字型)。

* Use the [Traffic Estimator](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) to make sure that your test is designed for the amount of traffic your page receives.

   確定流量估算程式對您的測試組態指示綠燈，使得您可以取得所需的結果。
* 建議您每個元素的替代項目之間必須有大幅差異。

## 分析 {#section_9A2118CF1039451681C13D9AE79A58AB}

* Make frequent use of the [Location Contribution report](/help/c-reports/location-contribution-report.md) to monitor the performance of each location and each offer.
* In the [Experience Performance report](/help/c-reports/experience-performance-report.md), base your decisions on the data shown using the Best 5 and Worst 5 filters.

   [!UICONTROL 「全部] 」篩選器會很難擷取所需的資訊，而並非所有體驗都能顯示在圖形中。Use the [!UICONTROL All] filter if you want to look at a specific experience that is not in the best or worst five.

## 後續事項 {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Although [!DNL Target] allows you to edit a live activity, be aware that editing an activity that is in progress could reset the test. 因此，報表可能無法識別某些變更。只有在選件資料庫中變更 HTML 選件是安全的。

   重設體驗名稱和報表的特定動作是:

   * 新增位置
   * 刪除位置
   * 新增選件或從現有位置刪除選件
   * 編輯 RTF 文字選件
   * 編輯背景顏色選件

* 遵循下列具有一或多個 A/B 測試的 MVT 測試，您可以判斷所需結果的最佳可能內容。

   一旦您判斷哪個位置和內容最有助於符合您的目標，您可以執行 A/B 測試來進一步細分結果。例如，當您知道哪個位置最重要時，對彼此測試兩個特定影像，或比較對動作的呼叫的文字或色彩。

