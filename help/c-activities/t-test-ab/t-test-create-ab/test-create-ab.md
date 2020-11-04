---
keywords: Create A/B;A/B test;A/B activity;new a/b activity;create a/b
description: 使用Adobe Target中的Visual Experience Composer，直接在啟用Target的頁面上建立A/B測試活動，並修改Target內頁面的部分。
title: 建立 A/B 測試
feature: ab
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 64%

---


# 建立 A/B 測試

Use the [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] to create your [!UICONTROL A/B Test] activity directly on a [!DNL Target]-enabled page and to modify portions of the page within [!DNL Target].

>[!NOTE]
>
>除了「手動（預設） [!UICONTROL A/B測試」活動(在本節中討論] )外， [!DNL Target] 還提供了兩種  A/B測試活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標]。
>
>請參 [閱A/B測試概觀中](/help/c-activities/t-test-ab/test-ab.md#types)*的A/B測試活動類型*。

要建立手動 [!UICONTROL A/B測試活動] :

1. 從&#x200B;**[!UICONTROL 「活動」]**&#x200B;清單，按一下&#x200B;**[!UICONTROL 「建立活動」]**>**[!UICONTROL 「A/B 測試」]**。

   ![建立活動下拉式清單](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 [!DNL Target] 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Recommendations] 是 [Target Premium 功能](/help/c-intro/intro.md#premium)。
   >
   >如需各種活動類型的相關資訊，請參閱[活動](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)和 [Target 活動指南](/help/c-activities/target-activities-guide.md)。

1. 視需要選取&#x200B;**[!UICONTROL 視覺 (預設)]**。

   ![建立A/B測試活動](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   If you prefer to use the [!UICONTROL Form-Based Experience Composer], select [!UICONTROL Form]. 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和表單型體 [!UICONTROL 驗撰寫器外], [!DNL Target] 還提供單頁應用程式VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上圖中的[!UICONTROL 選擇工作區](/help/administrating-target/c-user-management/property-channel/property-channel.md)選項是 [Target Premium](/help/c-intro/intro.md) 功能。Your organization has a [!UICONTROL Target Standard] license if you do not see this option.

1. (視條件而定) 如果您是 [Target Premium 客戶](/help/c-intro/intro.md#premium)，請選擇[工作區](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定[活動 URL](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然後按一下&#x200B;**[!UICONTROL 下一步]**。

   如果您的帳戶設定了預設的 URL，該 URL 依預設會顯示。您可以將預設 URL 變更為其他 URL。

   [!UICONTROL 「可視化體驗撰寫器」]隨即開啟，顯示 URL 中指定的頁面。

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 在提供的空間中輸入活動的名稱。

   ![名稱欄位](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

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

1. 建立任何新體驗，透過變更頁面上的元素。

   在您建立新增活動之後，[!UICONTROL 可視化體驗撰寫器]會在左邊顯示兩個標籤: 體驗 A 和體驗 B。體驗 A 為控制體驗。您的焦點會在體驗 B 標籤，您可以視需要加以修改。體驗 B 為您可以新增至您的測試的替代體驗。您可以對測試新增多個體驗。如果您不想要包括預設網站體驗作為選項，則也可以從活動刪除體驗 A。

   如需在[!UICONTROL 可視化體驗撰寫器]中新增和修改體驗的相關資訊，請參閱[新增體驗](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。若要修改體驗 B，請從步驟 3 開始。

1. 按一下&#x200B;**[!UICONTROL 可視化體驗撰寫器]**&#x200B;頂端的[!UICONTROL 鎖定目標]，以前往三步驟引導工作流程中的下一個步驟。

   流程圖表隨即開啟。

   ![A/B 測試鎖定目標步驟](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程圖表將引導您進行選擇活動對象和設定體驗的步驟。

1. 在「對 [!UICONTROL 像] 」方塊中，按一下編輯圖示（三個垂直的省略號），按一下「取代對象 **[!UICONTROL 」，然]**[](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) 後選取活動的對象。

   By default, the audience is set to [!UICONTROL All Visitors].

1. 選擇符合您要讓其進入活動之訪客的百分比。

   ![受眾百分比](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」觀眾的 45%。

1. 設定您的流量分配。

   您可以對相同對象顯示多個體驗。圖表顯示會顯示您選取的對象和新增至活動的體驗。

   選擇所需的流量分配方法:

   * **[!UICONTROL 手動 (預設)]**: 指定您希望在各體驗上看見的加入者百分比。您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。

   * **[!UICONTROL 自動分配至最佳體驗]**: 系統會自動將多數活動加入者導向表現較佳的體驗。有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。請參閱[自動流量分配](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL 自動鎖定個人化體驗]**: [!DNL Target] 使用進階的機器學習來識別多個高效能、行銷人員定義的體驗，以個人化內容並推動轉化，然後根據訪客的個人客戶個人檔案和類似訪客的過往行為，為訪客提供量身打造的體驗。 如需詳細資訊，請 [參閱自動定位](/help/c-activities/auto-target/auto-target-to-optimize.md)。
   You can also click **[!UICONTROL Add]** to add another experience to the activity.

1. When you are satisfied with your audience, experience choices, and traffic allocation choices, click **[!UICONTROL Next]** to move to the third step of the three-step guided workflow.

1. 指定活動的[目標與設定](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   ![A/B 活動設定](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. 按一 **[!UICONTROL 下「儲存並關閉]** 」或 **[!UICONTROL 「儲存]**」。

After you create the activity, the [!UICONTROL Overview] tab shows information about the activity, including a diagram of your activity.

## Training video: Creating A/B Tests (8:36) ![Tutorial badge](/help/assets/tutorial.png)

此影片示範如何使用 [!DNL Target] 三個步驟引導工作流程來建立 A/B 測試。

* 建立 [!UICONTROL A/B測試活動] ，位於 [!DNL Adobe Target]
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
