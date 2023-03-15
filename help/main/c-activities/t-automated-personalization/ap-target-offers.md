---
keywords: 自動個人化；選件；目標；對象；鎖定規則；鎖定目標
description: 了解如何使用Adobe Target中的Automated Personalization(AP)活動，將個別優惠方案鎖定在特定對象。
title: 如何 [!DNL Target] Automated Personalization選件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 87%

---

# [!DNL Target] Automated Personalization選件

在 [!DNL Adobe Target] [!DNL Automated Personalization] (AP)活動，您可以將選件鎖定在特定對象。

使用這項功能可減少特定訪客可看到的選件數量。舉例來說，假設 AP 活動有三個選件。選件 1 有目標規則，限制向對象 A 曝光。有兩位訪客看過這個 AP 活動。

|  | 訪客 1 | 訪客 2 |
|--- |--- |--- |
| 對象資格 | 對象 A | 對象 B |
| 選件 1 Target 個人化模型分數 | 90 | 90 |
| 選件 2 Target 個人化模型分數 | 50 | 70 |
| 選件 3 Target 個人化模型分數 | 80 | 60 |

在這個情況下，訪客 1 會看到選件 1 (因符合對象 A 資格)，是該訪客的最高分數。但即便訪客 2 的最高分數來自選件 1，仍會看到選件 2，這是因為訪客 2 不是對象 A。這個例子說明為何應謹慎使用目標規則，以符合企業需求。加入這些規則可降低 Target 個人化模型的有效程度。

## 設定鎖定規則

1. 建立包含您要鎖定選件的 [Automated Personalization 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)。
1. 在可視化體驗撰寫器中設定活動的選件之後，請按一下&#x200B;**[!UICONTROL 管理內容]**。

   ![管理內容](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   「管理內容」對話方塊隨即開啟。

1. 按一下選件標籤。

   ![選件頁面](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 選取所需的選件，然後選擇您要符合查看該選件之資格的受眾。

   若要針對單一選件設定鎖定目標，請將游標移至所需的選件上，然後按一下&#x200B;**[!UICONTROL 鎖定目標]**&#x200B;圖示。

   若要針對多個選件設定鎖定目標，請選取所需選件的核取方塊，然後按一下顯示於清單右上角的 **[!UICONTROL 鎖定目標]圖示。

1. 在[!UICONTROL 選擇受眾]對話方塊中，針對選件選取所需的受眾，然後按一下&#x200B;**[!UICONTROL 完成]**，以返回[!UICONTROL 管理內容]對話方塊。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

>[!NOTE]
>
>您可以設定 50 個位置，且每個位置最多可設定 250 個選件。
