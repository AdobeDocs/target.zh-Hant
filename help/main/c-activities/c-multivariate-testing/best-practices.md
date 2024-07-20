---
keywords: mvt;多變數測試;多變數測試最佳做法;mvt 最佳做法;mvt 組合;mvt 報告
description: 瞭解如何改善效能、避免問題，以及修正在 [!DNL Adobe Target]中建立及執行[!UICONTROL Multivariate Test]活動時可能會發生的已知問題。
title: '[!UICONTROL Multivariate Test]活動有何最佳實務？'
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 57%

---

# [!UICONTROL Multivariate Test]個最佳實務

提供提示，協助您改善效能、避免問題，以及修正在[!DNL Adobe Target]中建立和執行[!UICONTROL Multivariate Test] (MVT)活動時可能會發生的已知問題。

## 計劃 {#section_4D4A1F6226F042379BF48DB753608579}

* 請注意您的頁面上可能產生顯著結果的位置。

  例如，相較頁尾中的變更，橫幅或主圖影像可能會導致更多轉換。在您的測試中包含較不具影響的位置，只會增加測試頁面上更顯著位置所需的流量和時間量。
* 請提前準備您的頁面變數。

  請注意每個選件的內容差異，並建立您預期在 MVT 測試中使用的任何影像、文字和 HTML 選件。

## 建立 {#section_C59C722CA82E48ABA58A4A7FA758F193}

* 請勿包括多於測試所需的組合。

  每個測試的組合會明顯增加達成可接受的結果所需的流量和時間量。例如，如果有三個位置，每個均具有三個選件，那麼會有 27 個可能組合 (3x3x3)。三個位置，其中的兩個位置包含三個可能選件，而一個位置有兩個選件，那麼可提供 18 個選項 (3x3x2)。數量會隨著每個額外的位置和選件增加。

* 為位置和選件命名。

  您可以重新命名您的測試中的每個位置和選件，以使用更實用的名稱。每個位置中的選件數量會出現在位置標頭。有用的名稱可協助您在檢查報表時識別選件。

* 利用預覽功能來避免不需要的內容組合。

  檢閱測試產生的所有體驗，之後再上線。請確認沒有自相矛盾的宣告組合（例如，在相同的體驗中可享受20%的折扣和$19的折扣）或不相容的設計，例如使用相同顏色的背景和字型。

* 使用[流量估算程式](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md)來確定您的測試是針對頁面所接收的流量而設計。

  請確定流量估算程式為您的測試設定開了綠燈，以便您可以取得想要的結果。

* 每個元素的替代專案應彼此顯著不同。

## 分析 {#section_9A2118CF1039451681C13D9AE79A58AB}

* 經常使用[位置貢獻報表](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md)來監視每個位置和選件的效能。
* 在[體驗效能報表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)中，使用[!UICONTROL Best 5]和[!UICONTROL Worst 5]篩選器顯示的資料來進行決策。

  [!UICONTROL All]篩選器會使得您難以擷取想要的資訊，而且並非所有體驗都可以顯示在圖表中。 如果您想要檢視不在最佳或最差前五名之內的特定體驗，請使用[!UICONTROL All]篩選器。

## 後續事項 {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* 雖然[!DNL Target]可讓您編輯已上線的活動，但編輯進行中的活動可能會重設測試。 報表可能無法辨識某些變更。 只有在選件資料庫中變更 HTML 選件是安全的。

  重設體驗名稱和報表的特定動作包括：

   * 新增位置
   * 刪除位置
   * 新增選件或從現有位置刪除選件
   * 編輯 RTF 文字選件
   * 編輯背景顏色選件

* 遵循下列具有一或多個 A/B 測試的 MVT 測試，您可以判斷所需結果的最佳可能內容。

  一旦您判斷哪個位置和內容最有助於符合您的目標，您可以執行 A/B 測試來進一步細分結果。例如，當您知道哪些位置最重要時，請相互測試兩個特定影像，或比較行動號召的措辭或顏色。
