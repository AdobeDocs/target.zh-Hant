---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: Adobe "Analytics for Target" (A4T) 是交叉解決方案的整合，可讓您根據 Analytics 轉換量度和對象區段來建立活動。這個整合可讓您使用 Analytics 報表來檢查您的結果。如果您使用 Analytics 做為活動的報表來源，則該活動的所有報表和區段都會根據 Analytics 資料收集。
title: Adobe Analytics 作為 Adobe Target (A4T) 的報表來源
feature: a4t general
subtopic: Integrating
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 46%

---


# Adobe Analytics 作為 Adobe Target (A4T) 的報表來源{#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

[!DNL Adobe Analytics for Target] (A4T)是跨解決方案整合，可讓您根據轉換量度和受眾細分 [!DNL Analytics] 建立活動。 The A4T integration lets you use [!DNL Analytics] reports to examine your results. If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics] data collection.

## A4T 概覽 {#section_92B66069210C40DBA937790E8CC596CF}

The [!DNL Analytics for Target] integration between [!DNL Analytics] and [!DNL Target] provides powerful analysis and timesaving tools for your optimization program.

The three primary benefits of using [!DNL Analytics] data in [!DNL Target] are:

* Marketers can dynamically apply [!DNL Analytics] success metrics or reporting segments to [!DNL Target] activity reports at any time. 執行活動之前完全不需要指定。
* 單一資料來源可排除在兩個不同系統中收集資料時發生不一致的情況。
* Your existing [!DNL Analytics] implementation collects all required data. 不需要只為了收集報表的資料而在頁面上實作 Mbox。Although, it is still recommended that you implement an order confirmation mbox for [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) activities.

>[!IMPORTANT]
>
>開始使用 A4T 之前，您必須要求針對整合佈建您的帳戶。使用[此表單](https://www.adobe.com/go/audiences_tw)來要求佈建帳戶。
>
>The integration that enables [!DNL Analytics] as the data source for [!DNL Target] (A4T) represents the next generation of the Test&amp;Target to SiteCatalyst plug-in. 此外掛程式已淘汰，但仍支援原本已使用的客戶。

If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics].

All [!DNL Analytics] metrics, including calculated metrics, are available in [!DNL Target] and the [!UICONTROL Target Activities] report in [!DNL Analytics]. Likewise, any segment available in [!DNL Analytics] can be applied to both solutions. You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the activity has completed.

Every metric is included, including any customer or calculated metrics that are built-in in [!DNL Analytics].

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報表套裝。

考慮使用 A4T 時，請謹記下列重點:

* To use [!DNL Analytics] as the reporting source for [!DNL Target], both you and your company must have access to [!DNL Analytics] and to [!DNL Target]. [如果您需要任一解決方案，請聯絡客戶代表](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* 每個活動皆會設定報表來源。[!DNL Target] 繼續收集要用於報告的資料，如果您 [!DNL Target] 偏好以所收集的資料為基礎，資料仍可供使用 [!DNL Target]。
* 您必須使用這兩個報表來源的其中一個。您無法同時從這兩個來源收集單一活動的資料。
* When using A4T, all success metrics available to your activities are [!DNL Analytics] metrics. 不過，目標量度可以根據 Mbox 呼叫。For example, you can use Target&#39;s out-of-the-box click-tracking capabilities with A4T instead of having to implement [!DNL Analytics] click-tracking code.
* When viewing reporting of an A4T activity in the [!DNL Target] UI, you are viewing [!DNL Analytics] data. For example, if you use the [!UICONTROL Visitor] metric in [!DNL Target], you are using the [!DNL Analytics] [!UICONTROL Visitor] metric, not the [!DNL Target] [!UICONTROL Visitors] metric, which is now called [!UICONTROL Entrants]. This difference is especially important for basic traffic metrics ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) and conversion metrics.
* Any existing [!DNL Target] activities continue to use [!DNL Target] data collection and are not affected by enabling A4T.
* Only one mbox-based metric is allowed when using [!DNL Analytics] as the reporting source.
* A server-to-server call from [!DNL Target] to [!DNL Analytics] sends activity and experience information to [!DNL Analytics]. This integration does not result in additional server calls for either [!DNL Target] or [!DNL Analytics].

   在某些情況下，從到的分類呼 [!DNL Target] 叫可 [!DNL Analytics] 能會失敗，而活動不會在中顯示資料 [!DNL Analytics]。 如果發生此情況，請 [參閱「疑難排解Analytics與Target整合(A4T)」](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)。 您也可以聯 [絡Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) ，以取得進一步協助。

## Supported activity types {#section_F487896214BF4803AF78C552EF1669AA}

The following table shows you which activity types support [!DNL Analytics] as the reporting source in [!DNL Target] (A4T):

| 活動類型 | A4T 相容? | 備註 (若適用) |
|--- |--- |--- |
| 手動分割流量的 A//B 活動 | 是 |  |
| 自動分配的 A/B 活動 | 是 | 請參 [閱Analytics for Target(A4T)對「自動分配」和「自動目標」活動的支援](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)。 |
| 自動鎖定目標的 A/B 活動 | 是 | 請參 [閱Analytics for Target(A4T)對「自動分配」和「自動目標」活動的支援](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)。 |
| 體驗鎖定目標 (XT) | 是 |  |
| 多變數測試 (MVT) | 是 | Requires mbox-based goal metric goal to get the [!UICONTROL Element Contribution] report.  The [!UICONTROL Element Contribution] report does not currently support [!DNL Analytics] metrics. |
| 自動個人化 (AP) 活動 | 無 |  |
| Recommendations 活動 | 是 |  |
| 行動應用程式 | 是 | 支援行動服務 SDK 4.13.1 版或更新版本。如需詳細資訊，請參閱[行動服務文件](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)。 |
| 電子郵件 | 無 |  |
| 伺服器端傳送 API | 是 | 如需詳細資訊，請參閱[伺服器端: 實作 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| NodeJS SDK | 是 | 如需詳細資訊，請參閱[伺服器端: 實作 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| AEM 6.1 (或更舊) 雲端服務整合 | 無 |  |
| AEM 6.2 (或更新) 雲端服務整合 | 是 | For more information, see [Integrating with Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) in the [!DNL Adobe Experience Manager] 6.2 documentation. |
| 使用重新導向選件的任何活動 | 是 | 搭配 A4T 使用重新導向選件時，最低需求較嚴格。如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。 |
| Node.JS | 是 |  |

Because all activity types do not yet support A4T, it is recommended that you keep or implement important conversion mboxes, such as the `orderConfirmPage` mbox.

## Examples of A4T reports {#section_F0A43A1CB2F04E8282B909E4D7034361}

To view A4T reports in [!DNL Target], click **[!UICONTROL Activities]**, click the desired activity from the list that uses [!DNL Analytics] as its reporting source, then click the **[!UICONTROL Reports]** tab.

>[!NOTE]
>
>您可以使用[!UICONTROL 「活動」]頁面頂端的[!UICONTROL 「報表來源」]下拉式清單，指定只顯示使用 [!DNL Analytics] 作為報表來源的活動。

You can toggle between the [!UICONTROL Table View] and [!UICONTROL Graph View] of the report by clicking the appropriate icon at the top right side of the report.

下圖顯示 A4T 報表的[!UICONTROL 「圖表檢視」]，其中[!UICONTROL 「報表量度」]下拉式清單顯示可用的 [!DNL Analytics] 目標量度:

![](assets/a4t_report_graph1.png)

下圖顯示 A4T 報表的[!UICONTROL 「圖表檢視」]，其中[!UICONTROL 「對象」]下拉式清單顯示可用的 [!DNL Analytics] 對象:

![](assets/a4t_report_graph2.png)

下圖顯示 A4T 報表的[!UICONTROL 「表格檢視」]:

![](assets/a4t_report_table.png)

若要在 [!DNL Analytics] 中檢視報表，而非在 [!DNL Target] 中，請按一下報表頂端的&#x200B;****&#x200B;在 Analytics 中檢視。

## Analytics 與 Target: Analysis 最佳實務教學課程 {#section_3438E6E77A464424B717A4FD333B84B2}

Open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by [!DNL Adobe Experience League].

## 訓練影片:

以下影片包含本主題中討論之概念的詳細資訊。

### Analytics for Target(A4T)(4:32)概 ![觀徽章](/help/assets/overview.png)

This video explains how to use [!DNL Analytics] as a reporting source in [!DNL Target] to drive the analysis of your optimization program.

* 說明何謂 A4T 以及為何您會使用它
* 說明 A4T 的運作方式
* 瞭解使用 A4T 之前所需的先決條件

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics / Target整合(A4T)(40:33)教學課 ![程徽章](/help/assets/tutorial.png)

這支影片記錄了「[營業時間](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」，這是一項 Adobe 客戶服務團隊主導的計劃。

* 如何設定並驗證整合項目成功運作
* 整合項目的運作原理
* 瞭解適合用於 Analytics 的報表
* 回答有關 A4T 的常見問題

[Analytics/Target整合(A4T)辦公時間](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)