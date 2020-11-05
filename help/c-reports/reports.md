---
keywords: reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: 報表提供Adobe Target活動效能的相關資訊
title: 報表
feature: reports
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 64%

---


# 報表{#reports}

Reports provide information about the progress and results of your [!DNL Adobe Target] activities that help you make decisions based on your data. 報表資料可協助您決定何時結束活動、顯示哪個選件體驗是贏家，並提供您確定下一個動作所需的見解或學習。

## 顯示報表 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，然後從清單按一下需要的活動。

   如果您有許多活動，您可以利用從[!UICONTROL 「類型」]、[!UICONTROL 「狀態」]、[!UICONTROL 「報表來源」]、[!UICONTROL 「體驗撰寫器」]、[!UICONTROL 「量度類型」]和[!UICONTROL 「活動來源」]下拉式清單選取選項來篩選清單。

   例如，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「A/B 測試」]和[!UICONTROL 「體驗鎖定目標」]，並從[!UICONTROL 「狀態」]下拉式清單中選取[!UICONTROL 「上線」]，即可只顯示處於使用中狀態的 A/B 測試和「體驗鎖定目標」活動。

   下圖顯示的[!UICONTROL 「類型」]下拉式清單中已選取兩個類型: [!UICONTROL A/B Test] and [!UICONTROL Experience Targeting]. 請注意，根據預設會選取三種類型 A/B 測試 (手動、[自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)和[自動鎖定目標](/help/c-activities/auto-target/auto-target-to-optimize.md))。您可以視需要取消選取一或多個類型。

   ![依類型篩選報表](/help/c-reports/assets/report_filters-new.png)

1. 按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

   每一個報表都包含圖例來協助您瞭解報表。

   ![報表圖例](/help/c-reports/assets/report_menu_bar-new.png)

   圖例會顯示下列資訊:

   * 活動狀態，包括活動執行的日期範圍。
   * The [projected winning experience](/help/c-activities/automated-traffic-allocation/determine-winner.md) (if available).

   >[!NOTE]
   >
   >至少有一個加入者看過體驗之後，體驗結果才會出現。

1. (選用) 視需要[設定報表](/help/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)。
1. (選用) [下載 CSV 格式的報表](/help/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)，以便在 Excel 和其他工具中進行分析。

   可使用下列選項: 

   * [!UICONTROL 匯出報表至 CSV]
   * [!UICONTROL 匯出訂單詳細資料至 CSV]

1. (可選) 按一下&#x200B;**[!UICONTROL 「表格檢視」]**&#x200B;和&#x200B;**[!UICONTROL 「圖表檢視」]**&#x200B;圖示，以切換報表格式。

   ![表格和圖形檢視圖示](/help/c-reports/assets/table-and-graph-icons.png)

   視您選取的報表類型而定，其他檢視和報表可能可用：

   | 報表類型 | 檢視 |
   | --- | --- |
   | [自動鎖定目標](/help/c-activities/auto-target/auto-target-to-optimize.md) | 按一下「 **[!UICONTROL 自動化區段]** 」或「 **[!UICONTROL 重要屬性]** 」圖示。<ul><li>The [Automated Segments report](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) shows how different visitors respond differently to the offers/experiences in your AP/AT activity. 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) shows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. 此報表顯示影響模型及其相對重要性的常見屬性。</li></ul> |
   | [](/help/c-activities/t-automated-personalization/automated-personalization.md)自動個人化 (AP) | 除了「自動個人化 [摘要」報表](/help/c-reports/reports-ap.md)，您還可以按一下「自動化區段 **[!UICONTROL 」或「重]** 要屬性 **** 」圖示。<ul><li>The [Automated Segments report](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) shows how different visitors respond differently to the offers/experiences in your AP/AT activity. 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) hows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. 此報表顯示影響模型及其相對重要性的常見屬性。</li></ul> |
   | [多變數測試](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 除了「體驗效 [能」報表](/help/c-reports/experience-performance-report.md)，您還可以按一下「位置貢獻 [](/help/c-reports/location-contribution-report.md) 」圖示，以切換報表，依位置顯示貢獻。 |

## Additional reporting information for specific activity types {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

除了本主題及其子主題中的一般報表資訊以外，本指南其他部分提供專用於各活動類型的其他資訊:

| 活動類型 | 詳細資料 |
|--- |--- |
| [A/B 測試](/help/c-activities/t-test-ab/test-ab.md) | 若要瞭解提升度與可信度，以及 [!DNL Target] 中使用的統計方法，請參閱[計劃 A/B 測試](/help/c-activities/t-test-ab/sample-size-determination.md)。 |
| [解譯自動分配報表](/help/c-activities/automated-traffic-allocation/determine-winner.md) | 在UI中檢查重要 [!UICONTROL 指標（包括提升度和信賴度），以解譯「自動分配] A/B」活動的 [!DNL Target] 結果。 |
| [自動鎖定目標](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT) | AT 活動之[!UICONTROL 摘要]報表的相關資訊。如需詳細資訊，請參閱[自動鎖定目標摘要報表](/help/c-reports/auto-target-summary-report.md)。<br>AT 和 AP 活動之兩個[!UICONTROL 「個人化前瞻分析」]報表的相關資訊:[!UICONTROL 「自動化區段」]報表和[!UICONTROL 「重要屬性」]報表。如需詳細資訊，請參閱[個人化前瞻分析報表](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [](/help/c-activities/t-automated-personalization/automated-personalization.md)自動個人化 (AP) | AP 活動之兩個[!UICONTROL 「自動個人化摘要」]報表的相關資訊:[!UICONTROL 「活動層級」]報表和[!UICONTROL 「選件層級」]報表。如需詳細資訊，請參閱[自動個人化摘要報表](/help/c-reports/reports-ap.md)。<br>AT 和 AP 活動之兩個[!UICONTROL 「個人化前瞻分析」]報表的相關資訊:[!UICONTROL 「自動化區段」]報表和[!UICONTROL 「重要屬性」]報表。如需詳細資訊，請參閱[個人化前瞻分析報表](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [多變數測試](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | MVT 活動之兩個報表的相關資訊:[!UICONTROL 「體驗效能」]報表和[!UICONTROL 「位置貢獻」]報表。如需詳細資訊，請參閱[體驗效能報表](/help/c-reports/experience-performance-report.md) (MVT) 和[位置貢獻報表](/help/c-reports/location-contribution-report.md) (MVT)。 |
| [Adobe Analytics 作為 Adobe Target (A4T) 的報表來源](/help/c-integrating-target-with-mac/a4t/a4t.md) | 使用 [!DNL Adobe Analytics] 做為 [!DNL Target] 之報表來源的相關資訊。A4T 可讓您存取 [!DNL Target] 活動的 [!DNL Analytics] 報表。如需詳細資訊，請參閱 [Analytics for Target (A4T) 報表](/help/c-reports/analytics-for-target-a4t-reporting.md)。 |

## 從指定的IP位址封鎖報告資料

您可封鎖來自特定 IP 位址的訪客，不計算在報表中。例如，這有助於封鎖來自內部訪客的報告資料。

[請聯絡 Client Care 以設定 IP 過濾器。](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)當使用Analytics for Target [](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T)做為報表來源時，此篩選不適用。
