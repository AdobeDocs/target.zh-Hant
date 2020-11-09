---
keywords: mbox.js faq;mbox.js frequently asked questions;document.write;tt.omtrdc.net;parser blocking
description: 關於 mbox.js 常見問題的回答。
title: mbox.js 常見問題
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 98%

---


# mbox.js 常見問題{#mbox-js-frequently-asked-questions}

關於 mbox.js 常見問題的回答。

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
