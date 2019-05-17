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
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) 鎖定自動個人化選件{#target-automated-personalization-offers}

在自動個人化活動中，您可以將選件鎖定在特定對象。

使用這項功能可減少特定訪客可看到的選件數量。舉例來說，假設自動個人化 (AP) 活動有三個選件。選件 1 有目標規則，限制只能向對象 A 曝光。有兩位訪客看過這個 AP 活動。

|  | 訪客 1 | 訪客 2 |
|--- |--- |--- |
| 對象資格 | 對象 A | 對象 B |
| 選件 1 Target 個人化模型分數 | 90 | 90 |
| 選件 2 Target 個人化模型分數 | 50 | 70 |
| 選件 3 Target 個人化模型分數 | 80 | 60 |

在這個情況下，訪客 1 會看到選件 1 (因符合對象 A 資格)，是該訪客的最高分數。但即便訪客 2 的最高分數來自選件 1，仍會看到選件 2，這是因為訪客 2 不是對象 A。這個例子說明為何應謹慎使用目標規則，以符合企業需求。加入這些規則可降低 Target 個人化模型的有效程度。

## 設定鎖定規則

1. 建立包含您要鎖定選件的自動個人化活動。
1. 在可視化體驗撰寫器中設定活動的選件之後，請按一下**[!UICONTROL 「內容」]**。

   「管理內容」對話方塊隨即開啟。

   ![](assets/ap_content.png)

   >[!NOTE]
   >
   >您可以設定 50 個位置，且每個位置最多可設定 250 個選件。

1. 在**[!UICONTROL 「內容」]**欄中，選取選件，然後按一下**[!UICONTROL 「鎖定目標」]**並選擇有資格看見該選件的對象。

   只會對選取的對象呈現該選件。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 按一下**[!UICONTROL 「完成」]**。
