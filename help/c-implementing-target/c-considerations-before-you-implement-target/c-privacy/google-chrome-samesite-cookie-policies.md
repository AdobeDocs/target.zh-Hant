---
description: 自 Google Chrome 版本 76 起可開始使用 Target 和 SameSite IETF 標準的相關資訊。
keywords: google;samesite；Cookie；Chrome80；ietf
seo-description: Google Chrome 版本 80 推出的 Adobe Target 和 SameSite IETF 標準的相關資訊。
seo-title: Adobe Target和Google的SaveSite Cookie政策
solution: Target
subtopic: 快速入門
title: Google Chrome SameSite Cookie 原則
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Google Chrome SameSite Cookie 原則

Google將根據使用Chrome80開始的使用者預設新的Cookie政策，該政策將於2011年初推出。本文章說明您需要瞭解的新SaveSite Cookie原則、 [!DNL Adobe Target] 支援這些原則，以及如何使用 [!DNL Target] Google Chrome新的SaveSite Cookie原則。

從Chrome80開始，網頁開發人員必須明確指定哪些Cookie可以跨網站運作。這是Google規劃要改善網路隱私權和安全性的眾多公告中的第一個。

由於Facebook已走在隱私權與安全性的龍頭地位，其他主要競爭對手(例如Apple)和現在的Google等主要競爭對手，已利用這個機會，在隱私權和安全性方面創造新的身分。Apple在今年初期透過ITP2.1和ITP2.2首次宣佈變更其Cookie政策。在ITP2.1中，Apple完全封鎖第三方Cookie，並將瀏覽器建立的Cookie維持在天內。在ITP2.2中，Cookie僅保留一天。Google的公告遠不如Apple的創新功能，但這是邁向相同目標的第一步。如需Apple政策的詳細資訊，請參閱 [Apple Intelligent Tracking Premiention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## 甚麼是Cookie？他們如何使用？

在我們深入探究Google對Cookie政策的變更之前，請先瞭解Cookie及其使用方式。簡單來說，Cookie是儲存在網頁瀏覽器中用來記住使用者屬性的小型文字檔案。

Cookie很重要，因為它們可增強使用者瀏覽網頁時的體驗。例如，如果您在電子商務網站上購物，但在該次瀏覽中新增物品至購物車，但不在該次瀏覽中登入或購買，Cookie會記住您的項目，並保留在您的下一次瀏覽中。或者，假設您每次造訪最喜愛的社交媒體網站時被迫重新輸入使用者名稱和密碼。Cookie也能解決這個問題，因為他們儲存了有助於網站識別您身分的資訊。這類Cookie稱為第一方Cookie，因為它們是由您造訪的網站建立和使用。

第三方Cookie也存在。若要進一步瞭解它們，請考慮以下範例：

假設一家稱為「朋友」的假設社交媒體公司提供了其他網站的「共用」按鈕，讓「朋友」使用者可以在「朋友」動態消息上分享網站的內容。現在，使用者在使用「分享」按鈕的新聞網站上閱讀新聞文章，並按一下「分享」按鈕，以自動張貼至「朋友」帳戶。

為了發生這種情況，瀏覽器會在載入新聞文章時 `platform.friends.com` 擷取「好友分享」按鈕。在此程序中，瀏覽器會附加「好友」Cookie，其中包含使用者登入憑證，並向「朋友」伺服器提出要求。這可讓「朋友」代表使用者張貼動態消息中的新聞文章，而不需要使用者登入。

使用第三方Cookie即可做到這一點。在這種情況下，第三方Cookie會儲存在瀏覽器中 `platform.friends.com`，以便代表 `platform.friends.com` 使用者在「朋友」應用程式中製作貼文。

如果您想一下，如何在沒有第三方Cookie的情況下實現此使用案例，使用者必須遵循許多手動步驟。首先，使用者必須複製新聞文章的連結。其次，使用者必須分別登入「朋友」應用程式。然後，使用者就會按一下「建立貼文」按鈕。然後，使用者將複製並貼上文字欄位中的連結，然後按一下「貼文」。如您所見，協力廠商Cookie可大幅降低人工步驟的使用者體驗。

一般而言，第三方Cookie可讓資料儲存在使用者瀏覽器上，而不需要使用者明確瀏覽網站。

## 安全性顧慮

雖然Cookie增強了使用者體驗和強大的廣告，但也能引入安全性弱點，例如跨網站偽造要求(CSRF)攻擊。例如，如果使用者登入銀行網站以支付信用卡帳單並離開網站，而在同一作業中瀏覽到惡意網站，則可能會發生CSRF攻擊。惡意網站可能包含對銀行網站提出要求的程式碼，在頁面載入時執行。由於使用者仍在驗證銀行網站，因此作業Cookie可用來啓動CSRF攻擊，以啓動資金轉移事件以外的使用者銀行帳戶。這是因為當您造訪網站時，所有Cookie都會附加在HTTP請求中。由於這些安全性考量，Google目前正嘗試降低它們。

## Target如何使用Cookie？

在這一切中，讓我們來看看 [!DNL Target] 如何使用Cookie。為了讓您第一次使用 [!DNL Target] ，您需要在您的網站上安裝 [!DNL Target] JavaScript程式庫。這可讓您在瀏覽您網站的使用者瀏覽器上放置第一方Cookie。當使用者與您的網站互動時，您可以 [!DNL Target] 透過JavaScript程式庫傳遞使用者的行為和興趣資料。[!DNL Target] JavaScript程式庫使用第一方Cookie來擷取使用者的識別資訊，以對應使用者的行為和興趣資料。然後，此資料便會 [!DNL Target] 用來強化您的個人化活動。

Target也(有時)使用第三方Cookie。如果您擁有不同網域上的多個網站，而您想要追蹤跨這些網站的使用者旅程，則可以利用跨網域追蹤來使用第三方Cookie。透過在 [!DNL Target] JavaScript程式庫中啓用跨網域追蹤，您的帳戶就會開始使用第三方Cookie。當使用者從一個網域跳至另一個網域時，瀏覽器會與後端伺服器通訊 [!DNL Target]，並在此程序中建立第三方Cookie，並放置在使用者的瀏覽器上。透過使用者瀏覽器上的第三方Cookie [!DNL Target] ，可為單一使用者提供跨不同網域的一致體驗。

## Google的新Cookie配方

若要在跨網站傳送Cookie時提供安全防護，讓使用者受到保護，Google計劃新增支援IETF標準的IETF標準，這項功能要求網頁開發人員使用Set-Cookie標題中的saveSite屬性元件來管理Cookie。

有三個不同的值可傳遞至 SameSite 屬性: 嚴格、鬆散或無。

| 值 | 說明 |
| --- | --- |
| 嚴格 | 只有在造訪最初設定的網域時，才能存取具有此設定的 Cookie。也就是說，嚴格會完全封鎖 Cookie，以免跨網站使用。這個選項最適合需要高安全性的應用程式，例如銀行。 |
| 鬆散 | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`.  |
| 無 | 具有此設定的Cookie的運作方式與現今Cookie相同。 |

Chrome80為使用者提供兩種獨立設定：「SameSite by default cookies」和「沒有SameSite的Cookie必須是安全的」。Chrome80預設會啓用這些設定。

![SaveSite對話方塊](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SaveSite依預設Cookie**：設定時，所有未指定saveSite屬性的Cookie都會自動被強制使用 `SameSite = Lax`。
* **沒有SameSite的Cookie必須安全**：設定時，不含SameSite屬性或 `SameSite = None` 必須安全的Cookie。在此情境下，安全代表所有瀏覽器要求都必須遵循 HTTPS 通訊協定。未遵守此要求的 Cookie 會遭到拒絕。所有網站都應使用HTTPS來符合此項需求。

## Target 遵循 Google 的安全性最佳實務

在Adobe，我們一直想要支援業界最新的安全性和隱私權實務。We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

對於「依預設Cookie的SaveSite」設定， [!DNL Target] 將繼續提供個人化，而不會對您造成任何影響和干預。[!DNL Target] 使用第一方 Cookie 且將繼續正常運作，因為 Google Chrome 已套用 `SameSite = Lax` 標幟。

對於「沒有SameSite的Cookie」選項，如果您未選擇 [!DNL Target]加入跨網域追蹤功能，則第 [!DNL Target] 一方Cookie會繼續運作。

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. 這表示您必須確保您的網站使用HTTPS通訊協定。用戶端的程式庫會 [!DNL Target] 自動使用HTTPS通訊協定，並將「安全標幟」附加 `SameSite = None` 至第三方Cookie， [!DNL Target] 以確保所有活動都能繼續提供。

## 您需要做什麼?

若要瞭解您需要如何 [!DNL Target] 繼續適用於Google Chrome80+使用者，請參閱下表，其中包含下列欄：

* **目標JavaScript程式庫**：如果您使用mbox. js，at. js1。*x* 或 at.js 2.*x* 。
* **SaveSite依預設Cookie=啓用**：如果您的使用者已啓用「SaveSite by default Cookie」，它會如何影響您，而且您需要做甚麼才能 [!DNL Target] 繼續運作。
* **沒有SameSite的Cookie必須是安全的=啓用**：如果您的使用者已啓用「沒有SaveSite的Cookie」功能，它會如何影響您，而且您需要做甚麼才能 [!DNL Target] 繼續運作。

| Target JavaScript程式庫 | SameSite 依預設 Cookie = 啟用 | 不含 SameSite 的 Cookie 必須是安全狀態 = 啟用 |
| --- | --- | --- |
| 僅包含第一方Cookie的mbox. js。 | 無影響力。 | 如果您未使用跨網域追蹤，則無影響。 |
| 已啓用跨網域追蹤的mbox. js。 | 無影響力。 | 您必須為您的網站啓用HTTPS通訊協定。<br>[!DNL Target] 使用第三方Cookie追蹤使用者和Google需要第三方Cookie才能擁有 `SameSite = None` 和保全旗標。安全旗標需要您的網站必須使用HTTPS通訊協定。 |
| at.js 1.*x*&#x200B;使用第一方Cookie。 | 無影響力。 | 如果您未使用跨網域追蹤，則無影響。 |
| at.js 1.*x*&#x200B;啓用跨網域追蹤。 | 無影響力。 | 您必須為您的網站啓用HTTPS通訊協定。<br>[!DNL Target] 使用第三方Cookie追蹤使用者和Google需要第三方Cookie才能擁有 `SameSite = None` 和保全旗標。安全旗標需要您的網站必須使用HTTPS通訊協定。 |
| at.js 2.*x* | 無影響力。 | 無影響力。 |

## Target需要做甚麼？

因此，我們必須在我們的平台中做些甚麼，才能協助您遵守新的Google Chrome80+ SAMSite Cookie政策？

| Target JavaScript程式庫 | SameSite 依預設 Cookie = 啟用 | 不含 SameSite 的 Cookie 必須是安全狀態 = 啟用 |
| --- | --- | --- |
| 僅包含第一方Cookie的mbox. js。 | 無影響力。 | 如果您未使用跨網域追蹤，則無影響。 |
| 已啓用跨網域追蹤的mbox. js。 | 無影響力。 | [!DNL Target] 在呼叫伺服器時，新增 `SameSite = None` 和保全標幟至 [!DNL Target] 第三方Cookie。 |
| at.js 1.*x*&#x200B;使用第一方Cookie。 | 無影響力。 | 如果您未使用跨網域追蹤，則無影響。 |
| at.js 1.*x*&#x200B;啓用跨網域追蹤。 | 無影響力。 | at.js 1.*x*&#x200B;啓用跨網域追蹤。 |
| at.js 2.*x* | 無影響力。 | 無影響力。 |

## 如果您未移轉至HTTPS通訊協定，會造成甚麼影響？

唯一會影響您的使用案例是透過mbox. js或at. js中 [!DNL Target] 的跨網域追蹤功能。*x* 版本不支援此函數。若未移轉至Google要求的HTTPS，您將會看到跨網域中獨特訪客的尖峰，因為Google將會捨棄我們使用的第三方Cookie。由於第三方Cookie將被丟棄，因此當使用者從一個網域導覽至另一個網域時， [!DNL Target] 將無法提供一致且個人化的體驗。第三方Cookie主要用於識別單一使用者瀏覽您擁有的網域。

## 結論

當業界致力於為客戶建立更安全的網路時， [!DNL Adobe] 絕對致力於協助我們的客戶提供個人化體驗，確保使用者的安全性和隱私權。您只需要遵循上述最佳實務，並善用Google [!DNL Target] Chrome新的SaveSite Cookie政策。
