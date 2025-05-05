---
keywords: 表單式體驗撰寫器; 表單式撰寫器; 細分
description: 瞭解如何使用Adobe [!DNL Target] 表單式體驗撰寫器來建立非視覺體驗。 當VEC無法使用或不實用的情況下，使用此撰寫器。
title: 如何使用表單式體驗撰寫器？
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 33%

---

# 表單式體驗撰寫器

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]是非視覺化體驗和選件建立介面，當[!UICONTROL Visual Experience Composer] (VEC)無法使用或不實用的情況下，此介面有助於建立可在[!UICONTROL A/B Test]、[!UICONTROL Experience Targeting]、[!UICONTROL Automated Personalization]和[!UICONTROL Recommendations]活動中使用的體驗。 例如，您可以使用表單式體驗撰寫器，建立可在電子郵件、資訊站和語音助理中傳送的體驗和選件。

如果您正在建立[!UICONTROL Recommendations]活動，則沒有體驗。 選擇您的條件和設計。如果您選擇多個條件或設計，[!UICONTROL Target]會自動產生體驗。

1. 按一下&#x200B;**[!UICONTROL Create Activity]**，然後選取您要建立的活動型別。

   [!UICONTROL Form-Based Experience Composer]可用於[!UICONTROL A/B Test]、[!UICONTROL Experience Targeting]、[!UICONTROL Automated Personalization]和[!UICONTROL Recommendations]活動。

1. 從[!UICONTROL Create Activity]對話方塊中選取&#x200B;**[!UICONTROL Form]**。

1. （視條件而定）如果您是[Target Premium客戶](/help/main/c-intro/intro.md#premium)，請從&#x200B;**[!UICONTROL Choose Workspace]**&#x200B;下拉式清單中選擇[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)選項是[Target Premium](/help/main/c-intro/intro.md)功能，如果貴組織擁有[!UICONTROL Target Standard]授權，可能無法顯示。

1. 選擇屬性。

1. 按一下 **[!UICONTROL Create]**。

   [!UICONTROL Form-Based Experience Composer]隨即開啟。

   如果您要建立[!UICONTROL Recommendations]活動，此畫面會不同。 [!UICONTROL Recommendations]個活動不包含體驗。

1. &#x200B;
   1. 按一下&#x200B;**[!UICONTROL Rename]**&#x200B;圖示（![重新命名圖示](/help/main/assets/icons/MoreSmallListVert.svg)）、按一下&#x200B;**[!UICONTROL Rename]**、指定活動的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。

   活動名稱的開頭不能是下列任一字元：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

   活動名稱不能包含下列任一字元順序：

   | 字元順序 | 說明 |
   |--- |--- |
   | ；= | 分號，等於 |
   | ；+ | 分號，加號 |
   | ；- | 分號，減號 |
   | ；@ | 分號， At sign |
   | ，= | 逗號，等於 |
   | ，+ | 逗號，加號 |
   | ，- | 逗號，減號 |
   | ，@ | 逗號， At sign |
   | `[`&quot; | 左方括弧，雙引號 |
   | &quot;`]` | 雙引號，右方括弧 |

1. 選取位置。

   當您按一下「[!UICONTROL Select Location]」方塊時，會顯示可用位置清單。 選取其中一個位置。

   您也可以輸入此處未列出的位置。如果您尚未在頁面上建立或檢視 mbox，則此項目相當實用。輸入位置的名稱。輸入尚未存在的位置時請注意。如果拼字或大寫不符合進行 mbox 呼叫時使用的拼字或大寫，將不會傳送活動。手動輸入的位置會儲存至可用位置清單。 下次您嘗試選取手動輸入的位置時，將會從[!UICONTROL Select Location]下拉式清單中取得該活動的位置。

   >[!NOTE]
   >
   >在活動建立期間建立手動輸入的位置不會自動建立新位置。 位置名稱僅會儲存在活動內容中。 位置是在有內容傳遞呼叫時建立。 建立位置後，就可在其他活動、建立受眾等中使用了。 從可用位置的下拉式清單中選取。

1. 按一下&#x200B;**[!UICONTROL Add Audience Refinements]**，為此活動選擇一個或多個[對象](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)，然後按一下&#x200B;**[!UICONTROL Done]**。

   在[!UICONTROL Form-based Experience Composer]中，微調已取代為完整的對象功能。 現有活動的微調已移轉至[僅限於此活動的對象](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)。

1. 選取您要在該位置中顯示的內容類型。

1. 針對您選取的內容類型指定內容。

   **變更 HTML 產品建議:** 選擇 HTML 產品建議。

   **變更影像產品建議:** 選擇儲存在 Target 內容資料庫中的影像。

   您也可以新增連結至影像 (點進、目的地、登陸等等)。

   1. 按一下 [!UICONTROL Change Image Offer]。
   1. 選取想要的影像，然後按一下[!UICONTROL Edit Links]。
   1. 在您的網站上指定想要的URL或頁面，然後按一下[!UICONTROL Update]。

   **變更 JSON 產品建議:** 選擇 JSON 產品建議。

   **變更體驗片段：**&#x200B;選擇體驗片段。 如需詳細資訊，請參閱[體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

   **變更重新導向選件：**&#x200B;選擇重新導向選件。 如需詳細資訊，請參閱[建立重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

   **變更遠端選件：**&#x200B;選擇遠端選件。 如需詳細資訊，請參閱[建立遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

   **建立 HTML 產品建議:**

   1. 按一下「[!UICONTROL Offers]」，然後選取「[!UICONTROL Code Offers]」標籤。
   1. 按一下[!UICONTROL Create] > [!UICONTROL HTML Offer]。
   1. 輸入產品建議名稱。
   1. 在「程式碼」方塊中，輸入或貼上 HTML 程式碼。
   1. 按一下 [!UICONTROL Save]。

   **建立 JSON 產品建議:**

   1. 按一下「[!UICONTROL Offers]」，然後選取「[!UICONTROL Code Offers]」標籤。
   1. 按一下[!UICONTROL Create] > [!UICONTROL JSON Offer]。
   1. 輸入產品建議名稱。
   1. 在「程式碼」方塊中，輸入或貼上 JSON 程式碼。
   1. 按一下 [!UICONTROL Save]。

   **新增建議：**

   針對Recommendations活動，「內容」下拉式清單會提供[!UICONTROL Add Recommendation]選項。 按一下&#x200B;**[!UICONTROL Add Recommendation]**，然後選取頁面型別。 然後遵循介面中定義的步驟來[建立Recommendations 活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。

   在表單式體驗撰寫器選取「Recommendations」條件時，已有直接連結，可連結至選取的條件卡片，讓您輕鬆快速編輯條件。

   從[!DNL Target]三個步驟引導工作流程的[!UICONTROL Targeting]頁面：

   **新增優惠決定：**

   將在[!DNL Adobe Journey Optimizer] (AJO)中建立的選件新增至[!DNL Adobe Target]活動，以使用offer decisioning在您的網站或行動網站上向訪客呈現最佳動態選件和體驗。 此選項僅適用於手動[!UICONTROL A/B Test]和[!UICONTROL Experience Targeting] (XT)活動。

   如需詳細資訊，請參閱[使用優惠決定](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

1. （選擇性，適用於[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]和[!UICONTROL Experience Targeting]活動）若要對其他位置重複此程式，請按一下&#x200B;**[!UICONTROL Add Location]**&#x200B;並設定位置與內容。
1. 按一下&#x200B;**[!UICONTROL Next]**，然後照常對您的活動型別完成活動建立步驟。

* [建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [建立體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [建立建議活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## 訓練影片：表單式撰寫器![教學課程徽章](/help/main/assets/tutorial.png)

此影片提供表單式撰寫器的示範。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
