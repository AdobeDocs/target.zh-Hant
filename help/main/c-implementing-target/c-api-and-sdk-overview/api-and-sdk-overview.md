---
keywords: 伺服器端；伺服器端；api;sdk;node.js;nodejs;node js;recommendations api;api:api
description: 瞭解Adobe [!DNL Target] 伺服器端交付API、SDK和 [!DNL Target] RecommendationsAPI
title: 在何處可以瞭解 [!DNL Target] 伺服器端交付API和SDK?
feature: Implement Server-side
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 21%

---

# 伺服器端: 實作 Target

有關 [!DNL Adobe Target] 伺服器端交付API、SDK和 [!DNL Target Recommendations] API。

下列程序會發生在 [!DNL Target] 的伺服器端實作中:

1. 用戶端裝置會透過伺服器提出體驗的要求。
1. 伺服器會將該要求傳送至 [!DNL Target]。
1. [!DNL Target] 會將回應傳送回伺服器。
1. 伺服器決定將哪種體驗交付給客戶端設備以呈現。

無需在瀏覽器中顯示體驗。 這種體驗可以通過電子郵件或亭子、語音助手或通過其他一些非視覺體驗或基於瀏覽器的非設備來顯示。 由於伺服器位於用戶端與 [!DNL Target] 之間，如果您需要更多控制和安全性，或有要在伺服器上執行的複雜後端程序，這種類型的實施也是非常理想的選擇。

>[!NOTE]
>
>第一次訪問者只能在客戶端上初始化。 第一次訪問 *不能* 在伺服器端初始化。

以下各節提供了有關各種API和NodeJS SDK的詳細資訊：

## 伺服器端傳送 API

連結： [伺服器端傳遞API](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

使用 [!DNL Target] 交付API，您可以：

* 通過Web(包括SPA)和移動頻道以及基於非瀏覽器的IoT設備（如連接的電視、亭子或店內數字螢幕）提供體驗。
* 從任何可進行HTTP/s調用的伺服器端平台或應用程式提供體驗。
* 向訪問者提供一致且個性化的體驗，而不管訪問者使用哪種渠道或設備與您的業務打交道。
* 快取伺服器上會話中訪問者的體驗，以避免多個API調用，從而獲得更好的效能。
* 無縫整合 [!DNL Adobe Experience Cloud] 產品，如 [!DNL Adobe Analytics]。 [!DNL Adobe Audience Manager] (AAM)及 [!DNL Experience Cloud ID Service] 伺服器端。

## 伺服器端SDK

連結： [Adobe TargetSDK](https://developer.adobe.com/target/)

的 [!DNL Adobe Target] 伺服器端SDK文檔門戶可幫助您實施 [!DNL Target] 以你所選的語言在伺服器上。

## Target Recommendations API

連結： [目標RecommendationsAPI](https://developer.adobe.com/target/)。

RecommendationsAPI允許您以寫程式方式與 [!DNL Target] 建議伺服器。 這些API可以與一系列應用程式堆棧整合，以執行通常通過 [!DNL Target] 用戶介面。
