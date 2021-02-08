---
keywords: mbox.js faq;mbox.js 常見問題集;document.write;tt.omtrdc.net;剖析器封鎖
description: 瞭解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform Web SDK(AEP Web SDK)或最新版的at.js。
title: 有關Target mbox.js的一些常見問題？
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 73%

---


# mbox.js 常見問題{#mbox-js-frequently-asked-questions}

關於 mbox.js 常見問題的回答。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 將不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## mbox.js 對頁面載入時間有何影響? {#section_90B3B94FE0BF4B369577FCB97B67F089}

如需詳細資訊，請參閱 [at.js 的優點](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)。

## 使用 mbox.js 和 document.write{#section_355A3A5BF02F42EEB8271C96EF41590A} 時，在 Google Chrome 中為何出現「剖析器封鎖」警告訊息? 

在許多情況下，如果在 mbox.js 檔案內使用 `document.write` 函式，則使用 Chrom 時會出現此主控台訊息。這是警告訊息，應該不影響活動設定程序。

防止此狀況的最佳方式是[將 Target 實作移轉至 at.js JavaScript 程式庫](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)，此程式庫不使用 `document.write` 函式。使用 at.js 比使用 mbox.js 的好處更多。如需詳細資訊，請參閱 [at.js 常見問題](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769)。

## 為什麼在我的網頁上 mbox 不會觸發? {#section_4BA5DA424B734324AAB51E4588FA50F5}

 客戶有時使用雲端型例項搭配 [!DNL Target]Target 進行測試或簡單的概念證明用途。這些網域和許多其他網域均屬於[公用字尾清單](https://publicsuffix.org/list/public_suffix_list.dat)。

如果您使用這些網域，則現代瀏覽器不會儲存 Cookie，除非您使用 targetGlobalSettings() 自訂 `cookieDomain` 設定。如需詳細資訊，請參閱[使用雲端型例項搭配 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566)。

## Target 伺服器呼叫的目標網域 tt.omtrdc.net 為何? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] 是 Adobe 之 EDGE 網路的網域名稱，用來接收 Target 的所有伺服器呼叫。

## 為何 at.js 和 mbox.js 不使用 HttpOnly 與 Secure Cookie 旗標? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly 只能透過伺服器端編碼來設定。Mbox 之類的 Target Cookie 是透過 JavaScript 編碼來建立與儲存，因此 Target 無法使用 HttpOnly Cookie 旗標。

Secure 只有在頁面是經由 HTTPS 來載入時，能透過 JavaScript 設定。如果頁面一開始是透過 HTTP 載入，JavaScript 無法設定此旗標。此外，如果 Secure 旗標已使用，則只有 HTTPS 頁面可使用 Cookie。

為確保 Target 能正確追蹤使用者，且由於 Cookie 都是在用戶端產生，Target 不會使用這兩種旗標。
