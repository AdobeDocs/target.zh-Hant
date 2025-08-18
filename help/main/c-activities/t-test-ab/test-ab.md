---
keywords: AB； A/B； AB...n；比較體驗；鎖定目標；比較內容；自動鎖定目標；自動分配
description: 探索 [!DNL Target] - [!UICONTROL Manual]、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]中的A/B測試活動。
title: 探索 [!DNL Target]中可用的A/B測試活動。
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 974746e25724abf0e5edd3884331ec0975e5352e
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 21%

---

# A/B測試概覽

手動[!UICONTROL A/B Test]活動（有時稱為A/B...N測試）會比較兩個或更多版本的網站內容，以檢視哪個版本最能提升您的轉換、銷售或您識別的其他量度。 使用 A/B 測試來將對您的頁面的變更與您的預設頁面設計比較，以決定哪個體驗可產生最佳結果。

>[!TIP]
>
>除了[!UICONTROL Manual] （預設） [!UICONTROL A/B Test]活動（本文中討論）之外，[!DNL Target]還提供另外兩種型別的[!UICONTROL A/B Test]活動： [!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]。 如需詳細資訊，請參閱下列[A/B測試活動型別](#types)。

如果您對根據成功量度或替代內容傳送來改善頁面效能的方式有清楚的假設，手動A/B測試就十分實用。

手動A/B測試非常適合包含新版面或元素處理方式截然不同的大型變更。 如果您的測試設計不容易分解為個別頁面元素，您應先執行A/B測試，再執行[多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)。

設定A/B測試時，您可以決定可看見每個體驗的訪客百分比。 例如，您可在控制項和第二個體驗之間平均分割流量，或者可能透過僅向5%的受眾顯示來測試新的、風險更大的體驗。

>[!NOTE]
>
>如需判斷 A/B 測試最佳樣本大小的詳細資訊，請參閱[計劃 A/B 測試](/help/main/c-activities/t-test-ab/sample-size-determination.md)。

當不同體驗的數量超過5個，並橫跨兩個或更多位置時，在執行您的A/B測試之前最好考慮[MVT測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)。 多變數測試會顯示頁面上的哪些區域最可能改善轉換。這些區域是行銷人員應該關注的位置。 例如，MVT 測試可能顯示對動作的呼叫是符合您的目標的最重要位置。在您決定哪些位置和內容對協助您達成目標最有用後，就可以執行A/B測試以進一步調整結果。 例如，相互測試兩個特定影像，或比較call to action的文字或顏色。 遵循下列具有一或多個 A/B 測試的 MVT 測試，您可以判斷所需結果的最佳可能內容。

## A/B測試活動的型別 {#types}

除了手動[!UICONTROL A/B Test]活動之外，[!DNL Target]還提供另外兩種型別的[!UICONTROL A/B Testing]活動： [!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]。

| 活動類型 | 說明 |
| --- | --- |
| [!UICONTROL Manual A/B Test] | 比較兩個或多個體驗，以瞭解哪個體驗最能改善整個預先指定的測試期間的轉換。<P>本節說明如何設定手動[!UICONTROL A/B Test]活動，但其他型別的[!UICONTROL A/B Test]活動的步驟類似。 |
| [!UICONTROL Auto-Allocate] | 從兩個或多個體驗中識別獲勝者，然後將流量重新導向獲勝者，以隨著測試執行和學習增加轉換。<P>若要瞭解使用[!UICONTROL Auto-Allocate]活動的好處，請參閱[中的](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate)自動分配&#x200B;*您應該執行A/B測試*&#x200B;以及[自動分配總覽](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![進階徽章](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | 使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗來促進轉換。 接著，系統會根據訪客的個別客戶設定檔與類似訪客先前的行為，提供量身打造的最佳體驗。<P>如需詳細資訊，請參閱[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。 |

如需關於哪些[!UICONTROL A/B Test]活動適合您的詳細資訊，請參閱互動式[Adobe Target活動指南PDF](/help/main/c-activities/target-activities-guide.md)。

建立三種型別[!UICONTROL A/B Test]活動的步驟類似。 若要建立[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target]活動：

1. 從[建立A/B測試活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)開始。
1. 當您進入[!UICONTROL Targeting]頁面時，請按一下[!UICONTROL Traffic Allocation]控制項，然後在右窗格中選擇所需的流量配置方法，如下所示：

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experience]

   ![流量分配方法設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

## 在A/B活動中包含建議

您可以在[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動(和[!UICONTROL Experience Targeting] (XT)活動)中包含建議。 如需詳細資訊，請參閱 [推薦作為產品建議](/help/main/c-recommendations/recommendations-as-an-offer.md)。

若要使用此功能，您必須具備 [Target Premium 授權](/help/main/c-intro/intro.md#premium)。
