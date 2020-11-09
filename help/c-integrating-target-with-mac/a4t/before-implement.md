---
keywords: Recommendations
description: 啟用 Analytics 做為 Target (A4T) 的報表來源時，會在您的資料收集程序中發生數個變更。
title: 在您實作Adobe Analytics做為Adobe Target(A4T)的報表來源之前
feature: a4t implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 52%

---


# 實作之前{#before-you-implement}

Several changes occur in your data collection process when enabling [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

決定用此整合之前，請檢閱下列各節，並考量對報表程序造成的影響:

## 實作需求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>開始使用 A4T 之前，您必須要求針對整合佈建您的帳戶。使用 [Marketing Cloud整合布建表單](https://www.adobe.com/go/audiences_tw) ，請求布建。

視您是否要搭配 A4T 使用重新導向選件而定，此 A4T 整合需要您實作下列資料庫版本 (或更新版本):

### *不*&#x200B;搭配 A4T 使用重新導向選件之情況下的需求

如果您不打算搭配 A4T 使用重新導向選件，則此整合需要您實作下列程式庫版本 (或更新版本)。列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js 1.8.0版
* [!DNL Adobe Target] (根據您的實作): at.js 版本 0.9.1 或 mbox.js 版本 61
* Adobe Analytics: appMeasurement.js 版本 1.7.0

### 搭配 A4T 使用重新導向選件之情況下的需求

若要搭配 A4T 來使用重新導向選件，您必須實作下列程式庫版本 (或更新版本).列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js 2.3.0版
* [!DNL Adobe Target]: at.js 1.6.2 版

   **注意:** mbox.js 資料庫不支援使用 A4T 重新導向選件。您的實作必須使用 at.js。

* Adobe Analytics: appMeasurement.js 版本 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## 實施前須知 {#section_50D49CC52E11414089C89FB67F9B88F5}

* This integration is enabled on new activities when you select to use [!DNL Analytics] as the reporting source. 當您如本文所述進行實作變更時，現有的活動不受影響。
* The process of setting up [!DNL Analytics] as the reporting source for [!DNL Target] includes several implementation steps, followed by a provisioning step. 實作之前，最好閱讀一遍如下所述的程序。After you complete these steps, you will be ready to use [!DNL Analytics] as your reporting source as soon as it is enabled for you. 佈建程序最多可能需要五個工作天。
* 在 [!DNL Visitor ID service] 中建立 [!DNL Visitor ID] 共用 [!DNL Adobe Experience Cloud]。 Although it does not replace the [!DNL Target] mboxPC id or [!DNL Audience Manager] UUID, it does replace the way [!DNL Analytics] identifies new visitors. If set up properly, returning [!DNL Analytics] visitors should also be identified via their old [!DNL Analytics] ID to prevent visitor cliffing. Similarly, because the [!DNL Target] mboxPCid remains intact, no [!DNL Target] visitor profile data is lost when you upgrade to the [!DNL Visitor ID service].
* 必須 [!DNL Visitor ID service] 在您和頁面代碼 [!DNL Analytics] 之前 [!DNL Target] 執行。 Make sure that `VisitorAPI.js` appears above the tags for all other [!DNL Experience Cloud] solutions.

## 延遲性 {#section_9489BE6FD21641A4844E591711E3F813}

After this integration is enabled, you will experience an additional 5-10 minutes of latency in [!DNL Analytics]. This latency increase allows data from [!DNL Analytics] and [!DNL Target] to be stored on the same hit, allowing you to break down activities by page and site section.

This increase is reflected in all [!DNL Analytics] services and tools, including the live-stream and real-time reporting, and applies in the following scenarios:

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 若是目前轉換量度的資料、已完成的資料及資料摘要，則所有點擊均會額外延遲 5 至 7 分鐘。

Be aware that the latency increase starts after you implement the [!DNL Experience Cloud] visitor ID service, even if you have not fully implemented this integration.

## 補充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

All [!DNL Target] calls used by an A4T activity to deliver content or record the goal metric must have a corresponding [!DNL Analytics] hit that shares the same supplemental ID for A4T to work properly.

Hits that contain data from [!DNL Analytics] and [!DNL Target] contain a supplemental data ID. You can see this ID in the [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. 例如: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`。只要符合下列條件即會產生此 ID:

* 已實作訪客 ID 服務
* 已實作支援此整合的 [!DNL mbox.js] 版本。

When [troubleshooting](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), be sure to confirm that the supplemental ID is present on [!DNL Analytics] hits.

## 用戶端分析記錄 {#client-side}

根據預設，當 at.js、[!DNL Experience Cloud Visitor ID Service] 和 appMeasurement.js 位於頁面上時，只要如上所述包含來自頁面的正確補充 ID，[!DNL Analytics] 和 [!DNL Target] 就會正確地拼接事件，以用於後端的報表和分析用途。您不需要管理及執行任何其他作業，A4T 即可正常運作。

不過，在某些情況下，您可能會想要進一步掌控將 [!DNL Target] 相關分析資料傳送至 [!DNL Analytics] 以用於報表用途的時間和方式。您可能有要運用於內部用途的內部分析工具，但也想要透過內部分析產品將分析資料傳送至 [!DNL Analytics]，讓組織的其他成員能夠繼續利用 [!DNL Analytics] 作為視覺報表來源。如需詳細資訊，請參閱 *Analytics for Target 實作*&#x200B;中的[步驟 7: 在所有網頁上參照 at.js 或 mbox.js](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)。

## 共用對象

在填寫 [Marketing Cloud整合布建表單時](https://www.adobe.com/go/audiences_tw)，請注意下列與「您要求布建的功能」下方所列的「共用觀眾 [!UICONTROL 」選項相關的重要資訊]?

![申請表](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

當您請求「 [!UICONTROL 共用對象]」時，請啟用 [!UICONTROL Target] 和  Adobe Audience Manager(AAM)來共用資訊，在此例中為觀眾。

>[!IMPORTANT]
>
>Target與 [!UICONTROL AAM的整合] ，會帶來額外成本。 AAM中每次Target呼叫 [!UICONTROL 都會向您收] 費。
