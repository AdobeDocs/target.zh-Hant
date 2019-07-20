---
description: 選取要在您的建議活動中使用的條件。
keywords: recommendations;recommendations 活動;條件
seo-description: 選取要用於Adobe Target Recommendations活動的標準。
seo-title: 選取條件
solution: Target
title: 選取條件
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
translation-type: tm+mt
source-git-commit: e8e6dcadf307209abcc712798b714af0a5be2e7e

---


# ![PREMIUM](/help/assets/premium.png) 選取條件{#select-criteria}

Select the [criteria](/help/c-recommendations/c-algorithms/algorithms.md) to use in your Recommendations activity. 條件即為一種規則，用來根據預先決定的一組訪客行為決定要建議的產品。

您可以新增多個條件，以對比測試多種建議類型。

如果您選取多個條件，流量會在選取的條件間平均分割。例如，如果您已選取了兩個條件，而您的活動是設計為對 20% 的活動加入者顯示預設內容，那麼 40% 的活動加入者將看到每個條件所控制的建議。沒有選項可變更每個條件的百分比。

* 若要搜尋現有條件 (例如，如果顯示了許多條件卡片)，請在搜尋欄位中輸入內容，直到需要的條件出現為止，接著選取條件，然後按一下&#x200B;**[!UICONTROL 「完成」]**。

   有些條件是由 [!DNL Recommendations] 提供。您和您的團隊也可以建立自己的自訂條件。

* To create a new criteria, click **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. 如需建立新條件的詳細資訊，請參閱[建立新條件](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)。

**若要選擇標準：**

1. [建立新建議](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)時，在 **[!UICONTROL 「標準]** 」對話方塊中找出並選取一或多個標準。

   ![選取標準對話方塊](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   You can use the [!UICONTROL Industry Type] filter, [!UICONTROL Page Type] filter, and [!UICONTROL Compatible] checkbox to filter the list of criteria. 這些選項可協助您找到所需條件。

   * **產業類型:** 產業類型可用來幫助對 [!DNL Recommendations] 條件進行分類。若要變更您的預設垂直產業，請按一下&#x200B;**[!UICONTROL 「設定」]**&#x200B;並選取您需要的預設&#x200B;**「垂直產業」]設定。[!UICONTROL **
   * **頁面類型:** 頁面類型可幫助您對您的建議進行分類。也有可為每個頁面類型選擇的內建條件。
   * **相容:** 僅顯示選取的頁面通過所需資料的這些條件。不是每個條件都能在每個頁面上正確執行。頁面或 mbox 必須傳入 `entity.id` 或 `entity.categoryId`，目前項目/目前類別建議才能相容。一般來說，最好只顯示相容的條件。不過，如果您想要讓不相容的條件可供活動使用，請清除&#x200B;**[!UICONTROL 「相容」]核取方塊。**&#x200B;您可以在您的 [!DNL Target][!UICONTROL  「偏好設定」]中停用或啟用此選項。

1. Click **[!UICONTROL Next]** to display the [Select Design](/help/c-recommendations/c-design-overview/design-overview.md) dialog box.
