---
keywords: 標準序列；多標準；算法；標準；建議標準；序列；返回的項數；插槽級別控制；插槽
description: 瞭解如何設定最多五個標準的序列，以更好地控制Adobe中顯示的項 [!DNL Target] Recommendations活動。
title: 如何在Recommendations建立條件序列？
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 34%

---

# ![PREMIUM](/help/main/assets/premium.png) 建立條件序列

使用最多五個條件的序列來對 [!UICONTROL Recommendations] 活動中出現的項目執行更好的控制。您還可以限制返回的項數（有時稱為「插槽級別控制」）。

>[!NOTE]
>
>條件序列不能搭配在 [!UICONTROL  2016 年 10 月之前版本中建立的 ]Recommendations[!DNL Target Premium] 活動使用。

若要建立條件順序，您必須先建立您要在序列中包括的條件。請參閱[建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)，以取得相關資訊。

透過使用條件序列，您可以在條件未傳回可滿足您的設計的足夠結果時，提供其他鎖定目標的建議，而非使用更一般的備用建議。通常，標準序列將從返回較少結果的更具體目標，到通常返回較多結果的更一般目標。

您的條件序列可能會因頁面類型而有所不同，如下例所示：

| 頁面類型 | 可能的順序 |
| --- | --- |
| 產品頁 | <ol><li>根據目前項目，來自相同品牌</li><li>根據目前項目，來自所有品牌</li><li>根據內容相似度</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多的項目</li></ol> |
| 首頁 | <ol><li>根據訪客的最近一次的購買 </li><li>根據訪客最喜愛的項目</li><li>根據訪客最喜愛的類別</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多</li></ol> |

## 建立條件序列

從 [!UICONTROL 建立條件序列] 的上界。

有多個方式可到達[!UICONTROL 「建立條件順序」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在&#x200B;**[!UICONTROL 「Recommendations」]**>**[!UICONTROL 「條件」]**&#x200B;資料庫畫面上，按一下&#x200B;**[!UICONTROL 「建立條件」**[!UICONTROL >]**「建立條件順序」]**。您在這裡建立的條件會自動可供所有 [!UICONTROL Recommendations] 活動使用。
* 建立 [!UICONTROL Recommendations] 活動，在「選擇標準」螢幕中，按一下 **[!UICONTROL 新建]** > **[!UICONTROL 建立條件序列]**。 您將可以選擇儲存您的新條件順序以搭配其他 [!UICONTROL Recommendations] 活動使用。
* 編輯 [!UICONTROL Recommendations] 活動，按一下 [!UICONTROL Recommendations位置] 框中，選擇 **[!UICONTROL 更改條件]**。 在[!UICONTROL 「選取條件」]畫面上，按一下&#x200B;**[!UICONTROL 「新建」]**>**[!UICONTROL 「建立條件順序」]**。您將可以選擇儲存您的新條件以搭配其他 [!UICONTROL Recommendations] 活動使用。

以下步驟假定您訪問 [!UICONTROL 建立條件序列] 使用第一種方法進行螢幕顯示：這樣 **[!UICONTROL Recommendations]** > **[!UICONTROL 標準]** 庫螢幕。

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 標準]**。

1. 按一下 **[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件序列]**。

   ![](assets/CreateCriteriaSequence.png)

1. 填寫 [基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) 的子菜單。

1. 在 **[!UICONTROL 標準序列]** ，按一下 **[!UICONTROL 添加條件]**。

   序列順序定義設計填充的順序。 如果條件1沒有足夠的建議來填充您的設計，則剩餘的插槽將填充條件2等。

   ![添加條件](/help/main/c-recommendations/c-algorithms/assets/add-criteria.png)

1. 在 [!UICONTROL 選擇條件] ，選擇條件，然後按一下 **[!UICONTROL 添加]**。

   可以使用「搜索」(Search)框和「篩選器」(filter)下拉框來查找所需的條件。

   ![選取條件](/help/main/c-recommendations/c-algorithms/assets/select-criteria.png)

1. （可選）滑動 **[!UICONTROL 限制返回的項數]** 切換到「開啟」位置，然後指定項目數（介於1和50之間）。

   ![限制返回的項數切換](/help/main/c-recommendations/c-algorithms/assets/limit-number.png)

   幫助您瞭解 [!UICONTROL 限制返回的項數] 選項（有時稱為「插槽級別控制」），請考慮以下使用情形：

   * **用例1**:您希望在單個推薦托盤中混合使用各種不同的項目。 例如，您希望展示外套（夾克）和上衣（襯衫和T恤）的搭配。 要達到此目的，請使用「集合」(Collection)來執行活動，該活動包括您想要在設計的任何插槽中使用的所有潛在產品類型。 然後，使用靜態過濾器設定第一個標準，該靜態過濾器將標準限制為僅包括外套；使用靜態過濾器設定第二個標準，該靜態過濾器將標準限制為僅包括頂部。 最後，將兩個條件添加到條件序列，並將第一個條件限制為2個插槽。

      在您的站點上，建議托盤可能如下所示：

      ![特色產品推薦托盤](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **用例2**:您希望同時使用備選項和補充項。 設定一個標準以使用查看/查看的算法，並使用動態篩選器將建議的項目限制為當前項目的類別。 設定第二個標準以使用查看/購買的算法，並使用一個動態篩選器，該篩選器僅包括與當前項目類別不匹配的推薦項目。 最後，將兩個條件都添加到序列中，並將第一個條件限制為2個插槽。

1. 繼續向序列添加其他條件。 您可以新增最多五個條件至順序。

1. 啟用 [備份內容選項](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   條件序列會出現在條件清單中。

   如需關於建議邏輯選項的詳細資訊，請參閱[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)。

## 訓練影片: 在 Recommendations 中建立條件 (12:33) ![Tutorial badge](/help/main/assets/tutorial.png)

此影片包含下列資訊:

* 建立條件
* 建立條件序列
* 上傳自訂條件

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
