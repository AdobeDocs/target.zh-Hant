---
description: 表單式體驗撰寫器提供非視覺的體驗建立。
keywords: 表單式體驗撰寫器; 表單式撰寫器; 細分
seo-description: 表單式體驗撰寫器提供非視覺的體驗建立。
seo-title: 表單式體驗撰寫器
solution: Target
title: 表單式體驗撰寫器
topic: Standard
uuid: 6791ed6f-69d0-4ec4-9ea4-47aa92b2a4c9
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 表單式體驗撰寫器{#form-based-experience-composer}

表單式體驗撰寫器提供非視覺的體驗建立。

此功能可讓 Target Standard A/B 測試、體驗鎖定目標、自動個人化和 Recommendations 活動在電子郵件、行動應用程式、資訊站和使用可視化體驗撰寫器無法運作的其他位置中傳送。

如果是建立 Recommendations 活動，則沒有體驗。選擇您的條件和設計。如果您選擇多個條件或設計，Target 會自動產生體驗。

1. 按一下**[!UICONTROL 「建立活動」]**，然後選取您要建立的活動類型。

   表單式體驗撰寫器可用於 A/B 測試、體驗鎖定目標、自動個人化和 Recommendations 活動。
1. 從[!UICONTROL 「新增活動」]對話方塊選取**[!UICONTROL 「表單式體驗撰寫器」]**。

   表單式體驗撰寫器隨即開啟。

   ![](assets/location_refinements.png)

   如果您要建立 Recommendations 活動，則此畫面會不同。Recommendations 活動未包括體驗。
1. 為活動命名。
1. 選取位置。

   在「選取位置」方塊中按一下時，會出現可用位置的清單。選取這些位置中的一個。若要選擇透過 target.js 提供的全域位置，請選擇「target-global-mbox」。

   您也可以輸入此處未列出的位置。如果您尚未在頁面上建立或檢視 mbox，則此項目相當實用。輸入位置的名稱。輸入尚未存在的位置時請注意。如果拼字或大寫不符合進行 mbox 呼叫時使用的拼字或大寫，將不會傳送活動。手動輸入的位置會儲存至清單。
1. 按一下**[!UICONTROL 「新增對象細分」]**，然後選擇一或多個此活動的[對象](../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)。

   ![](assets/location_refinements_2.png)

   在表單式體驗撰寫器中，細分已由完整的對象功能取代。現有活動的細分已移轉至[僅限於此活動的對象](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)。
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

   **變更體驗片段:** 選擇體驗片段。

   **變更重新導向選件:** 選擇重新導向選件。

   **變更遠端選件:** 選擇遠端選件。

   **建立 HTML 選件:**

   1. 按一下[!UICONTROL 「選件」]，然後選取[!UICONTROL 「代碼選件」]索引標籤。
   1. 按一下[!UICONTROL 「建立] &gt; [!UICONTROL HTML 選件」]。
   1. 輸入選件名稱。
   1. 在「程式碼」方塊中，輸入或貼上 HTML 程式碼。
   1. 按一下[!UICONTROL 「儲存」]。
   **建立 JSON 選件:**

   1. 按一下[!UICONTROL 「選件」]，然後選取[!UICONTROL 「代碼選件」]索引標籤。
   1. 按一下「[!UICONTROL 建立] &gt; [!UICONTROL JSON 選件]」。
   1. 輸入選件名稱。
   1. 在「程式碼」方塊中，輸入或貼上 JSON 程式碼。
   1. 按一下[!UICONTROL 「儲存」]。
   針對 Recommendations 活動，內容下拉式清單會提供您「新增建議」選項。按一下**[!UICONTROL 「新增建議」]**，然後選取頁面類型。然後遵循介面中定義的步驟來[建立Recommendations 活動](https://marketing.adobe.com/resources/help/en_US/target/recs/t_create_recs_activity.html)。

   在表單式體驗撰寫器選取「Recommendations」條件時，已有直接連結，可連結至選取的條件卡片，讓您輕鬆快速編輯條件。

   ![](assets/change_criteria.png)

   在 Target 三步驟引導式工作流程的「鎖定目標」頁面:

   ![](assets/change_criteria_2.png)

1. (選用，適用於 AB 活動、自動個人化和體驗鎖定目標) 若要對其他位置重複此程序，請按一下「`Add Location`」，然後設定位置與內容。
1. 按一下**[!UICONTROL 「繼續」]**，然後照常對您的活動類型完成活動建立步驟。

* [建立 A/B 測試](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
* [建立體驗鎖定目標活動](../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [建立 Recommendations 活動](../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## 訓練影片: 表單式撰寫器

此影片提供表單式撰寫器的示範。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)