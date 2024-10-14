---
keywords: 自動個人化；選件；鎖定目標；對象；鎖定規則；鎖定目標
description: 探索如何使用[!UICONTROL Automated Personalization] (AP)活動將個別優惠方案鎖定在特定對象。
title: 如何鎖定[!UICONTROL Automated Personalization]選件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
solution: Target,Analytics
hide: true
hidefromtoc: true
source-git-commit: 2eb99fb0c108b600d098fc14036b678c50e689b3
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 19%

---

# 目標[!UICONTROL Automated Personalization]選件

在[!DNL Adobe Target] [!DNL Automated Personalization] (AP)活動中，您可以將選件鎖定在特定對象。

使用這項功能可減少特定訪客可看到的選件數量。例如，假設一個[!UICONTROL Automated Personalization]活動有三個選件。 選件1有目標規則，限制向對象A曝光。有兩個訪客看過此活動。

| | 訪客 1 | 訪客 2 |
|--- |--- |--- |
| 對象資格 | 對象 A | 對象 B |
| 選件 1 Target 個人化模型分數 | 90 | 90 |
| 選件 2 Target 個人化模型分數 | 50 | 70 |
| 選件 3 Target 個人化模型分數 | 80 | 60 |

在此案例中，訪客1看到選件1 （因為此訪客符合對象A的一部分），這是該訪客的最高分數。 不過，訪客2會看到選件2，即使最高分數是選件1，因為訪客2不屬於受眾A。此範例說明為何應謹慎使用鎖定目標規則以符合業務需求。 新增這些規則可能會降低[!DNL Target]個人化模型的有效性。

## 設定鎖定規則

1. 建立包含您要鎖定選件的[Automated Personalization活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)。
1. 在[!UICONTROL Visual Experience Composer]中設定活動的選件之後，請按一下&#x200B;**[!UICONTROL Manage Content]**&#x200B;圖示（ ![管理內容圖示](/help/main/assets/icons/Experience.svg) ）。

   [!UICONTROL Manage Content]對話方塊隨即顯示。

1. 按一下「**[!UICONTROL Offers]**」標籤。

1. 選取所需的選件，然後選擇您要符合檢視該選件之資格的受眾。

   若要設定單一選件的目標定位，請按一下所需選件旁的「更多資訊」 （![更多資訊圖示](/help/main/assets/icons/MoreSmallList.svg) ）圖示，然後按一下「**[!UICONTROL Target Audience]**」以顯示[!UICONTROL Add Audiences]對話方塊。

   若要針對多個選件設定鎖定目標，請選取所需選件的核取方塊，然後按一下顯示於清單底部的&#x200B;**[!UICONTROL Target Audience]**&#x200B;連結。

1. 在[!UICONTROL Add Audiences]對話方塊中，選取選件所需的對象，然後按一下&#x200B;**[!UICONTROL Assign Audience]**&#x200B;以返回[!UICONTROL Manage Content]對話方塊。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。 如需詳細資訊，請參閱[合併多個客群](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 按一下 **[!UICONTROL Done]**。

>[!NOTE]
>
>您可以設定 50 個位置，且每個位置最多可設定 250 個選件。