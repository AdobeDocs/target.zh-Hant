---
keywords: 進階 mbox.js 設定;用戶端;伺服器網域;xdomain;壓縮層級;用戶端工作階段 ID 支援;secureOnly;用戶端 PC ID 支援;傳遞頁面;反向連結 URL;流量層級;流量持續時間;mboxParameters() 函數主體;mboxSupported() 函數主體;mboxCookieDomain() 函數主體;額外 JavaScript;SiteCatalyst 外掛程式;取得 mbox.js 做為自動解壓縮 JavaScript;忽隱忽現;主體隱藏;隱藏主體
description: 瞭解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform網頁SDK（AEP網頁SDK）或最新版的at.js。
title: 如何設定 [!DNL Target] mbox.js程式庫？
feature: at.js
role: Developer
exl-id: 17821e60-2692-49af-a225-764bd1b6aec1
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 71%

---

# 設定 mbox.js

可協助您在 mbox.js「設定」頁面上設定數個設定的資訊。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

[!DNL mbox.js] 函數程式庫的預設設定可為大部分的 [!DNL Target] 客戶提供需求。

如有需要，請洽詢您的帳戶代表以變更 [!DNL mbox.js] 設定。

可使用下列設定:

## 客戶

您帳戶的用戶端代碼。

在檢視[!UICONTROL 管理>實施]時，頂端的用戶端是您帳戶的用戶端代碼。

## 逾時

Target 要求逾時。

檢視[!UICONTROL 管理>實作]時，逾時（秒）設定是您的Target請求逾時。 依預設，此值設為 15 秒，但建議您將它設定為介於 2 秒與 5 秒之間的值。

## XDomain

判斷瀏覽器設定 Cookie 的位置，是設定在您的專屬網域中 (第一方 Cookie)，還是在 Target 的網域中，還是兩者都有。

變更此設定會同時影響 mbox.js 和 at.js。

## 壓縮層級

決定 mbox.js 程式庫檔案的壓縮程度。增加壓縮層級會減少頁面的載入時間。

## mboxParameters() 函數主體

傳回額外參數以傳遞至每個 mbox 呼叫。

例如:

return &quot;test=123&quot;;

## mboxSupported() 函數主體

傳回 false 以排除特定使用者。

例如:

return !navigator.userAgent.indexOf(&#39;Safari&#39;) ! = -1;

可接受或除排下列瀏覽器:

* IE 5.0 或更新版本 (Windows)
* Netscape 5.0 或更新版本 (Mac、Windows、Linux)
* Safari 1.2.4 或更新版本 (Mac)
* Mozilla Firefox 1.0 或更新版本 (Mac、Windows、Linux)

## mboxCookieDomain() 函數主體

傳回描述網域的字串以設定第一方 Cookie。

例如:

return &quot;YOUR-DOMAIN&quot;;

## 額外 JavaScript

包含任何您想要在每個頁面上執行的額外 JavaScript。

## SiteCatalyst 外掛程式

啟用 Analytics Target 外掛程式。

啟用後，Analytics 外掛程式會在 mbox.js 中產生外掛程式碼。此外掛程式碼會在標記著 Analytics 的每個頁面上，將 Analytics 標記資訊作為 mbox 請求傳送至 Target 伺服器。

請注意，仍必須在頁面上參考 Analytics 外掛程式。

## secureOnly

指出 mbox.js 是否應該僅使用 HTTPS 或根據頁面通訊協定，允許在 HTTP 與 HTTPS 之間切換。這是進階的設定，預設值為 False。
