---
keywords: apple;ITP;intelligent tracking prevention
description: 關於 Adobe Target 可透過 Experience Cloud ID (ECID) 資料庫 4.3 支援 Apple 的 ITP 2.1 和 ITP 2.2 之資訊。
title: Adobe Target 和 Apple ITP 支援
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 0fad08727233566dae6e948e53cda4f7acb64f6f

---


# Apple 智慧型追蹤預防 (ITP) 2.x

智慧型追蹤預防 (ITP) 是 Apple 保護 Safari 使用者隱私權的計劃。ITP 是在 2017 年首次發行，將目標鎖定於協力廠商 Cookie 的使用方式。事實上，Apple 完全封鎖了協力廠商 Cookie，進而對廣告技術和行銷技術公司造成了嚴重的問題，因為協力廠商 Cookie 通常是用來追蹤訪客及收集訪客資料。現在，Apple 正在努力朝向針對 Safari 內第一方 Cookie 的使用方式設定限制。

這些 ITP 版本包含下列限制:

| 版本 | 詳細資料 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 針對使用 `document.cookie` API 放在瀏覽器上的用戶端 Cookie 設定七天過期的上限。<br>發行日期: 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 將七天過期的上限大幅縮短為一天。<br>發行日期: 2019 年 4 月 24 日。 |

## 身為 Adobe Target 客戶，這對我有何影響? {#impact}

[!DNL Target] 提供 JavaScript 程式庫，讓您在頁面上進行部署，這樣 [!DNL Target] 就能向訪客提供即時個人化內容。有三個 Target JavaScript 程式庫 ([at.js 1.x and at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md), and [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) that place client-side [!DNL Target] cookies on your visitors&#39; browsers via the `document.cookie` API. 因此，[!DNL Target] Cookie 會受到 Apple ITP 2.1 和 2.2 的影響，且將在七天後過期 (若是 ITP 2.1) 以及在一天後過期 (若是 ITP 2.2)。

Apple ITP 2.1 和 2.1 會影響 [!DNL Target] 的以下方面:

| 影響 | 詳細資料 |
| --- | --- |
| 獨特訪客計數可能會增加 | 由於過期時間設為七天 (若是 ITP 2.1) 和一天 (若是 ITP 2.2)，您可能會發現來自 Safari 瀏覽器的獨特訪客增加。如果訪客在七天後 (ITP 2.1) 或一天後 (ITP 2.2) 重新造訪網域，[!DNL Target] 會強制將新的 [!DNL Target] Cookie 放在網域上，來取代過期的 Cookie。即使是相同的使用者，新的 [!DNL Target] Cookie 會將其轉譯為新的獨特訪客。 |
| 縮短 [!DNL Target] 活動的回顧期 | [!DNL Target] 活動的訪客設定檔可能已針對決策功能縮短回顧期間。系統會運用 [!DNL Target] Cookie 來識別訪客，並針對個人化儲存使用者設定檔屬性。有鑑於 Safari 上的 [!DNL Target] Cookie 可能會在七天後 (ITP 2.1) 或一天後 (ITP 2.2) 過期，繫結至已清除的 [!DNL Target] Cookie 的使用者設定檔資料則無法用決策功能。 |
| 基於3rdPartyID的描述檔指令碼 | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2），因此，以第 [](/help/c-target/c-visitor-profile/profile-parameters.md) 3rdPartyID Cookie為基礎的描述檔指令碼在到期時將停止運作。 |
| iOS裝置中的QA/預覽URL | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2）, [QA/預覽URL](/help/c-activities/c-activity-qa/activity-qa.md) 將在過期時停止運作，因為URL是以第3rdPartyID Cookie為基礎。 |

## 我目前的 [!DNL Target] 實施是否會受到影響?

在 Safari 瀏覽器中，導覽至您擁有 [!DNL Target] JavaScript 程式庫的網站。如果您在 CNAME 的內容中看到 [!DNL Target] Cookie 設定 (例如 `analytics.company.com`)，則表示您未受到 ITP 2.1 或 2.2 的影響。

如果您除了 Target JavaScript 程式庫以外還使用 Experience Cloud ID (ECID) 資料庫，您的實施會以本文列出的方式受到影響: [Safari ITP 2.1 對 Adobe Experience Cloud 和 Experience Platform 客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 如何減少 ITP 2.1、ITP 2.2 和未來 ITP 版本對 [!DNL Target] 的影響?

為減少 ITP 2.1、ITP 2.2 和未來 ITP 版本對 [!DNL Target] 的影響，請完成下列工作:

1. 將 Experience Cloud ID (ECID) 資料庫部署至頁面。

   ECID 資料庫會針對 Experience Cloud Core 解決方案啟用使用者識別架構。ECID 資料庫可讓您指派持續和唯一的 ID，在不同的 Experience Cloud 解決方案中識別相同的網站訪客及其資料。ECID 資料庫會經常更新，協助您減少任何 ITP 相關變更對實施的影響。

   對於ITP 2.1和ITP 2.2, [ECID程式庫4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) ，必須用於緩解。

1. 在 Adobe Analytics Managed Certificate 方案中使用 Adobe 的 CNAME 並註冊。

   安裝 ECID 資料庫 4.3.0+ 後，您可以運用 Adobe Analytics 的 CNAME 和 Managed Certificate 方案。此程式可讓您免費針對第一方 Cookie 實施第一方認證。運用 CNAME 將能協助 [!DNL Target] 客戶減少 ITP 2.1 和 ITP 2.2 的影響。

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

在搭配 ECID 資料庫 v4.3.0+ 部署 Target JavaScript 程式庫並在 Adobe Managed Certificate 方案中註冊以運用 CNAME 後，針對 ITP 相關變更，您將有健全且長期的緩解計劃。

在產業大幅演進並為消費者打造更安全 Web 環境的同時，[!DNL Adobe Target] 全心致力於提供個人化體驗，同時符合並超越訪客對於隱私權的期望。除了支援 Apple ITP 2.1 和 ITP 2.2，[!DNL Adobe Target] 已宣佈支援 [Google 的 SameSite Chrome 原則](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md)。

隨著原則為了保護消費者而不斷演進，[!DNL Adobe] 也會持續在 [!DNL Target] 中支援這些計劃，同時協助客戶提供同級最佳的個人化體驗。
