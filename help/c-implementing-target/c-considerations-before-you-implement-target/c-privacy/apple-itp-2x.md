---
keywords: apple;ITP；智慧跟蹤預防；experience cloud id;ecid
description: 瞭解Adobe Target以及Apple Intelligent Tracking Prevention(ITP)計畫的影響，該計畫旨在保護Safari使用者的隱私權。
title: Target如何處理Apple ITP支援？
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 51%

---


# Apple 智慧型追蹤預防 (ITP) 2.x

透過Experience Cloud ID(ECID)程式庫4.3支援Apple ITP 2.x的[!DNL Adobe Target]資訊。

智慧型追蹤預防 (ITP) 是 Apple 保護 Safari 使用者隱私權的計劃。ITP 是在 2017 年首次發行，將目標鎖定於協力廠商 Cookie 的使用方式。事實上，Apple 完全封鎖了協力廠商 Cookie，進而對廣告技術和行銷技術公司造成了嚴重的問題，因為協力廠商 Cookie 通常是用來追蹤訪客及收集訪客資料。現在，Apple 正在努力朝向針對 Safari 內第一方 Cookie 的使用方式設定限制。

這些 ITP 版本包含下列限制:

| 版本 | 詳細資料 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 針對使用 `document.cookie` API 放在瀏覽器上的用戶端 Cookie 設定七天過期的上限。<br>發行日期: 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 將七天過期的上限大幅縮短為一天。<br>發行日期: 2019 年 4 月 24 日。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | 已消除數種解決方法，例如使用localStorage或使用JavaScript `Document.referrer property`。<br>2019年9月23日發行。 |

## 身為 Adobe Target 客戶，這對我有何影響? {#impact}

[!DNL Target] 提供 JavaScript 程式庫，讓您在頁面上進行部署，這樣 [!DNL Target] 就能向訪客提供即時個人化內容。有三個 Target JavaScript 程式庫 ([at.js 1.x、at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md))，透過`document.cookie` API將用戶端[!DNL Target] Cookie置於訪客的瀏覽器上。 因此，[!DNL Target] Cookies會受Apple的ITP 2.x影響，並會在七天後（使用ITP 2.1）和一天後（使用ITP 2.2和ITP 2.3）到期。

Apple ITP 2.x在下列方面會影響[!DNL Target]:

| 影響 | 詳細資料 |
| --- | --- |
| 獨特訪客計數可能會增加 | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2和ITP 2.3），您可能會看到來自Safari瀏覽器的獨特訪客增加。 如果您的訪客在七天(ITP 2.1)或一天（ITP 2.2和ITP 2.3）後再次造訪您的網域，則[!DNL Target]會被迫在您的網域上放置新的[!DNL Target] Cookie，以取代過期的Cookie。 即使是相同的使用者，新的 [!DNL Target] Cookie 會將其轉譯為新的獨特訪客。 |
| 縮短 [!DNL Target] 活動的回顧期 | [!DNL Target] 活動的訪客設定檔可能已針對決策功能縮短回顧期間。系統會運用 [!DNL Target] Cookie 來識別訪客，並針對個人化儲存使用者設定檔屬性。由於[!DNL Target] Cookie可在7天(ITP 2.1)或1天（ITP 2.2和2.3）後於Safari上過期，因此系結至已清除[!DNL Target] Cookie的使用者描述檔資料無法用於決策。 |
| 基於3rdPartyID的描述檔指令碼 | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2和ITP 2.3），根據第3rdPartyID Cookie的[描述檔指令碼](/help/c-target/c-visitor-profile/profile-parameters.md)將在過期時停止運作。 |
| iOS裝置中的QA/預覽URL | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2和ITP 2.3）,[QA/預覽URL](/help/c-activities/c-activity-qa/activity-qa.md)將在過期時停止運作，因為URL是以第3rdPartyID Cookie為基礎。 |

## 我目前的 [!DNL Target] 實施是否會受到影響?

在 Safari 瀏覽器中，導覽至您擁有 [!DNL Target] JavaScript 程式庫的網站。如果您在CNAME的內容中看到設定[!DNL Target] Cookie，例如`analytics.company.com`，則不會受到ITP 2.x的影響。

如果您除了 Target JavaScript 程式庫以外還使用 Experience Cloud ID (ECID) 資料庫，您的實施會以本文列出的方式受到影響: [Safari ITP 2.1 對 Adobe Experience Cloud 和 Experience Platform 客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 我要如何減輕未來ITP 2.x版本對Target的影響？

若要降低未來ITP 2.x版本對Target的影響，請完成下列工作：

1. 將 Experience Cloud ID (ECID) 資料庫部署至頁面。

   ECID 資料庫會針對 Experience Cloud Core 解決方案啟用使用者識別架構。ECID 資料庫可讓您指派持續和唯一的 ID，在不同的 Experience Cloud 解決方案中識別相同的網站訪客及其資料。ECID 資料庫會經常更新，協助您減少任何 ITP 相關變更對實施的影響。

   對於ITP 2.x,[ECID庫4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html)必須用於緩解。

1. 在 Adobe Analytics Managed Certificate 方案中使用 Adobe 的 CNAME 並註冊。

   安裝 ECID 資料庫 4.3.0+ 後，您可以運用 Adobe Analytics 的 CNAME 和 Managed Certificate 方案。此程式可讓您免費針對第一方 Cookie 實施第一方認證。利用CNAME將幫助[!DNL Target]客戶減輕ITP 2.x的影響。

   如果您未運用CNAME，則可以先與帳戶代表通話，然後註冊[Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)，開始此程式。

在搭配 ECID 資料庫 v4.3.0+ 部署 Target JavaScript 程式庫並在 Adobe Managed Certificate 方案中註冊以運用 CNAME 後，針對 ITP 相關變更，您將有健全且長期的緩解計劃。

在產業大幅演進並為消費者打造更安全 Web 環境的同時，[!DNL Adobe Target] 全心致力於提供個人化體驗，同時符合並超越訪客對於隱私權的期望。[!DNL Adobe Target] 已宣佈支援 [Google的SameSite Chrome ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Policies，以支援Apple的ITP 2.x。

隨著原則為了保護消費者而不斷演進，[!DNL Adobe] 也會持續在 [!DNL Target] 中支援這些計劃，同時協助客戶提供同級最佳的個人化體驗。
