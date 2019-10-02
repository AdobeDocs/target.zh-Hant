---
description: Release notes that provide information about features, enhancements, and fixes for the latest or upcoming Adobe Target releases.
keywords: 發行說明；發行；更新；未來發行；增強；新功能；修正
seo-description: 提供最新或即將發行的DNL Adobe target版本功能、增強功能和修正資訊的發行說明。
seo-title: Adobe target搶鮮版注意事項
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 285a09503ba6abaf2bfe19fc2b214c32ebd2de3a

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新: 2019 年 10 月 2 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>括號內的問題編號供 [!DNL Adobe] 內部使用。

## 目標平台（待確定日期）

| 功能/增強功能 | 說明 |
| --- | --- |
| Node.js SDK 1.0版 | The Target Node.js SDK lets you deploy Target server-side.<br>This Node.js SDK helps you easily integrate Target with other Experience Cloud solutions, such as the Adobe Experience Cloud Identity Service, Adobe Analytics, and Adobe Audience Manager.<br>The Node.js SDK introduces best practices and removes complexities when integrating with Adobe Target via our delivery API so that your engineering teams can focus on business logic. The following are notable features that we are introducing in the latest version:<ul><li>Support for prefetching and notifications that allows you to optimize for performance via caching.</li><li>支援在網頁和伺服器端混合整合Target時最佳化效能。 We are introducing a setting called  that will be populated by experiences retrieved via the server-side so that at.js 2.2 will no longer make an additional server call to retrieve the experiences. `serverState`此方法可最佳化頁面載入效能。</li><li> 支援透過Node.js SDK擷取VEC建立的活動，此為新的傳送API所提供。</li><li>開放來源，讓您的開發人員可以為Node.js SDK貢獻心力。</li></ul> |
| Delivery API | 生產中將提供全新的傳送API端點（/v1/傳送）。 主要功能包括：<ul><li>一個端點，可擷取一或多個mbox的體驗。</li><li>透過API擷取VEC建立的活動。</li><li>支援稱為「檢視」的全新物件，用於單頁應用程式(SPA)和行動應用程式。</li></ul> |
| at.js 2.2<br><br>andat.js 1.8版 | 這些版本的at.js提供：<ul><li>已改善在網頁上同時使用Experience Cloud ID Service(ECID)v4.4和at.js 2.2或at.js 1.8時的效能。</li><li>之前，ECID曾進行兩次封鎖呼叫，之後at.js才能擷取體驗。 這已簡化為單一呼叫，可大幅提升效能。</li></ul> 為運用這些效能改良功能，請升級至at.js 2.2或at.js 1.8以及ECID Library v4.4。 |


## Target Standard/Premium 19.10.1 (2019 年 10 月 22 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) User-Based Recommendations | 根據每位訪客的瀏覽、檢視和購買記錄來建議項目。 這些項目通常稱為「為您推薦」。<br>This criteria lets you deliver personalized content and experiences to both new and returning visitors. The list of recommendations is weighted towards the visitor's most-recent activity and is updated in-session and becomes more personalized as the visitor browses your site. |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
