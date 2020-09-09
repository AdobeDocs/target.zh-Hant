---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;
description: 使用最多5個標準的序列，對Adobe Target Recommendations活動中出現的項目進行更大的控制。
title: 建立條件序列
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: a4479a26873f39a41782e78651802899512b87fe
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 43%

---


# ![PREMIUM](/help/assets/premium.png) 建立條件序列

使用最多五個條件的序列來對 [!UICONTROL Recommendations] 活動中出現的項目執行更好的控制。

>[!NOTE]
>
>條件序列不能搭配在 [!UICONTROL  2016 年 10 月之前版本中建立的 ]Recommendations[!DNL Target Premium] 活動使用。

若要建立條件順序，您必須先建立您要在序列中包括的條件。請參閱[建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md)，以取得相關資訊。

透過使用條件序列，您可以在條件未傳回可滿足您的設計的足夠結果時，提供其他鎖定目標的建議，而非使用更一般的備用建議。通常，條件序列會從傳回較少結果的更特定定位，到傳回更多結果的更一般定位。

您的准則順序可能依頁面類型而異，如下列範例所示：

| 頁面類型 | 可能的順序 |
| --- | --- |
| 產品頁面 | <ol><li>根據目前項目，來自相同品牌</li><li>根據目前項目，來自所有品牌</li><li>根據內容相似度</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多的項目</li></ol> |
| 首頁 | <ol><li>根據訪客的最近一次的購買 </li><li>根據訪客最喜愛的項目</li><li>根據訪客最喜愛的類別</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多</li></ol> |

## 訪問「建立條件序列」螢幕

有多個方式可到達[!UICONTROL 「建立條件順序」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在&#x200B;**[!UICONTROL 「Recommendations」]**>**[!UICONTROL 「條件」]**&#x200B;資料庫畫面上，按一下&#x200B;**[!UICONTROL 「建立條件」**[!UICONTROL >]**「建立條件順序」]**。您在這裡建立的條件會自動可供所有 [!UICONTROL Recommendations] 活動使用。
* 當您建立 [!UICONTROL Recommendations活動時] ，從「選取准則」畫面中按一下「建立新 **[!UICONTROL 增]** >建立 **[!UICONTROL 准則序列」]**。 您將可以選擇儲存您的新條件順序以搭配其他 [!UICONTROL Recommendations] 活動使用。
* When you are editing a [!UICONTROL Recommendations] activity, click in a [!UICONTROL Recommendations Location] box on your page, then select **[!UICONTROL Change Criteria]**. 在[!UICONTROL 「選取條件」]畫面上，按一下&#x200B;**[!UICONTROL 「新建」]**>**[!UICONTROL 「建立條件順序」]**。您將可以選擇儲存您的新條件以搭配其他 [!UICONTROL Recommendations] 活動使用。

以下步驟假定您使用第一 [!UICONTROL 種方法訪問「建立標準序列] 」螢幕：「建 **[!UICONTROL 議]** > **[!UICONTROL 准則]** 」程式庫畫面。

1. 按一 **[!UICONTROL 下「建議]** > **[!UICONTROL 准則]**」。

1. 按一 **[!UICONTROL 下「建立條件]** >建 **[!UICONTROL 立條件順序」]**。

   ![](assets/CreateCriteriaSequence.png)

## 填寫「資訊」區段

1. 輸入序列的&#x200B;**[!UICONTROL 名稱]**。

   這是用來說明該條件順序的「內部」名稱。您的網站的訪客將不會看見此名稱。

   ![「建立標準序列」資訊部分](/help/c-recommendations/c-algorithms/assets/criteria-sequence-info.png)

1. 如果在序列中使用多個條件填入 **[!UICONTROL Recommendations]** 設計，請輸入要在頁面上公開顯示的[!UICONTROL 一般顯示標題]。

   例如，如果設計可能包括基於一個以上 [!UICONTROL Recommendations] 金鑰的項目，則可以將「檢視這個的客戶也檢視了...」取代為「給您的建議」。

1. 輸入條件序列的簡短&#x200B;**[!UICONTROL 說明]**。

   說明應協助您識別標準順序，並可能包含其用途的相關資訊。

1. 選取&#x200B;**[!UICONTROL 垂直產業]**.

   Your default [industry vertical](/help/c-recommendations/c-algorithms/algorithms.md#section_936BCFCF234C49A2BEC1C38AAC2D71AF) appears automatically.

1. 選取一個&#x200B;**[!UICONTROL 頁面類型]**。

   您可以選取多個頁面類型。

   垂直產業和頁面類型可共同用來分類您儲存的條件順序，讓您可輕鬆對其他 [!UICONTROL Recommendations] 活動重複使用順序。

## 建立序列 {#sequence}

序列順序定義填充設計的順序。 如果條件1沒有足夠的建議來填入您的設計，其餘的槽將填入條件2等。

1. 在「標準 **[!UICONTROL 序列]** 」區段中，按一 **[!UICONTROL 下「新增標準」]**。

   ![新增條件](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. On the [!UICONTROL Select Criteria] screen, select a criteria.

   您可以使用「搜尋」方塊和篩選下拉式清單來尋找所需的准則。

   ![選取條件](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. 按一下&#x200B;**[!UICONTROL 「新增」]**。

1. （選擇性）投 **[!UICONTROL 影片「限制傳回的項目數]** 」會切換至「開啟」位置，然後指定項目數（介於1到50之間）。

   ![限制傳回的項目數，切換](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   為協助您瞭解「限制傳回 [!UICONTROL 的項目數」選項的值] ，請考慮下列使用案例：

   * **使用案例1**:您想要在單一建議托盤中混合使用不同種類的項目。 例如，您想要展示混搭的外套（夾克）和上衣（襯衫、T恤）。 若要達成此目的，請使用「系列」作業，其中包含您設計中任何位置所需的所有潛在產品類型。 然後，使用限制條件僅包含外套的靜態篩選器來設定您的第一個准則，並使用限制條件僅包含頂端的靜態篩選器來設定您的第二個准則。 最後，將兩個准則新增至准則序列，並將第一個准則限制為2個槽。

      Recommendations托盤在您的網站上可能如下所示：

      ![精選產品建議托盤](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **使用案例2**:您需要混合使用替代項目和互補項目。 設定一個准則以使用已檢視／已檢視演算法，並使用動態篩選，將建議項目限制為目前項目的類別。 設定第二個條件以使用已檢視／購買的演算法，並使用動態篩選，其中僅包含不符合目前項目類別的建議項目。 最後，將兩個准則新增至序列，並將第一個准則限制為2個槽。

1. 繼續將其他條件新增至序列。 您可以新增最多五個條件至順序。

## 指定備份內容

當沒有足夠的建議可填寫設計範本時，選擇要傳回的內容。

建立條件順序時，系統會針對組成序列的個別條件，忽略其備用建議和部分設計呈現設定。若要使用備用建議和部分設計呈現，您必須啟用其序列。選取適當的切換。如果您選擇允許備用建議，則也可以選擇是否對備用套用包含規則。

![備份內容設定](/help/c-recommendations/c-algorithms/assets/backup-content-settings.png)

1. （可選）將「部 **[!UICONTROL 分設計演算]** 」切換至「開啟」位置。

   將會填入盡可能多的槽，但設計範本可能包含剩餘槽的空白空間。

1. （可選）將「備 **[!UICONTROL 份建議]** 」切換至「開啟」位置。

   從您的網站上隨機選擇檢視次數最多的產品，以填入設計中剩餘的空白位置。

   如需詳細資訊，請參 [閱使用備份建議](/help/c-recommendations/c-algorithms/backup-recs.md)。

1. （條件性）如果您在上 **[!UICONTROL 一步驟中選取「備份建議]** 」，則可以選取「套 **[!UICONTROL 用包含規則至備份建議」]**。

   For more information see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   條件序列會出現在條件清單中。

   如需關於建議邏輯選項的詳細資訊，請參閱[條件](../../c-recommendations/c-algorithms/algorithms.md)。

## 訓練影片: 在 Recommendations 中建立條件 (12:33) ![教學課程徽章](/help/assets/tutorial.png)

此影片包含下列資訊:

* 建立條件
* 建立條件序列
* 上傳自訂條件

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
