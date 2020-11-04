---
keywords: Target;reports;report settings;preset;target preset;metric;audience;date range;settings;download;table view;graph view;average lift;lift;lift bound;confidence interval;confidence;location contribution;running average;counting methodology
description: 這些資訊可協助您設定要顯示在Adobe Target報表中的元素。 可以儲存報表設定以供稍後使用。
title: 報表設定
feature: report settings
uuid: c3463f0d-8f09-4be2-9c85-f933578cce50
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '1891'
ht-degree: 68%

---


# 報表設定{#report-settings}

Information to help you set the elements you want to appear in your report in [!DNL Adobe Target]. 可以儲存報表設定以供稍後使用。

若要顯示報表:

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，然後從清單按一下需要的活動。
1. 按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

   ![報表 UI](/help/c-reports/c-report-settings/assets/report_ui-new.png)

## Target 預設集 {#section_51F67341465045BEB4F1A2FB638A8EB1}

視需要設定個別活動報表後，您最多可以儲存十個不同的預設集 (量度、日期範圍、對象、進階設定等)。All [!DNL Target] users can display, edit, and delete the various presets, regardless of who created them.

您也可以視需要設定個別活動報表，然後將該設定儲存為預設/我的最愛預設集。檢視活動報表進展時就會顯示這個畫面。

### 建立預設集或預設預設集

1. 視需要設定活動的報表。

   可用的設定，包括量度、日期範圍、對象、進階設定等，說明如下。

1. 在 **[!UICONTROL Target 預設集]**&#x200B;旁邊，依序按下三個垂直的點圖示 > **[!UICONTROL 「另存新檔」]**。

   ![報表預設集](/help/c-reports/c-report-settings/assets/report_preset-new.png)

   隨即顯示「新的預設集」對話方塊:

   ![新預設集對話方塊](/help/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Review the information in the **[!UICONTROL Filters]** and **[!UICONTROL Settings]** sections to ensure that the report is configured as desired, then specify the **[!UICONTROL Preset Name]** (up to 50 characters).
1. (Conditional) If you want this to be your default/favorite report view, slide the **[!UICONTROL Set as default preset]** toggle to the On position.
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

### 選擇不同的預設集

從&#x200B;**[!UICONTROL 「Target 預設集」]**&#x200B;下拉式清單選取所需的預設集。

![預設集下拉式清單](/help/c-reports/c-report-settings/assets/report_preset_drop-down-new.png)

### 編輯預設集

1. 選取要編輯的預設集。
1. 視需要編輯報表設定 (量度、日期範圍、對象、進階設定等)。

   在編輯報表的設定後，按一下[!UICONTROL 「儲存」]，預設集名稱後面會顯示一個星號 ( * )，表示預設集已變更，如下所示:

   ![報表預設集 (含星號)](/help/c-reports/c-report-settings/assets/report_preset_asterisk-new.png)

1. 依序按下「三個垂直橢圓圖示 > **[!UICONTROL 另存新檔」]**&#x200B;以建立新預設集。

   或

   依序按下「三個垂直橢圓圖示 > **[!UICONTROL 更新」]**&#x200B;以更新目前的預設集。

   ![報表預設更新](/help/c-reports/c-report-settings/assets/report_preset_update-new.png)

### 刪除預設集

1. 選取要刪除的預設集。
1. 依序按下三個垂直的點 > **[!UICONTROL 「刪除」]**。

   ![報表預設刪除](/help/c-reports/c-report-settings/assets/report_preset_delete-new.png)

1. 再按一 **[!UICONTROL 下「刪除]** 」以確認刪除（已刪除的預設集無法復原）。

### 預設集錯誤處理

報表中的警示和訊息可讓您知道預設集是否無效。警示或訊息指示您選擇其他對象、量度、主機群組或體驗，以製作有效的預設集。

下表說明可能造成預設集變成無效的一些情況:

* 報表對象已從活動中移除，但在預設集定義中參照。
* 已刪除一或多個量度，但在預設集定義中參照。例如，您可以從活動中刪除一或多個量度，然後新增量度。
* 一或多個主機群組 (環境) 不存在，但在預設集定義中參照。
* 建立預設集之後，已刪除一或多個體驗，但在預設集定義中參照。
* 預設集的語意無效，因為轉介的實體仍然存在，但是預設集定義在語義上變更的方式已更新。例如，假設您最初建立名為「Revenue on Chrome」的預設集。之後更新活動以測量「轉換」量度，而非「收入」。此活動定義更新會在語義上使預設定義無效。

## 報表量度 {#section_894ABD7148244806B7CE556EBBA2AD62}

按一下&#x200B;**[!UICONTROL 「報表量度」]**&#x200B;下拉式清單，選取不同的[成功量度](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)或多個量度以顯示於圖表中。

依預設，主要量度是在您建立活動時於成功量度設定中決定。如果您變更設定並重新儲存活動，報表的主要量度會更新。

如需選取多個量度以便於報表中檢視的相關資訊，請參閱[在報表中檢視多個量度](../../c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7)。

## 對象 {#section_70926EB4618945D9AFF2B0564FF3717B}

按一下[!UICONTROL 「對象」]下拉式清單，以變更報表所顯示的對象。

如需詳細資訊，請參閱[對象](../../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)。

## 日期範圍 {#section_A410A768403C4E01891F95CB357E63ED}

「日期範圍」方塊會顯示報表的目前日期範圍。 按一下下拉式圖示以顯示可讓您變更報表日期範圍的日曆。

![日曆](/help/c-reports/c-report-settings/assets/date_range-new.png)

為報表選取新的&#x200B;**[!UICONTROL 「開始」]**&#x200B;和&#x200B;**[!UICONTROL 「結束」]**&#x200B;日期。You can also use the **[!UICONTROL From start of Activity]** and **[!UICONTROL Till end of Activity]** check boxes.

按一下&#x200B;**[!UICONTROL 「自訂日期」]**&#x200B;以選取預先定義的日期範圍: 最近 7 天、最近 15 天，或最近 30 天。這些預先定義的日期範圍是動態範圍。如果開始日期早於於所選天數，則日曆將顯示從開始日期開始的範圍，一旦開始日期變成晚於活動持續時間增加時選擇的天數，則會動態變更範圍。

報表具有下列日期限制:

* 報表的開始日期必須在最近兩年內。
* 優惠群組報表自今天起不得超過99天。
* 每小時報表限制為 15 天。

## 設定 {#section_D99CE462107D45CABE0960F820E1E972}

若要設定報表設定：

1. 按一下齒輪圖示，進行所需的變更（如下所述）。
1. 完成時，按一下&#x200B;**[!UICONTROL 「儲存」]**。

下圖顯示 A/B 活動的「設定」對話方塊:

![設定對話方塊](/help/c-reports/c-report-settings/assets/ab_settings_dialog-new.png)

視選取的活動類型而定，選項會有所不同:

### 計算方法

選擇所需的方法：

* 訪客
* 瀏覽次數
* 活動曝光次數

### 控制

選取計算和比較提升度時要使用的控制體驗。

### 環境

選擇要用於報告的環境（主機組）。 如需詳細資訊，請參閱[主機](../../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

### 重設報告資料

重設報告資料以移除舊資料。 目前的訪客將保留在活動中。This option is available only for those with [!UICONTROL Approver] permissions.

>[!IMPORTANT]
>
>此為永久性動作，無法還原。

### 排除極端值

The [!UICONTROL Exclude Extreme Values] toggle applies to activities with Revenue and Engagement metric types only. 如需詳細資訊，請參閱[排除極端訂單](../../c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

## 下載 {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Click the **[!UICONTROL Download]** icon to download report data in a [!DNL .csv] format for quick import into Excel, Access, or other data analysis programs.

![下載圖示](/help/c-reports/c-report-settings/assets/download-icon.png)

如需詳細資訊，請參閱[將資料下載為 CSV 檔案](../../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)。

## 重新整理 {#section_E203729F2F314DF3856D2EE67C60B370}

Click the **[!UICONTROL Refresh]** icon to refresh a report&#39;s table and graph view without refreshing the entire page, its configuration, or its date range.

## More options {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

按一下「更多選項」圖示 (三個垂直橢圓)，以存取[!UICONTROL 「編輯活動」]和[!UICONTROL 「檢視體驗 URL」]選項。

## 檢視選項

您可以根據活動類型，以各種格式檢視報表。 選擇所要的選項.

![檢視選項圖示](/help/c-reports/c-report-settings/assets/view-options.png)

* **表格檢視**:按一下「 **[!UICONTROL 表格檢視]** 」圖示，將報表檢視為表格。
* **圖形檢視**:按一下「 **[!UICONTROL 圖形檢視]** 」圖示，以圖形形式檢視報表。
* **自動化區段**:(僅適用於自動個人化(AP)和自動目標(AT)活動。) 按一下「**自動[!UICONTROL 化區段」圖示] ，以檢視「自 [動化區段」報表](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。
* **重要屬性**:(僅適用於自動個人化(AP)和自動目標(AT)活動。) 按一下**重要[!UICONTROL 屬性圖示] ，檢視重要 [屬性報表](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

## 平均提升度、提升度界限和信賴區間 {#section_0D87615B1D3344B3858BA494EEBC16FB}

報表包含數個資料點和視覺效果表示法，可表達與活動相關聯的提升度界限和信賴水準。這可協助您正準確地判斷獲勝者。

如需詳細資訊，請參閱[平均提升度、提升度界限和信賴區間](../../c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md#topic_AFFDC672A8A34D028B100EF6BE5D8129)。

考慮以下事項:

* 只有以「表格檢視」來檢視報表時才可用。
* 此功能無法供以[ Analytics 作為報表來源 (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) 的活動使用。

## 位置貢獻 {#section_5832F126AC114AE1ABFFF4D9B904393B}

按一下&#x200B;**[!UICONTROL 「位置貢獻」]**&#x200B;圖示，將報表切換為依位置來顯示貢獻。

## 體驗 {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

(只有在圖表檢視中檢視報表時才可供使用)

在圖表左側選取或取消選取體驗，以決定在圖表中顯示或隱藏相對應的體驗。

在下圖中，只有預設、中東和總計體驗會顯示在報表中。圖表中的亞洲體驗為隱藏狀態。

![體驗](/help/c-reports/c-report-settings/assets/report_experiences-new.png)

## 執行中的平均值 {#section_59066693158C4433B87D07402C2BC6CD}

(只有在圖表檢視中檢視報表時才可供使用)

「執行平均值」反映累積轉換（從報告視窗開始到圖形上所呈現的日期）除以累計訪客。

選取所需的圖表檢視:

* 執行中的平均值
* 執行中的平均值提升
* 每日
* 每日提升

![報表執行中的平均值](/help/c-reports/c-report-settings/assets/report_running_average-new.png)

此下拉式清單的名稱會視選取的檢視而有所不同，但會是上述其中一個檢視。

## 計算方法 {#section_01B0ED5665C74AE1AE97259800190C3E}

(只有在圖表檢視中檢視報表時才可供使用)

您可以為報表中的圖形選擇計算方法。Note that this is not supported for [!UICONTROL Automated Personalization] (AP) activities.

To access the [!UICONTROL Counting Methodology] option, while viewing a report in graph mode, click the **[!UICONTROL My Primary Goal]** drop-down, then select the counting methodology.

此計數方法與上述[!UICONTROL 「設定」]對話方塊中選取的方法相同。

![計算方法](/help/c-reports/c-report-settings/assets/counting_methodology_2-new.png)

依預設會以[!UICONTROL 「每日」]模式繪製圖表。

You can change the mode by clicking the [!UICONTROL Daily] drop-down list, then selecting a cumulative option.

![累積](/help/c-reports/c-report-settings/assets/counting_methodology-new.png)

>[!NOTE]
>
>此下拉式清單的名稱會依選取的模式而不同。

「自動鎖定目標」活動有四種模式: 每日控制、每日已鎖定目標、累積控制和累積目標。

圖表的預設繪製順序如下:

* **A/B測試（包括自動分配和自動個人化）**:體驗建立的順序，依遞減順序排列。
* **體驗定位(XT)**:活動中的體驗順序。
* **多變數測試(MVT)**:依體驗名稱依字母順序排列。
* **建議**:體驗建立的順序，依遞減順序排列。

使用計數方法選項時，請注意下列警告:

* For [Auto-Target activities](/help/c-activities/auto-target/auto-target-to-optimize.md), there is no option for selecting &quot;Visitors&quot; as the counting methodology. 「自動鎖定目標」是唯一無法依訪客來繪製的活動類型。
* For activities that use [Analytics as the reporting source (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md), you cannot plot Visitor, Visit, or Impression cumulatively.

## 使用活動中有超過16個體驗的圖形

如果活動的體驗少於 16 個，圖表中會以不同顏色繪製每一個體驗。

如果活動的體驗超過 16 個，圖表中會顯示前 16 個體驗的彩色線條。剩餘的體驗會在左側「體驗」窗格中呈現灰色，圖表中不會顯示對應的繪圖線條。任何時候都只能顯示 16 個體驗的線條。

如果暫留在灰色體驗上，對應於該體驗的新灰色繪圖線條會短暫出現在圖表中。若要以色彩顯示灰色體驗的繪圖線條，您可以對彩色顯示的體驗按一下名稱將它取消選取，然後對所需的灰色體驗按一下名稱來選取它。

舉例來說，下圖顯示活動的圖表有 26 個體驗:

![](assets/graph_1.png)

圖表會顯示前 16 個體驗 (部分重疊，所以看起來少於 16 條線)。在左側的體驗窗格中，每一個體驗名稱旁的彩色點會指出體驗的繪圖線條，以對應的顏色顯示。

如果您在體驗窗格中向下捲動，可看到第 17 個至第 26 個體驗的名稱變成灰色，如下圖所示:

![](assets/graph_2.png)

如果暫留在其中一個灰色體驗上，對應於該體驗的新灰色繪圖線條會短暫出現在圖表中。

假設您想顯示體驗 R 的繪圖線條，而不想看到體驗 P 的線條。您可以按一下體驗 P 的名稱將它取消選取，然後按一下體驗 R 的名稱來選取它，如下所示:

![](assets/graph_3.png)

