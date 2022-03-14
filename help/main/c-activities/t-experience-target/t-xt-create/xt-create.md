---
keywords: 體驗目標；xt;create
description: 瞭解如何在Adobe中使用Visual Experience Composer(VEC) [!DNL Target] 在啟用目標的頁面上建立「體驗目標」(XT)活動。
title: 如何建立針對活動的體驗？
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 89%

---

# 建立體驗鎖定目標活動

使用[!UICONTROL 可視化體驗撰寫器] (VEC) 在啟用 Target 的頁面上建立[!UICONTROL 體驗鎖定目標] (XT) 活動，以及在 [!DNL Adobe Target] 內修改頁面的部分。

體驗鎖定目標 (XT) 會根據一組市場行銷人員定義的規則和條件為特定對象提供內容。

體驗鎖定目標 (包括[地理定位](/help/main/c-target/c-audiences/c-target-rules/geo.md)) 對於定義將特定體驗或內容鎖定在特定對象的規則大有幫助。您可以在傳送不同內容變數至不同對象的活動中定義數個規則。

如需體驗鎖定目標、使用案例和訓練影片的詳細資訊，請參閱[體驗鎖定目標](/help/main/c-activities/t-experience-target/experience-target.md)。

**若要建立 XT 活動:**

1. 從[!UICONTROL 「活動」]清單，按一下&#x200B;**[!UICONTROL 「建立活動」]**>**[!UICONTROL 「體驗鎖定目標」]**。

   ![建立活動 > 體驗鎖定目標](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 Target 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Automated Personalization] 是 [Target Premium 功能](/help/main/c-intro/intro.md#premium)。
   >
   >如需有關 [!DNL Target] 提供的各種活動類型及其差異的詳細資訊，請參閱[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。請參閱[Target 活動類型](/help/main/c-activities/target-activities-guide.md)，協助您決定哪種活動類型最適合您的需求。

1. 視需要選取&#x200B;**[!UICONTROL 視覺 (預設)]**。

   ![建立體驗鎖定目標活動對話方塊](/help/main/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   如果您偏好使用表單式體驗撰寫器，請選取[!UICONTROL 「表單」]。如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了 VEC 和表單式體驗撰寫器之外，Target 還提供單頁應用程式 VEC 和適用於行動應用程式的 VEC。如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上圖中的[!UICONTROL 選擇工作區]選項是 [Target Premium](/help/main/c-intro/intro.md) 功能。如果您沒有看到此選項，表示您的組織擁有的是 Target Standard 授權。

1. (視條件而定) 如果您是 Target Premium 客戶，請[選擇工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定[活動 URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然後按一下&#x200B;**[!UICONTROL 下一步]**。

   如果您的帳戶[設定了預設的 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，該 URL 依預設會顯示。您可以視需要將預設 URL 變更為其他 URL。

   VEC 隨即開啟，顯示 URL 中指定的頁面。

   ![VEC 內的體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. 在提供的空間中輸入活動的名稱。

   ![名稱欄位](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   活動名稱不能以下列任何字元開頭：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

1. 建立目標鎖定於不同受眾的新體驗。

   如需逐步指示，請參閱[新增體驗](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)。

1. 指定活動的[目標與設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。
