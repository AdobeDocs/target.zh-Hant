---
keywords: AB； A/B； AB...n；比較體驗；鎖定目標；比較內容；自動鎖定目標；自動分配
description: 瞭解Adobe中不同型別的A/B測試活動 [!DNL Target]  — 手動、自動分配和自動鎖定目標。 選擇適合您的選擇。
title: Target提供哪種A/B活動型別？
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 39%

---

# A/B測試概覽

手動 [!UICONTROL A/B測試] 活動會比較兩個或更多版本的網站內容，以檢視在預先指定的測試期間，哪個版本最能改善您的轉換。

>[!NOTE]
>
>除了手動（預設） [!UICONTROL A/B測試] 活動（在本節中討論）， [!DNL Target] 提供另外兩種型別 [!UICONTROL A/B測試] 活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標].
>
>另請參閱 [A/B測試活動的型別](#types) 詳細資訊，請參閱下文。

手動 [!UICONTROL A/B測試] 活動（有時稱為A/B...N測試）會比較兩個或更多版本的網站內容，以檢視哪些內容最能提高您的轉換、銷售或您識別的其他量度。 使用 A/B 測試來將對您的頁面的變更與您的預設頁面設計比較，以決定哪個體驗可產生最佳結果。

如果您有根據成功量度或替代內容傳送來改善頁面效能的明確假設，手動A/B測試特別實用。

手動A/B測試非常適合包含新版面或元素處理方式截然不同的大型變更。 如果您的測試設計不容易分解為個別頁面元素，您應先執行A/B測試，然後再執行 [多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

設定A/B測試時，您可以決定可看見每個體驗的訪客百分比。 例如，您可能會在控制與第二個體驗之間平均分割流量，或您可能會透過僅將它向您的 5% 對象顯示來測試全新且更具風險的體驗。

>[!NOTE]
>
>如需判斷 A/B 測試最佳樣本大小的詳細資訊，請參閱[計劃 A/B 測試](/help/main/c-activities/t-test-ab/sample-size-determination.md)。

當不同體驗的數量超出五個，並跨兩個或多個位置，在執行您的 A/B 測試之前考慮 [MVT 測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)是好主意。多變數測試會顯示頁面上的哪些區域最可能改善轉換。這些是行銷人員應該著重的位置。例如，MVT 測試可能顯示對動作的呼叫是符合您的目標的最重要位置。一旦您確定哪些位置和內容對於協助您達成目標最有用，就可以執行A/B測試以進一步調整結果，例如測試兩個特定影像彼此對照，或比較行動號召的措辭或顏色。 遵循下列具有一或多個 A/B 測試的 MVT 測試，您可以判斷所需結果的最佳可能內容。

## A/B測試活動的型別 {#types}

除了手冊 [!UICONTROL A/B測試] 活動（在本節中討論）， [!DNL Target] 提供另外兩種型別的A/B測試活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標].

| 活動類型 | 說明 |
| --- | --- |
| [!UICONTROL 手動 A/B 測試] | 比較兩個或多個體驗，以瞭解何者最能改善整個預先指定的測試期間的轉換。<br>本節說明如何設定手動 [!UICONTROL A/B測試] 活動，但針對其他型別的步驟 [!UICONTROL A/B測試] 活動類似。 |
| [!UICONTROL 自動分配] | 找出兩個或多個體驗中的獲勝者，然後將流量重新導向獲勝者，以隨著測試執行和學習增加轉換。<br>若要瞭解使用自動分配活動的好處，請參閱 [自動分配](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) 在 *A/B測試該執行多久* 和 [自動分配概觀](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Premium badge](/help/main/assets/premium.png) [!UICONTROL 自動鎖定目標] | 使用進階機器學習來個人化內容，並透過找到多個高執行效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。<br>如需詳細資訊，請參閱 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

如需關於其中哪些專案的詳細資訊 [!UICONTROL A/B測試] 活動最適合您，請參閱互動式 [Adobe Target活動指南PDF](/help/main/c-activities/target-activities-guide.md).

建立三種型別的步驟 [!UICONTROL A/B測試] 活動類似。 若要建立 [!UICONTROL 自動分配] 或 [!UICONTROL 自動鎖定目標] 活動，開始者 [建立A/B測試活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)，但當您前往 [!UICONTROL 目標定位] 頁面上，選擇所需的流量分配方法，如下所示：

* [!UICONTROL 自動分配至最佳體驗]
* [!UICONTROL 針對個人化體驗自動鎖定目標]

![流量分配方法設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 培訓影片：活動類型 (9:03)![Overview badge](/help/main/assets/overview.png)

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)
