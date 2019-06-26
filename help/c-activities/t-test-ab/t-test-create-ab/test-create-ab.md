---
description: 使用 Target 中的可視化體驗撰寫器直接在啟用 Target 的頁面上建立您的測試，以及在 Target 內修改頁面的部分。
keywords: 建立 A/B; A/B 測試; A/B 活動; 新 a/b 活動
seo-description: 使用 Target 中的可視化體驗撰寫器直接在啟用 Target 的頁面上建立您的測試，以及在 Target 內修改頁面的部分。
seo-title: 建立 A/B 測試
solution: Target
title: 建立 A/B 測試
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 建立 A/B 測試{#create-an-a-b-test}

使用 Target 中的可視化體驗撰寫器直接在啟用 Target 的頁面上建立您的測試，以及在 Target 內修改頁面的部分。

1. 在[!UICONTROL 「活動」]清單中，按一下 **[!UICONTROL 「建立活動]** &gt; **[!UICONTROL A/B 測試」]**。

   ![「建立活動」下拉式清單](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 [!DNL Target] 帳戶。有些活動類型可能不會出現在您的清單中。[!UICONTROL 例如，Recommendations] 是 [Target Premium功能](/help/c-intro/intro.md#premium)。
   >
   >For information about the various activity types, see [Activities](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) and the [Target activities guide](/help/c-activities/target-activities-guide.md).

   ![建立A/B測試](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   如果您偏好使用表單式體驗撰寫器，請選取[!UICONTROL 「表單」]。See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >除了CMS和表單型Experience Composer，Target還提供單頁應用程式CMS和CMS for Mobile Apps。For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >The [!UICONTROL [Choose Workplace](/help/administrating-target/c-user-management/property-channel/property-channel.md) option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. 如果您未看見此選項，則您的組織有Target Standard授權。]

1. (條件性)如果您是Target Premium客戶，請選擇工作區。

1. Specify your [activity URL](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), then click **[!UICONTROL Next]**.

   如果您的帳戶設定了預設的 URL，該 URL 依預設會顯示。您可以將預設 URL 變更為其他 URL。

   [!UICONTROL 「可視化體驗撰寫器」]隨即開啟，顯示 URL 中指定的頁面。

   ![CMS](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

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

1. Click **[!UICONTROL Targeting]** at the top of the [!UICONTROL Visual Experience Composer] to move to the next step in the three-step guided workflow.

   流程圖表隨即開啟。

   ![A/B測試定位步驟](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程圖表將引導您進行選擇活動對象和設定體驗的步驟。
1. 在[!UICONTROL 「對象」]方塊中，按一下編輯圖示，然後為您的活動[選取對象](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087)。

   依預設，對象會設為「所有訪客」。

1. 選擇符合您要讓其進入活動之訪客的百分比。

   ![讀者百分比](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」觀眾的 45%。

1. 設定您的流量分配。

   您可以對相同對象顯示多個體驗。圖表顯示會顯示您選取的對象和新增至活動的體驗。

   選擇您所需的流量分配方法：

   * **[!UICONTROL 手冊(預設)]**：指定您要查看每個體驗的數目百分比。您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。

   * **[!UICONTROL 自動分配給最佳體驗]**：大部分活動活動都會自動導向至高效能體驗。有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。請參閱[自動流量分配](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL 自動定位個人化體驗]**：Target使用進階機器學習演算法自動鎖定訪客，以最大化您的目標。如需詳細資訊，請參閱[自動鎖定目標以最佳化](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)。
   您也可以按一下 **[!UICONTROL 「新增體驗」]，以新增其他體驗至活動。**

1. 在您滿意您的對象和體驗選擇後，請按 **[!UICONTROL 「下一步」]** 以前往三步驟引導工作流程中的第三個步驟。

1. 指定活動的[目標與設定](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

   ![A/B活動設定](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. 按一下 **[!UICONTROL 「儲存」]**。

建立活動之後，「概覽」標籤會顯示關於活動的資訊，包括活動的圖表。

## 訓練影片: 建立 A/B 測試 (8:36)

此影片示範如何使用 [!DNL Target] 三個步驟引導工作流程來建立 A/B 測試。

* 在 Adobe Target 中建立 A/B 活動
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391?captions=chi_hant)
