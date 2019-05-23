---
description: 可搭配 at.js 使用的函數清單。
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: 可與 Adobe Target 中的 at.js JavaScript 資料庫搭配使用的函數清單。
seo-title: Adobe Target at.js 函數
solution: Target
subtopic: 快速入門
title: at.js 函數
topic: Standard
uuid: ec5f27a7-b22a-48c9-968c-9eb02830a2a6
translation-type: tm+mt
source-git-commit: c607b241afb535f324cd1357c8784a88fb183658

---


# at.js 函數{#at-js-functions}

可與 Adobe Target at.js JavaScript 資料庫搭配使用的函數清單。按一下「函數」欄中的連結，以瞭解更多資訊和範例。

| 函數 | 詳細資料 |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | 此函數會觸發要求來取得 Target 選件。搭配使用 `adobe.target.applyOffer()` 來處理回應或使用您自己的成功處理。 |
| [adobe. target. getOffers(選項)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at. js2.x) | 此函數可讓您透過傳入多個 mbox 來擷取多個選件。此外，還可針對使用中活動內的所有檢視擷取多個選件。<br>**注意：** 此函數是以. js2.x導入。此函數不適用於. js第版。*x* 版本不支援此函數。 |
| [adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | 此函數用來套用回應內容。 |
| [adobe. target. applyOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at. js2.x) | 此函數可讓您套用多個由adobe. target. getOffers()擷取的選件。<br>**注意：** 此函數是以. js2.x導入。此函數不適用於. js第版。*x* 版本不支援此函數。 |
| [adobe. target. righerView(ViewName，options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at. js2.x) | 每當新頁面載入或頁面上的元件重新呈現時，就可呼叫此函數。<br> 此函數應實施為單一頁面應用程式(SPA)，以便使用Visual Experience Composer(CMS)建立A/B測試和體驗定位(XT)活動。 |
| [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | 此函數會觸發要求以報告使用者動作，例如點擊和轉換。它不會在回應中傳遞活動。 |
| [mboxCreate(mbox，params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at. js1.x) | 執行要求並將選件套用至具有 mboxDefault 類別名稱的最接近 DIV。<br>**注意：** 此函數適用於at. js第版。*x* 版。在. js2.x發行時停用此函數。如果與at. js2.x搭配使用，此函數會傳回預設內容。 |
| [mboxDefine(選項)和mboxUpdate(選項)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at. js1.x) | 定義和更新 mbox。<br>**注意：** 此函數適用於at. js第版。*x* 版。在. js2.x發行時停用此函數。如果與at. js2.x搭配使用，此函數會傳回預設內容。 |
| [targetGlobalSettings(選項)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 您可以覆寫at at. js程式庫中的設定，而不是在Target `targetGlobalSettings()`Standard/Premium UI中設定設定，或使用REST API。<ul><li>資料供應商：此設定可讓客戶收集第三方資料供應商(例如Demandbase、BlueKai和自訂服務)的資料，並將資料傳遞至全域mbox請求中的mbox參數。</li></ul> |
| [targetPageParams(選項)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | 此方法允許您將參數從要求程式碼外部附加至全域 mbox。 |
| [targetPageParmsAll(選項)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | 此方法允許您將參數從要求程式碼外部附加至所有 mbox。 |
| [registerExtension(選項)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at. js1.x) | 提供標準方式來註冊特定的延伸模組。<br>**注意：** 此函數適用於at. js第版。*x* 版。在. js2.x發行時停用此函數。如果與at. js2.x搭配使用，此函數會傳回預設內容。 |
| [at.js 自訂事件](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | at. js自訂事件可讓您得知mbox請求或選件拒絕或失敗的時機。 |
