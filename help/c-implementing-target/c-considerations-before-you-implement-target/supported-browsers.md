---
description: Adobe Target 應用程式和內容傳遞已針對廣泛的瀏覽器和裝置進行測試。
keywords: 瀏覽器;必要條件;需求;internet explorer;chrome;firefox;safari;android;surface
seo-description: Adobe Target 應用程式和內容傳遞已針對廣泛的瀏覽器和裝置進行測試。
seo-title: 受支援的瀏覽器
solution: Target
subtopic: 快速入門
title: 受支援的瀏覽器
topic: Standard
uuid: 614088da-412c-45e3-9f2d-6985391973be
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 受支援的瀏覽器{#supported-browsers}

[!DNL Adobe Target] 應用程式和內容傳遞已針對廣泛的瀏覽器和裝置進行測試。

如需 TLS 的其他重要資訊，請參閱 [TLS (傳輸層安全性) 加密變更](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。

## [!DNL Target] Standard/Premium介面 {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

[!DNL Target] Standard/Premium 介面支援下列瀏覽器和裝置:

| 裝置類型 | 瀏覽器版本 |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (最新版本、最新版本減 1)</li><li>Mozilla Firefox (最新版本、最新版本減 1)</li></ul> |
| Mac | <ul><li>Firefox (最新版本、最新版本減 1)</li><li>Chrome (最新版本、最新版本減 1)</li></ul> |

## Content delivery {#section_1045A946056441268D40025529918D3D}

內容傳送已對下列瀏覽器和裝置進行測試:

| 裝置類型 | 瀏覽器版本 |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 和 10.在模擬模式中測試。<br>**注意:** at.js 1.3.0 (和更新版本) 不再支援 Microsoft Internet Explorer 9 上的內容傳遞。</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Chrome (最新版本、最新版本減 1)</li><li>Firefox (最新版本、最新版本減 1)</li></ul> |
| Mac | <ul><li>Apple Safari (最新版本)<br>**注意:** 如需 Safari 如何處理第一方和第三方 Cookie 的相關資訊，請參閱 [Target Cookie](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md)。</li><li>Firefox (最新版本、最新版本減 1)</li><li>Chrome (最新版本、最新版本減 1)</li></ul> |
| 行動裝置/平板電腦 | <ul><li>Apple iOS (最新版本)</li><li>Android 裝置和平板電腦 (Android 4 和更新版本)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

針對 [!DNL at.js] 實作，[!DNL Target] 會在舊版 Internet Explorer 中並可能在以上所列瀏覽器的舊版本中顯示預設內容。針對 [!DNL mbox.js] 實作，[!DNL Target] 會嘗試呈現內容但可能不會成功。

[!DNL Target] 會在以上未列出的瀏覽器中和使用[怪異模式](https://en.wikipedia.org/wiki/Quirks_mode)的瀏覽器中顯示預設內容。at.js 需要可呈現標準模式的 doctype，例如: `<!DOCTYPE html>`。

>[!NOTE]
>
>Adobe 傳送基礎架構已受保護，2018 年 9 月 12 日起不再支援 TLS 1.0 裝置和瀏覽器。請參閱 [TLS (傳輸層安全性) 加密變更](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)，瞭解這項變更帶來的整體影響。
