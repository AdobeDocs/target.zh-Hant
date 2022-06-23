---
keywords: 瀏覽器;必要條件;需求;internet explorer;chrome;firefox;safari;android;surface
description: 瞭解哪些Internet瀏覽器Adobe [!DNL Target] 支援其介面和內容交付。
title: 瀏覽器的功能 [!DNL Target] 支援？
feature: Implementation
role: Developer
exl-id: 8a366c79-d944-4d44-be5a-7c4f65385beb
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 44%

---

# 受支援的瀏覽器

[!DNL Adobe Target] 應用程式和內容傳遞已針對廣泛的瀏覽器和裝置進行測試。

有關TLS的更重要資訊，請參見 [TLS（傳輸層安全性）加密更改](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/)。

## [!DNL Target] Standard/Premium 介面 {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

的 [!DNL Target] 介面支援以下瀏覽器和設備：

| 裝置類型 | 瀏覽器版本 |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google克羅姆（最新，最新減1）</li><li>Mozilla Firefox（最新，最新減1）</li></ul> |
| Mac | <ul><li>Firefox（最新，最新減1）</li><li>Chrome（最新，最新減1）</li></ul> |

## 內容傳遞 {#section_1045A946056441268D40025529918D3D}

內容傳送已對下列瀏覽器和裝置進行測試:

| 裝置類型 | 瀏覽器版本 |
|--- |--- |
| 窗口 | <ul><li>Microsoft Internet Explorer 9 和 10. 在模擬模式中測試。<br>**注釋**:at.js 1.3.0（及更高版本）不再支援IE 9上的內容傳遞。 在IE 10、11和所有舊版本上提供內容不再受at.js 2.5.0（及更高版本）支援。</li><li>Internet Explorer 11 <br>**注釋**:在IE 10、11和所有舊版本上提供內容不再受at.js 2.5.0（及更高版本）支援。</li><li>Microsoft邊</li><li>Chrome（最新，最新減1）</li><li>Firefox（最新，最新減1）</li></ul> |
| Mac | <ul><li>Apple·薩法里（最新）<br>**注釋**:有關Safari如何處理第一方和第三方Cookie的詳細資訊，請參見 [目標Cookie](https://developer.adobe.com/target/before-implement/privacy/cookie-behavior/)。</li><li>Firefox（最新，最新減1）</li><li>Chrome（最新，最新減1）</li></ul> |
| 行動裝置/平板電腦 | <ul><li>Apple·iOS（最新）</li><li>Android 裝置和平板電腦 (Android 4 和更新版本)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

請注意：

* 針對 [!DNL at.js] 實作，[!DNL Target] 會在舊版 Internet Explorer 中並可能在以上所列瀏覽器的舊版本中顯示預設內容。
* Internet Explorer將所有未知元素（如自定義元素）視為相同的元素類型。 因此，交貨不能與自定義元素一起使用。
* [!DNL Target] 會在以上未列出的瀏覽器中和使用[怪異模式](https://en.wikipedia.org/wiki/Quirks_mode)的瀏覽器中顯示預設內容。at.js 需要可呈現標準模式的 doctype，例如: `<!DOCTYPE html>`。
* Adobe 傳送基礎架構已受保護，2018 年 9 月 12 日起不再支援 TLS 1.0 裝置和瀏覽器。請參閱 [TLS (傳輸層安全性) 加密變更](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/)，瞭解這項變更帶來的整體影響。
