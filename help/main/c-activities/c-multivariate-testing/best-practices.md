---
keywords: mvt;多變數測試;多變數測試最佳做法;mvt 最佳做法;mvt 組合;mvt 報告
description: 瞭解如何改善效能、避免問題，以及修正在[!DNL Adobe Target]中建立和執行[!UICONTROL 多變數測試]活動時可能會發生的已知問題。
title: '[!UICONTROL 多變數測試]活動的最佳實務是什麼？'
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
TQID: 'https://experienceleague.adobe.com/nQEf5GZ8-zVZakygPtMAYWk-xoJPdcycFbzCNKTqJ-k'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 30%
---
# [!UICONTROL 多變數測試]最佳實務 {#mvt-best-practices}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何規劃、建立、分析和追蹤&#x200B;**[!UICONTROL 多變數測試]**&#x200B;活動，以取得可靠的結果。

>[!ENDSHADEBOX]

下列提示可協助您改善效能、避免問題，以及修正您在[!DNL Adobe Target]中建立及執行&#x200B;**[!UICONTROL 多變數測試]** (MVT)活動時可能會發生的已知問題。

## 計劃 {#plan}

* **在測試中至少使用三個元素。**

  如果沒這麼多個，請執行 A/B 測試。 如需詳細資訊，請參閱[何時使用多變數測試與A/B](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#when-to-use-mvt)。

* **請注意您通常獲得的流量量，包括曝光次數和轉換次數。**

  MVT需要足夠的流量才能產生有用的結果，而這項資訊有助於降低設計需求超過網站流量的測試的可能性。

* **請注意您的頁面上可能產生顯著結果的位置。**

  相較頁尾中的變更，橫幅或主圖影像可能會導致更多轉換。 在您的測試中包含較不具影響的位置，只會增加測試頁面上更顯著位置所需的流量和時間量。

* **保持元素彼此獨立。**

  例如，請勿在相同測試中測試版面配置與內容。

* **檢查您要測試之頁面的HTML程式碼。**

  請確定網站上的HTML元素沒有重複的DOM ID。 重複 ID 會導致同一份內容傳遞至多個位置。

* **提前準備您的頁面變化。**

  請注意每個產品建議的內容差異，並建立您預期在 MVT 測試中使用的任何影像、文字和 HTML 產品建議。

* **為QA計畫額外的時間。**

  體驗的數量會增加，因此QA需要更多時間。

## 建立 {#create}

* **請勿包含超過測試需要的組合。**

  每個測試的組合會明顯增加達成可接受的結果所需的流量和時間量。 例如，如果有三個位置，每個均具有三個產品建議，那麼會有 27 個可能組合 (3x3x3)。 三個位置，其中的兩個位置包含三個可能產品建議，而一個位置有兩個產品建議，那麼可提供 18 個選項 (3x3x2)。 數量會隨著每個額外的位置和產品建議增加。

* **命名位置和選件。**

  您可以重新命名您的測試中的每個位置和產品建議，以使用更實用的名稱。 每個位置中的產品建議數量會出現在位置標頭。 有用的名稱可協助您在檢查報表時識別選件。

* **利用預覽功能來避免不想要的內容組合。**

  檢閱測試產生的所有體驗，之後再上線。 請確認沒有自相矛盾的宣告組合（例如相同體驗中可享受20%折扣和$19的優惠）或不相容的設計，例如相同顏色的背景和字型。

* **使用[流量估算程式](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator)，確定您的測試是針對頁面接收的流量而設計。**

  請確定&#x200B;**[!UICONTROL 流量估算程式]**&#x200B;為您的測試組態提供綠燈，以便您可以取得想要的結果。

* **讓每個元素的替代專案彼此顯著不同。**

  雖然不一定需要，但每個元素最好都有相同數量的替代專案。

## 分析 {#analyze}

* **經常使用[位置貢獻報表](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md)**&#x200B;來監視每個位置和選件的效能。

* **在[體驗效能報表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)中，使用[!UICONTROL 最佳5]與[!UICONTROL 最差5]篩選所顯示的資料來進行決策。**

  **[!UICONTROL 全部]**&#x200B;篩選器會使得您難以擷取想要的資訊，而且並非所有體驗都可以顯示在圖表中。 如果您想要檢視不在最佳或最差前五名之內的特定體驗，請使用&#x200B;**[!UICONTROL 全部]**&#x200B;篩選器。

## 後續追蹤 {#follow-up}

* 雖然[!DNL Target]可讓您編輯已上線的活動，但&#x200B;**編輯進行中的活動可能會重設測試。** 報表可能無法辨識某些變更。 只可以在選件資料庫中安全地變更HTML選件。

  重設體驗名稱和報表的特定動作包括：

  * 新增位置
  * 刪除位置
  * 新增產品建議或從現有位置刪除產品建議
  * 編輯 RTF 文字產品建議
  * 編輯背景顏色產品建議

* **如果您編輯使用[!DNL Analytics]型量度的活動（顯示旋轉圖示）時未載入報表套裝，**&#x200B;請將量度切換為[!DNL Target]個量度，然後再次切換為[!DNL Analytics]型量度。 報表套裝現在應該會載入。

* **遵循包含一或多個A/B測試的MVT測試**，以決定最適合您想要的結果。 一旦您判斷哪個位置和內容最有助於符合您的目標，您可以執行 A/B 測試來進一步細分結果。 例如，當您知道哪些位置最重要時，請相互測試兩個特定影像，或比較call to action的措辭或顏色。
