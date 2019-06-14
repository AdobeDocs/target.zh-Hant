---
description: 使用可視化體驗撰寫器在啟用 Target 的頁面上建立體驗鎖定目標活動，以及在 Target 內修改頁面的部分。
seo-description: 使用Visual Experience Composer在啓用Target的頁面上建立體驗鎖定(XT)活動，並修改Adobe Target中的部分頁面。
seo-title: 建立體驗鎖定目標活動
solution: Target
subtopic: 多變數測試
title: 建立體驗鎖定目標活動
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: dcddbf8c1a4f406fdbfb00b9deaa75113aa7b624

---


# 建立體驗鎖定目標活動{#create-an-experience-targeting-activity}

使用 [!UICONTROL Visual Experience Composer] (CMS)在啓用Target的頁面上建立 [!UICONTROL 體驗鎖定] (XT)活動，並修改內頁部分 [!DNL Adobe Target]。

體驗鎖定目標 (XT) 會根據一組市場行銷人員定義的規則和條件為特定對象提供內容。

體驗定位(包括 [地理定位](/help/c-target/c-audiences/c-target-rules/geo.md))對於定義將特定體驗或內容鎖定特定對象的規則非常有價值。您可以在傳送不同內容變數至不同對象的活動中定義數個規則。

如需體驗定位、使用案例情境和訓練影片的詳細資訊，請參閱 [體驗定位](/help/c-activities/t-experience-target/experience-target.md)。

**若要建立XT活動：**

1. 在[!UICONTROL 「活動」]清單中，按一下 **[!UICONTROL 「建立活動]** &gt; **[!UICONTROL 體驗鎖定目標」]**。

   ![建立活動&gt;體驗定位](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 Target 帳戶。有些活動類型可能不會出現在您的清單中。例如 [!UICONTROL ，「自動個人化」] 是 [Target Premium功能](/help/c-intro/intro.md#premium)。
   >
   >如需各種活動類型及其差異的詳細 [!DNL Target] 資訊，請參閱 [活動](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。請參閱 [Target活動類型](/help/c-activities/target-activities-guide.md) ，以協助您決定哪個活動類型最適合您的需求。

1. 視需要選取 **[!UICONTROL Visual(預設)]**。

   ![「建立體驗定位活動」對話方塊](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   如果您偏好使用表單式體驗撰寫器，請選取該選項。請參閱[表單式體驗撰寫器](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html)。

   >[!NOTE]
   >
   >除了CMS和表單型Experience Composer，Target還提供單頁應用程式CMS和CMS for Mobile Apps。如需各種編譯器的詳細資訊，請參閱 [體驗和選件](/help/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)。

1. 指定 [您的活動URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然後按一下 **[!UICONTROL 「下一步」]**。

   如果您的帳戶 [設定為預設URL](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)，預設會顯示該URL。如有需要，您可以從預設變更為另一個URL。

   CMS隨即開啓，顯示URL中指定的頁面。

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

1. 建立目標受眾的新體驗。

   如需逐步指示，請參閱 [新增體驗](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)。

1. 指定活動的[目標與設定](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。