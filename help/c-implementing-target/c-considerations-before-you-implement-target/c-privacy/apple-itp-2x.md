---
description: 透過Experience Cloud ID(ECID)程式庫4.3，瞭解Apple ITP 2.1和ITP 2.2的Target支援資訊。
keywords: apple;ITP；智慧跟蹤防護
seo-description: 透過Experience Cloud ID(ECID)程式庫4.3，瞭解Apple ITP 2.1和ITP 2.2的Adobe target支援資訊。
seo-title: Adobe target和Apple ITP支援
solution: Target
subtopic: 快速入門
title: Apple ITP 2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Apple Intelligent Tracking Prevention(ITP)2.x

Intelligent Tracking Prevention(ITP)是Apple保護Safari使用者隱私權的舉措。 ITP的第一版發行於2017年，其目標是使用協力廠商Cookie。 事實上，Apple封鎖了第三方Cookie的完整性，而這反過來又讓廣告技術和科技公司頭疼不已，因為第三方Cookie通常用於追蹤訪客和收集訪客資料。 現在，Apple正在對Safari中使用第一方Cookie的方式設定限制和限制。

這些ITP版本包含下列限制：

| 版本 | 詳細資料 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 使用 `document.cookie` API在瀏覽器上放置的用戶端Cookie有上限，到期為7天。<br>於2019年2月21日發行。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 將七天的過期限額大幅降低為一天。<br>於2019年4月24日發行。 |

## 身為Adobe target客戶，對我有何影響？

[!DNL Target] 提供JavaScript程式庫，讓您可部署在您的頁面上， [!DNL Target] 以便為訪客提供即時個人化。 目標JavaScript程式庫有三[個(at.js 1.*x*&#x200B;和at.js 2。*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和 [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md))，透過 [!DNL Target] API將用戶端Cookie置於訪客的 `document.cookie` 瀏覽器中。 因此， [!DNL Target] cookie會受Apple的ITP 2.1和2.2影響，並會在七天後（使用ITP 2.1）和一天後（使用ITP 2.2）到期。

Apple ITP 2.1和2.1對下列 [!DNL Target] 領域的影響：

| 影響 | 詳細資料 |
| --- | --- |
| 獨特訪客計數的潛在增加 | 由於有效期間設定為7天（使用ITP 2.1）和1天（使用ITP 2.2），您可能會看到來自Safari瀏覽器的獨特訪客增加。 如果您的訪客在七天(ITP 2.1)或一天(ITP 2.2)後再次造訪您的網域， [!DNL Target] 就必須在您的網域上放置新 [!DNL Target] Cookie來取代過期的Cookie。 新的 [!DNL Target] Cookie會轉換為新的獨特訪客，即使使用者相同。 |
| 減少活動回顧時 [!DNL Target] 間 | 活動的訪客 [!DNL Target] 資料可能會縮短決策回顧期。 [!DNL Target] Cookie可用來識別訪客身分，並儲存使用者描述檔屬性以進行個人化。 由於 [!DNL Target] Cookie可在七天(ITP 2.1)或一天(ITP 2.2)之後於Safari上過期，因此系結至已清除 [!DNL Target] Cookie的使用者描述檔資料無法用於決策。 |

## 我目前的實作是否受 [!DNL Target] 影響？

在Safari瀏覽器中，導覽至您有JavaScript程式庫的 [!DNL Target] 網站。 如果您在CNAME [!DNL Target] 的上下文中看到設定的Cookie, `analytics.company.com`則不會受到ITP 2.1或2.2的影響。

如果您除了使用Target javaScript程式庫外，還使用Experience Cloud ID(ECID)程式庫，您的實作會受到本文章所列方式的影響： [Safari ITP 2.1對Adobe Experience cloud和Experience platform客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 我要如何減輕ITP 2.1、ITP 2.2和未來ITP版本對的影響 [!DNL Target]?

為了減輕ITP 2.1、ITP 2.2和未來ITP發行的影響，請完 [!DNL Target]成下列工作：

1. 將Experience Cloud ID(ECID)程式庫部署至您的頁面。

   ECID程式庫可讓Experience Cloud Core解決方案的人員識別架構。 ECID程式庫可讓您指派永久和唯一的識別碼，以識別不同Experience cloud解決方案中的相同網站訪客及其資料。 ECID程式庫會經常更新，以協助您減輕影響實作的ITP相關變更。

   對於ITP 2.1和ITP 2.2, [ECID程式庫4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) ，必須用於緩解。

1. 使用Adobe的CNAME並註冊Adobe Analytics的「管理認證計畫」。

   在安裝ECID程式庫4.3.0+後，您就可以運用Adobe Analytics的CNAME和受管理的憑證程式。 此方案可讓您免費實作第一方Cookie的第一方憑證。 運用CNAME可協 [!DNL Target] 助客戶減輕ITP 2.1和ITP 2.2的影響。

   如果您未運用CNAME，則可以先與帳戶代表通話，然後註冊 [Adobe Managed Certificate Program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)。

在您與ECID程式庫v4.3.0+一起部署Target javaScript程式庫並註冊Adobe管理認證計畫以運用CNAME後，您將針對ITP相關變更提供強穩且長期的緩解計畫。

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] 除了支援 [Apple的ITP 2.1和ITP 2.2外，已宣佈支援Google的SameSite Chrome政策](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) 。

隨著政策的不斷演變以保護我們的 [!DNL Adobe] 消費者，我們也將繼續支援這些計畫 [!DNL Target]，同時協助客戶提供同級最佳的個人化�