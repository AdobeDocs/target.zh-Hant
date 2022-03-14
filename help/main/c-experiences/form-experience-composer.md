---
keywords: 表單式體驗撰寫器; 表單式撰寫器; 細分
description: 瞭解如何使用Adobe [!DNL Target] 基於表單的經驗編寫器，用於非視覺體驗建立。 當VEC不可用或不實用時，請使用此編寫器。
title: 如何使用基於表單的體驗作曲家？
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 46%

---

# 表單式體驗撰寫器

的 [!DNL Adobe Target] [!UICONTROL 基於表單的體驗作曲家] 是一種非視覺體驗，提供建立介面，在建立體驗時非常有用，可在 [!UICONTROL A/BTest]。 [!UICONTROL 體驗目標]。 [!UICONTROL Automated Personalization], [!UICONTROL Recommendations] 活動 [!UICONTROL 視覺體驗作曲家] (VEC)不可用或不實用。 例如，您可以使用基於表單的體驗作曲家建立體驗和優惠，以便在電子郵件、資訊亭和語音助理中提供。

如果要建立 [!UICONTROL Recommendations] 活動，沒有經驗。 選擇您的條件和設計。如果選擇多個標準或設計， [!UICONTROL 目標] 自動生成體驗。

1. 按一下&#x200B;**[!UICONTROL 「建立活動」]**，然後選取您要建立的活動類型。

   的 [!UICONTROL 基於表單的體驗作曲家] 可用 [!UICONTROL A/BTest]。 [!UICONTROL 體驗目標]。 [!UICONTROL Automated Personalization], [!UICONTROL Recommendations] 活動。

1. 選擇 **[!UICONTROL 窗體]** 從 [!UICONTROL 建立活動] 對話框。

1. （條件）選擇工作區和屬性。

1. 按&#x200B;**[!UICONTROL 「下一步」]**。

   的 [!UICONTROL 基於表單的體驗作曲家] 的上界。

   ![](assets/location_refinements.png)

   如果要建立 [!UICONTROL Recommendations] 的子菜單。 [!UICONTROL Recommendations 活動未包括體驗。]

1. 按一下「」命名活動[!UICONTROL 無標題活動]&quot;
1. 選取位置。

   在 [!UICONTROL 選擇位置] 框中，將顯示可用位置的清單。 選取這些位置中的一個。

   您也可以輸入此處未列出的位置。如果您尚未在頁面上建立或檢視 mbox，則此項目相當實用。輸入位置的名稱。輸入尚未存在的位置時請注意。如果拼字或大寫不符合進行 mbox 呼叫時使用的拼字或大寫，將不會傳送活動。手動輸入的位置將保存到可用位置清單。 下次嘗試選擇手動輸入的位置時，它將從 [!UICONTROL 選擇位置] 下拉清單。

   >[!NOTE]
   >
   >在建立活動期間建立手動輸入的位置不會自動建立新位置。 位置名稱僅保存在活動的上下文中。 當存在內容傳遞呼叫時建立該位置。 在建立位置後，它將可用於其他活動，用於建立受眾等。 從可用位置的下拉清單中。

1. 按一下 **[!UICONTROL 添加受眾改進]**，選擇一個或多個 [觀眾](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) 對於此活動，請按一下 **[!UICONTROL 完成]**。

   ![](assets/location_refinements_2.png)

   在 [!UICONTROL 基於表單的體驗作曲家]，已用完整的觀眾功能替換了改進。 對現有活動的改進已遷移到 [僅活動受眾](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)。

1. 選取您要在該位置中顯示的內容類型。

   ![](assets/form_content.png)

1. 針對您選取的內容類型指定內容。

   **變更 HTML 選件:** 選擇 HTML 選件。

   **變更影像選件:** 選擇儲存在 Target 內容資料庫中的影像。

   您也可以新增連結至影像 (點進、目的地、登陸等等)。

   1. 按一下[!UICONTROL 「變更影像選件」]。
   1. 選取需要的影像，然後按一下[!UICONTROL 「編輯連結」]。
   1. 指定您的網站上需要的 URL 或頁面，然後按一下[!UICONTROL 「更新」]。

   **變更 JSON 選件:** 選擇 JSON 選件。

   **變更體驗片段:** 選擇體驗片段。有關詳細資訊，請參見 [體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

   **變更重新導向選件:** 選擇重新導向選件。有關詳細資訊，請參見 [建立重定向服務](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

   **變更遠端選件:** 選擇遠端選件。有關詳細資訊，請參見 [建立遠程服務](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

   **建立 HTML 選件:**

   1. 按一下[!UICONTROL 「選件」]，然後選取[!UICONTROL 「代碼選件」]索引標籤。
   1. 按一下[!UICONTROL 「建立] > [!UICONTROL HTML 選件」]。
   1. 輸入選件名稱。
   1. 在「程式碼」方塊中，輸入或貼上 HTML 程式碼。
   1. 按一下[!UICONTROL 「儲存」]。

   **建立 JSON 選件:**

   1. 按一下[!UICONTROL 「選件」]，然後選取[!UICONTROL 「代碼選件」]索引標籤。
   1. 按一下「[!UICONTROL 建立] > [!UICONTROL JSON 選件]」。
   1. 輸入選件名稱。
   1. 在「程式碼」方塊中，輸入或貼上 JSON 程式碼。
   1. 按一下[!UICONTROL 「儲存」]。

   **添加建議：**

   對於Recommendations活動，「內容」(Content)下拉框將為您提供 [!UICONTROL 添加建議] 的雙曲餘切值。 按一下&#x200B;**[!UICONTROL 「新增建議」]**，然後選取頁面類型。然後遵循介面中定義的步驟來[建立Recommendations 活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。

   在表單式體驗撰寫器選取「Recommendations」條件時，已有直接連結，可連結至選取的條件卡片，讓您輕鬆快速編輯條件。

   ![](assets/change_criteria.png)

   在 Target 三步驟引導式工作流程的「鎖定目標」頁面:

   ![](assets/change_criteria_2.png)

   **添加優惠決定：**

   添加在中建立的聘用 [!DNL Adobe Journey Optimizer] (AJO)到 [!DNL Adobe Target] 活動，通過offer decisioning向網站或移動站點上的訪問者提供最佳動態優惠和體驗。 此選項可手動使用 [!UICONTROL A/BTest] 和 [!UICONTROL 體驗目標] (XT)活動。

   如需詳細資訊，請參閱[使用報價決策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

1. (可選，用於 [!UICONTROL A/BTest]。 [!UICONTROL Automated Personalization], [!UICONTROL 體驗目標] 活動)要重複此過程以獲取其他位置，請按一下 **[!UICONTROL 添加位置]** 並配置位置和內容。
1. 按一下 **[!UICONTROL 下一個]**，然後按照通常的方式完成活動類型的活動建立步驟。

* [建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [建立體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [建立 Recommendations 活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## 培訓視頻：基於表單的作曲家 ![教程徽章](/help/main/assets/tutorial.png)

此影片提供表單式撰寫器的示範。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
