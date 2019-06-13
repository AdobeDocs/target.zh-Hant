---
description: 使用可視化體驗撰寫器在啟用 Target 的頁面上建立體驗鎖定目標活動，以及在 Target 內修改頁面的部分。
seo-description: 使用Visual Experience Composer在啓用Target的頁面上建立「體驗鎖定」活動，並修改Adobe Target中的部分頁面。
seo-title: 建立體驗鎖定目標活動
solution: Target
subtopic: 多變數測試
title: 建立體驗鎖定目標活動
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: f81d3ab49dc2cd01b4025f542d3174abf0a3c0d6

---


# 建立體驗鎖定目標活動{#create-an-experience-targeting-activity}

使用 [!UICONTROL Visual Experience Composer] (CMS)在啓用Target的頁面上建立 [!UICONTROL 體驗鎖定] (XT)活動，並修改內頁部分 [!DNL Adobe Target]。

1. 在[!UICONTROL 「活動」]清單中，按一下 **[!UICONTROL 「建立活動]** &gt; **[!UICONTROL 體驗鎖定目標」]**。

   ![建立活動&gt;體驗定位](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 Target 帳戶。有些活動類型可能不會出現在您的清單中。例如，「自動個人化」是 [Target Premium功能](/help/c-intro/intro.md#premium)。

   如需活動類型的相關資訊，請參閱 [活動](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) 和 [Target活動類型](/help/c-activities/target-activities-guide.md)。

1. 視需要選取 **[!UICONTROL Visual(預設)]**。

   ![「建立體驗定位活動」對話方塊](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   如果您偏好使用表單式體驗撰寫器，請選取該選項。請參閱[表單式體驗撰寫器](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html)。

   >[!NOTE]
   >
   >除了CMS和表單型Experience Composer，Target還提供單頁應用程式CMS和CMS for Mobile Apps。如需各種編譯器的詳細資訊，請參閱 [體驗和選件](/help/c-experiences/experiences.md)。

   如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)。

1. 指定 [您的活動URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然後按一下 **[!UICONTROL 「下一步」]**。

   如果您的帳戶設定了預設的 URL，該 URL 依預設會顯示。您可以將預設 URL 變更為其他 URL。

   「可視化體驗撰寫器」隨即開啟，顯示 URL 中指定的頁面。

   ![CMS中的體驗定位活動](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. 在提供的空間中輸入活動的名稱。

   ![名稱欄位](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   活動名稱中不允許下列字元:

   | 字元 | 說明 |
   |--- |--- |
   | `/` | 正斜線 |
   | `?` | 問號 |
   | `#` | 數字符號 |
   | `:` | 冒號 |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

1. [建立任何新體驗](../../../c-activities/t-experience-target/t-xt-create/xt-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)，透過變更頁面上的元素。



   依預設，可視化體驗撰寫器不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。如果您要能夠使用可視化體驗撰寫器來更改這些元素，則可以選擇停用 JavaScript。

   >[!NOTE]
   >
   >如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。

   將游標移至頁面上的元素時，元素會強調顯示。任何強調顯示的元素可以使用體驗撰寫器加以更改。

   如果您在使用 Target Classic (先前的 Test&amp;Target) 的頁面上建立 mbox，該 mbox 會以元素的形式出現並顯示 mbox 名稱，且可如同任何其他元素般加以修改。

   >[!NOTE]
   >
   >如果您從主要頁面以外的來源 (例如在 akamai.net 上託管並在 dell.com 上傳送的影像) 傳送影像，那麼該影像不會顯示在流程圖中所顯示頁面的縮圖中。

1. 按 **[!UICONTROL 「下一步」]**。

   流程圖表隨即開啟。

   ![](assets/xt_diagram.png)

   流程圖表將引導您進行選擇活動對象和設定體驗的步驟。
1. 將游標移至對象上，按一下顯示的 **[!UICONTROL 「編輯」]** 圖示 (三個垂直的點)，按一下 **[!UICONTROL 「變更對象」]**，然後選取您的活動中第一個體驗的對象。

   ![](assets/xt_change_audience.png)

   對象資料庫隨即顯示。對象資料庫包含先前已定義的對象，包括一些隨著 Target 預先建置的共通對象。您可以從資料庫選取對象，或是[建立新對象](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。若要對所有加入者顯示相同體驗，請選擇「所有訪客」。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

   建立觀眾時，您可以選取位置 (mbox) 並指定該位置的參數。在「自訂參數」下，選取 mbox，然後指定需要的參數。

   >[!NOTE]
   >
   >當您開啟對象清單時，系統會自動在背景匯入對象，且匯入的是登入超過 10 分鐘的對象。

   您可以按一下顯示的[!UICONTROL 「編輯」]圖示 (三個垂直的點)，然後按一下[!UICONTROL 「移除對象」]以移除現有對象。
1. 按一下 **[!UICONTROL 「新增體驗鎖定目標」]**。

   >[!NOTE]
   >
   >如果您要將體驗鎖定到某個對象，則必須先選取對象，才可以新增體驗。系統會出現訊息以提醒您選擇對象。

1. (選用) 按一下 **[!UICONTROL 「新增」]**，然後設定其他鎖定目標的體驗。

   ![](assets/xt_add_xt.png)

   完成此步驟時，請按一下 **[!UICONTROL 「繼續」]。**
1. 指定活動的[目標與設定](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

   ![](assets/xt_settings.png)

1. 按一下 **[!UICONTROL 「儲存並關閉」]**。
