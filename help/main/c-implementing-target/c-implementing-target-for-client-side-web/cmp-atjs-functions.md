---
keywords: at.js;函數;JavaScript 程式庫
description: 查看可與Adobe Targetat.js JavaScript庫的1.x和2.x版本一起使用的函式清單。
title: 我可以與at.js一起使用哪些功能？
feature: at.js
role: Developer
exl-id: a386e478-16f4-4bf6-9771-6b1e75f2e362
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 78%

---

# at.js 函數

可與 Adobe Target at.js JavaScript 資料庫搭配使用的函數清單。按一下函數欄中的連結，取得詳細資訊和範例。

| 函數 | 詳細資料 |
| --- | --- | 
| [adobe.target.getOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/) | 此函數會觸發要求來取得 Target 選件。搭配使用 `adobe.target.applyOffer()` 來處理回應或使用您自己的成功處理。 |
| [adobe.target.getOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)<br>(at.js 2.x) | 此函數可讓您透過傳入多個 mbox 來擷取多個選件。此外，還可針對使用中活動內的所有檢視擷取多個選件。<br>**注意:** 此函數已於 at.js 2.x 推出。此函數不適用於 at.js 版本 1。*x* 版本不支援此函數。 |
| [adobe.target.applyOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffer/) | 此函數用來套用回應內容。 |
| [adobe.target.applyOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffers-atjs-2/)<br>(at.js 2.x) | 此函數可讓您套用多個由 adobe.target.getOffers() 擷取的選件。<br>**注意:** 此函數已於 at.js 2.x 推出。此函數不適用於 at.js 版本 1。*x* 版本不支援此函數。 |
| [adobe.target.triggerView (viewName, options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/)<br>(at.js 2.x) | 每當新頁面載入或頁面上的元件重新呈現時，就可呼叫此函數。<br> 此函數應為單頁應用程式 (SPA) 實作，以便使用可視化體驗撰寫器 (VEC) 來建立 A/B 測試和體驗鎖定目標 (XT) 活動。 |
| [adobe.target.trackEvent(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-trackevent/) | 此函數會觸發要求以報告使用者動作，例如點擊和轉換。它不會在回應中傳遞活動。 |
| [mboxCreate(mbox,params)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxcreate-atjs/)<br>(at.js 1.x) | 執行要求並將選件套用至具有 mboxDefault 類別名稱的最接近 DIV。<br>**注意:** 此函數適用於 at.js 版本 1。*x* 版。自 at.js 2.x 版起已棄用此函數。如果與 at.js 2.x 搭配使用，此函數會傳回預設內容。 |
| [mboxDefine(options) 和 mboxUpdate(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxdefine-mboxupdate-atjs-1x/)<br>(at.js 1.x) | 定義和更新 mbox。<br>**注意:** 此函數適用於 at.js 版本 1。*x* 版。自 at.js 2.x 版起已棄用此函數。如果與 at.js 2.x 搭配使用，此函數會傳回預設內容。 |
| [targetGlobalSettings(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) | 您可以使用 `targetGlobalSettings()` 覆寫 at.js 資料庫中的設定，而非在 Target Standard/Premium UI 中或使用 REST API 進行設定。<ul><li>資料提供者: 此設定可讓客戶收集來自協力廠商資料提供者 (例如 Demandbase、BlueKai 和自訂服務) 的資料，並在全域 mbox 要求中以 mbox 參數的形式傳遞資料至 Target。</li></ul> |
| [targetPageParams(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparams/) | 此方法允許您將參數從要求程式碼外部附加至全域 mbox。 |
| [targetPageParamsAll(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/) | 此方法允許您將參數從要求程式碼外部附加至所有 mbox。 |
| [registerExtension(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/registerextension-atjs-1x/)<br>(at.js 1.x) | 提供標準方式來註冊特定的延伸模組。<br>**注意:** 此函數適用於 at.js 版本 1。*x* 版。自 at.js 2.x 版起已棄用此函數。如果與 at.js 2.x 搭配使用，此函數會傳回預設內容。 |
| [at.js 自訂事件](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/) | at.js 自訂事件可讓您知道 mbox 要求或選件失敗或成功。 |
| [adobe.target.sendNotifications(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-sendnotifications-atjs-21/)<br>(at.js 2.1.0) | 此函數會在體驗呈現時傳送通知給 Target Edge，而不需要使用 `adobe.target.applyOffer()` 或 `adobe.target.applyOffers()`。<br>**注意**: 此函數已在 at.js 2.1.0 中推出，且將適用於 2.1.0 以上的任何版本。 |
