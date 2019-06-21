---
description: 關於客戶使用雲端型例項來測試 Adobe Target 時所面臨問題的資訊。
keywords: 雲端例項;公用尾碼清單;公用尾碼;Cookie;第一方 Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
seo-description: 關於客戶使用雲端型例項來測試 Adobe Target 時所面臨問題的資訊。
seo-title: 使用雲端型例項搭配 Target
solution: Target
title: 使用雲端型例項搭配 Target
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 使用雲端型例項搭配 Target{#use-cloud-based-instances-with-target}

關於客戶使用雲端型例項來測試 [!DNL Adobe Target] 時所面臨問題的資訊。

 客戶有時使用雲端型例項搭配 [!DNL Target]Target 進行測試或簡單的概念證明用途。這些例項可能包含下列網域:

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com` 或 `firebaseapp.com`

這些網域和許多其他網域均屬於[公用字尾清單](https://publicsuffix.org/list/public_suffix_list.dat)。

**問題:** 如果您使用這些網域，新式瀏覽器不會儲存 Cookie。

[!DNL at.js] 和 [!DNL mbox.js] JavaScript 程式庫會使用 Cookie 來追蹤使用者，以確保 [!DNL Target] 永遠展現一致的體驗。如果 [!DNL Target] JavaScript 程式庫無法儲存 Cookie，[!DNL Target] 請求會停用。

**解決方案:** 如果您想要搭配「公用尾碼清單」上包含的網域來使用雲端式例項，最佳做法是自訂 `cookieDomain` 設定。如需詳細資訊，請參閱 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。
