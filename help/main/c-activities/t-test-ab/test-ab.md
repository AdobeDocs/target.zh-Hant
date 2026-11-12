---
keywords: AB； A/B； AB...n；比較體驗；鎖定目標；比較內容；自動鎖定目標；自動分配
description: 在[!DNL Target] - [!UICONTROL 手動]、[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]中探索A/B測試活動。
title: 探索[!DNL Target]中可用的A/B測試活動。
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
TQID: 'https://experienceleague.adobe.com/wcflYDj0VB7dJODNO6XjFHB0PPIhN4aUrBJxbKPoNdg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: d887712962ad4e3cecd6b3b86ee33a4bcb99f2a8
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 19%
---
# A/B測試概覽 {#test-ab}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解什麼是手動A/B測試、何時使用它而不是多變數測試，以及它與「自動分配」和「自動鎖定目標」活動型別的關係。

>[!ENDSHADEBOX]

手動&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動（有時稱為A/B...N測試）會比較兩個或更多版本的網站內容，以檢視哪個版本最能提升您的轉換、銷售或其他識別量度。 使用 A/B 測試來將對您的頁面的變更與您的預設頁面設計比較，以決定哪個體驗可產生最佳結果。

## 何時使用手動A/B測試 {#when-to-use}

使用手動A/B測試，當：

* 您對如何改善您的頁面效能有清楚的假設，這些假設會根據成功量度或替代內容傳遞。
* 您想要測試大型變更，例如新版面配置或元素的處理方式大不相同。 如果您的測試設計不容易分解為個別頁面元素，您應先執行A/B測試，再執行[多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)。
* 您希望決定可看見每個體驗的訪客百分比。 例如，您可在控制項和第二個體驗之間平均分割流量，或者可能透過僅向5%的受眾顯示來測試新的、風險更大的體驗。

如需判斷 A/B 測試最佳樣本大小的詳細資訊，請參閱[計劃 A/B 測試](/help/main/c-activities/t-test-ab/sample-size-determination.md)。

### 結合多變數測試和A/B測試

當不同體驗的數量超過五個，並橫跨兩個或更多位置時，在執行您的A/B測試之前最好考慮[MVT測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)：

1. **執行多變數測試**，以檢視頁面上的哪些區域最有可能改善轉換。 這些區域是行銷人員應該關注的位置。 例如，MVT 測試可能顯示對動作的呼叫是符合您的目標的最重要位置。

1. **在這些位置上執行一或多個A/B測試**&#x200B;以進一步調整結果。 例如，相互測試兩個特定影像，或比較call to action的文字或顏色。

遵循下列具有一或多個 A/B 測試的 MVT 測試，您可以判斷所需結果的最佳可能內容。

## A/B測試活動的型別 {#types}

除了手動&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動之外，[!DNL Target]還提供另外兩種型別的&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動： **[!UICONTROL 自動分配]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**。

| 活動類型 | 說明 |
| --- | --- |
| **[!UICONTROL 手動A/B測試]** | 比較兩個或多個體驗，以瞭解哪個體驗最能改善整個預先指定的測試期間的轉換。<P>本節說明如何設定手動&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動，但其他型別的&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動的步驟類似。 |
| **[!UICONTROL 自動分配]** | 從兩個或多個體驗中識別獲勝者，然後將流量重新導向獲勝者，以隨著測試執行和學習增加轉換。<P>若要瞭解使用&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動的好處，請參閱&#x200B;*中的[自動分配](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate)您應該執行A/B測試*&#x200B;多久以及[自動分配總覽](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![進階徽章](/help/main/assets/premium.png) **[!UICONTROL 自動鎖定目標]** | 使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗來促進轉換。 接著，系統會根據訪客的個別客戶設定檔與類似訪客先前的行為，提供量身打造的最佳體驗。<P>如需詳細資訊，請參閱[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。 |

如需關於哪些&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動適合您的詳細資訊，請參閱互動式[Adobe Target活動指南PDF](/help/main/c-activities/target-activities-guide.md)。

>[!NOTE]
>
>您可以在&#x200B;**[!UICONTROL A/B測試]**、**[!UICONTROL 自動分配]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動(和&#x200B;**[!UICONTROL 體驗鎖定目標]** (XT)活動)中包含建議。 如需詳細資訊，請參閱 [推薦作為產品建議](/help/main/c-recommendations/recommendations-as-an-offer.md)。 若要使用此功能，您必須具備 [Target Premium 授權](/help/main/c-intro/intro.md#premium)。
