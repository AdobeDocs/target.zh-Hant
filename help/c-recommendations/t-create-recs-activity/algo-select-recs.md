---
keywords: recommendations;recommendations activity;criteria;algorithm
description: 選取要在您的 Adobe Target Recommendations 活動中使用的條件。
title: 選取條件
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 82%

---


# ![PREMIUM](/help/assets/premium.png) 選取條件{#select-criteria}

選取要在您的 活動中使用的[條件](/help/c-recommendations/c-algorithms/algorithms.md)。[!DNL Adobe Target Recommendations]條件即為一種規則，用來根據預先決定的一組訪客行為決定要建議的產品。

您可以新增多個條件，以對比測試多種建議類型。

如果您選取多個條件，流量會在選取的條件間平均分割。例如，如果您已選取了兩個條件，而您的活動是設計為對 20% 的活動加入者顯示預設內容，那麼 40% 的活動加入者將看到每個條件所控制的建議。沒有選項可變更每個條件的百分比。

* 若要搜尋現有條件 (例如，如果顯示了許多條件卡片)，請在搜尋欄位中輸入內容，直到需要的條件出現為止，接著選取條件，然後按一下&#x200B;**[!UICONTROL 「完成」]**。

   有些條件是由 [!DNL Recommendations] 提供。您和您的團隊也可以建立自己的自訂條件。

* 若要建立新標準，請按一下「建立標準&#x200B;**** > **[!UICONTROL 建立標準]**」，然後填寫新標準的資訊。 如需建立新條件的詳細資訊，請參閱[建立新條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)。

**若要選取條件:**

1. 在[建立新建議](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)時，在&#x200B;**[!UICONTROL 選擇標準]**&#x200B;對話方塊中，找出並選取一或多個標準。

   ![選取條件對話方塊](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   您可以使用[!UICONTROL 產業類型]篩選、[!UICONTROL 頁面類型]篩選和[!UICONTROL 相容]核取方塊來篩選條件清單。這些選項可協助您找到所需的條件。

   * **產業類型:** 產業類型可用來幫助對 [!DNL Recommendations] 條件進行分類。若要變更您的預設產業垂直，請按一下「**[!UICONTROL Recommendations]** > **[!UICONTROL 設定]**」，然後選取您想要的預設&#x200B;**[!UICONTROL 產業垂直]**&#x200B;設定。
   * **頁面類型:** 頁面類型可幫助您對您的建議進行分類。也有可為每個頁面類型選擇的內建條件。
   * **相容:** 僅顯示選取的頁面通過所需資料的這些條件。不是每個條件都能在每個頁面上正確執行。頁面或 mbox 必須傳入 `entity.id` 或 `entity.categoryId`，目前項目/目前類別建議才能相容。一般來說，最好只顯示相容的條件。不過，如果您想要讓不相容的條件可供活動使用，請清除&#x200B;**[!UICONTROL 「相容」]**&#x200B;核取方塊。您可以在您的設定中停用或啟用此選項：**[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**。

1. 按一下&#x200B;**[!UICONTROL 下一步]**&#x200B;以顯示[選取設計](/help/c-recommendations/c-design-overview/design-overview.md)對話方塊。
