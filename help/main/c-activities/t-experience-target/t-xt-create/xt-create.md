---
keywords: 體驗鎖定目標； XT；建立
description: 瞭解如何在 [!DNL Adobe Target] 中使用[!UICONTROL Visual Experience Composer] (VEC)來建立[!UICONTROL Experience Targeting] (XT)活動。
title: 如何建立[!UICONTROL Experience Targeting]活動？
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 4faafcef38d02674072d8b20ae03d3e2ef2115d6
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# 建立[!UICONTROL Experience Targeting] (XT)活動

使用[!UICONTROL Visual Experience Composer] (VEC)在啟用[!DNL Target]的頁面上建立[!UICONTROL Experience Targeting] (XT)活動，以及在[!DNL Adobe Target]內修改頁面的部分。

[!UICONTROL Experience Targeting] (XT)會根據一組行銷人員定義的規則和條件將內容提供給特定對象。

[!UICONTROL Experience Targeting] （包括[地理定位](/help/main/c-target/c-audiences/c-target-rules/geo.md)）對於定義將特定體驗或內容鎖定在特定對象的規則大有幫助。 您可以在傳送不同內容變數至不同客群的活動中定義數個規則。

如需[!UICONTROL Experience Targeting]、使用案例情境和訓練影片的詳細資訊，請參閱[體驗鎖定目標](/help/main/c-activities/t-experience-target/experience-target.md)。

**若要建立[!UICONTROL Experience Targeting]活動：**

1. 從[!UICONTROL Activities]清單，按一下&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL Experience Targeting]**。

   ![建立活動 > 體驗鎖定目標](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 [!DNL Target] 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Automated Personalization]是[Target Premium功能](/help/main/c-intro/intro.md#premium)。
   >
   >如需有關 [!DNL Target] 提供的各種活動類型及其差異的詳細資訊，請參閱[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。請參閱[Target 活動類型](/help/main/c-activities/target-activities-guide.md)，協助您決定哪種活動類型最適合您的需求。

1. 視需要選取&#x200B;**[!UICONTROL Visual (Default)]**。

   如果您偏好使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，請選取[!UICONTROL Form]。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]，[!DNL Target]還提供單頁應用程式VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如需VEC的疑難排解資訊，請參閱[疑難排解視覺化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （視條件而定）如果您是[!DNL Target Premium]客戶，[請選擇工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   [!UICONTROL Choose Workplace]選項是[Target Premium](/help/main/c-intro/intro.md)功能。 如果您沒有看到此選項，表示貴組織擁有[!DNL Target Standard]授權。

1. 指定您的[活動URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然後按一下&#x200B;**[!UICONTROL Create]**。

   如果您的帳戶[設定了預設的 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，該 URL 依預設會顯示。您可以視需要將預設 URL 變更為其他 URL。

   VEC 隨即開啟，顯示 URL 中指定的頁面。

   ![VEC 內的體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. 在提供的空間中輸入活動的名稱。

   ![名稱欄位](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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

1. 建立鎖定在不同對象的新體驗。

   如需逐步指示，請參閱[新增體驗](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)。

1. 指定活動的[目標與設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。
