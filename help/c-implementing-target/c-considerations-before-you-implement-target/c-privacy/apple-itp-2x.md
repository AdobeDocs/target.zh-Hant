---
keywords: apple;ITP;intelligent tracking prevention
description: 透過Experience Cloud ID(ECID)程式庫4.3，瞭解Apple ITP 2.x的Adobe Target支援。
title: Adobe Target 和 Apple ITP 支援
feature: privacy and security
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 54%

---


# Apple 智慧型追蹤預防 (ITP) 2.x

智慧型追蹤預防 (ITP) 是 Apple 保護 Safari 使用者隱私權的計劃。ITP 是在 2017 年首次發行，將目標鎖定於協力廠商 Cookie 的使用方式。事實上，Apple 完全封鎖了協力廠商 Cookie，進而對廣告技術和行銷技術公司造成了嚴重的問題，因為協力廠商 Cookie 通常是用來追蹤訪客及收集訪客資料。現在，Apple 正在努力朝向針對 Safari 內第一方 Cookie 的使用方式設定限制。

這些 ITP 版本包含下列限制:

| 版本 | 詳細資料 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 針對使用 `document.cookie` API 放在瀏覽器上的用戶端 Cookie 設定七天過期的上限。<br>發行日期: 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 將七天過期的上限大幅縮短為一天。<br>發行日期: 2019 年 4 月 24 日。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | 已消除數種解決方法，例如使用localStorage或使用JavaScript `Document.referrer property`。<br>2019年9月23日發行。 |

## 身為 Adobe Target 客戶，這對我有何影響? {#impact}

[!DNL Target] 提供 JavaScript 程式庫，讓您在頁面上進行部署，這樣 [!DNL Target] 就能向訪客提供即時個人化內容。有三個 Target JavaScript 程式庫 ([at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md), and [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) that place client-side [!DNL Target] cookies on your visitors&#39; browsers via the `document.cookie` API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.x and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2 and ITP 2.3).

Apple ITP 2.x在下列 [!DNL Target] 方面有影響：

| 影響 | 詳細資料 |
| --- | --- |
| 獨特訪客計數可能會增加 | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2和ITP 2.3），您可能會看到來自Safari瀏覽器的獨特訪客增加。 If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2 and ITP 2.3), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. 即使是相同的使用者，新的 [!DNL Target] Cookie 會將其轉譯為新的獨特訪客。 |
| 縮短 [!DNL Target] 活動的回顧期 | [!DNL Target] 活動的訪客設定檔可能已針對決策功能縮短回顧期間。系統會運用 [!DNL Target] Cookie 來識別訪客，並針對個人化儲存使用者設定檔屬性。Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2 and 2.3), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |
| 基於3rdPartyID的描述檔指令碼 | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2和ITP 2.3），因此，以第 [](/help/c-target/c-visitor-profile/profile-parameters.md) 3rdPartyID Cookie為基礎的描述檔指令碼在有效期間時將停止運作。 |
| iOS裝置中的QA/預覽URL | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2和ITP 2.3）, [QA/預覽URL](/help/c-activities/c-activity-qa/activity-qa.md) 將在到期時停止運作，因為URL是以第三方ID Cookie為基礎。 |

## 我目前的 [!DNL Target] 實施是否會受到影響?

在 Safari 瀏覽器中，導覽至您擁有 [!DNL Target] JavaScript 程式庫的網站。If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

如果您除了 Target JavaScript 程式庫以外還使用 Experience Cloud ID (ECID) 資料庫，您的實施會以本文列出的方式受到影響: [Safari ITP 2.1 對 Adobe Experience Cloud 和 Experience Platform 客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 我要如何減輕未來ITP 2.x版本對Target的影響？

若要降低未來ITP 2.x版本對Target的影響，請完成下列工作：

1. 將 Experience Cloud ID (ECID) 資料庫部署至頁面。

   ECID 資料庫會針對 Experience Cloud Core 解決方案啟用使用者識別架構。ECID 資料庫可讓您指派持續和唯一的 ID，在不同的 Experience Cloud 解決方案中識別相同的網站訪客及其資料。ECID 資料庫會經常更新，協助您減少任何 ITP 相關變更對實施的影響。

   對於ITP 2.x，必 [須使用ECID程式庫4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html) ，以進行緩解。

1. 在 Adobe Analytics Managed Certificate 方案中使用 Adobe 的 CNAME 並註冊。

   安裝 ECID 資料庫 4.3.0+ 後，您可以運用 Adobe Analytics 的 CNAME 和 Managed Certificate 方案。此程式可讓您免費針對第一方 Cookie 實施第一方認證。Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.x.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

在搭配 ECID 資料庫 v4.3.0+ 部署 Target JavaScript 程式庫並在 Adobe Managed Certificate 方案中註冊以運用 CNAME 後，針對 ITP 相關變更，您將有健全且長期的緩解計劃。

在產業大幅演進並為消費者打造更安全 Web 環境的同時，[!DNL Adobe Target] 全心致力於提供個人化體驗，同時符合並超越訪客對於隱私權的期望。[!DNL Adobe Target] 除了支援 [Apple的ITP 2.x外，已宣佈支援Google的SameSite Chrome Policies](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) 。

隨著原則為了保護消費者而不斷演進，[!DNL Adobe] 也會持續在 [!DNL Target] 中支援這些計劃，同時協助客戶提供同級最佳的個人化體驗。
