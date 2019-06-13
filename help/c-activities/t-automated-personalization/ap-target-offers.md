---
description: 在自動個人化活動中，您可以將選件鎖定在特定對象。
seo-description: 在自動個人化活動中，您可以將選件鎖定在特定對象。
seo-title: 鎖定自動個人化選件
solution: Target、Analytics
title: 鎖定自動個人化選件
title-outputclass: premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: premium
translation-type: tm+mt
source-git-commit: 7b7f61efde2c72e6054dd8f08fbde2a395b6447c

---


# ![PREMIUM](/help/assets/premium.png) 鎖定自動個人化選件{#target-automated-personalization-offers}

在「自動個人化」(AP)活動中，您可以定位選件給特定對象。

使用這項功能可減少特定訪客可看到的選件數量。例如，假設AP活動有三個選件。選件具有定位規則，限制其對對象A的曝光。有兩位訪客看見此AP活動。

|  | 訪客 1 | 訪客 2 |
|--- |--- |--- |
| 對象資格 | 對象 A | 對象 B |
| 選件 1 Target 個人化模型分數 | 90 | 90 |
| 選件 2 Target 個人化模型分數 | 50 | 70 |
| 選件 3 Target 個人化模型分數 | 80 | 60 |

在這個情況下，訪客 1 會看到選件 1 (因符合對象 A 資格)，是該訪客的最高分數。但即便訪客 2 的最高分數來自選件 1，仍會看到選件 2，這是因為訪客 2 不是對象 A。這個例子說明為何應謹慎使用目標規則，以符合企業需求。加入這些規則可降低 Target 個人化模型的有效程度。

## 設定定位規則

1. 建立 [包含您想要定位之選件的「自動個人化」活動](/help/c-activities/t-automated-personalization/create-ap-activity.md) 。
1. 在Visual Experience Composer中設定活動的選件後，按一下 **[!UICONTROL 「管理內容]**」。

   ![管理內容](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   「管理內容」對話方塊隨即開啟。

1. 按一下「選件」標籤。

   ![選件頁面](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 選擇所要的選件，並選擇您想要查看該選件的對象。

   若要設定單一選件的定位，請將滑鼠指標暫留在所要的選件上，然後按一下 **[!UICONTORL 「定位]** 」圖示。

   若要設定多個選件的定位，請選取所需選件的核取方塊，然後按一下清單右上角的「**[!UICONTROL 定位」] 圖示。

1. 在 [!UICONTROL 「選擇對象] 」對話方塊中，選取選件所要的對象，然後按一下 **[!UICONTROL 「完成」]** 返回 [!UICONTROL 「管理內容] 」對話方塊。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 按一下 **[!UICONTROL 「完成」]**。

>[!NOTE]
>
>您可以設定 50 個位置，且每個位置最多可設定 250 個選件。
