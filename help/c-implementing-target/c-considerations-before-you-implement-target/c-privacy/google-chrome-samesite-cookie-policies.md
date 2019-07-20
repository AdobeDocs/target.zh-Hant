---
description: 從Google Chrome76開始使用Target和SaveSite IETF標準的相關資訊。
keywords: google；samsite
seo-description: 與Google Chrome76一同推出的Adobe Target和SaveSite IETF標準的相關資訊。
seo-title: Adobe Target和SaveSite Cookie原則
solution: Target
subtopic: 快速入門
title: Google Chrome SameSite Cookie 原則
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Google Chrome SameSite Cookie 原則

Google最近宣佈從Chrome76(於2019年月30日推出)開始，開發人員必須明確指定哪些Cookie可以跨網站運作，以及哪些Cookie可追蹤使用者。

## SameSite總覽

若要在跨網站傳送Cookie時提供安全防護，讓使用者受到保護，Google在Google Chrome76(及更新版本)中新增了對IETF標準的支援。SameSite requires web developers to manage cookies with the SameSite attribute component in the `Set-Cookie` header.

有三種不同的值可傳入SaveSite屬性中：Strict、Layx或None。

| 值 | 說明 |
| --- | --- |
| Strict | 具有此設定的Cookie只能在造訪其最初設定之網域時存取。換言之，Strict完全封鎖了跨網站使用Cookie。這個選項最適合需要高安全性的應用程式，例如銀行。 |
| Lakox | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, such as `HTTP GET`. Therefore, this option should be used if the cookie can be used by third-parties, but with an added security benefit that protects users from being victimized by [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) (Cross-Site Request Forgery) attacks. |
| 無 | 具有此設定的Cookie的運作方式與現今Cookie相同。 |

請記住上述事項，Chrome76(及更新版本)提供兩種設定：「SameSite by default cookies」和「沒有SameSite的Cookie必須是安全的」。使用者可以啓用設定或這兩項設定。

| 設定 | 說明 |
| --- | --- |
| SaveSite依預設Cookie | When set, all cookies that don't specify the SameSite attribute are automatically forced with `SameSite = Lax`. |
| 不含SameSite的Cookie必須安全 | When set, cookies without the SameSite attribute or with `SameSite = None`, must be Secure. 在此上下文中安全表示所有瀏覽器要求必須遵循HTTPS通訊協定。不遵守此項規定的Cookie遭到拒絕。 |

![SaveSite設定頁面](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

## Target遵循Google的安全性最佳實務

透過Target，我們希望始終支持業界最新的安全性最佳做法，以確保您成功。我們很高興宣佈Target支援Google Chrome76中引進的新安全性設定。

當您的訪客依據預設Cookie設定開啓「SaveSite」時，Target會持續提供個人化，而沒有任何影響，而您也沒有任何介入。Target uses first-party cookies and will continue to function properly as the flag `SameSite = Lax` is applied by Google Chrome.

當訪客啓用「沒有SameSite的Cookie」時，而您不選擇「Target的跨網域追蹤」功能，則Target的第一方Cookie會繼續運作。However, when you opt-in to using cross-domain tracking to leverage Target across multiple domains, Google Chrome 76 (and later) requires `SameSite = None` and `Secure` flags to be used for third-party cookies. 這表示您必須確保您的網站使用HTTPS通訊協定。Target's client-side libraries automatically use the HTTPS protocol and, in addition to that, attach the `SameSite = None` and `Secure` flags to Target’s third-party cookie to ensure all activities continue to deliver.

## 您需要做甚麼？

請檢閱下表以瞭解如何讓Target繼續適用於Google Chrome76+使用者。

表格包含下列欄：

* **目標用戶端程式庫**：無論您是使用mbox. js，at. js1。*x*&#x200B;或at. js2。*網站上的x，* 以及Google Chrome設定如何影響您
* **SaveSite依預設Cookie=啓用**：如果您的訪客已啓用Chrome76+上啓用的「SaveSite」，它會對您造成甚麼影響，而您需要做甚麼才能讓Target繼續運作
* **沒有SameSite的Cookie必須是安全的=啓用**：如果您的訪客擁有Chrome76+上啓用的「沒有SameSite的Cookie」，它會對您造成甚麼影響，而您需要做甚麼才能讓Target繼續運作
* **Adobe Target的跨網域追蹤=已啓用**：如果您的訪客已啓用「依預設Cookie」啓用「網站」和「沒有SaveSite的Cookie」，且您在Chrome76+上啓用「Target」，而您使用Target進行跨網域追蹤，則它會對您造成甚麼影響，而您需要做甚麼才能讓Target繼續運作

| 目標用戶端程式庫 | SaveSite依預設Cookie=啓用 | 沒有SameSite的Cookie必須為secure= Enabled | Adobe Target的跨網域追蹤=已啓用 |
| --- | --- | --- | --- |
| mbox.js | 沒有影響，因為mbox. js使用第一方Cookie | 不會影響，因為客戶不會使用跨網域追蹤 | 客戶必須啓用其網站的HTTPS通訊協定。<br>Target使用第三方Cookie來追蹤使用者，而Google需要第三方Cookie才能使用 `SameSite = None` HTTPS通訊協定。 |
| at.js 1。*x* | 沒有影響，因為at. js1。*x* 使用第一方Cookie | 不會影響，因為客戶不會使用跨網域追蹤 | 客戶必須啓用其網站的HTTPS通訊協定。<br>Target使用第三方Cookie來追蹤使用者，而Google需要第三方Cookie才能使用 `SameSite = None` HTTPS通訊協定 |
| at.js 2。*x* | 沒有影響，因為at. js2。*x* 使用第一方Cookie | 不會影響，因為客戶不會使用跨網域追蹤 | 在at. js中不支援跨網域追蹤。*x* ，因此對客戶並無影響 |

## Adobe需要做甚麼？

| 目標用戶端程式庫 | SaveSite依預設Cookie=啓用 | 沒有SameSite的Cookie必須為secure= Enabled | Adobe Target的跨網域追蹤=已啓用 |
| --- | --- | --- | --- |
| mbox.js | 沒有影響，因為mbox. js使用第一方Cookie | 不會影響，因為客戶不會使用跨網域追蹤 | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 1。*x* | 沒有影響，因為at. js1。*x* 使用第一方Cookie | 不會影響，因為客戶不會使用跨網域追蹤 | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 2。*x* | 沒有影響，因為at. js2。*x* 使用第一方Cookie | 不會影響，因為客戶不會使用跨網域追蹤 | 在at. js中不支援跨網域追蹤。*x* |

## 結論

隨著產業致力於為消費者建立更安全的網路，Target絕對致力於提供個人化體驗，並超越對訪客的隱私權期望。
