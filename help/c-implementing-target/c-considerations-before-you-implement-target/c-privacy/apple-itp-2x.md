---
keywords: apple;ITP；智慧型追蹤預防；experience cloud id;ecid;itp
description: 了解Adobe [!DNL Target] 以及Apple智慧型追蹤預防(ITP)計畫對保護Safari使用者隱私的影響。
title: ' [!DNL Target] 如何處理Apple ITP支援？'
feature: 隱私權與安全性
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: 898a18cbd9c6f499f9e7b74078575bc149c9a292
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 38%

---

# Apple 智慧型追蹤預防 (ITP) 2.x

智慧型追蹤預防 (ITP) 是 Apple 保護 Safari 使用者隱私權的計劃。ITP 是在 2017 年首次發行，將目標鎖定於協力廠商 Cookie 的使用方式。事實上，Apple 完全封鎖了協力廠商 Cookie，進而對廣告技術和行銷技術公司造成了嚴重的問題，因為協力廠商 Cookie 通常是用來追蹤訪客及收集訪客資料。現在，Apple 正在努力朝向針對 Safari 內第一方 Cookie 的使用方式設定限制。

這些 ITP 版本包含下列限制:

| 版本 | 詳細資料 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 針對使用 `document.cookie` API 放在瀏覽器上的用戶端 Cookie 設定七天過期的上限。<br>發行日期: 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 將七天過期的上限大幅縮短為一天。<br>發行日期: 2019 年 4 月 24 日。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | 消除了幾項因應措施，例如使用localStorage或使用JavaScript `Document.referrer property`。<br>發行日期： 2019年9月23日。<br>在Safari 14、macOS Big Sur、Catalina、Mojave、iOS 14和iPadOS 14中發行的ITP CNAME隱匿防禦功能。所有由第三方CNAME隱藏的HTTP回應建立的Cookie都將設為在七天後過期。<br>2020年11月12日宣佈。 |

## 作為Adobe[!DNL Target]客戶，對我有何影響？ {#impact}

[!DNL Target] 提供 JavaScript 程式庫，讓您在頁面上進行部署，這樣 [!DNL Target] 就能向訪客提供即時個人化內容。有三個Target JavaScript資料庫at.js 1.x、at.js 2.x，可透過`document.cookie` API將用戶端[!DNL Target] Cookie放置在訪客的瀏覽器上。 因此，[!DNL Target] Cookie會受到Apple ITP 2.1、2.2和2.3的影響，且將在七天後過期（若是ITP 2.1）以及在一天後過期（若是ITP 2.2和ITP 2.3）。

Apple ITP 2.x在以下方面影響[!DNL Target]:

| 影響 | 詳細資料 |
| --- | --- |
| 獨特訪客計數可能會增加 | 由於過期時間設為七天（若是ITP 2.1）和一天（若是ITP 2.2和ITP 2.3），您可能會發現來自Safari瀏覽器的獨特訪客增加。 如果訪客在七天後(ITP 2.1)或一天後（ITP 2.2和ITP 2.3）重新造訪網域， [!DNL Target]會強制將新的[!DNL Target] Cookie放在網域上，來取代過期的Cookie。 即使是相同的使用者，新的 [!DNL Target] Cookie 會將其轉譯為新的獨特訪客。 |
| 縮短 [!DNL Target] 活動的回顧期 | [!DNL Target] 活動的訪客設定檔可能已針對決策功能縮短回顧期間。系統會運用 [!DNL Target] Cookie 來識別訪客，並針對個人化儲存使用者設定檔屬性。鑑於Safari上的[!DNL Target] Cookie可能會在七天後(ITP 2.1)或一天後（ITP 2.2和2.3）過期，系結至已清除的[!DNL Target] Cookie的使用者設定檔資料無法用於決策功能。 |
| 基於 3rdPartyID 的設定檔指令碼 | 由於過期時間設為七天（若是ITP 2.1）和一天（若是ITP 2.2和ITP 2.3），基於3rdPartyID Cookie的[設定檔指令碼](/help/c-target/c-visitor-profile/profile-parameters.md)將在過期時停止運作。 |
| iOS 裝置內的 QA/Preview URL | 由於過期時間設為七天（若是ITP 2.1）和一天（若是ITP 2.2和ITP 2.3）,[QA/預覽URL](/help/c-activities/c-activity-qa/activity-qa.md)將在過期時停止運作，因為URL是以3rdPartyID Cookie為基礎。 |

## 我目前的 [!DNL Target] 實施是否會受到影響?

如果您除了[!DNL Target] JavaScript程式庫以外還使用Experience CloudID(ECID)程式庫，您的實作會以本文列出的方式受到影響：[Safari ITP 2.1對Adobe Experience Cloud和Experience Platform客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。
