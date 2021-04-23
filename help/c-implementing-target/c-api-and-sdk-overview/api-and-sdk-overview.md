---
keywords: 伺服器端；伺服器端；api;sdk;node.js;nodejs;nodejs;recommendations api;api:api
description: 瞭解Adobe [!DNL Target] server-side delivery APIs, SDKs, and [!DNL Target] RecommendationsAPI。
title: 我可以從哪裡取得 [!DNL Target] 伺服器端傳送API和SDK的相關資訊？
feature: 實作伺服器端
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 20%

---

# 伺服器端: 實作 Target

有關[!DNL Adobe Target]伺服器端傳送API、SDK和[!DNL Target Recommendations] API的資訊。

下列程序會發生在 [!DNL Target] 的伺服器端實作中:

1. 用戶端裝置會透過伺服器提出體驗的要求。
1. 伺服器會將該要求傳送至 [!DNL Target]。
1. [!DNL Target] 會將回應傳送回伺服器。
1. 您的伺服器會決定要提供哪些體驗給用戶端裝置，以供其呈現。

體驗不需要在瀏覽器中顯示。 體驗可透過電子郵件或資訊站、語音助理或其他非視覺化體驗或非瀏覽器裝置顯示。 由於伺服器位於用戶端與 [!DNL Target] 之間，如果您需要更多控制和安全性，或有要在伺服器上執行的複雜後端程序，這種類型的實施也是非常理想的選擇。

>[!NOTE]
>
>首次訪客只能在用戶端進行初始化。 首次訪客&#x200B;*無法在伺服器端初始化*。

以下各節提供有關各種API和NodeJS SDK的詳細資訊：

## 伺服器端傳送 API

連結：[伺服器端傳送API](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

透過[!DNL Target]傳送API，您可以：

* 透過網路、行動通SPA道以及非瀏覽器型IoT裝置（例如連線電視、資訊站或店內數位螢幕）提供體驗。
* 從任何可進行HTTP/s呼叫的伺服器端平台或應用程式提供體驗。
* 不論訪客使用何種通道或裝置與您的業務互動，都能為訪客提供一致的個人化體驗。
* 在伺服器上的作業階段中快取訪客的體驗，以避免多個API呼叫，進而獲得更佳的效能。
* 從伺服器端順暢地與[!DNL Adobe Experience Cloud]產品整合，例如[!DNL Adobe Analytics]、&lt;a2/AAM>()和[!DNL Experience Cloud ID Service]。[!DNL Adobe Audience Manager]

## 伺服器端SDK

連結：[Adobe TargetSDK](https://adobetarget-sdks.gitbook.io/docs/)

[!DNL Adobe Target]伺服器端SDK檔案入口網站可協助您以您選擇的語言在伺服器上實作[!DNL Target]。

## Target Recommendations API

連結：[目標RecommendationsAPI](https://developers.adobetarget.com/api/recommendations)和[Adobe RecommendationsAPI概述](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html)。

RecommendationsAPI可讓您以程式設計方式與[!DNL Target]建議伺服器互動。 這些API可與一系列應用程式堆疊整合，以執行通常透過[!DNL Target]使用者介面執行的函式。
