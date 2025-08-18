---
keywords: 報表；封鎖ip位址；封鎖來自ip位址的訪客；下載報表；csv；報表
description: 精通 [!DNL Adobe Target]的報告功能以最佳化您的活動，進而增強決策能力並提高ROI。
title: 如何檢視報表？
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: bd65cb9339dbe4b79d26c314cfb81d1fc7226fd2
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 26%

---

# 報告

報表提供有關[!DNL Adobe Target]活動進度和結果的資訊，可協助您根據資料進行決策。 報表資料可協助您決定要在何時終止活動、顯示哪個體驗或選件是獲勝者，以及提供判斷後續動作所需的前瞻分析或經驗談。

## 顯示報表 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 按一下 **[!UICONTROL Activities]**，然後從清單按一下需要的活動。

   如果您有許多活動，可以按一下「篩選」圖示（ ![篩選圖示](/help/main/assets/icons/Filter.svg) ）來篩選清單，方法是從[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、[!UICONTROL Decisioning Method]和[!UICONTROL Activity Source]清單中選取選項。

   例如，您可以從[!UICONTROL A/B Test]下拉式清單中選取[!UICONTROL Experience Targeting]和[!UICONTROL Type]，以及從[!UICONTROL Live]下拉式清單中選取[!UICONTROL Status]，以僅顯示處於作用中狀態的[!UICONTROL A/B Test]和[!UICONTROL Experience Targeting]活動。

   下圖顯示已選取兩種型別的[!UICONTROL Type]下拉式清單： [!UICONTROL A/B Test]和[!UICONTROL Experience Targeting]。 請注意，根據預設會選取三種類型 A/B 測試 (手動、[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)和[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md))。您可以視需要取消選取一或多個類型。

   ![依類型篩選報表](/help/main/c-reports/assets/report-filters-refresh.png)

1. 從清單中按一下所需的活動以顯示其[!UICONTROL Overview]頁面。

1. 按一下左側邊欄中的&#x200B;**[!UICONTROL Reports]**&#x200B;索引標籤。

   ![A/B報告](/help/main/c-reports/assets/reports-refresh.png)

   每一個報表都包含圖例來協助您瞭解報表。

   圖例會顯示下列資訊:

   * 活動狀態，包括活動執行的日期範圍。
   * [預計的獲勝體驗](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) （如果有的話）。

   >[!NOTE]
   >
   >至少有一個加入者看過體驗之後，體驗結果才會出現。

1. （選擇性） [按一下「報表設定」圖示（](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)報表設定圖示![）來設定報表](/help/main/assets/icons/Setting.svg)。
1. （選擇性）按一下「下載報表」圖示（![下載報表圖示](/help/main/assets/icons/Download.svg)）以[下載CSV格式的報告](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)，以便在Excel和其他工具中進行分析。

   可使用下列選項: 

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. （選擇性）按一下&#x200B;**[!UICONTROL Table View]** （![表格檢檢視示](/help/main/assets/icons/Table.svg) ）和&#x200B;**[!UICONTROL Graph View]** （![圖表檢檢視示](/help/main/assets/icons/GraphTrend.svg) ）圖示，以切換報表格式。

   根據您選取的報表型別，可能提供其他檢視和報表：

   | 報表類型 | 檢視 |
   | --- | --- |
   | [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 按一下&#x200B;**[!UICONTROL Automated Segments]** （![自動化區段報表](/help/main/assets/icons/AutomatedSegment.svg) ）或&#x200B;**[!UICONTROL Important Attributes]** （![重要屬性圖示](/help/main/assets/icons/ViewList.svg) ）圖示。<ul><li>[[!UICONTROL Automated Segments]報表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)顯示不同訪客對您[!UICONTROL Automated Personalization]或[!UICONTROL Auto-Target]活動中的選件和體驗有不同的回應。 此報表顯示[!DNL Target]個人化模型定義的不同自動化區段如何回應活動中的選件和體驗。</li><li>[[!UICONTROL Important Attributes]報表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)顯示在不同的活動中，不同屬性對於模型決定個人化的方式或多或少重要。 此報表顯示影響模型及其相對重要性的常見屬性。</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 除了[[!UICONTROL Automated Personalization Summary]報表](/help/main/c-reports/personalization-reports/reports-ap.md)之外，您也可以按一下&#x200B;**[!UICONTROL Automated Segments]** （![自動化區段報表](/help/main/assets/icons/AutomatedSegment.svg) ）或&#x200B;**[!UICONTROL Important Attributes]** （![重要屬性圖示](/help/main/assets/icons/ViewList.svg) ）圖示。<ul><li>[[!UICONTROL Automated Segments]報表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)顯示不同訪客對您[!UICONTROL Automated Personalization]或[!UICONTROL Auto-Target]活動中的選件和體驗有不同的回應。 此報表顯示[!DNL Target]個人化模型定義的不同自動化區段如何回應活動中的選件和體驗。</li><li>[[!UICONTROL Important Attributes]報表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)顯示在不同的活動中，不同屬性對於模型決定個人化的方式或多或少重要。 此報表顯示影響模型及其相對重要性的常見屬性。</li></ul> |
   | [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 除了[[!UICONTROL Experience Performance]報表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)之外，您也可以按一下[[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （![位置貢獻圖示](/help/main/assets/icons/LocationContribution.svg) ）圖示，將報表切換為依位置顯示貢獻。 |

## 特定活動型別的其他報表資訊 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

除了本主題及其子主題中的一般報表資訊以外，本指南其他部分提供專用於各活動類型的其他資訊:

| 活動類型 | 詳細資料 |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | 若要瞭解提升度與可信度，以及 [!DNL Target] 中使用的統計方法，請參閱[計劃 A/B 測試](/help/main/c-activities/t-test-ab/sample-size-determination.md)。 |
| [解譯[!UICONTROL Auto-Allocate]報告](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | 在[!UICONTROL Auto-Allocate] UI中檢查重要指標（包括提升度和信賴度），以解譯[!DNL Target] A/B活動的結果。 |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | AT活動[!UICONTROL Summary]報表的相關資訊。 如需詳細資訊，請參閱[[!UICONTROL Auto-Target Summary]報表](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)。<br>AT和AP活動之兩個[!UICONTROL Personalization Insights]報表的相關資訊： [!UICONTROL Automated Segments]報表和[!UICONTROL Important Attributes]報表。 如需詳細資訊，請參閱[個人化前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | AP活動之兩個[!UICONTROL Automated Personalization Summary]報表的相關資訊： [!UICONTROL Activity Level]報表與[!UICONTROL Offer Level]報表。 如需詳細資訊，請參閱[自動個人化摘要報表](/help/main/c-reports/personalization-reports/reports-ap.md)。<br>AT和AP活動之兩個[!UICONTROL Personalization Insights]報表的相關資訊： [!UICONTROL Automated Segments]報表和[!UICONTROL Important Attributes]報表。 如需詳細資訊，請參閱[個人化前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | MVT活動之兩個報表的相關資訊： [!UICONTROL Experience Performance]報表和[!UICONTROL Location Contribution]報表。 如需詳細資訊，請參閱[體驗效能報表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT)和[位置貢獻報表](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT)。 |
| [[!DNL Adobe Analytics] 作為Adobe Target ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的報表Source | 使用[!DNL Adobe Analytics]做為[!DNL Target] (A4T)之報表來源的相關資訊。 A4T 可讓您存取 [!DNL Target] 活動的 [!DNL Analytics] 報表。如需詳細資訊，請參閱 [Analytics for Target (A4T) 報表](/help/main/c-reports/analytics-for-target-a4t-reporting.md)。 |
| [[!DNL Target] 在 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中報告 | 有關[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics){target=_blank}與[!DNL Target]之間整合的資訊，可為您的最佳化程式提供強大的分析與省時的工具。 |

## 封鎖來自指定IP位址的報告資料

您可封鎖來自特定 IP 位址的訪客，不計算在報表中。例如，此選項有助於封鎖來自內部訪客的報告資料。

[連絡客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以設定IP篩選器。 使用[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T)作為報表來源時，此篩選不適用。
