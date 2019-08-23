---
description: Target中支援且不支援的. js外掛程式相關資訊。
keywords: at. js外掛程式；支援的外掛程式；不支援的外掛程式；Ttmeta；ttmeta；mboxTrack
seo-description: Adobe Target支援且不支援at. js增效模組的資訊。
seo-title: at. js增效模組for Adobe Target
solution: Target
title: at.js 外掛程式
topic: Standard
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
translation-type: tm+mt
source-git-commit: c3afa420f33f98d7c4bb332acdef7a248fe4670a

---


# at.js plug-ins{#at-js-plug-ins}

Adobe Target中支援且不支援的. js外掛程式相關資訊。

許多人都已針對 [!DNL mbox.js] 建立自訂的外掛程式和回應外掛程式。若不升級這些自訂外掛程式，[!DNL at.js] 可能無法予以支援。

如果您使用這裡未列出的外掛程式，但想知道狀態，請聯絡客戶代表。

以下是許多客戶搭配 [!DNL at.js] 一起使用的一些外掛程式的目前狀態:

| Plugin | 詳細資料 |
|--- |--- |
| mboxTrack | 不支援。<br>此項由 [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 函數取代。請更新外掛程式以套用新的函式。<br>請參閱[整合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md)頁面。 |
| 持續性設定檔備份外掛程式 | 不支援。<br>此外掛程式已於 Target 設定檔存留期從兩週延長到 90 天時淘汰。請檢查 mbox Cookie 的到期日，以查看帳戶的設定檔存留期設定。<br>如果您想要將設定檔存留期延長至 90 天，請聯絡客戶服務。 |
| ttMeta | Old SiteCatalyst plugins should be disabled and replaced with [Adobe Analytics as the reporting source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). 應該停用 ttMeta 外掛程式並換成 [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj)。 |