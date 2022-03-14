---
keywords: 報表；阻止IP地址；阻止訪問者從IP地址；下載報表；csv;reports;block ip address;block visitor from ip address;download reports;reporting
description: 瞭解如何在Adobe中使用報告功能 [!DNL Target] 檢查活動的執行情況。 根據您的資料做出更好的決策，以提高ROI。
title: 如何查看報告？
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 62%

---

# 報告

報告提供有關您的 [!DNL Adobe Target] 幫助您根據資料做出決策的活動。 報告資料可以幫助您確定何時結束活動、向您顯示哪種服務體驗是贏家，並提供確定下一步操作所需的見解或學習。

## 顯示報告 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，然後從清單按一下需要的活動。

   如果您有許多活動，您可以利用從[!UICONTROL 「類型」]、[!UICONTROL 「狀態」]、[!UICONTROL 「報表來源」]、[!UICONTROL 「體驗撰寫器」]、[!UICONTROL 「量度類型」]和[!UICONTROL 「活動來源」]下拉式清單選取選項來篩選清單。

   例如，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「A/B 測試」]和[!UICONTROL 「體驗鎖定目標」]，並從[!UICONTROL 「狀態」]下拉式清單中選取[!UICONTROL 「上線」]，即可只顯示處於使用中狀態的 A/B 測試和「體驗鎖定目標」活動。

   下圖顯示的[!UICONTROL 「類型」]下拉式清單中已選取兩個類型: [!UICONTROL A/BTest] 和 [!UICONTROL 體驗目標]。 請注意，根據預設會選取三種類型 A/B 測試 (手動、[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)和[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md))。您可以視需要取消選取一或多個類型。

   ![依類型篩選報表](/help/main/c-reports/assets/report_filters-new.png)

1. 按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

   每一個報表都包含圖例來協助您瞭解報表。

   ![報表圖例](/help/main/c-reports/assets/report_menu_bar-new.png)

   圖例會顯示下列資訊:

   * 活動狀態，包括活動執行的日期範圍。
   * 的 [預計贏取經驗](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) （如果可用）。

   >[!NOTE]
   >
   >至少有一個加入者看過體驗之後，體驗結果才會出現。

1. (選用) 視需要[設定報表](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)。
1. (選用) [下載 CSV 格式的報表](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)，以便在 Excel 和其他工具中進行分析。

   可使用下列選項: 

   * [!UICONTROL 匯出報表至 CSV]
   * [!UICONTROL 匯出訂單詳細資料至 CSV]

1. (可選) 按一下&#x200B;**[!UICONTROL 「表格檢視」]**&#x200B;和&#x200B;**[!UICONTROL 「圖表檢視」]**&#x200B;圖示，以切換報表格式。

   ![表和圖形視圖表徵圖](/help/main/c-reports/assets/table-and-graph-icons.png)

   根據您選擇的報告類型，其他視圖和報告可能可用：

   | 報表類型 | 檢視 |
   | --- | --- |
   | [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 按一下 **[!UICONTROL 自動化段]** 或 **[!UICONTROL 重要屬性]** 表徵圖。<ul><li>的 [「 Automated Segments 」報告](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) 顯示不同訪問者對AP/AT活動中的服務/體驗的不同反應。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。</li><li>的 [重要屬性報告](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) 顯示在不同的活動中，不同的屬性對模型決定如何個性化更加重要（或更少）。 此報表顯示影響模型及其相對重要性的常見屬性。</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 除 [Automated Personalization摘要報告](/help/main/c-reports/reports-ap.md)，可按一下 **[!UICONTROL 自動化段]** 或 **[!UICONTROL 重要屬性]** 表徵圖。<ul><li>的 [「 Automated Segments 」報告](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) 顯示不同訪問者對AP/AT活動中的服務/體驗的不同反應。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。</li><li>的 [重要屬性報告](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) 如何在不同的活動中，不同的屬性對於模型決定如何個性化更加重要（或更少）。 此報表顯示影響模型及其相對重要性的常見屬性。</li></ul> |
   | [多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 除 [體驗績效報告](/help/main/c-reports/experience-performance-report.md)，可按一下 [地點貢獻](/help/main/c-reports/location-contribution-report.md) 表徵圖，以切換報表以按位置顯示貢獻。 |

## 特定活動類型的其他報告資訊 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

除了本主題及其子主題中的一般報表資訊以外，本指南其他部分提供專用於各活動類型的其他資訊:

| 活動類型 | 詳細資料 |
|--- |--- |
| [A/B 測試](/help/main/c-activities/t-test-ab/test-ab.md) | 若要瞭解提升度與可信度，以及 [!DNL Target] 中使用的統計方法，請參閱[計劃 A/B 測試](/help/main/c-activities/t-test-ab/sample-size-determination.md)。 |
| [解讀自動分配報告](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | 解釋 [!UICONTROL 自動分配] A/B活動，通過審查重要指標，包括提升和信心， [!DNL Target] UI。 |
| [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | AT 活動之[!UICONTROL 摘要]報表的相關資訊。如需詳細資訊，請參閱[自動鎖定目標摘要報表](/help/main/c-reports/auto-target-summary-report.md)。<br>AT 和 AP 活動之兩個[!UICONTROL 「個人化前瞻分析」]報表的相關資訊:[!UICONTROL 「自動化區段」]報表和[!UICONTROL 「重要屬性」]報表。如需詳細資訊，請參閱[個人化前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [](/help/main/c-activities/t-automated-personalization/automated-personalization.md)自動個人化 (AP) | AP 活動之兩個[!UICONTROL 「自動個人化摘要」]報表的相關資訊:[!UICONTROL 「活動層級」]報表和[!UICONTROL 「選件層級」]報表。如需詳細資訊，請參閱[自動個人化摘要報表](/help/main/c-reports/reports-ap.md)。<br>AT 和 AP 活動之兩個[!UICONTROL 「個人化前瞻分析」]報表的相關資訊:[!UICONTROL 「自動化區段」]報表和[!UICONTROL 「重要屬性」]報表。如需詳細資訊，請參閱[個人化前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | MVT 活動之兩個報表的相關資訊:[!UICONTROL 「體驗效能」]報表和[!UICONTROL 「位置貢獻」]報表。如需詳細資訊，請參閱[體驗效能報表](/help/main/c-reports/experience-performance-report.md) (MVT) 和[位置貢獻報表](/help/main/c-reports/location-contribution-report.md) (MVT)。 |
| [Adobe Analytics 作為 Adobe Target (A4T) 的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | 使用 [!DNL Adobe Analytics] 做為 [!DNL Target] 之報表來源的相關資訊。A4T 可讓您存取 [!DNL Target] 活動的 [!DNL Analytics] 報表。如需詳細資訊，請參閱 [Analytics for Target (A4T) 報表](/help/main/c-reports/analytics-for-target-a4t-reporting.md)。 |

## 阻止從指定的IP地址報告資料

您可封鎖來自特定 IP 位址的訪客，不計算在報表中。這對阻止來自內部訪問者的報告資料非常有用。

[請聯絡 Client Care 以設定 IP 過濾器。](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)此篩選在使用 [目標分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T)作為報告源。
