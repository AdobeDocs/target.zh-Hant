---
keywords: at.js 外掛程式;支援的外掛程式;不支援的外掛程式;ttMeta;ttmeta;mboxTrack
description: 關於 Adobe Target 支援和不支援的 at.js 外掛程式之資訊。
title: at.js外掛程式
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 96%

---


# At.js 外掛程式

關於 Adobe Target 中支援和不支援的 at.js 外掛程式之資訊。

許多人都已針對 [!DNL mbox.js] 建立自訂的外掛程式和回應外掛程式。若不升級這些自訂外掛程式，[!DNL at.js] 可能無法予以支援。

如果您使用這裡未列出的外掛程式，但想知道狀態，請聯絡客戶代表。

以下是許多客戶搭配 [!DNL at.js] 一起使用的一些外掛程式的目前狀態:

| Plugin | 詳細資料 |
|--- |--- |
| mboxTrack | 不支援。<br>此項由 [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 函數取代。請更新外掛程式以套用新的函式。<br>請參閱[整合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md)頁面。 |
| 持續性設定檔備份外掛程式 | 不支援。<br>此外掛程式已於 Target 設定檔存留期從兩週延長到 90 天時淘汰。請檢查 mbox Cookie 的到期日，以查看帳戶的設定檔存留期設定。<br>如果您想要將設定檔存留期延長至 90 天，請聯絡客戶服務。 |
| ttMeta | 您應停用舊版 SiteCatalyst 增效模組，並改用[ Adobe Analytics 取代，作為 Adobe Target (A4T) 的報表來源](/help/c-integrating-target-with-mac/a4t/a4t.md)。應該停用 ttMeta 外掛程式並換成 [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj)。 |