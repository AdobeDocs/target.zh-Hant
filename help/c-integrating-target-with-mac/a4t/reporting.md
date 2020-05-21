---
keywords: analytics for target;a4t;analytics as the reporting source
description: 使用 Analytics 做為您的 Target (A4T) 報表來源，可讓您存取 Target 活動的 Analytics 報表。
title: A4T 報表
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 44%

---


# A4T 報表{#a-t-reporting}

Using [!DNL Analytics] as your reporting source for [!DNL Target] (A4T) gives you access to [!DNL Analytics] reports for your [!DNL Target] activities.

You can view reports for your activities in both [!DNL Analytics] and [!DNL Target].

For reporting best practices using [!DNL Analytics] for [!DNL Target], [visit this Adobe Spark page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

Both [!DNL Analytics] and [!DNL Target] reports measure entrants (the people who enter the tests), rather than visitors to the site.

Every time a visitor sees activity content on the page, [!DNL Target] makes a direct server-to-server call to [!DNL Analytics], including which activity and experience the visitor saw. [!DNL Target] 也會在進 [!DNL Analytics] 行轉換時呼叫。 [!DNL Analytics] 將轉換新增為名為「活 [!DNL Analytics] 動轉換」的特定新事件，此事件會與收集到的其他資料一起追蹤 [!DNL Analytics]。

When the [!UICONTROL Select] operation is used and you sort on *Entrants*, then only experiences that received entrants during the selected time period are displayed in the reports.

>[!NOTE]
>
>Reports powered by [!DNL Target] have a latency of four minutes. For activities powered by A4T, in both the [!DNL Target] and [!DNL Analytics] reports, it can take up to 24 hours after the activity is initially saved before the report data can be broken down by experiences. 在這最初 24 小時收集的資料仍然正確，且會指派給正確的體驗。

## Analytics 中的報表 {#section_F6884872DC864AE7913587FAED4CD11C}

In [!DNL Analytics], click **[!UICONTROL Target]** > **[!UICONTROL Target Activities]** in the left menu. In [!DNL Target], the activity&#39;s reports automatically show [!DNL Analytics] data, metrics, and segments. 從網站收集資料後，大約一小時後資料就會出現在這些報表中。報表中的所有量度、對象和值，來自於您設定活動時所選取的報表套裝。

In [!DNL Analytics], use the [!UICONTROL Target Activities] report to view the results of your [!DNL Target] activity. Test&amp;Target (Legacy) Reports provides information about your old Test&amp;Target plug-in style page integrations and does not include [!DNL Analytics] for [!DNL Target] data. In the [!UICONTROL Activities] report, view information about your [!DNL Target] experiences. 按一下&#x200B;**[!UICONTROL 「量度」]**，然後選取 **[!UICONTROL Target]** 量度類型。有兩個量度可用於報表:

* **活動項目:**[!DNL Target]會在 報表中比對「加入者」數目。
* **活動轉換:**[!DNL Target]會在 報表中比對「自訂轉換」次數。

>[!NOTE]
>
>[!DNL Target] 如需提升度和信賴度詳細資訊，請參閱 [!DNL Analytics]。 如需詳細資訊，請參 [閱「Analytics元件指南」中的](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/report-target-lift-confidence.html)*「目標提升度和可信度」*。

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. 請聯絡客戶服務以解決此問題。

## Target 中的報表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Every metric is available, including any custom or calculated metrics that are built-in in [!DNL Analytics].

   請注意，任何增加的數字在報表中都顯示為正數，即使您其實不希望增加也一樣。例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. 您事先完全不需要知道要測量什麼。

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Analysis Workspace 中的報表 {#reports-in-analysis-workspace}

您可以使用 [!DNL Adobe Analysis Workspace] 更進一步深入瞭解並以視覺化方式呈現資料，或發掘隱藏於表面下的分析。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by [!DNL Adobe Experience League].

## 活動建立 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在建立活動期間，您必須在[!UICONTROL 「設定」]頁面上指定活動的目標。此目標會成為報表的預設量度，且一律列為量度選取器的第一個選項。您無法像一般 Target 活動一樣選取要報告的區段。A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。

如需詳細資訊，請參閱[對 Analytics for Target (A4T) 執行離線計算](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
