---
keywords: apple;ITP；智慧跟蹤預防；體驗雲ID;ecid;itp
description: 瞭解Adobe [!DNL Target] 以及Apple智慧跟蹤預防(ITP)計畫的影響，該計畫旨在保護Safari用戶的隱私。
title: 如何 [!DNL Target] 處理AppleITP支援？
feature: Privacy & Security
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 38%

---

# Apple 智慧型追蹤預防 (ITP) 2.x

智慧型追蹤預防 (ITP) 是 Apple 保護 Safari 使用者隱私權的計劃。ITP 是在 2017 年首次發行，將目標鎖定於協力廠商 Cookie 的使用方式。事實上，Apple 完全封鎖了協力廠商 Cookie，進而對廣告技術和行銷技術公司造成了嚴重的問題，因為協力廠商 Cookie 通常是用來追蹤訪客及收集訪客資料。現在，Apple 正在努力朝向針對 Safari 內第一方 Cookie 的使用方式設定限制。

這些 ITP 版本包含下列限制:

| 版本 | 詳細資料 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 針對使用 `document.cookie` API 放在瀏覽器上的用戶端 Cookie 設定七天過期的上限。<br>發行日期: 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 將七天過期的上限大幅縮短為一天。<br>發行日期: 2019 年 4 月 24 日。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | 消除了幾種變通辦法，如使用localStorage或使用JavaScript `Document.referrer property`。<br>2019年9月23日發佈。<br>CNAME-Cloging防禦功能在Safari 14、macOS大南、卡塔利納、莫哈韋、iOS14和iPadOS 14中發佈。 由第三方CNAME掩蔽的HTTP響應建立的所有Cookie將設定為在七天內過期。<br>2020年11月12日宣佈。 |

## 作為Adobe，對我有什麼影響 [!DNL Target] 客戶？ {#impact}

[!DNL Target] 提供 JavaScript 程式庫，讓您在頁面上進行部署，這樣 [!DNL Target] 就能向訪客提供即時個人化內容。有三個目標JavaScript庫at.js 1.x, at.js 2.x放置客戶端 [!DNL Target] 訪問者瀏覽器上的cookie `document.cookie` API。 因此， [!DNL Target] Cookie受AppleITP 2.1、2.2和2.3的影響，將在7天後（使用ITP 2.1）和1天後（使用ITP 2.2和ITP 2.3）過期。

AppleITP 2.x影響 [!DNL Target] 在以下區域中：

| 影響 | 詳細資料 |
| --- | --- |
| 獨特訪客計數可能會增加 | 由於過期窗口設定為七天(ITP 2.1)和一天（ITP 2.2和ITP 2.3），您可能會看到來自Safari瀏覽器的獨特訪問者增加。 如果訪問者在七天後(ITP 2.1)或一天（ITP 2.2和ITP 2.3）再次訪問您的域， [!DNL Target] 被迫在 [!DNL Target] 域上的cookie代替過期的cookie。 即使是相同的使用者，新的 [!DNL Target] Cookie 會將其轉譯為新的獨特訪客。 |
| 縮短 [!DNL Target] 活動的回顧期 | [!DNL Target] 活動的訪客設定檔可能已針對決策功能縮短回顧期間。系統會運用 [!DNL Target] Cookie 來識別訪客，並針對個人化儲存使用者設定檔屬性。鑑於 [!DNL Target] Cookie可在七天(ITP 2.1)或一天（ITP 2.2和2.3）後在Safari過期，這是與已清除的用戶配置檔案資料關聯 [!DNL Target] cookie不能用於決策。 |
| 基於 3rdPartyID 的設定檔指令碼 | 由於過期時間被設為七天(ITP 2.1)和一天（ITP 2.2和ITP 2.3）, [配置檔案指令碼](/help/main/c-target/c-visitor-profile/profile-parameters.md) 基於3rdPartyIDcookie將在到期後停止工作。 |
| iOS 裝置內的 QA/Preview URL | 由於過期時間被設為七天(ITP 2.1)和一天（ITP 2.2和ITP 2.3）, [QA/預覽URL](/help/main/c-activities/c-activity-qa/activity-qa.md) 將在過期時停止運行，因為URL基於第3PartyIDcookie。 |

## 我目前的 [!DNL Target] 實施是否會受到影響?

如果除Experience CloudID(ECID)庫外， [!DNL Target] JavaScript庫，您的實現將受本文所列方式的影響： [Safari ITP 2.1對Adobe Experience Cloud和Experience Platform客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。
