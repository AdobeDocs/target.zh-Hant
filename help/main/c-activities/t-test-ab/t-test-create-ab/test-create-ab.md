---
keywords: 建立A/B； A/B測試； A/B活動；新a/b活動；建立a/b
description: 瞭解如何在Adobe [!DNL Target] 中使用視覺化體驗撰寫器(VEC)，直接在啟用 [!DNL Target]的頁面上建立您的A/B測試活動。
title: 如何建立A/B測試？
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: ec1041fd1823d1ab7f1af147af5825c3ae8662b5
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 35%

---

# 建立 A/B 測試

在[!DNL Adobe Target]中使用[!UICONTROL Visual Experience Composer] (VEC)直接在啟用[!DNL Target]的頁面上建立您的[!UICONTROL A/B Test]活動，以及在[!DNL Target]內修改頁面的部分。

>[!NOTE]
>
>除了手動（預設） [!UICONTROL A/B Test]活動（本文中討論）之外，[!DNL Target]還提供另外兩種型別的[!UICONTROL A/B Test]活動： [!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]。
>
>檢視&#x200B;*A/B測試總覽*&#x200B;中的[A/B測試活動型別](/help/main/c-activities/t-test-ab/test-ab.md#types)。

若要建立手動[!UICONTROL A/B Test]活動：

1. 從&#x200B;**[!UICONTROL Activities]**&#x200B;清單，按一下&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**。

   ![建立活動下拉式清單](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 [!DNL Target] 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Recommendations]是[Target Premium功能](/help/main/c-intro/intro.md#premium)。
   >
   >如需各種活動類型的相關資訊，請參閱[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)和 [Target 活動指南](/help/main/c-activities/target-activities-guide.md)。

1. 從「建立A/B測試活動」對話方塊中，視需要選取&#x200B;**[!UICONTROL Visual (Default)]**。

   如果您偏好使用[!UICONTROL Form-Based Experience Composer]，請選取[!UICONTROL Form]。 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]，[!DNL Target]還提供單頁應用程式VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （視條件而定）如果您是[Target Premium客戶](/help/main/c-intro/intro.md#premium)，請從&#x200B;**[!UICONTROL Choose Workspace]**&#x200B;下拉式清單中選擇[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   上圖中的[[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)選項是[Target Premium](/help/main/c-intro/intro.md)功能，如果您的組織有[!UICONTROL Target Standard]授權，則可能不會顯示。

1. 在&#x200B;**[!UICONTROL Enter Activity URL]**&#x200B;方塊中，指定您的[活動URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然後按一下&#x200B;**[!UICONTROL Create]**。

   如果您的帳戶[設定了預設的 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，該 URL 依預設會顯示。您可以視需要將預設URL變更為其他URL。

   [!UICONTROL Visual Experience Composer]隨即開啟，顯示URL中指定的頁面。

1. 按一下VEC頂端的&#x200B;**[!UICONTROL Untitled Activity]**，然後在提供的空間中指定活動的名稱。

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

1. 建立任何新體驗，透過變更頁面上的元素。

   建立新活動後，[!UICONTROL Visual Experience Composer]在左側顯示兩個標籤：體驗A和體驗B。體驗A是控制體驗。 您的焦點在體驗B索引標籤，您可以視需要修改它。 體驗B是可新增至測試的替代體驗。 您可以對測試新增多個體驗。如果您不想要包括預設網站體驗作為選項，則也可以從活動刪除體驗 A。

   如需在[!UICONTROL Visual Experience Composer]中新增及修改體驗的詳細資訊，請參閱[新增體驗](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。 若要修改體驗 B，請從步驟 2 開始。

1. 按一下[!UICONTROL Visual Experience Composer]頂端的&#x200B;**[!UICONTROL Targeting]**，以前往三步驟引導工作流程中的下一個步驟。

   流程圖表隨即開啟。

   ![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程圖表將引導您進行選擇活動對象和設定體驗的步驟。

1. 在&#x200B;**[!UICONTROL Audience]**&#x200B;方塊中，按一下編輯圖示（垂直省略符號），按一下&#x200B;**[!UICONTROL Replace Audience]**，然後[為您的活動選取對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)。

   依預設，對象會設為[!UICONTROL All Visitors]。

1. 選擇符合您要讓其進入活動之訪客的百分比。

   ![受眾百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」觀眾的 45%。

1. 設定您的流量分配。

   您可以對相同對象顯示多個體驗。系統會顯示圖表，顯示您選取的對象以及您新增至活動的體驗。

   選擇所需的流量分配方法:

   * **[!UICONTROL Manual (Default)]**：指定您希望在各體驗上看見的加入者百分比。 您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。

   * **[!UICONTROL Auto-allocate to best experience]**：系統會自動將多數活動加入者導向表現較佳的體驗。 有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。如需詳細資訊，請參閱[[!UICONTROL Auto-Allocate]總覽](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL Auto-target for personalized experiences]**： [!DNL Target]會使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。 如需詳細資訊，請參閱[自動鎖定目標總覽](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

   您也可以按一下「**[!UICONTROL Add]**」以新增其他體驗至活動。

1. 在您滿意您的對象、體驗選擇和流量配置選擇後，請按一下&#x200B;**[!UICONTROL Next]**&#x200B;以移至三步驟引導式工作流程的第三個步驟。

1. 指定活動的[目標與設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

1. 按一下&#x200B;**[!UICONTROL Save & Close]**&#x200B;或&#x200B;**[!UICONTROL Save]**。

建立活動後，[!UICONTROL Overview]索引標籤會顯示有關活動的資訊，包括活動的圖表。

## 訓練影片：建立A/B測試(8:36) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片示範如何使用 [!DNL Target] 三個步驟引導工作流程來建立 A/B 測試。

* 在[!DNL Adobe Target]中建立[!UICONTROL A/B Test]活動
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
