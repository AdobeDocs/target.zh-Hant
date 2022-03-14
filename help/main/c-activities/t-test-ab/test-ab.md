---
keywords: AB;A/B;AB...n；比較經驗；目標；比較內容；自動目標；自動分配
description: 瞭解Adobe中不同類型的A/BTest活動 [!DNL Target]  — 手動、自動分配和自動目標。 選擇適合你的。
title: 目標中提供哪種類型的A/B活動？
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 39%

---

# A/BTest概述

手冊 [!UICONTROL A/BTest] 活動將比較網站內容的兩個或兩個以上版本，以查看哪個版本在預先指定的test期間最能改進轉換。

>[!NOTE]
>
>除手冊（預設）外 [!UICONTROL A/BTest] 活動（在本節中討論）, [!DNL Target] 提供了另外兩種類型 [!UICONTROL A/BTest] 活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標]。
>
>請參閱 [A/B測試活動的類型](#types) 下面的。

手冊 [!UICONTROL A/BTest] 活動(有時稱為A/B...Ntest)比較網站內容的兩個或兩個以上版本，以查看哪個版本能最有效地提升轉換、銷售或您確定的其他指標。 使用 A/B 測試來將對您的頁面的變更與您的預設頁面設計比較，以決定哪個體驗可產生最佳結果。

當您對如何根據成功度量或替代內容交付來改進頁面效能有明確的假設時，手動A/Btest尤其有用。

手動A/Btest非常適合於可能涉及新佈局或對元素進行顯著不同處理的大規模更改。 如果您的test設計不易分解為各個頁面元素，則應在 [多元test](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)。

在設定A/Btest時，您可以確定每個體驗的訪問者百分比。 例如，您可能會在控制與第二個體驗之間平均分割流量，或您可能會透過僅將它向您的 5% 對象顯示來測試全新且更具風險的體驗。

>[!NOTE]
>
>如需判斷 A/B 測試最佳樣本大小的詳細資訊，請參閱[計劃 A/B 測試](/help/main/c-activities/t-test-ab/sample-size-determination.md)。

當不同體驗的數量超出五個，並跨兩個或多個位置，在執行您的 A/B 測試之前考慮 [MVT 測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)是好主意。多變數測試會顯示頁面上的哪些區域最可能改善轉換。這些是行銷人員應該著重的位置。例如，MVT 測試可能顯示對動作的呼叫是符合您的目標的最重要位置。確定哪些位置和內容對幫助您實現目標最有用後，您就可以運行A/Btest來進一步細化結果，例如，將兩個特定影像相互test，或比較行動要求的措辭或顏色。 遵循下列具有一或多個 A/B 測試的 MVT 測試，您可以判斷所需結果的最佳可能內容。

## A/B測試活動的類型 {#types}

除了手冊 [!UICONTROL A/BTest] 活動（在本節中討論）, [!DNL Target] 提供了另外兩種類型的A/B測試活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標]。

| 活動類型 | 說明 |
| --- | --- |
| [!UICONTROL 手動 A/B 測試] | 比較兩個或多個體驗，以瞭解何者最能改善整個預先指定的測試期間的轉換。<br>本節介紹如何設定手冊 [!UICONTROL A/BTest] 活動，但是其他類型的步驟 [!UICONTROL A/BTest] 活動類似。 |
| [!UICONTROL 自動分配] | 找出兩個或多個體驗中的獲勝者，然後將流量重新導向獲勝者，以隨著測試執行和學習增加轉換。<br>要瞭解使用自動分配活動的好處，請參閱 [自動分配](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) 在 *您應運行A/BTest多長時間* 和 [自動分配概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![高級徽章](/help/main/assets/premium.png) [!UICONTROL 自動目標] | 使用進階機器學習來個人化內容，並透過找到多個高執行效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。<br>有關詳細資訊，請參見 [自動目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。 |

有關其中哪項的詳細資訊 [!UICONTROL A/BTest] 活動適合您，請參閱互動式 [Adobe Target活動指南PDF](/help/main/c-activities/target-activities-guide.md)。

建立這三種類型的 [!UICONTROL A/BTest] 活動類似。 建立 [!UICONTROL 自動分配] 或 [!UICONTROL 自動目標] 活動，開始於 [建立A/BTest活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)但當你到達 [!UICONTROL 目標] 頁，選擇所需的流量分配方法，如下所示：

* [!UICONTROL 自動分配以獲得最佳體驗]
* [!UICONTROL 個性化體驗的自動目標]

![流量分配方法設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 培訓影片：活動類型 (9:03)![Overview badge](/help/main/assets/overview.png)

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)
