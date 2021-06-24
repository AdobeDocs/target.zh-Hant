---
keywords: mbox.js faq;mbox.js 常見問題集;document.write;tt.omtrdc.net;剖析器封鎖
description: 了解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform Web SDK(AEP Web SDK)或最新版at.js。
title: 關於 [!DNL Target] mbox.js的一些常見問題是什麼？
feature: at.js
role: Developer
exl-id: 0e207896-d45b-45f9-8556-6532fda72a45
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 75%

---

# mbox.js 常見問題

關於 mbox.js 常見問題的回答。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免您的網站出現任何潛在問題。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## 為什麼在我的網頁上 mbox 不會觸發? {#section_4BA5DA424B734324AAB51E4588FA50F5}

 客戶有時使用雲端型例項搭配 [!DNL Target]Target 進行測試或簡單的概念證明用途。這些網域和許多其他網域均屬於[公用字尾清單](https://publicsuffix.org/list/public_suffix_list.dat)。

如果您使用這些網域，則現代瀏覽器不會儲存 Cookie，除非您使用 targetGlobalSettings() 自訂 `cookieDomain` 設定。如需詳細資訊，請參閱[使用雲端型例項搭配 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566)。

## [!DNL Target]伺服器呼叫的目標網域tt.omtrdc.net為何？ {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] 是 Adobe 之 EDGE 網路的網域名稱，用來接收 Target 的所有伺服器呼叫。

## 為何 at.js 和 mbox.js 不使用 HttpOnly 與 Secure Cookie 旗標? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly 只能透過伺服器端編碼來設定。Mbox 之類的 Target Cookie 是透過 JavaScript 編碼來建立與儲存，因此 Target 無法使用 HttpOnly Cookie 旗標。

Secure 只有在頁面是經由 HTTPS 來載入時，能透過 JavaScript 設定。如果頁面一開始是透過 HTTP 載入，JavaScript 無法設定此旗標。此外，如果 Secure 旗標已使用，則只有 HTTPS 頁面可使用 Cookie。

為確保 Target 能正確追蹤使用者，且由於 Cookie 都是在用戶端產生，Target 不會使用這兩種旗標。
