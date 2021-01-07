---
keywords: google;samesite;cookies;chrome 80;ietf
description: Google Chrome 版本 80 推出的 Adobe Target 和 SameSite IETF 標準的相關資訊。
title: Adobe Target和Google的SameSite Cookie政策
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '2033'
ht-degree: 8%

---


# Google Chrome SameSite Cookie 原則

谷歌將開始根據預設，為從Chrome 80開始的用戶實施新的Cookie政策。 Chrome 80計畫於2020年初推出。 本文將說明您需要瞭解的有關新SameSite Cookie政策、[!DNL Adobe Target]如何支援這些政策，以及如何使用[!DNL Target]來符合Google Chrome的新SameSite Cookie政策。

從Chrome 80開始，網頁開發人員必須明確指定哪些Cookie可以跨網站運作。 這是谷歌計畫為改善網路隱私和安全性而發佈的眾多公告中的首次。

鑑於Facebook在隱私和安全方面一直處於熱門地位，蘋果等其他主要企業迅速抓住機會，將新身份打造為隱私和安全捍衛者。 蘋果率先宣佈在今年年初通過ITP 2.1和最近通過ITP 2.2對其Cookie政策進行了修改，從而成為這一領域的領導者。在ITP 2.1中，Apple會完全封鎖協力廠商Cookie，並將在瀏覽器上建立的Cookie保留僅7天。 在ITP 2.2中，Cookie僅保存一天。 谷歌的聲明遠沒有蘋果那麼激進，但這是朝著同一目標邁出的第一步。 如需Apple政策的詳細資訊，請參閱[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## 什麼是Cookie，以及它們的使用方式？

在深入探討Google對Cookies政策的變更之前，讓我們先瞭解Cookies是什麼，以及如何使用。 簡而言之，Cookie是儲存在網頁瀏覽器中的小型文字檔案，用於記住使用者屬性。

Cookie很重要，因為它們可增強使用者在瀏覽網頁時的體驗。 例如，如果您在電子商務網站上購物並新增內容至購物車，但未在該次瀏覽中登入或購買，Cookie會記住您的項目，並將其保存在您的購物車中，以供您下次瀏覽。 或者，想像一下，如果您每次造訪您最愛的社交媒體網站時都被迫重新輸入您的使用者名稱和密碼。 Cookie也能解決這個問題，因為Cookie會儲存有助於網站識別您身分的資訊。 這些類型的Cookie稱為第一方Cookie，因為您所造訪的網站會建立和使用它們。

第三方Cookie也存在。 為了更好地瞭解它們，我們來考慮下列範例：

假設一家名為「朋友」的社交媒體公司提供「分享」按鈕，讓其他網站實作，讓「朋友」使用者在「朋友」動態消息中分享網站的內容。 現在，使用者會在使用「分享」按鈕的新聞網站上閱讀新聞文章，並按一下該按鈕以自動張貼至其「朋友」帳戶。

為此，當新聞文章載入時，瀏覽器會從`platform.friends.com`擷取「朋友分享」按鈕。 在此程式中，瀏覽器會將包含使用者登入認證的朋友Cookie附加至朋友伺服器的請求。 這可讓「朋友」代表使用者在動態消息中張貼新聞文章，而不需要使用者登入。

這一切皆可透過使用第三方Cookie來實現。 在這種情況下，協力廠商Cookie會儲存在瀏覽器上，以供`platform.friends.com`使用，如此`platform.friends.com`就可代表使用者在朋友應用程式中張貼貼文。

如果您想像一下如何在沒有第三方Cookie的情況下達成此使用案例，使用者將必須執行許多手動步驟。 首先，使用者必須複製新聞文章的連結。 其次，使用者必須個別登入「朋友」應用程式。 然後，使用者會按一下「建立貼文」按鈕。 然後，使用者會複製並貼上文字欄位中的連結，最後按一下「貼文」。 如您所見，協力廠商Cookie可大幅降低手動步驟的使用體驗。

更一般地說，協力廠商Cookie可讓資料儲存在使用者的瀏覽器上，而不需要該使用者明確造訪網站。

## 安全性顧慮

雖然Cookie可增強使用者體驗並強化廣告功能，但也可能會引入跨網站偽造要求(CSRF)攻擊等安全性弱點。 例如，如果使用者登入銀行網站以支付信用卡帳單而離開網站而未登出，然後在同一作業中瀏覽至惡意網站，則可能會發生CSRF攻擊。 惡意網站可能包含對銀行網站提出要求的程式碼，該要求會在頁面載入時執行。 由於使用者仍可驗證至銀行網站，因此作業Cookie可用來啟動CSRF攻擊，從使用者的銀行帳戶啟動資金轉移事件。 這是因為每當您造訪網站時，所有Cookie都會附加在HTTP請求中。 由於這些安全方面的擔憂，谷歌現在正試圖緩解這些擔憂。

## Target如何使用Cookie?

儘管如此，讓我們來看看[!DNL Target]如何使用Cookie。 您必須先將[!DNL Target] JavaScript程式庫安裝在您的網站上，才能使用[!DNL Target]。 這可讓您將第一方Cookie置於瀏覽您網站之使用者的瀏覽器中。 當您的使用者與您的網站互動時，您可以透過JavaScript程式庫將使用者的行為與興趣資料傳遞至[!DNL Target]。 [!DNL Target] JavaScript程式庫使用第一方Cookie來擷取有關使用者的識別資訊，以對應至使用者的行為與興趣資料。 然後，[!DNL Target]會使用此資料來推動您的個人化活動。

Target也（有時）使用第三方Cookie。 如果您擁有多個網站，且這些網站位於不同網域，而您想要追蹤這些網站的使用者歷程，則可運用跨網域追蹤功能來使用協力廠商Cookie。 透過在[!DNL Target] JavaScript程式庫中啟用跨網域追蹤，您的帳戶就會開始使用第三方Cookie。 當使用者從一個網域跳至另一個網域時，瀏覽器會與[!DNL Target]的後端伺服器通訊，而在此程式中，會建立協力廠商Cookie並放在使用者的瀏覽器上。 透過使用者瀏覽器上的協力廠商Cookie,[!DNL Target]可以為單一使用者在不同網域間提供一致的體驗。

## Google的新Cookie配方

為了在跨網站傳送Cookie以保護使用者時提供安全性，Google計畫新增對IETF標準SameSite的支援，此標準要求網頁開發人員在Set-Cookie標題中使用SameSite屬性元件來管理Cookie。

有三個不同的值可傳遞至 SameSite 屬性: 嚴格、鬆散或無。

| 值 | 說明 |
| --- | --- |
| 嚴格 | 只有在造訪最初設定的網域時，才能存取具有此設定的 Cookie。也就是說，嚴格會完全封鎖 Cookie，以免跨網站使用。這個選項最適合需要高安全性的應用程式，例如銀行。 |
| 鬆散 | 具有此設定的Cookie僅會在相同網站要求或具有非冪等HTTP要求（例如`HTTP GET`）的頂層導覽上傳送。 因此，如果協力廠商可使用Cookie，但有額外的安全性優點，可保護使用者不受CSRF攻擊之害，則可使用此選項。 |
| 無 | 使用此設定的Cookie與Cookie目前的運作方式相同。 |

請記住，Chrome 80為使用者提供兩種獨立的設定：&quot;SameSite by default cookies&quot;和&quot;Cookies without SameSite必須安全。&quot; 這些設定預設會在Chrome 80中啟用。

![「相同站點」對話框](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite依預設為Cookie**:設定後，所有未指定SameSite屬性的Cookie都會自動強制使用 `SameSite = Lax`。
* **沒有SameSite的Cookie必須是安全的**:設定時，不含SameSite屬性或具有Secure `SameSite = None` 的Cookie。在此情境下，安全代表所有瀏覽器要求都必須遵循 HTTPS 通訊協定。未遵守此要求的 Cookie 會遭到拒絕。所有網站都應使用HTTPS來符合此要求。

## Target 遵循 Google 的安全性最佳實務

在Adobe，我們始終希望支援業界最新的安全與隱私權最佳實務。 我們很高興宣佈[!DNL Target]支援Google推出的新安全性和隱私權設定。

對於「SameSite by default cookies」設定，[!DNL Target]將持續提供個人化，而不會受到您的影響和干預。 [!DNL Target] 使用第一方 Cookie 且將繼續正常運作，因為 Google Chrome 已套用 `SameSite = Lax` 標幟。

對於「不含SameSite的Cookies必須是安全的」選項，如果您未選擇加入[!DNL Target]中的跨網域追蹤功能，則[!DNL Target]中的第一方Cookie將繼續運作。

不過，當您選擇加入以跨網域追蹤來跨多個網域運用[!DNL Target]時，Chrome需要`SameSite = None`和「保全」標幟才能用於第三方Cookie。 這表示您必須確保您的網站使用HTTPS通訊協定。 [!DNL Target]中的用戶端程式庫會自動使用HTTPS通訊協定，並將`SameSite = None`和Secure標幟附加至[!DNL Target]中的第三方Cookie，以確保所有活動都能持續傳送。

## 您需要做什麼?

若要瞭解讓[!DNL Target]繼續為Google Chrome 80+使用者運作，請參閱下表，您會看到下列各欄：

* **目標JavaScript程式庫**:如果您使用mbox.js，則at.js 1。*x* 或 at.js 2.*從您* 的網站開始。
* **SameSite依預設為Cookie = Enabled**:如果您的使用者已啟用「SameSite by default cookies」（預設為SameSite cookies），它會對您產生什麼影響，以及您需要做什麼才能 [!DNL Target] 繼續運作。
* **沒有SameSite的Cookie必須是安全的=已啟用**:如果您的使用者已啟用「無SameSite的Cookies必須安全」，它會對您造成何種影響，以及您需要做什麼才能 [!DNL Target] 繼續運作。

| 目標JavaScript程式庫 | SameSite 依預設 Cookie = 啟用 | 不含 SameSite 的 Cookie 必須是安全狀態 = 啟用 |
| --- | --- | --- |
| mbox.js，僅含第一方Cookie。 | 沒有影響。 | 如果您未使用跨網域追蹤，則不會產生任何影響。 |
| mbox.js，並啟用跨網域追蹤。 | 沒有影響。 | 您必須為您的網站啟用HTTPS通訊協定。<br>[!DNL Target] 使用協力廠商Cookie來追蹤使用者，而Google則要求協力廠商Cookie具有 `SameSite = None` 和安全標幟。安全標幟要求您的網站必須使用HTTPS通訊協定。 |
| at.js 1.** xwith第一方Cookie。 | 沒有影響。 | 如果您未使用跨網域追蹤，則不會產生任何影響。 |
| at.js 1.*啟* 用跨網域追蹤。 | 沒有影響。 | 您必須為您的網站啟用HTTPS通訊協定。<br>[!DNL Target] 使用協力廠商Cookie來追蹤使用者，而Google則要求協力廠商Cookie具有 `SameSite = None` 和安全標幟。安全標幟要求您的網站必須使用HTTPS通訊協定。 |
| at.js 2.*x* | 沒有影響。 | 沒有影響。 |

## Target需要做什麼？

那麼，我們在我們的平台中需要做什麼來協助您符合新的Google Chrome 80+ SameSite Cookie政策？

| 目標JavaScript程式庫 | SameSite 依預設 Cookie = 啟用 | 不含 SameSite 的 Cookie 必須是安全狀態 = 啟用 |
| --- | --- | --- |
| mbox.js，僅含第一方Cookie。 | 沒有影響。 | 如果您未使用跨網域追蹤，則不會產生任何影響。 |
| mbox.js，並啟用跨網域追蹤。 | 沒有影響。 | [!DNL Target] 在呼 `SameSite = None` 叫伺服器時，新增並保全標幟 [!DNL Target] 至第三方Cookie。 |
| at.js 1.** xwith第一方Cookie。 | 沒有影響。 | 如果您未使用跨網域追蹤，則不會產生任何影響。 |
| at.js 1.*啟* 用跨網域追蹤。 | 沒有影響。 | at.js 1.*啟* 用跨網域追蹤。 |
| at.js 2.*x* | 沒有影響。 | 沒有影響。 |

## 如果您不改用HTTPS通訊協定，會有什麼影響？

唯一會影響您的使用案例是，如果您是透過mbox.js或at.js 1使用[!DNL Target]中的跨網域追蹤功能。*x* 不提供跨網域追蹤的立即可用支援。若不改用Google所要求的HTTPS，您將會看到網域中的獨特訪客數量出現尖峰，因為Google會捨棄我們使用的第三方Cookie。 由於第三方Cookie將會被捨棄，當使用者從一個網域導覽至另一個網域時，[!DNL Target]將無法為該使用者提供一致且個人化的體驗。 協力廠商Cookie主要用於識別在您擁有的網域間瀏覽的單一使用者。

## 結論

隨著業界大步邁向為消費者建立更安全的網路，[!DNL Adobe]絕對致力於協助客戶以確保使用者安全和隱私的方式提供個人化體驗。 您只需要遵循上述最佳實務，並善用[!DNL Target]來符合Google Chrome的新SameSite Cookie政策。
