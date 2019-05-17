---
description: Target 伺服器端傳送 API、Recommendations API 與 NodeJS SDK 的相關資訊。
keywords: 伺服器端; API; SDK; nodejs; node js; Recommendations API
seo-description: Target 伺服器端傳送 API、Recommendations API 與 NodeJS SDK 的相關資訊。
seo-title: 伺服器端實作 Target
solution: Target
title: 伺服器端實作 Target
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 伺服器端: 實作 Target{#server-side-implement-target}

提供 Target 伺服器端傳送 API、伺服器端批次傳送 API、NodeJS SDK、Target Recommendations API 和 Target Classic API (已停止支援) 的相關資訊。

下節列出多種 API 和 NodeJS SDK，並提供額外資訊:

## 伺服器端傳送 API

連結： [伺服器端傳送API](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

Adobe Target 可讓您的應用程式從任一瀏覽器、行動裝置甚至另一台伺服器執行 mbox 呼叫。伺服器端傳送 API 經過專門設計，以將 Adobe Target 與任一執行 HTTP/HTTPS 呼叫的伺服器端平台整合。

您可使用 API 來整合您的自訂應用程式與 Target。這對要傳送鎖定至聯網電視、資訊站或店內數位螢幕等非瀏覽器型 IoT 裝置的組織特別有用。

端點只能傳回一般 mbox 的選件。您亦僅能從單一 mbox 擷取內容。

本 API 會採用 RESTful 作法來實作現有的 mbox 功能。

本 API 不會處理 Cookie 或重新導向呼叫。

## 伺服器端批次傳送 API

連結： [伺服器端批次傳送API](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

批次傳送 API 可讓您的應用程式以單一呼叫，即可從多個 mbox 要求內容。此 API 亦具備預先擷取模式，可讓行動應用程式、伺服器等用戶端透過一次要求從多個 mbox 擷取內容、在本地快取，接著在有使用者造訪這些 mbox 時通知 Target。

端點只能傳回一般 mbox 的選件。由於您可以從多個 mbox 擷取內容，為求效能，使用批次 mbox API 更理所當然。此 API 可讓您不用執行多個 HTTP 要求。多個 HTTP 要求可能所費不。

## NodeJS SDK

連結： [nodeJS SDK](https://www.npmjs.com/package/@adobe/target-node-client)

雖說是「多套」 SDK，目前我們只有一套 SDK，也就是 NodeJS SDK。

NodeJS SDK 是 NodeJS 核心 HTTP/HTTPS 模組的輕薄包裝函式。NodeJS SDK API 在背景使用相同的伺服器端傳送 API。

對應關係如下:

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## Target Recommendations API

連結： [Target Recommendations API](https://developers.adobetarget.com/api/recommendations)

Recommendations API 可讓您以程式設計方式與 Target 的 Recommendations 伺服器互動。這些 API 可與一系列應用程式堆疊整合，執行一些您通常得透過使用者介面操作的功能。

## Target Classic API

我們已停止支援 Target Classic UI 與 API。如需關於轉換為 Target 現代化 API 的詳細資訊，請參閱[從 Target Legacy API 轉換為 Adobe I/O](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2)。

>[!NOTE]
>撰寫 API (用來建立活動、選件、對象等) 不支援跨來源資源共用 (CORS)。

## 伺服器端傳送 API 和 NodeJS SDK 間的差異 {#section_10336B7934F54CE98E35907A4748A4A4}

許多客戶會不大清楚伺服器端傳送 API 和 NodeJS SDK 間的差異，尤其牽涉到效能時。

下列的常見問題集應可協助您判斷要採用何者:

**何時該採用「原始」伺服器端傳送 API，何時要使用 NodeJS SDK?**

理想上，如果您的後端技術採用的是 NodeJS，那麼選擇 NodeJS SDK 很合理。SDK 會負責許多細節作業，像是 Cookie、標題、承載等等。這樣您就可以專注在應用程式核心上。

**採用 NodeJS SDK 就能讓我獲得效能改善嗎?**

很抱歉，我們沒有任何效能數據。不過，一般來說，NodeJS 事件驅動架構 應該可為 NodeJS SDK 提供良好效能。請注意，大部分的時間都是花在 Target 後端。NodeJS SDK 幾乎不負責處理工作。SDK 基本上是負責封裝 Target 要求，並剖析 Target 回應。
