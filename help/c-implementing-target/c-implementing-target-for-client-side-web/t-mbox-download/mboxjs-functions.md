---
keywords: mbox functions
description: 使用 mbox.js 實作時要使用的 mbox.js 函數的清單。
title: mbox.js 函數
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 100%

---


# mbox.js 函數{#mbox-js-functions}

使用 mbox.js 實作時要使用的 mbox.js 函數的清單。

>[!NOTE]
>
>如果您使用 [!DNL at.js]，則這些方法不適用。

| 方法 | 附註 |
|--- |--- |
| `mbox.getName()` |  |
| `mbox.getURL()` |  |
| `mbox.getDiv()` | 傳回與 mbox 相關聯的 div (包含預設內容或選件) |
| `mbox.getParameters()` | 以兩個欄位 (名稱及值) 組成之參數的陣列 |
| `mbox.setOnError()` | 範例:<br>`mbox.setOnError(function() { alert(this.getName() +" had error"});` |
| `mbox.setMessage(message)` | 您可以在除錯視窗中看到訊息。 |
| `mboxCurrent.activate()` |  |
| `mboxCurrent.cancelTimeout()` |  |
| `mboxCurrent.finalize()` |  |
| `mboxCurrent.getDefaultDiv()` |  |
| `mboxCurrent.getDiv()` | 傳回與 mbox 相關聯的 div (包含預設內容或選件) |
| `mboxCurrent.getEventTimes()` |  |
| `mboxCurrent.getFetcher()` |  |
| `mboxCurrent.getId()` |  |
| `mboxCurrent.getImportName()` |  |
| `mboxCurrent.getName()` |  |
| `mboxCurrent.getOffer()` |  |
| `mboxCurrent.getParameters()` | 以兩個欄位 (名稱及值) 組成之參數的陣列。 |
| `mboxCurrent.getURL()` |  |
| `mboxCurrent.getURLBuilder()` |  |
| `mboxCurrent.hide()` |  |
| `mboxCurrent.isActivated`() |  |
| `mboxCurrent.load()` |  |
| `mboxCurrent.loaded()` |  |
| `mboxCurrent.setEventTime()` |  |
| `mboxCurrent.setFetcher()` |  |
| `mboxCurrent.setMessage()` |  |
| `mboxCurrent.setMessage(message)` | 在除錯視窗中檢視訊息。 |
| `mboxCurrent.setOffer()` |  |
| `mboxCurrent.setOnError()` | 範例:<br>`mboxCurrent.setOnError(function(){ alert(this.getName() +" had error"});` |
| `mboxCurrent.setOnLoad()` | 範例:<br>`mboxCurrent.setOnLoad(function(){alert(this.getName()+" loaded")});` |
| `mboxCurrent.show()` |  |
| `mboxCurrent.showContent()` |  |
| `mboxFactoryDefault.addOnLoad(action)` | 頁面載入時呼叫的動作。 |
| `mboxFactoryDefault.getMboxes().each()` | 範例:<br>`mboxFactoryDefault.getMboxes().each(function() { alert(mbox.getName()) };` |
| `mboxFactoryDefault.getMboxes().length()` |  |
| `mboxFactoryDefault.getPageId()` |  |
| `mboxFactoryDefault.getPCId().getId()` |  |
| `mboxFactoryDefault.getSessionId().getId()` |  |
| `mboxFactories.get('default').getSessionId()&#x200B;.forceId("1276011116668");` |  |
| `mboxFactories.get('default').getPCId()&#x200B;.forceId("1276011116668");` |  |
| `mboxFactoryDefault.create()` |  |
| `mboxFactoryDefault.disable()` |  |
| `mboxFactoryDefault.enable()` |  |
| `mboxFactoryDefault.get()` |  |
| `mboxFactoryDefault.getCookieManager()` |  |
| `mboxFactoryDefault.getDisableReason()` |  |
| `mboxFactoryDefault.getEllapsedTime()` |  |
| `mboxFactoryDefault.getEllapsedTimeUntil()` |  |
| `mboxFactoryDefault.getMboxes()` | 傳回 `mboxList`。 |
| `mboxFactoryDefault.getSignaler()` |  |
| `mboxFactoryDefault.getURLBuilder()` |  |
| `mboxFactoryDefault.isAdmin()` |  |
| `mboxFactoryDefault.isDomLoaded()` |  |
| `mboxFactoryDefault.isEnabled()` |  |
| `mboxFactoryDefault.isSupported()` |  |
| `mboxFactoryDefault.limitTraffic()` |  |
| `mboxFactoryDefault.update()` |  |
| `mboxFactoryDefault.getCookieManager()&#x200B;.getCookie("name")//!= null) {` |  |
| `mboxFactoryDefault.getCookieManager()&#x200B;.setCookie(_name,_value, _duration);` |  |