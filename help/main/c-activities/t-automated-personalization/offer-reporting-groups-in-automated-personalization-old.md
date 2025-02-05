---
keywords: 自動個人化；選件；報表；群組；報表群組；ap
description: 瞭解如何在 [!DNL Adobe Target] [!UICONTROL Automated Personalization]活動中使用選件報表群組。
title: 我可以在[!UICONTROL Automated Personalization]個活動中使用選件報表群組嗎？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 15%

---

# [!UICONTROL Automated Personalization]中的選件報表群組

有關在[!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活動中使用報表群組的資訊。

報表群組執行兩個重要功能:

* 報表群組可讓您檢視在AP活動報表中分組的選件。
* 報表群組對於[!DNL Target]個人化模型的運作方式起著關鍵作用。

當您使用報表群組時，[!DNL Target]會使用該群組所有選件的資料，為每個報表群組建立一個個人化模型。 若沒有報表群組，[!DNL Target]會為您的AP活動中的每個選件建立個人化模型。

如果您的活動設定沒有足夠的資料可針對每個選件建立個人化模型，則報表群組可協助減少使用[!UICONTROL Automated Personalization]的資料需求。 報表群組也可以藉由分組類似產品建議來幫助解決新產品建議的「冷啟動」問題，以便每個模型獲得更多資料以進行訓練。模型群組也可用於定期為AP活動引入新優惠方案的活動。

如果訪客以相同的方式回應群組中的所有產品建議，則此方法很有效。最佳做法是對類似訪客群組以類似方式回應的產品建議進行分組。換句話說，群組產品建議具有類似的轉換率。您永遠不應將所有產品建議放置在單一報表群組中。以不同轉換率來分組所有選件或分組選件，可能會降低[!DNL Target]個人化模型的有效性。

>[!NOTE]
>
>如果從特定模組化群組中移除或替換產品建議，則也會從模組化群組中刪除看到該特定產品建議的歷史流量。換句話說，刪除的選件不會貢獻哪些資料要用於[!DNL Target]個人化模型學習。

## 設定報表群組

1. 在AP活動的&#x200B;**[!UICONTROL Experiences]**&#x200B;頁面上，按一下&#x200B;**[!UICONTROL Manage Content]**&#x200B;圖示。

   ![管理內容圖示](/help/main/c-reports/assets/ap_manage_content.png)

1. 按一下[!UICONTROL Manage Content]對話方塊頂端的&#x200B;**[!UICONTROL Offers]**&#x200B;標籤。
1. （視條件而定）將特定體驗新增至報表群組，方法是暫留在所需的選件上，然後按一下「**[!UICONTROL Reporting Group]**」資料夾圖示。

   ![報表群組圖示](/help/main/c-reports/assets/ap_manage_content_2.png)

1. （條件性）藉由選取相關體驗的核取方塊，然後按一下對話方塊右上角的&#x200B;**[!UICONTROL Reporting Group]**&#x200B;資料夾圖示，將體驗批次加入報表群組。

   ![報表群組圖示](/help/main/c-reports/assets/ap_manage_content_3.png)

1. 若要將選取的選件指派至現有的報表群組，請選取&#x200B;**[!UICONTROL Existing]**，從下拉式清單中選取所需的報表群組，然後按一下&#x200B;**[!UICONTROL Apply]**。

   或

   若要建立報表群組以將選取的選件指派至該群組，請選取「**[!UICONTROL New]**」，命名新的報表群組，然後按一下「**[!UICONTROL Apply]**」。

   ![建立新報表群組的新圖示](/help/main/c-reports/assets/ap_reporting_groups.png)

您可以使用[!UICONTROL Location]清單來依位置篩選選件。 使用[!UICONTROL Report Group]清單可依報表群組篩選選件。 您也可以使用[!UICONTROL Report Group]清單來篩選[!UICONTROL Unassigned Offers]，以便將報表群組指派給目前未指派給任何報表群組的選件。

如需將選件鎖定在特定對象的相關資訊，請參閱[Target [!UICONTROL Automated Personalization]選件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E)。

## 注意事項

* 請務必瞭解報表群組會影響[!DNL Target]建立模型的方式。 因此，[!DNL Adobe]建議，只有在您打算在活動上線時取代或新增選件時，才使用報表群組。 如果將新選件匯入已上線的活動中，將新選件放入具有現有類似選件的群組中，可讓電腦使用已為其群組中的其他選件收集的資料，來瞭解新選件。 您永遠不應將所有產品建議放置在單一報表群組中。

* AP活動具有位置+選件（可模型）的組合。 當[!DNL Target]在報表中記錄資料時，[!DNL Target]會考量這類組合，以清楚知道選件是來自哪個事件（顯示、點按等）。

  例如，活動可能有數個位置和數個選件，這些位置和選件可能會重疊。 如果訪客在不同位置看到多個這些選件，[!DNL Target]只會記錄這些選件的資料。 如果同一位訪客稍後點按了選件，[!DNL Target]只會記錄該組合中的事件（並非針對所有組合）。

  同樣地，如果點按來自於不同位置（存在於量度中，但未顯示選件），此事件會記錄於活動下，但不會記錄於任何選件+位置組合。 因此，此選件不會出現在選件報表群組中。

  此行為是因為點選可能來自不同的mbox，而不是提供選件的mbox。 因此，量度會與活動相關聯，但不會與選件相關聯。

## 在報表群組中檢視選件

1. 按一下&#x200B;**[!UICONTROL Activities]**，從清單中按一下所需的[!UICONTROL Automated Personalization]活動，然後按一下&#x200B;**[!UICONTROL Reports]**&#x200B;索引標籤以顯示[選件層級](/help/main/c-reports/personalization-reports/reports-ap.md)報告。

   如果您有許多活動，請按一下[!UICONTROL Show Filters] （漏斗）圖示，然後選取[!UICONTROL Automated Personalization]核取方塊以篩選清單以僅顯示[!UICONTROL Automated Personalization]個活動。

1. 按一下表格中的&#x200B;**[!UICONTROL Control]**&#x200B;或&#x200B;**[!UICONTROL Targeted]**，以在報表群組內顯示未分組的選件和選件。

   ![優惠方案群組：控制與目標](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

如需使用[!UICONTROL Automated Personalization]報告（包括[!UICONTROL Offer Level]報告）的相關資訊，請參閱[Automated Personalization摘要報告](/help/main/c-reports/personalization-reports/reports-ap.md)。


