---
keywords: 建立A/B;A/Btest;A/B活動；新建a/b活動；建立a/b
description: 瞭解如何在Adobe中使用Visual Experience Composer(VEC) [!DNL Target] 直接在A/BTest上建立 [!DNL Target]-enabled頁。
title: 如何建立A/BTest?
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 61%

---

# 建立 A/B 測試

使用 [!UICONTROL 視覺體驗作曲家] (VEC) [!DNL Adobe Target] 建立 [!UICONTROL A/BTest] 直接在 [!DNL Target]-enabled頁面和修改頁面中的部分 [!DNL Target]。

>[!NOTE]
>
>除手冊（預設）外 [!UICONTROL A/BTest] 活動（在本節中討論）, [!DNL Target] 提供了另外兩種類型 [!UICONTROL A/BTest] 活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標]。
>
>請參閱 [A/B測試活動的類型](/help/main/c-activities/t-test-ab/test-ab.md#types) 在 *A/BTest概述*。

建立手動 [!UICONTROL A/BTest] 活動：

1. 從&#x200B;**[!UICONTROL 「活動」]**&#x200B;清單，按一下&#x200B;**[!UICONTROL 「建立活動」]**>**[!UICONTROL 「A/B 測試」]**。

   ![建立活動下拉式清單](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 [!DNL Target] 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Recommendations] 是 [Target Premium 功能](/help/main/c-intro/intro.md#premium)。
   >
   >如需各種活動類型的相關資訊，請參閱[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)和 [Target 活動指南](/help/main/c-activities/target-activities-guide.md)。

1. 視需要選取&#x200B;**[!UICONTROL 視覺 (預設)]**。

   ![建立A/BTest活動](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   如果你想用 [!UICONTROL 基於表單的體驗作曲家]選中 [!UICONTROL 窗體]。 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 基於表單的體驗作曲家]。 [!DNL Target] 提供了單頁應用程式VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上圖中的[[!UICONTROL 選擇工作區]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)選項是 [Target Premium](/help/main/c-intro/intro.md) 功能。您的組織 [!UICONTROL 目標標準] 的下界。

1. (視條件而定) 如果您是 [Target Premium 客戶](/help/main/c-intro/intro.md#premium)，請選擇[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定[活動 URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然後按一下&#x200B;**[!UICONTROL 下一步]**。

   如果您的帳戶設定了預設的 URL，該 URL 依預設會顯示。您可以將預設 URL 變更為其他 URL。

   [!UICONTROL 「可視化體驗撰寫器」]隨即開啟，顯示 URL 中指定的頁面。

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 在提供的空間中輸入活動的名稱。

   ![名稱欄位](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   活動名稱不能以下列任何字元開頭：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

1. 建立任何新體驗，透過變更頁面上的元素。

   在您建立新增活動之後，[!UICONTROL 可視化體驗撰寫器]會在左邊顯示兩個標籤: 體驗 A 和體驗 B。體驗 A 為控制體驗。您的焦點會在體驗 B 標籤，您可以視需要加以修改。體驗 B 為您可以新增至您的測試的替代體驗。您可以對測試新增多個體驗。如果您不想要包括預設網站體驗作為選項，則也可以從活動刪除體驗 A。

   如需在[!UICONTROL 可視化體驗撰寫器]中新增和修改體驗的相關資訊，請參閱[新增體驗](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。若要修改體驗 B，請從步驟 3 開始。

1. 按一下&#x200B;**[!UICONTROL 可視化體驗撰寫器]**&#x200B;頂端的[!UICONTROL 鎖定目標]，以前往三步驟引導工作流程中的下一個步驟。

   流程圖表隨即開啟。

   ![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程圖表將引導您進行選擇活動對象和設定體驗的步驟。

1. 在 [!UICONTROL 觀眾] 框中，按一下「編輯」表徵圖（三個垂直橢圓），按一下 **[!UICONTROL 替換受眾]**，則 [選擇受眾](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) 為您的活動。

   預設情況下，訪問群體設定為 [!UICONTROL 所有訪問者]。

1. 選擇符合您要讓其進入活動之訪客的百分比。

   ![受眾百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」觀眾的 45%。

1. 設定您的流量分配。

   您可以對相同對象顯示多個體驗。圖表顯示會顯示您選取的對象和新增至活動的體驗。

   選擇所需的流量分配方法:

   * **[!UICONTROL 手動 (預設)]**: 指定您希望在各體驗上看見的加入者百分比。您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。

   * **[!UICONTROL 自動分配至最佳體驗]**: 系統會自動將多數活動加入者導向表現較佳的體驗。有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。請參閱[自動流量分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL 個性化體驗的自動目標]**: [!DNL Target] 使用高級機器學習來通過識別多個高效能的商家定義體驗來個性化內容並推動轉換，然後根據訪問者的個人客戶資料和類似訪問者的過往行為為訪問者提供最定製的體驗。 有關詳細資訊，請參見 [自動目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
   也可以按一下 **[!UICONTROL 添加]** 以向活動添加其他體驗。

1. 如果您對受眾、體驗選擇和流量分配選擇感到滿意，請按一下 **[!UICONTROL 下一個]** 移到三步指導工作流的第三步。

1. 指定活動的[目標與設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   ![A/B 活動設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. 按一下 **[!UICONTROL 保存並關閉]** 或 **[!UICONTROL 保存]**。

建立活動後， [!UICONTROL 概述] 頁籤顯示有關活動的資訊，包括活動的圖。

## 培訓視頻：建立A/BTest(8:36) ![教程徽章](/help/main/assets/tutorial.png)

此影片示範如何使用 [!DNL Target] 三個步驟引導工作流程來建立 A/B 測試。

* 建立 [!UICONTROL A/BTest] 活動 [!DNL Adobe Target]
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
