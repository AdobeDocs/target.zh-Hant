---
description: 透過Experience Cloud ID(ECID)程式庫4.3對Apple ITP2.1和ITP2.2的Target支援相關資訊。
keywords: Apple；ITP；智慧追蹤防範
seo-description: 透過Experience Cloud ID(ECID)程式庫4.3對Apple的ITP2.1和ITP2.2支援的相關資訊。
seo-title: Adobe Target與Apple ITP支援
solution: Target
subtopic: 快速入門
title: Apple ITP2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Apple Intelligent Tracking Premiention(ITP)2.x

智慧追蹤防範(ITP)是Apple保護Safari使用者隱私權的舉措。第一次發行的ITP是在2017年，目標是使用第三方Cookie。事實上，Apple封鎖了第三方Cookie，因此導致廣告技術和技術公司嚴重頭痛，因為第三方Cookie通常用於追蹤訪客並收集訪客資料。Apple現在正努力在Safari中放置第一方Cookie的限制和限制。

這些ITP版本包含下列限制：

| 版本 | 詳細資料 |
| --- | --- |
| [ITP2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Capped client-side cookies that are placed on the browser using the `document.cookie` API to a seven-day expiry.<br>發行日期：2019年月21日。 |
| [ITP2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 大幅縮短七天的過期時間。<br>發行日期：2019年月24日。 |

## 身為Adobe Target客戶，對我有何影響？

[!DNL Target] 提供JavaScript程式庫供您在頁面上部署 [!DNL Target] ，以便為訪客提供即時個人化。There are three Target JavaScript libraries ([at.js 1.*x*&#x200B;和at. js2。*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和 [mbox. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md))，可將用戶端 [!DNL Target] Cookie置於訪客的瀏覽器 `document.cookie` 上。[!DNL Target] 因此，Apple的ITP2.1和2.2會影響Cookie，並將在天後過期(ITP2.1)以及一天後過期(使用ITP2.2)。

Apple ITP 2.1 and 2.1 impact [!DNL Target] in the following areas:

| 影響 | 詳細資料 |
| --- | --- |
| 可能增加獨特訪客計數 | 由於過期時間設為天(使用ITP2.1)和一天(使用ITP2.2)，您可能會看到來自Safari瀏覽器的獨特訪客增加。If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. The new [!DNL Target] cookie translates to a new unique visitor even though the user is the same. |
| Decreased lookback periods for [!DNL Target] activities | [!DNL Target] 活動的訪客資料可能會有較短的決策期間。[!DNL Target] Cookie會運用於識別訪客，並儲存使用者描述檔屬性以進行個人化。Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |

## Is my current implementation of [!DNL Target] impacted?

In a Safari browser, navigate to your website on which you have a [!DNL Target] JavaScript library. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## How can I mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target]?

To mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target], complete the following tasks:

1. 將Experience Cloud ID(ECID)程式庫部署至您的頁面。

   ECID程式庫可讓Experience Cloud核心解決方案的人員識別架構。ECID程式庫可讓您指派永久性和獨特識別碼，在不同的Experience Cloud解決方案中識別相同的網站訪客及其資料。ECID程式庫會經常更新，以協助您減輕影響實施的ITP相關變更。

   For ITP 2.1 and ITP 2.2, [ECID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) must be utilized for mitigation.

1. 使用Adobe的CNAME和註冊Adobe Analytics的Managed Certificate Program。

   安裝ECID程式庫4.3.0+後，您可以運用Adobe Analytics的CNAME和Managed Certificate Program。此程式可讓您免費實作第一方Cookie的第一方憑證。Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.1 and ITP 2.2.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).

在您搭配EID程式庫v4.3.0+部署Target JavaScript程式庫並註冊Adobe Managed Certificate Program以運用CNAME之後，您就會針對ITP相關變更制定健全且長期的緩解計劃。

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] 已宣佈支援 [Google的SaveSite Chrome政策](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) ，除了支援Apple的ITP2.1和ITP2.2之外。

As policies continue to evolve to protect our consumers, [!DNL Adobe] will also continue to support these initiatives in [!DNL Target], while helping our customers provide the best-in-class personalized experiences.
