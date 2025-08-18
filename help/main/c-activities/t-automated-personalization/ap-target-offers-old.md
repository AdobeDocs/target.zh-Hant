---
keywords: 自動個人化；選件；鎖定目標；對象；鎖定規則；鎖定目標
description: 瞭解如何在[!UICONTROL Automated Personalization]中使用 [!DNL Adobe Target] (AP)活動，將個別優惠方案鎖定在特定對象。
title: 如何鎖定[!UICONTROL Automated Personalization]選件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 27%

---

# 目標[!UICONTROL Automated Personalization]選件

在[!DNL Adobe Target] [!DNL Automated Personalization] (AP)活動中，您可以將選件鎖定在特定對象。

使用這項功能可減少特定訪客可看到的產品建議數量。例如，假設一個[!UICONTROL Automated Personalization]活動有三個選件。 選件1有目標規則，限制向對象A曝光。有兩個訪客看過此活動。

| | 訪客 1 | 訪客 2 |
|--- |--- |--- |
| 對象資格 | 對象 A | 對象 B |
| 產品建議 1 Target 個人化模型分數 | 90 | 90 |
| 產品建議 2 Target 個人化模型分數 | 50 | 70 |
| 產品建議 3 Target 個人化模型分數 | 80 | 60 |

在此案例中，訪客1看到選件1 （因為此訪客符合對象A的一部分），這是該訪客的最高分數。 不過，訪客2會看到選件2，即使最高分數是選件1，因為訪客2不屬於受眾A。此範例說明為何應謹慎使用鎖定目標規則以符合業務需求。 新增這些規則可能會降低[!DNL Target]個人化模型的有效性。

## 設定鎖定規則

1. 建立包含您要鎖定選件的[Automated Personalization活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)。
1. 在[!UICONTROL Visual Experience Composer]中設定活動的選件之後，請按一下&#x200B;**[!UICONTROL Manage Content]**。

   ![管理內容](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL Manage Content]對話方塊隨即顯示。

1. 按一下「**[!UICONTROL Offers]**」標籤。

   ![產品建議頁面](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 選取所需的選件，然後選擇您要符合檢視該選件之資格的受眾。

   若要針對單一選件設定鎖定目標，請將游標移至所需的選件上，然後按一下&#x200B;**[!UICONTROL Targeting]**&#x200B;圖示。

   若要針對多個選件設定鎖定目標，請選取所需選件的核取方塊，然後按一下顯示於清單右上角的&#x200B;**[!UICONTROL Targeting]**&#x200B;圖示。

1. 在[!UICONTROL Choose Audience]對話方塊中，選取選件所需的對象，然後按一下&#x200B;**[!UICONTROL Done]**&#x200B;以返回[!UICONTROL Manage Content]對話方塊。

   >[!NOTE]
   >
   >除了選取現有客群，您可以結合多個客群來建立隨選結合的客群而非建立新客群。如需詳細資訊，請參閱[合併多個客群](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 按一下 **[!UICONTROL Done]**。

>[!NOTE]
>
>您可以設定 50 個位置，且每個位置最多可設定 250 個產品建議。
