---
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
description: 與Adobe Target Java SDK相關的發行說明。
title: 與Adobe Target Java SDK相關的發行說明。
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---


# 發行說明——目標Java SDK

與 [Target Java SDK相關的發行說明](https://github.com/adobe/target-java-sdk)。

Java [!DNL Target] SDK可讓您部署 [!DNL Target] 伺服器端。 此Java SDK可協助您輕鬆 [!DNL Target] 地與其 [!DNL Adobe Experience Cloud] 他解決方案整 [!DNL Adobe Experience Cloud Identity Service]合， [!DNL Adobe Analytics]例如 [!DNL Adobe Audience Manager]。

Java SDK透過我們的傳送API與整合時引入最佳實務並免除複雜性， [!DNL Target] 讓您的工程團隊能夠專注在商業邏輯上。

透過全新的Target Java SDK，在Adobe技術部落格——伺服器 [端最佳化中進一步瞭解Target Java SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。

## 1.1.0版（2019年12月16日）

下節提供有關Target Java SDK 1.1.0版的詳細資訊：

### 新增

* 由於@hisham-hassan提供開放原始碼貢獻，所以新增了對proxy設定的支援。

## 1.0.1版（2019年11月11日）

下節提供有關Target Java SDK 1.0.1版的詳細資訊：

### 固定

* 即使沒有訪客API Cookie存在，仍可在Target請求中傳送補充資料ID。

## 1.0.0版（2019年10月31日）

以下各節提供有關Target Java SDK 1.0.0版的詳細資訊：

### 新增

* [Target View Delivery v1 API支援](https://developers.adobetarget.com/api/delivery-api/) ，包括「頁面載入」和「檢視預回遷」。
   * 完整支援提供在Visual Experience Composer(VEC)中撰寫的所有選件類型。
* 支援預取和通知，可透過快取預取內容來最佳化效能。
* 支援透過在伺服器端和 [!DNL Target] 用戶端部 `serverState`署時， [!DNL Target] 在混合整合中最佳化效能。
   * 我們引入一個名為 `serverState` 的設定，其中包含透過伺服器端擷取的體驗，因此at.js v2.2+不會進行額外的伺服器呼叫來擷取體驗。 此方法可最佳化頁面載入效能。
* 以 [Target Java SDK形式在GitHub上開啟](https://github.com/adobe/target-java-sdk)。
* 驗證SDK API方法引數。
* 已添加自述檔案、示例和單元測試。
* 新增CoC、貢獻准則、公關和期刊範本。

