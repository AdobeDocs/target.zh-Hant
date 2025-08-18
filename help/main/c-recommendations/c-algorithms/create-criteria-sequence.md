---
keywords: 條件序列；多個條件；演演算法；條件；建議條件；序列；限制傳回的專案數；位置層級控制；位置
description: 瞭解如何設定最多五個條件的順序，以更能掌控建議活動中出現的專案。
title: 如何在Recommendations中建立條件序列？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 18%

---

# 建立條件序列

使用最多五個條件的序列來對出現在您[!DNL Adobe Target] [!UICONTROL Recommendations]活動中的專案執行更好的控制。 您也可以限制傳回的專案數（有時稱為「位置層級控制」）。

>[!NOTE]
>
>條件序列不能搭配在2016年10月發行的[!UICONTROL Recommendations]之前建立的[!DNL Target Premium]活動使用。

若要建立條件順序，您必須先建立您要在序列中包括的條件。如需詳細資訊，請參閱[建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

透過使用條件序列，您可以在條件未傳回可滿足您的設計的足夠結果時，提供其他鎖定目標的建議，而非使用更一般的備用建議。通常，條件序列會從更具體的目標定位（可能會傳回較少的結果）進展到更一般的目標定位（通常傳回更多結果）。

您的條件序列可能會依頁面型別的不同而有所不同，如下列範例所示：

| 頁面型別 | 可能的順序順序 |
| --- | --- |
| 產品頁面 | <ol><li>根據目前專案，來自相同品牌</li><li>根據目前項目，來自所有品牌</li><li>根據內容相似度</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多的項目</li></ol> |
| 首頁 | <ol><li>根據訪客的最近一次的購買 </li><li>根據訪客最喜愛的項目</li><li>根據訪客最喜愛的類別</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多</li></ol> |

## 建立條件序列

您可以從[!UICONTROL Create Criteria Sequence]畫面建立條件序列。

有多種方式可以到達[!UICONTROL Create Criteria Sequence]畫面。 根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;資料庫畫面上，按一下&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**。 您在這裡建立的條件會自動可供所有 [!UICONTROL Recommendations] 活動使用。
* 建立[!UICONTROL Recommendations]活動時，從[!UICONTROL Select Criteria]畫面按一下「**[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**」。 您可以選擇儲存您的新條件序列以搭配其他[!UICONTROL Recommendations]活動使用。
* 編輯[!UICONTROL Recommendations]活動時，請在頁面上的[!UICONTROL Recommendations Location]方塊中按一下，然後選取&#x200B;**[!UICONTROL Change Criteria]**。 在[!UICONTROL Select Criteria]畫面上，按一下&#x200B;**[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**。 您可以選擇儲存您的新條件以搭配其他[!UICONTROL Recommendations]活動使用。

下列步驟假設您使用第一個方法存取[!UICONTROL Create Criteria Sequence]畫面： **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;資料庫畫面。

1. 按一下&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**。

1. 按一下&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**。

1. 在[基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)區段中填入資訊。

1. 在&#x200B;**[!UICONTROL Criteria Sequence]**&#x200B;區段中，按一下加號( + )以新增一或多個條件序列。

   序列順序會定義設計填入的順序。 如果條件1的建議不足以填滿您的設計，則其餘位置會填滿條件2，依此類推。

1. 在[!UICONTROL Select Criteria]畫面上，選取條件，然後按一下&#x200B;**[!UICONTROL Save]**。

   您可以使用[!UICONTROL Search]方塊和篩選選項來尋找所需的條件。

1. （選用）將&#x200B;**[!UICONTROL Limit the number of items returned]**&#x200B;切換滑至「開啟」位置，然後指定專案數量（介於1到50之間）。

   為協助您瞭解[!UICONTROL Limit the number of items returned]選項（有時稱為「位置層級控制」）的值，請考慮下列使用案例：

   * **使用案例1**：您想要在單一建議匣中混合使用不同型別的專案。 例如，您想要混合顯示外套（夾克）和上衣（襯衫、T恤）。 若要達成此目的，請針對包含您要在設計中任何位置中的所有潛在產品型別的活動使用集合。 然後，使用靜態篩選器設定您的第一個條件，限制該條件僅包含外套，並使用靜態篩選器設定您的第二個條件，限制該條件僅包含上衣。 最後，將兩個條件新增至條件序列，並將第一個條件限製為2個槽。

     在您的網站上，建議匣看起來可能像這樣：

     ![精選產品推薦匣](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **使用案例2**：您想要同時使用替代專案與補充專案。 設定一個條件以使用已檢視/已檢視的演演算法，並使用動態篩選器將建議專案限製為目前專案的類別。 設定第二個條件以使用已檢視/已購買的演演算法，並使用僅包含不符合目前專案類別之建議專案的動態篩選器。 最後，將兩個條件新增至序列，並將第一個條件限製為2個槽。

1. 繼續新增其他條件至您的序列。 您可以新增最多五個條件至順序。

1. 啟用[備份內容選項](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)。

1. 按一下 **[!UICONTROL Create]**。

   條件序列會顯示在[!UICONTROL Criteria]清單中。

   如需關於建議邏輯選項的詳細資訊，請參閱[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)。
