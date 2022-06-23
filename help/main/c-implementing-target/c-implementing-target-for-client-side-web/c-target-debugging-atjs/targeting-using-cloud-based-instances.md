---
keywords: 雲端例項;公用尾碼清單;公用尾碼;Cookie;第一方 Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: 探討客戶在使用基於雲的實例進行testAdobe時面臨的問題（使用解決方案） [!DNL Target] 或者為了概念驗證。
title: 我可以使用 [!DNL Target] 使用基於雲的實例？
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 64%

---

# 使用雲端型例項搭配 Target

關於客戶使用雲端型例項來測試 [!DNL Adobe Target] 時所面臨問題的資訊。

 客戶有時使用雲端型例項搭配 [!DNL Target]Target 進行測試或簡單的概念證明用途。這些例項可能包含下列網域:

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com` 或 `firebaseapp.com`

這些網域和許多其他網域均屬於[公用字尾清單](https://publicsuffix.org/list/public_suffix_list.dat)。

**問題:** 如果您使用這些網域，新式瀏覽器不會儲存 Cookie。

的 [!DNL at.js] JavaScript庫使用cookie跟蹤用戶以確保 [!DNL Target] 總能提供一貫的體驗。 如果 [!DNL Target] JavaScript庫無法保存Cookie, [!DNL Target] 請求被禁用。

**解決方案:**&#x200B;如果您想要搭配「公用尾碼清單」上包含的網域來使用雲端式例項，最佳做法是自訂 `cookieDomain` 設定。如需詳細資訊，請參閱 [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。
