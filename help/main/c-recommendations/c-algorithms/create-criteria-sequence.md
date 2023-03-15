---
keywords: 條件序列；多個條件；演算法；條件；建議條件；序列；傳回的項目數限制；槽層級控制；槽
description: 了解如何設定最多五個條件的序列，以對您Adobe中顯示的項目執行更好的控制 [!DNL Target] Recommendations活動。
title: 如何在Recommendations中建立條件序列？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 34%

---

# 建立條件序列

使用最多五個條件的序列來對 [!UICONTROL Recommendations] 活動中出現的項目執行更好的控制。您也可以限制傳回的項目數（有時稱為「槽層級控制」）。

>[!NOTE]
>
>條件序列不能搭配在 [!UICONTROL  2016 年 10 月之前版本中建立的 ]Recommendations[!DNL Target Premium] 活動使用。

若要建立條件順序，您必須先建立您要在序列中包括的條件。請參閱[建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)，以取得相關資訊。

透過使用條件序列，您可以在條件未傳回可滿足您的設計的足夠結果時，提供其他鎖定目標的建議，而非使用更一般的備用建議。條件序列通常會從傳回較少結果的更特定鎖定目標，繼續到傳回較多結果的更一般鎖定目標。

您的條件序列可能會依頁面類型而有所不同，如下列範例所示：

| 頁面類型 | 可能的序列順序 |
| --- | --- |
| 產品頁面 | <ol><li>根據目前項目，來自相同品牌</li><li>根據目前項目，來自所有品牌</li><li>根據內容相似度</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多的項目</li></ol> |
| 首頁 | <ol><li>根據訪客的最近一次的購買 </li><li>根據訪客最喜愛的項目</li><li>根據訪客最喜愛的類別</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多</li></ol> |

## 建立條件序列

您可以從 [!UICONTROL 建立條件序列] 螢幕。

有多個方式可到達[!UICONTROL 「建立條件順序」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在&#x200B;**[!UICONTROL 「Recommendations」]**>**[!UICONTROL 「條件」]**&#x200B;資料庫畫面上，按一下&#x200B;**[!UICONTROL 「建立條件」**[!UICONTROL >]**「建立條件順序」]**。您在這裡建立的條件會自動可供所有 [!UICONTROL Recommendations] 活動使用。
* 建立 [!UICONTROL Recommendations] 活動，在「選取條件」畫面中，按一下 **[!UICONTROL 新建]** > **[!UICONTROL 建立條件序列]**. 您將可以選擇儲存您的新條件順序以搭配其他 [!UICONTROL Recommendations] 活動使用。
* 編輯 [!UICONTROL Recommendations] 活動，按一下 [!UICONTROL Recommendations位置] ，然後選取 **[!UICONTROL 變更條件]**. 在[!UICONTROL 「選取條件」]畫面上，按一下&#x200B;**[!UICONTROL 「新建」]**>**[!UICONTROL 「建立條件順序」]**。您將可以選擇儲存您的新條件以搭配其他 [!UICONTROL Recommendations] 活動使用。

下列步驟假設您存取 [!UICONTROL 建立條件序列] 使用第一個方法進行篩選：the **[!UICONTROL Recommendations]** > **[!UICONTROL 條件]** 程式庫畫面。

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 條件]**.

1. 按一下 **[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件序列]**.

   ![CreateCriteriaSequence影像](assets/CreateCriteriaSequence.png)

1. 填寫 [基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) 區段。

1. 在 **[!UICONTROL 條件序列]** ，按一下 **[!UICONTROL 新增條件]**.

   序列順序定義填充設計的順序。 如果條件1沒有足夠的建議來填入您的設計，其餘的位置將會填入條件2，以此類推。

   ![新增條件](/help/main/c-recommendations/c-algorithms/assets/add-criteria.png)

1. 在 [!UICONTROL 選取條件] 畫面，選取條件，然後按一下 **[!UICONTROL 新增]**.

   您可以使用「搜尋」方塊和篩選下拉式清單來尋找所需的條件。

   ![選取條件](/help/main/c-recommendations/c-algorithms/assets/select-criteria.png)

1. （可選）滑動 **[!UICONTROL 限制傳回的項目數]** 切換至「開啟」位置，然後指定項目數（介於1和50之間）。

   ![限制傳回的項目數](/help/main/c-recommendations/c-algorithms/assets/limit-number.png)

   協助您了解 [!UICONTROL 限制傳回的項目數] 選項（有時稱為「槽級控制」）考慮以下使用案例：

   * **使用案例1**:您想在單一建議匣中混合使用不同類型的項目。 例如，您想要顯示外套（夾克）和上衣（襯衫、T恤）的混合。 若要達成此目標，請對活動使用集合，其中包含您想在設計的任何位置使用的所有潛在產品類型。 然後，使用靜態篩選器設定您的第一個條件，該靜態篩選器將條件限制為僅包括外套，並使用靜態篩選器將條件限制為僅包括頂部來設定您的第二個條件。 最後，將兩個條件新增至條件序列，並將第一個條件限制為2個槽。

      建議匣在您的網站上可能如下所示：

      ![精選產品建議匣](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **使用案例2**:您想要混合使用替代項目和互補項目。 設定一個條件以使用已檢視/已檢視演算法，並使用動態篩選來限制建議項目為目前項目的類別。 設定第二個條件以使用已檢視/已購買的演算法，並使用動態篩選，其中僅包含不符合目前項目類別的建議項目。 最後，將兩個條件新增至序列，並將第一個條件限制為2個槽。

1. 繼續將其他條件新增至您的序列。 您可以新增最多五個條件至順序。

1. 啟用 [備份內容選項](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

   條件序列會出現在條件清單中。

   如需關於建議邏輯選項的詳細資訊，請參閱[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)。

## 訓練影片: 在 Recommendations 中建立條件 (12:33) ![Tutorial badge](/help/main/assets/tutorial.png)

此影片包含下列資訊:

* 建立條件
* 建立條件序列
* 上傳自訂條件

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
