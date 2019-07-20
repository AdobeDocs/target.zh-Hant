---
description: 這些發行說明提供最新或即將到來[！DNL Adobe Target]發行。
keywords: 版本說明
seo-description: 這些發行說明提供最新或即將到來[！DNL Adobe Target]發行。
seo-title: Adobe Target發行說明(搶鮮版)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 45d0a73faafd216b5a4686501c548f5771943050

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新日期: 2019 年 7 月 19 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (2019 年 7 月 24 日) {#tgt-19-7-1}

此版本包含下列新功能和增強功能:

| 功能 / 增強功能 | 說明 |
| --- | --- |
| 行動應用程式可視化體驗撰寫器 | Mobile App CMS會顯示新的「修改」面板，顯示您已設定用於點按追蹤的元素。(TGT-31741) |
| ![A/B測試與體驗定位(XT)活動](/help/assets/premium.png)<br>中的Premium BadgereCommendations | Recommendations(演算法)狀態會顯示在「概述」頁面上，用於A/B測試和包含Recommendations選件的XT活動。狀態包括：Results Ready、Results not Ready和Feed fails.(TGT-33649) |
| 透過Experience Cloud ID(ECID)程式庫對at. js2.0+的跨網域追蹤支援 | 以前，at. js不支援跨網域追蹤。*x* 版本不支援此函數。在此版本中，使用at. js2.0或更新版本的客戶現在可以透過ECID程式庫使用跨網域追蹤。必須將ECID程式庫與at. js2.0或以上版本一起安裝在頁面上，才能讓跨網域追蹤運作。[必須使用Experience Cloud ID庫4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 。 |
| Target支援Apple的ITP2.1和ITP2.2透過Experience Cloud ID(ECID)庫4.3 | 如今，Target客戶可以運用Adobe的CNAME認證計劃來降低Apple的ITP2.1和ITP2.2。With this release, Target introduces a seamless integration with the ECID library 4.3, which leverages a server-side cookie to mitigate ITP 2.1 and ITP 2.2. It is highly recommended that Target customers deploy [ECID library 4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) in conjunction with Target’s JavaScript library to mitigate any future ITP releases. ECID程式庫將繼續推行增強功能，為不斷變化的瀏覽器引進的Cookie原則提供強大的解決方案。 |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
