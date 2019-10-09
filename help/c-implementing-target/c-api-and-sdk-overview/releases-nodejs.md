---
description: 與Adobe Target的Node.js SDK相關的發行說明
keywords: at.js;sdk;node.js;release;updates;sdks；伺服器端；伺服器端；伺服器端
seo-description: 與Adobe Target伺服器端API相關的發行說明。
seo-title: 與Adobe Target的Node.js SDK相關的發行說明。
solution: Target
title: 發行說明- Target Node.js SDK
topic: Standard
translation-type: tm+mt
source-git-commit: 434b103cee15e2e3efdb53febe15c689b5ccd48e

---


# 發行說明- Target Node.js SDK

與 [Adobe Target Node.js SDK相關的發行說明](https://github.com/adobe/target-nodejs-sdk)。

## 1.0.0版（2019年10月9日）

以下各節提供有關Target Node.js SDK 1.0.0版的詳細資訊：

### 新增

* 目標檢視傳送v1 API支援，包括頁面載入和檢視預回遷。
* 完整支援提供在Visual Experience Composer(VEC)中撰寫的所有選件類型。
* 支援預取和通知，以快取預取的內容來最佳化效能。
* 支援在伺服器端和 [!DNL Target] 用戶端 `serverState` 部 [!DNL Target] 署時，最佳化混合整合的效能。

   我們引入一個名為 `serverState` 的設定，其中包含透過伺服器端擷取的體驗，因此at.js v2.2+不會進行額外的伺服器呼叫來擷取體驗。 此方法可最佳化頁面載入效能。

* 以 [Target Node.js SDK形式在GitHub上開啟](https://github.com/adobe/target-nodejs-sdk)。
* 新 [的sendNotifications()API方法](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) ，可傳送顯示／點按的通知至 [!DNL Target] ，以透過 [getOffers()預取的內容](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers)。
* 簡化檢視傳送API請求建立，內部欄位自動完成，預設值 `request.id`( `request.context`例如，等等)。
* 驗證SDK API方法引數。
* 更新了自述檔案、示例和單元測試。
* 使用GitHub動作設定新的CI流程。
* 新增CoC、貢獻准則、公關和期刊範本

### 將 

* 專案已重新命名為 `target-nodejs-sdk`。
* 主要重構功能，將Target BatchMbox v2 API取代為Target View Delivery v1 API。
* [create()API方法引數已修改](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) ，並移除多餘的巢狀結構(請參閱此處的舊 [方法聲明](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate))。
* [getOffers()API方法引數已修改](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) (請參閱此處的舊方 [法聲明](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers))。
* API `getTargetCookieName()` 方法已取代為存取 `TargetCookieName` 子。 請參 [閱TargetClient公用程式存取器](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。
* API `getTargetLocationHintCookieName()` 方法已取代為存取 `TargetLocationHintCookieName` 子。  請參 [閱TargetClient公用程式存取器](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。

### 已移除

* Target batchMbox v2 API支援。
* 已 [移除getOffer()API方法](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) ，請改用 [getOffers()API方法](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) 。

