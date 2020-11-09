---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: 手動A/B測試活動會比較您的兩個或多個網站內容版本，以查看哪個版本在預先指定的測試期間最能改善您的轉換。
title: A/B測試概觀
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 38%

---


# A/B測試概觀

A manual [!UICONTROL A/B Test] activity compares two or more versions of your website content to see which version best improves your conversions during a pre-specified test period.

>[!NOTE]
>
>除了「手動（預設） [!UICONTROL A/B測試」活動(在本節中討論] )外， [!DNL Target] 還提供了兩種  A/B測試活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標]。
>
>如需 [詳細資訊，請參閱下方的A/B測試](#types) 類型活動。

A manual [!UICONTROL A/B Test] activity (sometimes referred to as an A/B...N test) compares two or more versions of your Web site content to see which best lifts your conversions, sales, or other metrics you identify. 使用 A/B 測試來將對您的頁面的變更與您的預設頁面設計比較，以決定哪個體驗可產生最佳結果。

當您有明確的假設，可以根據成功度量或替代內容傳送來改善頁面效能時，手動A/B測試特別有用。

手動A/B測試非常適合用於可能包含新版面或元素處理方式大幅不同的大型變更。 If your test design does not easily break down into individual page elements, you should run an A/B test before a [multivariate test](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

當您設定A/B測試時，您可以決定每個體驗的訪客百分比。 例如，您可能會在控制與第二個體驗之間平均分割流量，或您可能會透過僅將它向您的 5% 對象顯示來測試全新且更具風險的體驗。

>[!NOTE]
>
>如需判斷 A/B 測試最佳樣本大小的詳細資訊，請參閱[計劃 A/B 測試](/help/c-activities/t-test-ab/sample-size-determination.md)。

當不同體驗的數量超出五個，並跨兩個或多個位置，在執行您的 A/B 測試之前考慮 [MVT 測試](/help/c-activities/c-multivariate-testing/multivariate-testing.md)是好主意。多變數測試會顯示頁面上的哪些區域最可能改善轉換。這些是行銷人員應該著重的位置。例如，MVT 測試可能顯示對動作的呼叫是符合您的目標的最重要位置。在您確定哪些位置和內容最有助於您達成目標後，就可執行A/B測試以進一步調整結果，例如測試兩個特定影像，或比較行動呼籲的措辭或顏色。 遵循下列具有一或多個 A/B 測試的 MVT 測試，您可以判斷所需結果的最佳可能內容。

## A/B測試活動類型 {#types}

除了手動 [!UICONTROL A/B測試活動] （本節討論）外， [!DNL Target] 還提供兩種A/B測試活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標]。

| 活動類型 | 說明 |
| --- | --- |
| [!UICONTROL 手動 A/B 測試] | 比較兩個或多個體驗，以瞭解何者最能改善整個預先指定的測試期間的轉換。<br>本節說明如何設定手動 [!UICONTROL A/B測試活動] ，但其他類型  A/B測試活動的步驟類似。 |
| [!UICONTROL 自動分配] | 找出兩個或多個體驗中的獲勝者，然後將流量重新導向獲勝者，以隨著測試執行和學習增加轉換。<br>要瞭解使用自動分配活動的優點，請參閱 [A/B測試和自動分配概述中的自動分配](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate)*(Auto-Allocate*[](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md))。 |
| ![Premium徽章](/help/assets/premium.png)[!UICONTROL 自動定位] | 使用進階機器學習來個人化內容，並透過找到多個高執行效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。<br>如需詳細資訊，請 [參閱自動定位](/help/c-activities/auto-target/auto-target-to-optimize.md)。 |

如需這些 [!UICONTROL A/B測試活動適合您的詳細資訊] ，請參閱互動式 [Adobe Target活動指南PDF](/help/c-activities/target-activities-guide.md)。

建立三種 [!UICONTROL A/B測試活動的步驟類似] 。 若要建立「自 [!UICONTROL 動分配] 」或「自動 [!UICONTROL 目標」活動，請先建立「] A/B測試」活動 [](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ，但是當您進入「定位頁面」時，請選擇所需的流量分配方法，如下所示：

* [!UICONTROL 自動分配以獲得最佳體驗]
* [!UICONTROL 自動鎖定個人化體驗]

![流量分配方法設定](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 訓練影片：活動類型(9:03)概 ![述徽章](/help/assets/overview.png)

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)
