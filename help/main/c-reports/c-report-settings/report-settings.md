---
keywords: Target;報表;報表設定;預設集;target 預設集;量度;客群;日期範圍;設定;下載;表格檢視;圖表檢視;平均提升度;提升度;提升度界限;信賴區間;信賴;位置貢獻;執行中的平均值;計數方法
description: 瞭解如何在Adobe Target中設定報表設定，包括量度、對象、日期範圍等。
title: 如何設定報表設定？
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 48%

---

# 報表設定

可協助您設定要在[!DNL Adobe Target]的報表中顯示之元素的資訊。 可以儲存報表設定以供稍後使用。

若要顯示報表：

1. 按一下 **[!UICONTROL Activities]**，然後從清單按一下需要的活動。
1. 按一下「**[!UICONTROL Reports]**」標籤。

   ![報表 UI](/help/main/c-reports/c-report-settings/assets/report-ui-refresh.png)

## Target 預設集 {#section_51F67341465045BEB4F1A2FB638A8EB1}

視需要設定個別活動報表後，您最多可以儲存十個不同的預設集 (量度、日期範圍、對象、進階設定等)。所有[!DNL Target]使用者都可以顯示、編輯和刪除各種預設集，無論這些預設集的建立者為何。

您也可以視需要設定個別活動報表，然後將該設定儲存為預設/我的最愛預設集。檢視活動報表進展時就會顯示這個畫面。

### 建立預設集或預設的預設集

1. 視需要設定活動的報表。

   可用的設定（包括量度、日期範圍、對象、進階設定等）說明如下。

1. 在&#x200B;**[!UICONTROL Target Preset]**&#x200B;旁邊，按一下&#x200B;**[!UICONTROL More Options]** （![更多選項圖示](/help/main/assets/icons/MoreSmallListVert.svg) ）圖示> **[!UICONTROL Save as New]**。

   [!UICONTROL Create Preset]對話方塊隨即顯示。

   ![新預設集對話方塊](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. 請檢閱&#x200B;**[!UICONTROL Filters]**&#x200B;區段中的資訊，以確保根據需要設定報表，然後指定&#x200B;**[!UICONTROL Preset Name]** （最多50個字元）。
1. （視條件而定）如果您希望將此作為預設/我的最愛報表檢視，請滑動「**[!UICONTROL Set as default preset]**」切換至「開啟」位置。
1. 按一下 **[!UICONTROL Create]**。

### 選取其他預設集

從&#x200B;**[!UICONTROL Target Preset]**&#x200B;下拉式清單中選取所需的預設集。

### 編輯預設集

1. 選取要編輯的預設集。
1. 視需要編輯報表設定 (量度、日期範圍、對象、進階設定等)。

   在編輯報表的設定後按一下「[!UICONTROL Save]」，預設集名稱后面會顯示一個星號( &#42; )，表示預設集已變更。

1. 按一下&#x200B;**[!UICONTROL More Options]** （![更多選項圖示](/help/main/assets/icons/MoreSmallListVert.svg) ）圖示> **[!UICONTROL Save as New]**&#x200B;以建立新的預設集。

### 刪除預設集

1. 選取要刪除的預設集。
1. 按一下&#x200B;**[!UICONTROL More Options]** （![更多選項圖示](/help/main/assets/icons/MoreSmallListVert.svg) ）圖示> **[!UICONTROL Delete]**。

1. 再按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以確認刪除（已刪除的預設集無法復原）。

### 預設集錯誤處理

報表中的警示和訊息可讓您知道預設集是否無效。警示或訊息指示您選擇其他對象、量度、主機群組或體驗，以製作有效的預設集。

下表說明可能造成預設集變成無效的一些情況:

* 報表對象已從活動中移除，但在預設集定義中參照。
* 已刪除一或多個量度，但在預設集定義中參照。例如，您可以從活動中刪除一或多個量度，然後新增量度。
* 一或多個主機群組 (環境) 不存在，但在預設集定義中參照。
* 建立預設集之後，已刪除一或多個體驗，但在預設集定義中參照。
* 預設集的語意無效，因為轉介的實體仍然存在，但是預設集定義在語義上變更的方式已更新。例如，假設您最初建立名為「Revenue on Chrome」的預設集。之後更新活動以測量「轉換」量度，而非「收入」。此活動定義的更新會以語義方式讓預設集定義失效。

## [!UICONTROL Report Metric] {#section_894ABD7148244806B7CE556EBBA2AD62}

按一下&#x200B;**[!UICONTROL Report Metric]**&#x200B;下拉式清單，選取其他[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)或多個量度以顯示於圖表中。

依預設，主要量度是在您建立活動時於成功量度設定中決定。如果您變更設定並重新儲存活動，報表的主要量度會更新。

如需在報表中選取多個要檢視的量度的詳細資訊，請參閱[在報表中檢視多個量度](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7)。

## [!UICONTROL Audience] {#section_70926EB4618945D9AFF2B0564FF3717B}

按一下&#x200B;**[!UICONTROL Audience]**&#x200B;下拉式清單，以變更報表所顯示的對象。

如需詳細資訊，請參閱[客群](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)。

## [!UICONTROL Preset Date Range]

按一下&#x200B;**[!UICONTROL Preset Date Range]**&#x200B;下拉式清單，從預設日期範圍中選擇。

為報告選取新的&#x200B;**[!UICONTROL Start]**&#x200B;和&#x200B;**[!UICONTROL End]**&#x200B;日期。 您也可以使用&#x200B;**[!UICONTROL Start of Activity]**&#x200B;和&#x200B;**[!UICONTROL Start of activity - End of Activity]**&#x200B;範圍。

預先定義的日期範圍包括：最近7天、最近15天或最近30天。 這些預先定義的日期範圍是動態範圍。如果開始日期小於所選的天數，則行事曆會顯示從開始日期開始的範圍，但一旦開始日期超過所選的天數（隨著活動期間增加），行事曆就會滾動。

報表具有下列日期限制:

* 報表的開始日期必須在最近兩年內。
* 選件群組報表的上限為從今天起的99天。
* 每小時報表限制為 15 天。

## 日期範圍 {#section_A410A768403C4E01891F95CB357E63ED}

[!UICONTROL Date Range]方塊會顯示報表目前的日期範圍。 按一下&#x200B;**[!UICONTROL Calendar]** （ ![行事曆圖示](/help/main/assets/icons/Calendar.svg) ）圖示，即可顯示可讓您變更報表日期範圍的行事曆。

## 設定 {#section_D99CE462107D45CABE0960F820E1E972}

若要設定報表設定：

1. 按一下&#x200B;**[!UICONTROL Report Settings]** （![報表設定圖示](/help/main/assets/icons/Setting.svg) ）圖示，進行所需的變更（如下所述）。
1. 完成時，按一下&#x200B;**[!UICONTROL Save]**。

視選取的活動類型而定，選項會有所不同:

### 計算方法

選取所需的方法：

* 訪客
* 瀏覽次數
* 活動曝光次數

### 控制

選取計算及比較提升度時要使用的控制體驗。

### 環境 {#environment}

選取用於報表的環境（主機群組）。 如需詳細資訊，請參閱[主機](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

>[!NOTE]
>
>如果您的組織使用[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=zh-Hant){target=_blank} (AEP)將量度資料傳送至[!DNL Target]，則AEP Datastream中的環境應符合[!DNL Target]報告設定中的環境。

### 重設報告資料

按一下[!UICONTROL Reset Report Data]。 重設報表資料以移除舊資料。 目前的訪客會保留在活動中。  此選項僅適用於具有[!UICONTROL Approver]許可權的使用者。

>[!IMPORTANT]
>
>此為永久性動作，無法還原。

排除極端值

[!UICONTROL Exclude Extreme Values]切換僅適用於具有收入和參與量度型別的活動。 如需詳細資訊，請參閱[排除極端訂單](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

## 下載 {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

按一下「**[!UICONTROL Download]**」（「![下載」圖示](/help/main/assets/icons/Download.svg)）圖示，即可下載[!DNL .csv]格式的報表資料，以快速匯入至Excel、Access或其他資料分析程式。

如需詳細資訊，請參閱[將資料下載為 CSV 檔案](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)。

## 重新整理 {#section_E203729F2F314DF3856D2EE67C60B370}

按一下「**[!UICONTROL Refresh]**」（「![重新整理」圖示](/help/main/assets/icons/Refresh.svg)）圖示，重新整理報表的表格和圖形檢視，而不重新整理整個頁面、其設定或日期範圍。

## 更多選項 {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

按一下&#x200B;**[!UICONTROL More Options]**&#x200B;圖示（![更多選項圖示](/help/main/assets/icons/MoreSmallListVert.svg) ）以存取[!UICONTROL Save as New]和[!UICONTROL Delete]選項。

## 檢視選項

您可以根據活動型別，以各種格式檢視報表。 選取所需的選項。

* **表格檢視**：按一下&#x200B;**[!UICONTROL Table View]** （![表格檢檢視示](/help/main/assets/icons/Table.svg)）圖示，以表格形式檢視報表。
* **圖表檢視**：按一下&#x200B;**[!UICONTROL Graph View]** （![圖表檢檢視示](/help/main/assets/icons/GraphTrend.svg) ）圖示，以圖表形式檢視報表。
* **自動化區段**：(僅適用於[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target] (AT)活動。) 按一下**[!UICONTROL Automated Segments] （![自動化區段圖示](/help/main/assets/icons/AutomatedSegment.svg) ）圖示以檢視[自動化區段報表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。
* **重要屬性**： (僅適用於[!DNL Automated Personalization] (AP)和[!UICONTROL Auto-Target] (AT)活動。) 按一下&#x200B;**[!UICONTROL Important Attributes]** （![重要屬性圖示](/help/main/assets/icons/ViewList.svg) ）圖示以檢視[重要屬性報表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

## 平均提升度、提升度界限和信賴區間 {#section_0D87615B1D3344B3858BA494EEBC16FB}

報表包含數個資料點和視覺效果表示法，可表達與活動相關聯的提升度界限和信賴水準。這可協助您正準確地判斷獲勝者。

如需詳細資訊，請參閱[A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

考慮以下事項：

* 僅在[!UICONTROL Table View]中檢視報表時可用。
* 此功能無法供以[ Analytics 作為報表來源 (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 的活動使用。

## 位置貢獻 {#section_5832F126AC114AE1ABFFF4D9B904393B}

按一下[[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （ ![位置貢獻圖示](/help/main/assets/icons/LocationContribution.svg) ）圖示，將報表切換為依位置顯示多變數測試(MVT)活動的貢獻。

## 體驗 {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

僅在[!UICONTROL Graph View]中檢視報告時可用。

在圖表左側選取或取消選取體驗，以決定在圖表中顯示或隱藏相對應的體驗。

## 執行中的平均值 {#section_59066693158C4433B87D07402C2BC6CD}

僅在[!UICONTROL Graph View]中檢視報告時可用。

「執行中的平均值」反映了累積轉換（從報表回溯期開始到圖形上顯示的日期）除以累積訪客。

選取所需的圖表檢視:

* 執行中的平均值
* 執行中的平均值提升
* 每日
* 每日提升

此下拉式清單的名稱會依選取的檢視而不同，但一定是上述檢視之一。

## 計算方法 {#section_01B0ED5665C74AE1AE97259800190C3E}

僅在[!UICONTROL Graph View]中檢視報告時可用。

您可以為報表中的圖形選擇計算方法。請注意，[!UICONTROL Automated Personalization] (AP)活動不支援此功能。

若要存取[!UICONTROL Counting Methodology]選項，在以圖表模式檢視報表時，請按一下&#x200B;**[!UICONTROL My Primary Goal]**&#x200B;下拉式清單，然後選取計數方法。

此計數方法與上述[!UICONTROL Settings]對話方塊中選取的方法相同。

依預設，圖表是以[!UICONTROL Daily]模式繪製。

您可以按一下[!UICONTROL Daily]下拉式清單，然後選取累積選項來變更模式。

>[!NOTE]
>
>此下拉式清單的名稱會依選取的模式而不同。

[!UICONTROL Auto-Target]活動有四種模式： [!UICONTROL Daily Control]、[!UICONTROL Daily Targeted]、[!UICONTROL Cumulative Control]和[!UICONTROL Cumulative Targeted]。

圖表的預設繪製順序如下:

* **[!UICONTROL A/B Test]（包括[!UICONTROL Auto-Allocate]和[!UICONTROL Automated Personalization]）**：體驗建立的順序（以降序排列）。
* **[!UICONTROL Experience Targeting] (XT)**：活動中的體驗順序。
* **[!UICONTROL Multivariate Test] (MVT)**：依體驗名稱的字母順序。
* **[!UICONTROL Recommendations]**：體驗建立的順序（以降序排列）。

使用[!UICONTROL Counting Methodology]選項時，請考量下列警告：

* 針對[[!UICONTROL Auto-Target]活動](/help/main/c-activities/auto-target/auto-target-to-optimize.md)，沒有選項可選取「訪客」作為計數方法。 [!UICONTROL Auto-Target]是唯一您無法由訪客繪製的活動型別。
* 對於使用[Analytics做為報告來源(A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的活動，您無法累計繪製訪客、造訪或曝光數。

## 使用在活動中擁有超過16個體驗的圖表

如果活動的體驗少於 16 個，圖表中會以不同顏色繪製每一個體驗。

如果活動的體驗超過 16 個，圖表中會顯示前 16 個體驗的彩色線條。剩餘的體驗會在左側「體驗」窗格中呈現灰色，圖表中不會顯示對應的繪圖線條。任何時候都只能顯示 16 個體驗的線條。

如果暫留在灰色體驗上，對應於該體驗的新灰色繪圖線條會短暫出現在圖表中。若要以色彩顯示灰色體驗的繪圖線條，您可以對彩色顯示的體驗按一下名稱將它取消選取，然後對所需的灰色體驗按一下名稱來選取它。

圖表會顯示前 16 個體驗 (部分重疊，所以看起來少於 16 條線)。在左側的體驗窗格中，每一個體驗名稱旁的彩色點會指出體驗的繪圖線條，以對應的顏色顯示。

如果您在體驗窗格中向下捲動，可看到第 17 個至第 26 個體驗的名稱變成灰色，如下圖所示:

如果暫留在其中一個灰色體驗上，對應於該體驗的新灰色繪圖線條會短暫出現在圖表中。

假設您想顯示體驗 R 的繪圖線條，而不想看到體驗 P 的線條。您可以按一下體驗 P 的名稱將它取消選取，然後按一下體驗 R 的名稱來選取它，如下所示:
