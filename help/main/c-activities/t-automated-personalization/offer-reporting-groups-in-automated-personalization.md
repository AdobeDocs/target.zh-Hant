---
keywords: 自動個人化；選件；報表；群組；報表群組；應用程式
description: 了解如何在Adobe中使用優惠方案報表群組 [!DNL Target] [!UICONTROL Automated Personalization] 活動。
title: 我可以在Automated Personalization活動中使用選件報表群組嗎？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 29%

---

# [!UICONTROL Automated Personalization 中的優惠方案報告群組]

在中使用報表群組的相關資訊 [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活動。

報表群組執行兩個重要功能:

* 報表群組可讓您查看在AP活動報表中分組的選件。
* 報表群組在 [!DNL Target] 個人化模型功能。

使用報表群組時， [!DNL Target] 使用該群組中所有選件的資料，為每個報表群組建立一個個人化模型。 若沒有報告群組， [!DNL Target] 會為AP活動中的每個選件建立個人化模型。

如果您的活動設定沒有足夠的資料可供每個選件建立個人化模型，報表群組可協助減少要使用的資料需求 [!UICONTROL Automated Personalization]. 報表群組也可以藉由分組類似選件來幫助解決新選件的「冷啟動」問題，以便每個模型獲得更多資料以進行訓練。模型群組也可用於定期向AP活動引入新選件的活動。

如果訪客以相同的方式回應群組中的所有選件，則此方法很有效。最佳做法是對類似訪客群組以類似方式回應的選件進行分組。換句話說，群組選件具有類似的轉換率。您永遠不應將所有選件放置在單一報表群組中。將所有選件分組或以不同轉換率將選件分組可能會降低 [!DNL Target] 個人化模型。

>[!NOTE]
>
>如果從特定模組化群組中移除或替換選件，則也會從模組化群組中刪除看到該特定選件的歷史流量。換言之，已刪除的選件不會對用於 [!DNL Target] 要學習的個人化模型。

## 設定報表群組

1. 在 **[!UICONTROL 體驗]** AP活動的頁面，按一下 **[!UICONTROL 管理內容]** 表徵圖。

   ![「管理內容」圖示](/help/main/c-reports/assets/ap_manage_content.png)

1. 按一下&#x200B;**[!UICONTROL 「管理內容」]**&#x200B;對話方塊頂端的[!UICONTROL 「選件」]索引標籤。
1. (條件性) 藉由將游標移至所需的選件上，然後按一下&#x200B;**[!UICONTROL 「報表群組」]**&#x200B;資料夾圖示，將特定體驗加入報表群組。

   ![報表群組圖示](/help/main/c-reports/assets/ap_manage_content_2.png)

1. （條件性）借由選取相關體驗的核取方塊，然後按一下 **[!UICONTROL 報表群組]** 資料夾表徵圖。

   ![報表群組圖示](/help/main/c-reports/assets/ap_manage_content_3.png)

1. 若要將選取的選件指派至現有的報表群組，請選取&#x200B;**[!UICONTROL 「現有」]**，從下拉式清單選取所需的報表群組，然後按一下&#x200B;**[!UICONTROL 「套用」]**。

   或

   若要建立報表群組以指派所選選件給，請選取 **[!UICONTROL 新增]**，為新報表群組命名，然後按一下 **[!UICONTROL 套用]**.

   ![建立新報表群組的新圖示](/help/main/c-reports/assets/ap_reporting_groups.png)

您可以使用 [!UICONTROL 位置] 清單，依位置篩選選件。 使用[!UICONTROL 「報表群組」]清單，依報表群組篩選選件。您也可以使用[!UICONTROL 「報表群組」]清單，篩選[!UICONTROL 「未指派的選件」]，為目前未指派任何報表群組的選件，指派報表群組。

如需將選件鎖定在特定對象的相關資訊，請參閱 [Target AP選件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## 注意事項

* 請務必了解報表群組如何影響 [!DNL Target] 建立模型。 因此， [!DNL Adobe] 建議您僅在計畫在活動上線時取代或新增選件時，才使用報表群組。 如果將新選件引入已上線活動中，將新選件放入具有現有類似選件的群組中，電腦就可以使用已針對其群組中其他選件收集的資料來了解新選件。 您永遠不應將所有選件放置在單一報表群組中。

* AP活動具有位置+選件（可模型）的組合。 當 [!DNL Target] 記錄報表中的資料， [!DNL Target] 會考量這些組合，以清楚知道選件來自哪個事件（顯示、點按等）。

   例如，活動可能有數個位置和數個選件，可能會重疊。 如果訪客在不同位置看到多個這些選件， [!DNL Target] 僅記錄這些選件的資料。 如果同一位訪客稍後點按了選件， [!DNL Target] 僅會從該組合中記錄事件（不適用於所有組合）。

   同樣地，如果點按來自不同位置（存在於量度中，但未顯示選件），此事件會記錄在活動下，但不會記錄在任何選件+位置組合中。 因此，此選件不會出現在選件報表群組中。

   此行為是因為點按可能來自不同的mbox，而非提供選件的mbox。 因此，量度與活動相關聯，但與選件無關。

## 檢視報表群組中的選件

1. 按一下 **[!UICONTROL 活動]**，按一下所需 [!UICONTROL Automated Personalization] 活動，然後按一下 **[!UICONTROL 報表]** 標籤來顯示 [選件層級](/help/main/c-reports/personalization-reports/reports-ap.md) 報表。

   如果您有許多活動，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「自動個人化」]，以篩選清單。

1. 按一下 **[!UICONTROL 控制]** 或 **[!UICONTROL 已鎖定]** 在表格中，顯示報表群組內未分組的選件和選件。

   ![選件群組：控制與鎖定](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

如需使用的相關資訊 [!UICONTROL Automated Personalization] 報表(包括 [!UICONTROL 選件層級] )，請參閱 [Automated Personalization摘要報表](/help/main/c-reports/personalization-reports/reports-ap.md).


