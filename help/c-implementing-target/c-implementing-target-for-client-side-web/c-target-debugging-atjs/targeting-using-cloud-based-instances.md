---
keywords: 雲端例項;公用尾碼清單;公用尾碼;Cookie;第一方 Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: 探索客戶使用雲端型例項來測試Adobe [!DNL Target] 或用於概念證明時所面臨的問題（解決方案的相關問題）。
title: 我可以對雲端型例項使用 [!DNL Target] 嗎？
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 67%

---

# 使用雲端型例項搭配 Target

關於客戶使用雲端型例項來測試 [!DNL Adobe Target] 時所面臨問題的資訊。

 客戶有時使用雲端型例項搭配 [!DNL Target]Target 進行測試或簡單的概念證明用途。這些例項可能包含下列網域:

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com` 或 `firebaseapp.com`

這些網域和許多其他網域均屬於[公用字尾清單](https://publicsuffix.org/list/public_suffix_list.dat)。

**問題:** 如果您使用這些網域，新式瀏覽器不會儲存 Cookie。

[!DNL at.js] JavaScript資料庫使用Cookie來追蹤使用者，以確保[!DNL Target]一律呈現一致的體驗。 如果[!DNL Target] JavaScript程式庫無法儲存Cookie，則會停用[!DNL Target]請求。

**解決方案:**&#x200B;如果您想要搭配「公用尾碼清單」上包含的網域來使用雲端式例項，最佳做法是自訂 `cookieDomain` 設定。如需詳細資訊，請參閱 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。
