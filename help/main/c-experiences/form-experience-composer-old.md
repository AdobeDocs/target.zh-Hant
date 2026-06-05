---
keywords: 表單式體驗撰寫器; 表單式撰寫器; 細分
description: 瞭解如何使用Adobe [!DNL Target] 表單式體驗撰寫器來建立非視覺體驗。 當VEC無法使用或不實用的情況下，使用此撰寫器。
title: 如何使用表單式體驗撰寫器？
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 39%

---

# 表單式體驗撰寫器

[!DNL Adobe Target] [!UICONTROL 表單式體驗撰寫器]是一種非視覺化體驗和選件建立介面，適合在[!UICONTROL 視覺化體驗撰寫器] (VEC)無法使用或不實用的情況下，用於建立可供[!UICONTROL A/B測試]、[!UICONTROL 體驗鎖定目標]、[!UICONTROL Automated Personalization]和[!UICONTROL Recommendations]活動使用的體驗。 例如，您可以使用表單式體驗撰寫器，建立可在電子郵件、資訊站和語音助理中傳送的體驗和選件。

如果您正在建立[!UICONTROL Recommendations]活動，則沒有體驗。 選擇您的條件和設計。 如果您選擇多個條件或設計，[!UICONTROL Target]會自動產生體驗。

1. 按一下&#x200B;**[!UICONTROL 建立活動]**，然後選取您要建立的活動型別。

   [!UICONTROL 表單式體驗撰寫器]可用於[!UICONTROL A/B測試]、[!UICONTROL 體驗鎖定目標]、[!UICONTROL Automated Personalization]和[!UICONTROL Recommendations]活動。

1. 從[!UICONTROL 建立活動]對話方塊中選取&#x200B;**[!UICONTROL 表單]**。

1. （視條件而定）選擇工作區和屬性。

1. 按一下&#x200B;**[!UICONTROL 下一步]**。

   [!UICONTROL 表單式體驗撰寫器]開啟。

   ![location_refinements影像](assets/location_refinements.png)

   如果您要建立[!UICONTROL Recommendations]活動，此畫面會不同。 [!UICONTROL Recommendations]活動不包含體驗。

1. 按一下「[!UICONTROL 未命名活動]」以命名活動。
1. 選取位置。

   當您按一下[!UICONTROL 選取位置]方塊時，會顯示可用位置清單。 選取這些位置中的一個。

   您也可以輸入此處未列出的位置。 如果您尚未在頁面上建立或檢視 mbox，則此項目相當實用。 輸入位置的名稱。 輸入尚未存在的位置時請注意。 如果拼字或大寫不符合進行 mbox 呼叫時使用的拼字或大寫，將不會傳送活動。 手動輸入的位置會儲存至可用位置清單。 下次您嘗試選取手動輸入的位置時，將會從該活動的[!UICONTROL 選取位置]下拉式清單中取得該位置。

   >[!NOTE]
   >
   >在活動建立期間建立手動輸入的位置不會自動建立新位置。 位置名稱僅會儲存在活動內容中。 位置是在有內容傳遞呼叫時建立。 建立位置之後，就可在其他活動中使用，以便從可用位置的下拉式清單中建立對象等。

1. 按一下「新增對象細分」****，為此活動選擇一個或多個[對象](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)，然後按一下「完成」****。

   ![location_refinements_2圖片](assets/location_refinements_2.png)

   在[!UICONTROL 表單式體驗撰寫器]中，精簡已取代為完整的對象功能。 現有活動的微調已移轉至[僅限於此活動的對象](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)。

1. 選取您要在該位置中顯示的內容類型。

   ![form_content圖片](assets/form_content.png)

1. 針對您選取的內容類型指定內容。

   **變更 HTML 產品建議:** 選擇 HTML 產品建議。

   **變更影像產品建議:** 選擇儲存在 Target 內容資料庫中的影像。

   您也可以新增連結至影像 (點進、目的地、登陸等等)。

   1. 按一下[!UICONTROL 「變更影像選件」]。
   1. 選取需要的影像，然後按一下[!UICONTROL 「編輯連結」]。
   1. 指定您的網站上需要的 URL 或頁面，然後按一下[!UICONTROL 「更新」]。

   **變更 JSON 產品建議:** 選擇 JSON 產品建議。

   **變更體驗片段：**&#x200B;選擇體驗片段。 如需詳細資訊，請參閱[體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

   **變更重新導向選件：**&#x200B;選擇重新導向選件。 如需詳細資訊，請參閱[建立重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

   **變更遠端選件：**&#x200B;選擇遠端選件。 如需詳細資訊，請參閱[建立遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

   **建立 HTML 產品建議:**

   1. 按一下[!UICONTROL 「選件」]，然後選取[!UICONTROL 「代碼選件」]索引標籤。
   1. 按一下[!UICONTROL 建立] > [!UICONTROL HTML選件]。
   1. 輸入產品建議名稱。
   1. 在「程式碼」方塊中，輸入或貼上 HTML 程式碼。
   1. 按一下[!UICONTROL 「儲存」]。

   **建立 JSON 產品建議:**

   1. 按一下[!UICONTROL 「選件」]，然後選取[!UICONTROL 「代碼選件」]索引標籤。
   1. 按一下「[!UICONTROL 建立] > [!UICONTROL JSON 選件]」。
   1. 輸入產品建議名稱。
   1. 在「程式碼」方塊中，輸入或貼上 JSON 程式碼。
   1. 按一下[!UICONTROL 「儲存」]。

   **新增建議：**

   針對Recommendations活動，內容下拉式清單會提供[!UICONTROL 新增建議]選項。 按一下&#x200B;**[!UICONTROL 「新增建議」]**，然後選取頁面類型。 然後遵循介面中定義的步驟來[建立Recommendations 活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。

   在表單式體驗撰寫器選取「Recommendations」條件時，已有直接連結，可連結至選取的條件卡片，讓您輕鬆快速編輯條件。

   ![change_criteria影像](assets/change_criteria.png)

   在 Target 三步驟引導式工作流程的「鎖定目標」頁面:

   ![change_criteria_2圖片](assets/change_criteria_2.png)

   **新增優惠決定：**

   將在[!DNL Adobe Journey Optimizer] (AJO)中建立的選件新增至[!DNL Adobe Target]活動，以使用offer decisioning在您的網站或行動網站上向訪客呈現最佳動態選件和體驗。 此選項僅適用於手動[!UICONTROL A/B測試]和[!UICONTROL 體驗鎖定目標] (XT)活動。

   如需詳細資訊，請參閱[使用優惠決定](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

1. （選擇性，適用於[!UICONTROL A/B測試]、[!UICONTROL Automated Personalization]和[!UICONTROL 體驗鎖定目標]活動）若要對其他位置重複此程式，請按一下&#x200B;**[!UICONTROL 新增位置]**&#x200B;並設定位置與內容。
1. 按一下&#x200B;**[!UICONTROL 下一步]**，然後照常對您的活動型別完成活動建立步驟。

* [建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [建立體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [建立建議活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## 訓練影片：表單式撰寫器![教學課程徽章](/help/main/assets/tutorial.png)

此影片提供表單式撰寫器的示範。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
