---
description: Target 伺服器端傳送 API、Recommendations API 與 NodeJS SDK 的相關資訊。
keywords: 伺服器端; API; SDK; nodejs; node js; Recommendations API
seo-description: 有關Adobe Target Server端遞送API、Recommendations API和NodeJS SDK的資訊。
seo-title: 伺服器端實作Adobe Target
solution: Target
title: 伺服器端實作 Target
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 伺服器端: 實作 Target{#server-side-implement-target}

[!DNL Adobe Target] 伺服器端傳送API、伺服器端批次傳送API、NodeJS SDK、 [!DNL Target Recommendations] API和 [!DNL Target Classic] API(解壓縮)的相關資訊。

The following process occurs in a server-side implementation of [!DNL Target]:

1. 用戶端裝置會透過您的伺服器要求體驗。
1. Your server sends that request to [!DNL Target].
1. [!DNL Target] 將回應傳送回伺服器。
1. 您的伺服器會決定要提供哪一種體驗給用戶端裝置，以便轉譯。

不需要在瀏覽器中顯示體驗；它可顯示在電子郵件或資訊站中，透過語音助理或其他非視覺體驗或非瀏覽器型裝置顯示。Because your server sits between the client and [!DNL Target], this type of implementation is also ideal if you need greater control and security or have complex backend processes that you want to run on your server.

下節列出多種 API 和 NodeJS SDK，並提供額外資訊:

## 伺服器端傳送 API

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

[!DNL Target] 可讓您的應用程式從任一瀏覽器、行動裝置甚至另一台伺服器執行 mbox 呼叫。The Server Side delivery API is specifically designed to integrate [!DNL Target] with any server-side platform that makes HTTP/HTTPS calls.

您可使用 API 來整合您的自訂應用程式與 [!DNL Target]. 這對要傳送鎖定至聯網電視、資訊站或店內數位螢幕等非瀏覽器型 IoT 裝置的組織特別有用。

端點只能傳回一般 mbox 的選件。您亦僅能從單一 mbox 擷取內容。

本 API 會採用 RESTful 作法來實作現有的 mbox 功能。

本 API 不會處理 Cookie 或重新導向呼叫。

## 伺服器端批次傳送 API

Link: [Server Side Batch Delivery APIs](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

批次傳送 API 可讓您的應用程式以單一呼叫，即可從多個 mbox 要求內容。It also has a prefetch mode that enables clients like mobile apps, servers, and so forth to fetch content for multiple mboxes in one request, cache it locally, and later notify [!DNL Target] when the user visits those mboxes.

端點只能傳回一般 mbox 的選件。由於您可以從多個 mbox 擷取內容，為求效能，使用批次 mbox API 更理所當然。此 API 可讓您不用執行多個 HTTP 要求。多個 HTTP 要求可能所費不。

## NodeJS SDK

Link: [NodeJS SDK](https://www.npmjs.com/package/@adobe/target-node-client)

雖說是「多套」 SDK，目前我們只有一套 SDK，也就是 NodeJS SDK。

NodeJS SDK 是 NodeJS 核心 HTTP/HTTPS 模組的輕薄包裝函式。NodeJS SDK API 在背景使用相同的伺服器端傳送 API。

對應關係如下:

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## [!DNL Target Recommendations] API

Link: [Target Recommendations APIs](https://developers.adobetarget.com/api/recommendations)

Recommendations API 可讓您以程式設計方式與 Target 的 Recommendations 伺服器互動。這些 API 可與一系列應用程式堆疊整合，執行一些您通常得透過使用者介面操作的功能。

## [!DNL Target Classic] API

[!DNL Target Classic] UI和API已解除運作。如需關於轉換為 Target 現代化 API 的詳細資訊，請參閱[從 Target Legacy API 轉換為 Adobe I/O](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2)。

>[!NOTE]
>撰寫 API (用來建立活動、選件、對象等) 不支援跨來源資源共用 (CORS)。

## 伺服器端傳送 API 和 NodeJS SDK 間的差異 {#section_10336B7934F54CE98E35907A4748A4A4}

許多客戶會不大清楚伺服器端傳送 API 和 NodeJS SDK 間的差異，尤其牽涉到效能時。

下列的常見問題集應可協助您判斷要採用何者:

**何時該採用「原始」伺服器端傳送 API，何時要使用 NodeJS SDK?**

理想上，如果您的後端技術採用的是 NodeJS，那麼選擇 NodeJS SDK 很合理。SDK 會負責許多細節作業，像是 Cookie、標題、承載等等。這樣您就可以專注在應用程式核心上。

**採用 NodeJS SDK 就能讓我獲得效能改善嗎?**

很抱歉，我們沒有任何效能數據。不過，一般來說，NodeJS 事件驅動架構 應該可為 NodeJS SDK 提供良好效能。Be aware that most of the time is spent on the [!DNL Target] backend. NodeJS SDK 幾乎不負責處理工作。The SDK is basically responsible for packaging a [!DNL Target] request and parsing a [!DNL Target] response.
