---
keywords: Recommendations；Recommendations活動；條件；演演算法
description: 瞭解如何選取條件（決定要建議哪些產品或內容的規則），以用於您的Adobe [!DNL Target] Recommendations活動。
title: 如何為Recommendations活動選取條件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 55%

---

# 選取條件

選取要在您的[活動中使用的](/help/main/c-recommendations/c-algorithms/algorithms.md)條件[!DNL Adobe Target Recommendations]。 條件即為一種規則，用來根據預先決定的一組訪客行為決定要建議的產品。

您可以新增多個條件，以對比測試多種建議類型。

如果您選取多個條件，流量會在選取的條件間平均分割。例如，如果您已選取了兩個條件，而您的活動是設計為對 20% 的活動加入者顯示預設內容，那麼 40% 的活動加入者將看到每個條件所控制的建議。沒有選項可變更每個條件的百分比。

* 若要搜尋現有條件（例如，如果顯示了許多條件卡片），請在搜尋欄位中輸入內容，直到需要的條件出現為止，接著選取條件，然後按一下&#x200B;**[!UICONTROL Done]**。

  有些條件是由 [!DNL Recommendations] 提供。您和您的團隊也可以建立自己的自訂條件。

* 若要建立新條件，請按一下&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**，然後填寫新條件的資訊。 如需建立新條件的詳細資訊，請參閱[建立新條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)。

**若要選取條件:**

1. 在[建立新建議](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)時，請在&#x200B;**[!UICONTROL Select Criteria]**&#x200B;對話方塊中，找出並選取一或多個條件。

   您可以使用[!UICONTROL Industry Type]篩選器、[!UICONTROL Page Type]篩選器和[!UICONTROL Compatible]核取方塊來篩選條件清單。 這些選項可協助您找到所需的條件。

   * **產業類型:** 產業類型可用來幫助對 [!DNL Recommendations] 條件進行分類。若要變更您的預設垂直產業，請按一下&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**&#x200B;並選取您想要的預設&#x200B;**[!UICONTROL Industry Vertical]**&#x200B;設定。
   * **頁面類型:** 頁面類型可幫助您對您的建議進行分類。也有可為每個頁面類型選擇的內建條件。
   * **相容:** 僅顯示選取的頁面通過所需資料的這些條件。不是每個條件都能在每個頁面上正確執行。頁面或 mbox 必須傳入 `entity.id` 或 `entity.categoryId`，目前項目/目前類別建議才能相容。一般來說，最好只顯示相容的條件。不過，如果您想要讓不相容的條件可供活動使用，請清除「**[!UICONTROL Compatible]**」核取方塊。 可以在您的設定中停用或啟用此選項： **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**。

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以顯示[選取設計](/help/main/c-recommendations/c-design-overview/design-overview.md)對話方塊。
