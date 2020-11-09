---
keywords: Browsers;Prerequisites;Requirements;internet explorer;chrome;firefox;safari;android;surface
description: Adobe Target 應用程式和內容傳遞已針對廣泛的瀏覽器和裝置進行測試。
title: 受支援的瀏覽器
feature: reference general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 86%

---


# 受支援的瀏覽器{#supported-browsers}

[!DNL Adobe Target] 應用程式和內容傳遞已針對廣泛的瀏覽器和裝置進行測試。

如需 TLS 的其他重要資訊，請參閱 [TLS (傳輸層安全性) 加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。

## [!DNL Target] Standard/Premium 介面 {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

The [!DNL Target] interface supports the following browsers and devices:

| 裝置類型 | 瀏覽器版本 |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (最新版本、最新版本減 1)</li><li>Mozilla Firefox (最新版本、最新版本減 1)</li></ul> |
| Mac | <ul><li>Firefox (最新版本、最新版本減 1)</li><li>Chrome (最新版本、最新版本減 1)</li></ul> |

## 內容傳遞 {#section_1045A946056441268D40025529918D3D}

內容傳送已對下列瀏覽器和裝置進行測試:

| 裝置類型 | 瀏覽器版本 |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 和 10.在模擬模式中測試。<br>**注意:** at.js 1.3.0 (和更新版本) 不再支援 Microsoft Internet Explorer 9 上的內容傳遞。</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Chrome (最新版本、最新版本減 1)</li><li>Firefox (最新版本、最新版本減 1)</li></ul> |
| Mac | <ul><li>Apple Safari (最新版本)<br>**注意:** 如需 Safari 如何處理第一方和第三方 Cookie 的相關資訊，請參閱 [Target Cookie](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md)。</li><li>Firefox (最新版本、最新版本減 1)</li><li>Chrome (最新版本、最新版本減 1)</li></ul> |
| 行動裝置/平板電腦 | <ul><li>Apple iOS (最新版本)</li><li>Android 裝置和平板電腦 (Android 4 和更新版本)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

請注意下列事項：

* 針對 [!DNL at.js] 實作，[!DNL Target] 會在舊版 Internet Explorer 中並可能在以上所列瀏覽器的舊版本中顯示預設內容。針對 [!DNL mbox.js] 實作，[!DNL Target] 會嘗試呈現內容但可能不會成功。
* Internet Explorer將所有未知元素（例如自訂元素）視為相同的元素類型。 因此，傳送無法與自訂元素搭配使用。
* [!DNL Target] 會在以上未列出的瀏覽器中和使用[怪異模式](https://en.wikipedia.org/wiki/Quirks_mode)的瀏覽器中顯示預設內容。at.js 需要可呈現標準模式的 doctype，例如: `<!DOCTYPE html>`。
* Adobe 傳送基礎架構已受保護，2018 年 9 月 12 日起不再支援 TLS 1.0 裝置和瀏覽器。請參閱 [TLS (傳輸層安全性) 加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)，瞭解這項變更帶來的整體影響。
