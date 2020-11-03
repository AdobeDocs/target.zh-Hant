---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content
description: A/B 測試會比較兩個或更多版本的網站內容，以查看哪個版本在預先指定的測試持續時間最能改善您的轉換。
title: A/B 測試
feature: ab
uuid: 154559cf-58bb-425d-bb2e-4eaf34c89451
translation-type: tm+mt
source-git-commit: 130edc89b2c324a0d892a4221f644248e23357a4
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 58%

---


# A/B 測試

手動A/B測試會比較您的兩個或多個網站內容版本，以瞭解哪個版本在預先指定的測試期間最能改善您的轉換。

>[!NOTE]
>
>除了「手動（預設）A/B測試」活動（在本節中討論）外，還提供 [!DNL Target] 兩種額外的A/B測試活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標]。
>
>如需 [詳細資訊，請參閱下方的A/B測試](#types) 類型活動。

手動A/B測試（有時稱為A/B...N測試）會比較您的兩個或多個網站內容版本，以找出最能提升轉換、銷售或其他您所識別量度的版本。 使用 A/B 測試來將對您的頁面的變更與您的預設頁面設計比較，以決定哪個體驗可產生最佳結果。

當您有明確的假設，可以根據成功度量或替代內容傳送來改善頁面效能時，手動A/B測試特別有用。

手動A/B測試非常適合用於可能包含新版面或元素處理方式大幅不同的大型變更。 如果您的測試設計不易細分成單獨的頁面元素，那麼您應該在執行多變數測試之前，先執行 A/B 測試。

設定您的測試時，您可以決定看見每個體驗的訪客百分比。例如，您可能會在控制與第二個體驗之間平均分割流量，或您可能會透過僅將它向您的 5% 對象顯示來測試全新且更具風險的體驗。

>[!NOTE]
>
>如需判斷 A/B 測試最佳樣本大小的詳細資訊，請參閱[計劃 A/B 測試](../../c-activities/t-test-ab/sample-size-determination.md#concept_2801F552DB874C20B8A17C1B774C0383)。

當不同體驗的數量超出五個，並跨兩個或多個位置，在執行您的 A/B 測試之前考慮 [MVT 測試](/help/c-activities/c-multivariate-testing/multivariate-testing.md)是好主意。多變數測試會顯示頁面上的哪些區域最可能改善轉換。這些是行銷人員應該著重的位置。例如，MVT 測試可能顯示對動作的呼叫是符合您的目標的最重要位置。一旦您決定哪個位置和內容對於幫助您符合您的目標最有用，您可以執行 A/B 測試來進一步微調結果，例如對彼此測試兩個特定影像，或比較對動作呼叫的用字或色彩。遵循下列具有一或多個 A/B 測試的 MVT 測試，您可以判斷所需結果的最佳可能內容。

## A/B測試活動類型 {#types}

除了「手動（預設）A/B測試」活動（在本節中討論）外，還提供 [!DNL Target] 兩種額外的A/B測試活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標]。

| 活動類型 | 說明 |
| --- | --- |
| 手動 A/B 測試 | 比較兩個或多個體驗，以瞭解何者最能改善整個預先指定的測試期間的轉換。<br>本節說明如何設定手動A/B測試活動，但其他類型A/B測試活動的步驟類似。 |
| [!UICONTROL 自動分配] | 找出兩個或多個體驗中的獲勝者，然後將流量重新導向獲勝者，以隨著測試執行和學習增加轉換。<br>如需詳細資訊，請參閱[自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![Premium徽章](/help/assets/premium.png)[!UICONTROL 自動定位] | 使用進階機器學習來個人化內容，並透過找到多個高執行效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。<br>如需詳細資訊，請 [參閱自動定位](/help/c-activities/auto-target-to-optimize.md)。 |

如需這些A/B測試活動適合您的詳細資訊，請參閱互動式 [Adobe Target活動指南PDF](/help/c-activities/target-activities-guide.md)。

建立三種A/B測試活動的步驟類似。 若要建立「 [!UICONTROL 自動分配] 」或「自動 [!UICONTROL 目標」活動，請先] 建立A/B測試活動 [](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ，但是當您進入「定位頁面」時，請選擇所需的流量分配方法：

* [!UICONTROL 自動分配以獲得最佳體驗]
* [!UICONTROL 自動鎖定個人化體驗]

![流量分配方法設定](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 訓練影片：活動類型(9:03)概 ![述徽章](/help/assets/overview.png)

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)
