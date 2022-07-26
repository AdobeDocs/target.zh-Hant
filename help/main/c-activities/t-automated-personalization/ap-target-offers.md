---
keywords: 自動個性化；提供；目標；受眾；目標規則；目標；automated personalization;offirs;target;auteging rules;targeting
description: 通過在Adobe Target的Automated Personalization(AP)活動，瞭解如何針對特定受眾提供個性化服務。
title: 我如何 [!DNL Target] Automated Personalization提供？
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 87%

---

# ![高級](/help/main/assets/premium.png) [!DNL Target] Automated Personalization提供

在 [!DNL Adobe Target] [!DNL Automated Personalization] (AP)活動，您可以針對特定的受眾提供服務。

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
