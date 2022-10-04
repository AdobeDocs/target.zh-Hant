---
keywords: 自動個人化；選件；報表；群組；報表群組
description: 了解如何在Adobe中使用優惠方案報表群組 [!DNL Target] Automated Personalization活動。 使用報表群組， [!DNL Target] 每個報表群組僅建立一個個人化模型。
title: 我可以在Automated Personalization活動中使用選件報表群組嗎？
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 62%

---

# ![PREMIUM](/help/main/assets/premium.png) 自動個人化中的選件報表群組

在中使用報表群組的相關資訊 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活動。

報表群組執行兩個重要功能:

* 這些功能可讓您查看 AP 活動報表中分組的選件。
* 他們在 [!DNL Target] 個人化模型功能。

使用報表群組時， [!DNL Target] 使用來自該群組中所有選件的資料，為每個報表群組僅建立一個個人化模型，而不是AP活動中的每個選件。

如果您的活動設定沒有足夠的資料來為每個選件建立個人化模型，則報表群組可幫助減少使用「自動個人化」的資料要求。報表群組也可以藉由分組類似選件來幫助解決新選件的「冷啟動」問題，以便每個模型獲得更多資料以進行訓練。模組化群組也可用於定期向 AP 活動提供新選件的活動。

如果訪客以相同的方式回應群組中的所有選件，則此方法很有效。最佳做法是對類似訪客群組以類似方式回應的選件進行分組。換句話說，群組選件具有類似的轉換率。您永遠不應將所有選件放置在單一報表群組中。將所有選件分組或將具有非常不同轉換率的選件分組，可能會降低 [!DNL Target] 個人化模型。

>[!NOTE]
>
>如果從特定模組化群組中移除或替換選件，則也會從模組化群組中刪除看到該特定選件的歷史流量。換言之，已刪除的選件不會對用於 [!DNL Target] 要學習的個人化模型。

**若要設定報表群組:**

1. 在 [!UICONTROL 體驗] AP活動的頁面，按一下 **[!UICONTROL 管理內容]** 表徵圖。

   ![](/help/main/c-reports/assets/ap_manage_content.png)

1. 按一下&#x200B;**[!UICONTROL 「管理內容」]**&#x200B;對話方塊頂端的[!UICONTROL 「選件」]索引標籤。
1. (條件性) 藉由將游標移至所需的選件上，然後按一下&#x200B;**[!UICONTROL 「報表群組」]**&#x200B;資料夾圖示，將特定體驗加入報表群組。

   ![](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (條件性) 藉由選取相關體驗的核取方塊，然後按一下對話方塊右上角的&#x200B;**[!UICONTROL 「報表群組」]**&#x200B;資料夾圖示，將體驗批次加入報表群組。

   ![](/help/main/c-reports/assets/ap_manage_content_3.png)

1. （條件性）若要將選取的選件指派至現有的報表群組，請選取 **[!UICONTROL 現有]**，從下拉式清單中選取所需的報表群組，然後按一下 **[!UICONTROL 套用]**.

   或

   若要建立新報表群組以將選定選件指派至該群組，請選取&#x200B;**[!UICONTROL 「新增」]**，命名新報表群組，然後按一下&#x200B;**[!UICONTROL 「套用」]**。

   ![](/help/main/c-reports/assets/ap_reporting_groups.png)
