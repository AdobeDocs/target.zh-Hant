---
keywords: 建議；建議活動；標準；算法
description: 瞭解如何選擇在您的Adobe中使用的標準（確定推薦哪些產品或內容的規則） [!DNL Target] Recommendations活動。
title: 如何為Recommendations活動選擇條件？
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 74%

---

# ![PREMIUM](/help/main/assets/premium.png) 選取條件

選取要在您的 活動中使用的[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)。[!DNL Adobe Target Recommendations]條件即為一種規則，用來根據預先決定的一組訪客行為決定要建議的產品。

您可以新增多個條件，以對比測試多種建議類型。

如果您選取多個條件，流量會在選取的條件間平均分割。例如，如果您已選取了兩個條件，而您的活動是設計為對 20% 的活動加入者顯示預設內容，那麼 40% 的活動加入者將看到每個條件所控制的建議。沒有選項可變更每個條件的百分比。

* 若要搜尋現有條件 (例如，如果顯示了許多條件卡片)，請在搜尋欄位中輸入內容，直到需要的條件出現為止，接著選取條件，然後按一下&#x200B;**[!UICONTROL 「完成」]**。

   有些條件是由 [!DNL Recommendations] 提供。您和您的團隊也可以建立自己的自訂條件。

* 要建立新條件，請按一下 **[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**，然後填寫新標準的資訊。 如需建立新條件的詳細資訊，請參閱[建立新條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)。

**若要選取條件:**

1. 同時 [建立新建議](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)，也請參見Wiki頁。 **[!UICONTROL 選擇條件]** 對話框，查找並選擇一個或多個條件。

   ![選取條件對話方塊](/help/main/c-recommendations/t-create-recs-activity/assets/filters.png)

   您可以使用[!UICONTROL 產業類型]篩選、[!UICONTROL 頁面類型]篩選和[!UICONTROL 相容]核取方塊來篩選條件清單。這些選項可協助您找到所需的條件。

   * **產業類型:** 產業類型可用來幫助對 [!DNL Recommendations] 條件進行分類。要更改預設行業垂直，請按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 設定]** 選擇所需的預設值 **[!UICONTROL 行業垂直]** 的子菜單。
   * **頁面類型:** 頁面類型可幫助您對您的建議進行分類。也有可為每個頁面類型選擇的內建條件。
   * **相容:** 僅顯示選取的頁面通過所需資料的這些條件。不是每個條件都能在每個頁面上正確執行。頁面或 mbox 必須傳入 `entity.id` 或 `entity.categoryId`，目前項目/目前類別建議才能相容。一般來說，最好只顯示相容的條件。不過，如果您想要讓不相容的條件可供活動使用，請清除&#x200B;**[!UICONTROL 「相容」]**&#x200B;核取方塊。可以在您的設定中禁用或啟用此選項： **[!UICONTROL Recommendations]** > **[!UICONTROL 設定]**。

1. 按一下&#x200B;**[!UICONTROL 下一步]**&#x200B;以顯示[選取設計](/help/main/c-recommendations/c-design-overview/design-overview.md)對話方塊。
