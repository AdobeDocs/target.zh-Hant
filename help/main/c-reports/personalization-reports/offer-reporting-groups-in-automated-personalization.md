---
keywords: 自動個人化；選件；報表；群組；報表群組；應用程式
description: 了解如何在Adobe中使用優惠方案報表群組 [!DNL Target] [!UICONTROL Automated Personalization] 活動。
title: 我可以在Automated Personalization活動中使用選件報表群組嗎？
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: a4219573c1ce253b1c2e163483fb6d901176ed70
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 47%

---

# ![PREMIUM](/help/main/assets/premium.png)[!UICONTROL  自動個人化中的選件報表群組]

在中使用報表群組的相關資訊 [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活動。

報表群組執行兩個重要功能:

* 報表群組可讓您查看在AP活動報表中分組的選件。
* 報表群組在 [!DNL Target] 個人化模型功能。

使用報表群組時， [!DNL Target] 使用該群組中所有選件的資料，為每個報表群組建立一個個人化模型。 若沒有報告群組， [!DNL Target] 會為AP活動中的每個選件建立個人化模型。

如果您的活動設定沒有足夠的資料可供每個選件建立個人化模型，報表群組可協助減少要使用的資料需求 [!UICONTROL Automated Personalization]. 報表群組也可以藉由分組類似選件來幫助解決新選件的「冷啟動」問題，以便每個模型獲得更多資料以進行訓練。模型群組也可用於定期向AP活動引入新選件的活動。

如果訪客以相同的方式回應群組中的所有選件，則此方法很有效。最佳做法是對類似訪客群組以類似方式回應的選件進行分組。換句話說，群組選件具有類似的轉換率。您永遠不應將所有選件放置在單一報表群組中。將所有選件分組或將具有非常不同轉換率的選件分組，可能會降低 [!DNL Target] 個人化模型。

>[!NOTE]
>
>如果從特定模組化群組中移除或替換選件，則也會從模組化群組中刪除看到該特定選件的歷史流量。換言之，已刪除的選件不會對用於 [!DNL Target] 要學習的個人化模型。

## 設定報表群組

1. 在 **[!UICONTROL 體驗]** AP活動的頁面，按一下 **[!UICONTROL 管理內容]** 表徵圖。

   ![「管理內容」圖示](/help/main/c-reports/assets/ap_manage_content.png)

1. 按一下&#x200B;**[!UICONTROL 「管理內容」]**&#x200B;對話方塊頂端的[!UICONTROL 「選件」]索引標籤。
1. (條件性) 藉由將游標移至所需的選件上，然後按一下&#x200B;**[!UICONTROL 「報表群組」]**&#x200B;資料夾圖示，將特定體驗加入報表群組。

   ![報表群組圖示](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (條件性) 藉由選取相關體驗的核取方塊，然後按一下對話方塊右上角的&#x200B;**[!UICONTROL 「報表群組」]**&#x200B;資料夾圖示，將體驗批次加入報表群組。

   ![報表群組圖示](/help/main/c-reports/assets/ap_manage_content_3.png)

1. 若要將選取的選件指派至現有的報表群組，請選取&#x200B;**[!UICONTROL 「現有」]**，從下拉式清單選取所需的報表群組，然後按一下&#x200B;**[!UICONTROL 「套用」]**。

   或

   若要建立新報表群組以將選定選件指派至該群組，請選取&#x200B;**[!UICONTROL 「新增」]**，命名新報表群組，然後按一下&#x200B;**[!UICONTROL 「套用」]**。

   ![建立新報表群組的新圖示](/help/main/c-reports/assets/ap_reporting_groups.png)

## 檢視報表群組中的選件

1. 按一下 **[!UICONTROL 活動]**，按一下所需 [!UICONTROL Automated Personalization] 活動，然後按一下 **[!UICONTROL 報表]** 標籤來顯示 [選件層級](/help/main/c-reports/personalization-reports/reports-ap.md) 報表。

   如果您有許多活動，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「自動個人化」]，以篩選清單。

1. 按一下 **[!UICONTROL 控制]** 或 **[!UICONTROL 已鎖定]** 在表格中，顯示報表群組內未分組的選件和選件。

   ![選件群組：控制與鎖定](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

如需使用的相關資訊 [!UICONTROL Automated Personalization] 報表(包括 [!UICONTROL 選件層級] )，請參閱 [Automated Personalization摘要報表](/help/main/c-reports/personalization-reports/reports-ap.md).


