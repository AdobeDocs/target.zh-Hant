---
keywords: 自動個人化；選件；鎖定目標；對象；鎖定規則；鎖定目標
description: 瞭解如何使用，將個別優惠方案鎖定在特定對象 [!UICONTROL Automated Personalization] (AP)活動在 [!DNL Adobe Target].
title: 如何鎖定目標 [!UICONTROL Automated Personalization] 選件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 34%

---

# Target [!UICONTROL Automated Personalization] 優惠方案

在 [!DNL Adobe Target] [!DNL Automated Personalization] (AP)活動，您可以將選件鎖定在特定對象。

使用這項功能可減少特定訪客可看到的選件數量。例如，假設有一個 [!UICONTROL Automated Personalization] 具有三個選件的活動。 選件 1 有目標規則，限制向對象 A 曝光。有兩位訪客看過這個 活動。

| | 訪客 1 | 訪客 2 |
|--- |--- |--- |
| 對象資格 | 對象 A | 對象 B |
| 選件 1 Target 個人化模型分數 | 90 | 90 |
| 選件 2 Target 個人化模型分數 | 50 | 70 |
| 選件 3 Target 個人化模型分數 | 80 | 60 |

在此案例中，訪客1看到選件1 （因為此訪客符合對象A的一部分），這是該訪客的最高分數。 不過，訪客2會看到選件2，即使最高分數是選件1，因為訪客2不屬於受眾A。此範例說明為何應謹慎使用鎖定目標規則以符合業務需求。 新增這些規則可能會降低的效能 [!DNL Target] 個人化模型。

## 設定鎖定規則

1. 建立 [Automated Personalization活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) 包含您要鎖定目標的選件。
1. 在中設定活動的選件之後 [!UICONTROL 視覺化體驗撰寫器]，按一下 **[!UICONTROL 管理內容]**.

   ![管理內容](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   此 [!UICONTROL 管理內容] 對話方塊隨即顯示。

1. 按一下 **[!UICONTROL 選件]** 標籤。

   ![選件頁面](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 選取所需的選件，然後選擇您要符合檢視該選件之資格的受眾。

   若要針對單一選件設定鎖定目標，請將游標移至所需的選件上，然後按一下&#x200B;**[!UICONTROL 鎖定目標]**&#x200B;圖示。

   若要針對多個選件設定鎖定目標，請選取所需選件的核取方塊，然後按一下 **[!UICONTROL 目標定位]** 圖示即會顯示在清單的右上方。

1. 在 [!UICONTROL 選擇對象] 對話方塊中，選取選件所需的對象，然後按一下 **[!UICONTROL 完成]** 以返回 [!UICONTROL 管理內容] 對話方塊。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

>[!NOTE]
>
>您可以設定 50 個位置，且每個位置最多可設定 250 個選件。
