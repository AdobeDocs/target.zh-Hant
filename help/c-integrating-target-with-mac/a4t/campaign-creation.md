---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: 您可以在 Target Standard/Premium 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。
title: 活動建立
feature: a4t general
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 21%

---


# 活動建立{#activity-creation}

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. 選擇活動的最終成功量度。Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

## 建立使用Analytics做為報告來源的活動

Creating a [!DNL Target] activity that uses [!DNL Analytics] as the reporting source is similar to setting up a regular [!DNL Target] activity, with a few important differences. For example, you cannot select a segment for reporting while creating the activity because all segments available in [!DNL Analytics] can be applied when viewing a report.

1. 按一下&#x200B;**[!UICONTROL 「建立活動」]**。

   >[!NOTE]
   >
   >An activity name cannot include the &quot;%&quot; character if [!DNL Analytics] is used as the reporting source.

1. 選取活動類型並開始設定活動。
1. 進入活動建立流程的&#x200B;**[!UICONTROL 「設定」]**&#x200B;部分時，請選擇&#x200B;**[!UICONTROL 「Adobe Analytics」]**&#x200B;並指定您的公司。
1. 選擇一個報表套裝。

   You can choose any report suite that is available to you in [!DNL Analytics]. 報表套裝會定義所收集的資料將可供使用的位置。報表套裝清單中未包括虛擬報表套裝。

   選取報表套裝時，您可能遇到兩個可能的錯誤:

   * 您遇到沒有可用的報表套裝的錯誤，但您的帳戶已正確設定。

      You might need to check your [!DNL Analytics] company. If your [!DNL Adobe Experience Cloud] account is tied to more than one [!DNL Analytics] company, log out of [!DNL Target], and log in to [!DNL Analytics] under the right company. Then return to [!DNL Target], and the report suites will load.

   * 您並未看到所預期的報表套裝。

      Only report suites that are provisioned to connect to [!DNL Target] will be available for selection. If you don&#39;t see the report suite(s) you expect, first try logging out and logging back in to the [!DNL Adobe Experience Cloud] to try again.
   If the report suite(s) is still missing from the list, please [contact Customer Care](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. 指定您的追蹤伺服器。

   請參閱[使用 Analytics 追蹤伺服器](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定義體驗。
1. 指定活動目標。

   您必須選取成功度量，以用作每個活動的目標。 您的活動目標為代表成功活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。You can choose any [!DNL Analytics] metric available in the [!DNL Analytics] metric selector.

   >[!NOTE]
   >
   >You can send a custom Target-based metric to [!DNL Analytics] rather than relying only on [!DNL Analytics] data. For example, you can monitor clicking on a page, which is usually not tracked by [!DNL Analytics]. This custom metric is sent to [!DNL Analytics] automatically from the [!DNL Target] server, and appears as the &quot;[!DNL Target] Conversion&quot; metric in the metrics selector in [!DNL Analytics]. The [!DNL Target] Conversion metric is empty if you choose to use [!DNL Analytics] metrics.

   設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對活動改善之項目的提示。

   在訪客達到目標之後會保持在活動中。訪客會繼續看見活動內容，但不會被計為新活動項目。

   >[!NOTE]
   >
   >When setting up an activity after setting up [!DNL Analytics] as your reporting source, there is no option to set up audiences for reporting. [!DNL Analytics] 區段可在「活動」報 [!DNL Target] 表中使用。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## Analytics for Target(A4T)支援自動配置活動 {#a4t-aa}

我們已升級Adobe Target至Adobe Analytics整合，稱為 [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)。

[!UICONTROL 自動配置活動] ，現在支援 [!UICONTROL Analytics for Target]。 此整合可讓您使用自動配置的多重授權功能，來推動流量流向成功體驗，同時使用目標量度 [!DNL Adobe Analytics] 及／或報告 [!DNL Adobe Analytics] 和分析功能。 如果您已實作 [A4T以搭配A/B測試和體驗定位活動使用](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)，您就可開始使用！

若要開始執行:

1. 建立A/B測試活動，並選取「自 **[!UICONTROL 動配置至最佳體驗」]** ，做為「定位」頁 **[!UICONTROL 面上的「流量分]** 配方法  」。
1. 在「目 **[!UICONTROL 標與設定」頁面上，為您的「報表來源]********** 」選取「Adobe Analytics」，然後選取與您所要的最佳化目標對應的報表套裝。
1. 選擇主要目標量度。

   選擇 **[!UICONTROL 轉換]** ，以 [!DNL Adobe Target] 用來指定最佳化目標。

   或

   選擇 **[!UICONTROL 使用Analytics量度]** ，然後從中選取量度 [!DNL Analytics] 以用作最佳化目標。 您可以使用現成可用的轉換 [!DNL Analytics] 量度或自訂 [!DNL Analytics] 事件。

1. 儲存並啟動您的活動。

   [!UICONTROL 「自動分配] 」會使用您選取的量度來最佳化活動，將訪客帶往體驗，以最大化您的目標量度。

1. 使用「 **[!UICONTROL 報表]** 」標籤，依據您選擇的量度來檢視活動的 [!DNL Adobe Analytics] 報表。 按一 **[!UICONTROL 下Analytics中的檢視]** ，深入探索並進一步細分您的報告資料。

### 支援的目標量度

A4T for [!UICONTROL Auto-Allocate] 可讓您選擇下列任何量度類型作為最佳化的主要目標量度：

* [!DNL Adobe Target] 轉換量度
* [!DNL Adobe Analytics] 轉換量度
* [!DNL Adobe Analytics] 個自訂事件

A4T for [!UICONTROL Auto-Allocate] ，要求您選擇以二項式事件（即發生或未發生的事件）為基礎的量度，例如點按、轉換、訂購等。 （這些類型的事件有時也稱為Bernoulli、二進位或離散事件。）

A4T for [!UICONTROL Auto-Allocate] 不支援連續度量的最佳化，例如收入、訂購的產品數、作業期間、作業中的頁面檢視次數等。 （這些不支援的量度類型有時也稱為非二項式或非伯努利量度。）

下列量度類型不支援做為主要目標量度：

* [!DNL Adobe Target] 參與度與收入度量
* [!DNL Adobe Analytics] 參與度與收入度量

   >[!NOTE]
   >
   >您可能會選擇參與和收 [!DNL Analytics] 入量度作為主要目標量度，因為無法 [!DNL Target] 識別所有的參與和收入量度 [!DNL Analytics]。 請小心，只從中選取二項式轉換量度或自訂事件 [!DNL Analytics]。

* Adobe Analytics計算量度

### 限制與附註

* 活動啟動後，報表來源 [!DNL Analytics] 無法 [!DNL Target] 從變更為，反之亦然。
* 雖然計算量度不支援做為主要目標量度，但通常可以選擇自訂事件作為主要目標量度，以達到預期結果。 例如，如果您想要最佳化度量（例如「每位訪客表單填寫」），請選取與「表單填寫」對應的自訂事件作為主要目標度量。 [!DNL Target] 自動標準化每次瀏覽的轉換量度，以考慮不均勻的流量分佈，因此不需要使用計算量度來執行標準化。
* [!DNL Target] 在「自動配置A4T」實作中使用「相同觸控」歸因模型。

如需詳細資訊，請參 [閱「Analytics工具指南](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html) 」中的 *「歸因概述」*。
