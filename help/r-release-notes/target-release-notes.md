---
description: 發行說明，提供最新或即將到來[！DNL Adobe Target]發行。
keywords: 版本說明
seo-description: 發行說明，提供最新或即將到來[！DNL Adobe Target]發行。
seo-title: Adobe Target發行說明(搶鮮版)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新日期: 2019 年 7 月 24 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (2019 年 7 月 24 日) {#tgt-19-7-1}

此版本包含下列新功能和增強功能:

| 功能 / 增強功能 | 說明 |
| --- | --- |
| 行動應用程式可視化體驗撰寫器 | Mobile App CMS會顯示新的「修改」面板，顯示您已設定用於點按追蹤的元素。(TGT-31741)<br> See [Set up click tracking in the Mobile App](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![A/B測試與體驗定位(XT)活動](/help/assets/premium.png)<br>中的Premium BadgereCommendations | Recommendations(演算法)狀態會顯示在「概述」頁面上，用於A/B測試和包含Recommendations選件的XT活動。狀態包括：Results Ready、Results not Ready和Feed fails.(TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| 透過Experience Cloud ID(ECID)程式庫對at. js2.0+的跨網域追蹤支援 | 以前，at. js不支援跨網域追蹤。*x* 版本不支援此函數。在此版本中，使用at. js2.0或更新版本的客戶現在可以透過ECID程式庫使用跨網域追蹤。必須將ECID程式庫與at. js2.0或以上版本一起安裝在頁面上，才能讓跨網域追蹤運作。[必須使用Experience Cloud ID庫4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 。<br>請參閱 [at. js2.x中的跨網域追蹤支援](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain)。 |
| Target支援Apple的ITP2.1和ITP2.2透過Experience Cloud ID(ECID)庫4.3 | 如今，Target客戶可以運用Adobe的CNAME認證計劃來降低Apple的ITP2.1和ITP2.2。<br>在此版本中，Target可與ECID程式庫4.3完美整合，後者運用伺服器端Cookie來降低ITP2.1和ITP2.2。強烈建議Target客戶將 [ECID程式庫4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 與Target的JavaScript程式庫搭配部署，以降低任何未來的ITP版本。ECID程式庫將繼續推行增強功能，為不斷變化的瀏覽器引進的Cookie原則提供強大的解決方案。<br>請參閱 [Apple Intelligent Tracking Premiention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。 |

**增強功能、修正和變更**

* 修正新增重復值時，Recommendations活動中排除值無法清除的問題。(TGT-34996)
* 您現在可以從「定位」頁面(三部分引導工作流程的步驟2)中移除「建議」活動中的設計。請注意，若要移除設計，必須選取多個設計。(TGT-35118)
* 修正某些客戶無法在Target UI中正確載入或可編輯的自訂條件卡問題。(TGT-35170)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
