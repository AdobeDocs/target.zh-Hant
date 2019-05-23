---
description: 在自動個人化 (AP) 活動中使用報表群組的相關資訊。
keywords: 自動個人化;選件;報表;群組
seo-description: 在自動個人化 (AP) 活動中使用報表群組的相關資訊。
seo-title: 自動個人化中的選件報表群組
solution: Target
title: 自動個人化中的選件報表群組
title-outputclass: premium
topic: 進階
uuid: 5b111a68-bd05-4ef1-8156-d064f2c7e257
badge: premium
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# ![PREMIUM](/help/assets/premium.png) 自動個人化中的選件報表群組{#offer-reporting-groups-in-automated-personalization}

在自動個人化 (AP) 活動中使用報表群組的相關資訊。

報表群組執行兩個重要功能:

* 這些功能可讓您查看 AP 活動報表中分組的選件。
* 他們在 Target 的個人化模型如何運作方面扮演重要角色。

當您使用報表群組時，Target 會使用該群組中所有選件的資料，為每個報表群組 (而非 AP 活動中的每個選件) 僅建立一個個人化模型。

如果您的活動設定沒有足夠的資料來為每個選件建立個人化模型，則報表群組可幫助減少使用「自動個人化」的資料要求。報表群組也可以藉由分組類似選件來幫助解決新選件的「冷啟動」問題，以便每個模型獲得更多資料以進行訓練。模組化群組也可用於定期向 AP 活動提供新選件的活動。

如果訪客以相同的方式回應群組中的所有選件，則此方法很有效。最佳做法是對類似訪客群組以類似方式回應的選件進行分組。換句話說，群組選件具有類似的轉換率。您永遠不應將所有選件放置在單一報表群組中。分組所有選件或分組具有不同轉換率的選件可能會降低 Target 個人化模型的效用。

>[!NOTE]
>
>如果從特定模組化群組中移除或替換選件，則也會從模組化群組中刪除看到該特定選件的歷史流量。換言之，刪除的選件不會影響用於 Target 個人化模型學習的資料。

**若要設定報表群組:**

1. 在 AP 活動的「體驗」頁面中，按一下**[!UICONTROL 「管理內容」]圖示。**

   ![](assets/ap_manage_content.png)

1. 按一下[!UICONTROL **「管理內容」]對話方塊頂端的**[!UICONTROL 「選件」]索引標籤。
1. (條件性) 藉由將游標移至所需的選件上，然後按一下**[!UICONTROL 「報表群組」]資料夾圖示，將特定體驗加入報表群組。**

   ![](assets/ap_manage_content_2.png)

1. (條件性) 藉由選取相關體驗的核取方塊，然後按一下對話方塊右上角的**[!UICONTROL 「報表群組」]資料夾圖示，將體驗批次加入報表群組。**

   ![](assets/ap_reporting_groups.png)

1. 若要將選取的選件指派至現有的報表群組，請選取**[!UICONTROL 「現有」]**，從下拉式清單選取所需的報表群組，然後按一下**[!UICONTROL 「套用」]**。

   或

   若要建立新報表群組以將選定選件指派至該群組，請選取**[!UICONTROL 「新增」]**，命名新報表群組，然後按一下**[!UICONTROL 「套用」]**。

   ![](assets/ap_manage_content_3.png)

