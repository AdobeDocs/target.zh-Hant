---
keywords: cloud instances;public suffix list;public suffix;cookie;first-party cookie;1st-party cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: 關於客戶使用雲端型例項來測試 Adobe Target 時所面臨問題的資訊。
title: 使用雲端型例項搭配 Target
feature: client-side
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 95%

---


# 使用雲端型例項搭配 Target{#use-cloud-based-instances-with-target}

關於客戶使用雲端型例項來測試 [!DNL Adobe Target] 時所面臨問題的資訊。

 客戶有時使用雲端型例項搭配 [!DNL Target]Target 進行測試或簡單的概念證明用途。這些例項可能包含下列網域:

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com` 或 `firebaseapp.com`

這些網域和許多其他網域均屬於[公用字尾清單](https://publicsuffix.org/list/public_suffix_list.dat)。

**問題:** 如果您使用這些網域，新式瀏覽器不會儲存 Cookie。

[!DNL at.js] 和 [!DNL mbox.js] JavaScript 程式庫會使用 Cookie 來追蹤使用者，以確保 [!DNL Target] 永遠展現一致的體驗。如果 [!DNL Target] JavaScript 程式庫無法儲存 Cookie，[!DNL Target] 請求會停用。

**解決方案:**&#x200B;如果您想要搭配「公用尾碼清單」上包含的網域來使用雲端式例項，最佳做法是自訂 `cookieDomain` 設定。如需詳細資訊，請參閱 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。
