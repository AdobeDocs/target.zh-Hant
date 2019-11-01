---
description: Adobe Target伺服器端傳送API、Node.js SDK和Target Recommendations API的相關資訊。
keywords: 伺服器端；伺服器端；api;sdk;node.js;nodejs;nodejs;recommendations api;api:api
seo-description: Adobe Target伺服器端傳送API、Node.js SDK和Target Recommendations API的相關資訊。
seo-title: Adobe Target伺服器端傳送API、Node.js SDK和Target Recommendations API的相關資訊。
solution: Target
title: 伺服器端實作 Target
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: aa08021bdafbc857bd82c97462cacc0152fc4040

---


# 伺服器端: 實作 Target{#server-side-implement-target}

伺服器 [!DNL Adobe Target] 端傳送API、Node.js SDK和API的相 [!DNL Target Recommendations] 關資訊。

下列程序會發生在 [!DNL Target] 的伺服器端實作中:

1. 用戶端裝置會透過伺服器提出體驗的要求。
1. 伺服器會將該要求傳送至 [!DNL Target]。
1. [!DNL Target] 會將回應傳送回伺服器。
1. 您的伺服器會決定要提供哪些體驗給用戶端裝置，以供其呈現。

體驗不需要在瀏覽器中顯示。 體驗可透過電子郵件或資訊站、語音助理或其他非視覺化體驗或非瀏覽器裝置顯示。 由於伺服器位於用戶端與 [!DNL Target] 之間，如果您需要更多控制和安全性，或有要在伺服器上執行的複雜後端程序，這種類型的實施也是非常理想的選擇。

以下各節提供有關各種API和NodeJS SDK的詳細資訊：

## 伺服器端傳送 API

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

透過 [!DNL Target] 傳送API，您可以：

* 跨網路提供體驗，包括SPA、行動通道以及非瀏覽器型IoT裝置，例如連線電視、資訊站或店內數位螢幕。
* 從任何可進行HTTP/s呼叫的伺服器端平台或應用程式提供體驗。
* 不論訪客使用何種通道或裝置與您的業務互動，都能為訪客提供一致的個人化體驗。
* 在伺服器上的作業階段中快取訪客的體驗，以避免多個API呼叫，進而獲得更佳的效能。
* 與產品 [!DNL Adobe Experience Cloud] (例如 [!DNL Adobe Analytics]、 [!DNL Adobe Audience Manager] (AAM)和伺服器端 [!DNL Experience Cloud ID Service] )完美整合。

## Node.js SDK

連結： [Node.js SDK](https://github.com/adobe/target-nodejs-sdk)

Node.js SDK是一套複雜的軟體開發套件，可免除管理Cookie、工作階段以及與產品（例如、和）整 [!DNL Experience Cloud] 合時的 [!DNL Analytics]繁 [!DNL Experience Cloud Visitor ID Service]雜工作 [!DNL Audience Manager]。 在幕後，Node.js SDK使用 `/rest/v1/delivery` API。 以下是Node.js SDK支援的一些顯著功能：

* **** 支援預回遷和通知，讓您透過快取最佳化效能：您可以使用Node.js SDK在Node.js伺服器上擷取體驗並在本機快取體驗，以盡量減少伺服器對應用程式的呼叫 [!DNL Target] 並最佳化其效能。
* **** 能夠檢索VEC建立的活動：在伺服器端擷取VEC建立的活動。 包含VEC建立之活動的回應包含選擇器，可用來僅預先隱藏頁面中需要個人化的部分。 這可協助您最佳化頁面的「第一個內容上色」量度 [，這是企業在](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Google PageRank系統中獲得高分的重要KPI [](https://en.wikipedia.org/wiki/PageRank) 。

## 目標Java SDK

連結：目 [標Java SDK](https://github.com/adobe/target-java-sdk)

Java SDK是一套複雜的軟體開發套件，可免除管理Cookie、工作階段以及與解決方案（例如、和）整 [!DNL Adobe Experience Cloud] 合的複雜 [!DNL Adobe Analytics]工作 [!DNL Experience Cloud Visitor ID Service]流程 [!DNL Adobe Audience Manager]。 在幕後，Java SDK使用 `/rest/v1/delivery` API。 以下是Java SDK支援的一些重要功能：

* **支援預回遷和通知，讓您透過快取最佳化效能**:您可以使用JavaSDK在Java伺服器上擷取體驗並在本機快取體驗，以便將伺服器呼叫次數減至最少並最佳化您 [!DNL Target] 的應用程式效能。
* **可擷取VEC建立的活動**:在伺服器端擷取VEC建立的活動。 包含VEC建立之活動的回應包含選擇器，可用來僅預先隱藏頁面中需要個人化的部分。 這可協助您最佳化頁面的「第一個內容上色 [」量度，這是企業在](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)[](https://en.wikipedia.org/wiki/PageRank) Google PageRank系統中獲得高分的重要KPI。

## Target Recommendations API

Link: [Target Recommendations APIs](https://developers.adobetarget.com/api/recommendations)

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
