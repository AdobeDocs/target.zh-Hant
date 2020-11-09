---
keywords: analytics for target;a4t;analytics as the reporting source
description: 使用 Analytics 做為您的 Target (A4T) 報表來源，可讓您存取 Target 活動的 Analytics 報表。
title: A4T 報表
feature: a4t reports
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 35%

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

## Analytics 中的報表 {#analytics}

在中 [!DNL Analytics]，啟用A4T整合後，有數個維度和量度可供使用。

### 維度

* [!UICONTROL Analytics for Target] —— 透過整合傳入的父ID。 此維的格式為 `Activity ID:Experience ID:3rd ID`。 以下維度是此維度的分類。
* [!UICONTROL Target 活動]
* [!UICONTROL 目標體驗]
* [!UICONTROL 目標活動] >體 [!UICONTROL 驗]
* [!UICONTROL 第3個ID] —— 可以忽略

### 量度

* [!UICONTROL 活動印象] -符合報 [!UICONTROL 表中的] 「新進者」 [!DNL Target] 編號。
* [!UICONTROL 活動轉換] -符合報 [!UICONTROL 表中的自訂轉][!DNL Target] 換數。

在中 [!DNL Analysis Workspace]，使用「Analytics for Target [!UICONTROL 」面板，以提升和自信][!DNL Target] 度分析您的活動和體驗。 如需詳細資訊，請 [參閱「Analytics工具指南」中的](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) 「Analytics for Target(A4T) *面板」*。

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. 請聯絡客戶服務以解決此問題。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by Adobe Experience League.

## Target 中的報表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Every metric is available, including any custom or calculated metrics that are built-in in [!DNL Analytics].

   請注意，任何增加的數字在報表中都顯示為正數，即使您其實不希望增加也一樣。例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. 您事先完全不需要知道要測量什麼。

Click to view the full [!DNL Analytics] report directly from the activity report page.

## 活動建立 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在建立活動期間，您必須在[!UICONTROL 「設定」]頁面上指定活動的目標。此目標會成為報表的預設量度，且一律列為量度選取器的第一個選項。您無法像一般 Target 活動一樣選取要報告的區段。A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。

如需詳細資訊，請參閱[對 Analytics for Target (A4T) 執行離線計算](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
