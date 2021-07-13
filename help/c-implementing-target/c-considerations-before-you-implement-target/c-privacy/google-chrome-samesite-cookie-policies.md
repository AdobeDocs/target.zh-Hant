---
keywords: google;samesite;cookie;chrome 80;ietf
description: 了解Adobe [!DNL Target] 如何處理Google Chrome 80版推出的SameSite IETF標準，以及您需要執行哪些動作來遵循這些原則。
title: ' [!DNL Target] 如何處理Google的Samesite Cookie原則？'
feature: 隱私權與安全性
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 7%

---

# Google Chrome SameSite Cookie 原則

自Chrome 80起，Google將預設開始為使用者實施新的Cookie政策，預計於2020年初發行。 本文說明您需要了解的關於新SameSite Cookie原則的所有資訊、[!DNL Adobe Target]如何支援這些原則，以及如何使用[!DNL Target]來遵循Google Chrome的新SameSite Cookie原則。

自Chrome 80起，網頁開發人員必須明確指定哪些Cookie可以跨網站運作。 這是谷歌計畫為改善網路隱私和安全而發佈的眾多公告中的首個。

鑑於Facebook在隱私和安全方面一直處於熱門地位，蘋果等其他主要公司，如谷歌，都迅速抓住機會，將新身份打造成隱私和安全捍衛者。 Apple在Cookie政策方面居於領先地位，於今年初透過ITP 2.1和最近宣佈ITP 2.2變更其Cookie政策。在ITP 2.1中，Apple會完全封鎖第三方Cookie，並將在瀏覽器上建立的Cookie保留僅七天。 在ITP 2.2中，Cookie僅會保留一天。 谷歌的宣佈遠沒有蘋果那麼激進，但這是朝著同樣的目標邁出的第一步。 如需Apple原則的詳細資訊，請參閱[Apple智慧型追蹤預防(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## 什麼是Cookie？如何使用？

在深入探討Google對其Cookie原則的變更前，請先詳閱Cookie的內容及使用方式。 簡言之，Cookie是儲存在Web瀏覽器中用於記憶用戶屬性的小型文本檔案。

Cookie之所以重要，是因為它們可增強使用者在瀏覽網路時的體驗。 例如，如果您在電子商務網站上購物，並新增某些項目至購物車，但未在該次造訪中登入或購買，Cookie會記住您的項目，並將其保留在您的購物車中，以供您下次造訪。 或者，想像一下，如果每次訪問您最喜愛的社交媒體網站時，您都被迫重新輸入用戶名和密碼。 Cookie也解決了這個問題，因為它們儲存有助於網站識別您的身份的資訊。 這類Cookie稱為第一方Cookie，因為這些Cookie是由您造訪的網站所建立和使用。

第三方Cookie也存在。 為了更好地了解這些內容，我們來考慮以下範例：

假設有一家名為「好友」的社交媒體公司，提供了一個「共用」按鈕，讓其他網站實施該按鈕，讓「好友」用戶能夠在「好友」動態消息上共用該網站的內容。 現在，一個用戶在一個使用「分享」按鈕的新聞網站上閱讀新聞文章，然後按一下該按鈕以自動在其「好友」帳戶上發佈。

為此，載入新聞文章時，瀏覽器會從`platform.friends.com`擷取「好友共用」按鈕。 在此過程中，瀏覽器會將包含用戶登錄憑據的好友Cookie附加到向好友伺服器發出的請求。 這可讓朋友代表使用者，在動態消息中張貼新聞文章，而不要求使用者登入。

使用協力廠商Cookie就能做到這一切。 在此情況下，第三方Cookie會儲存在瀏覽器上以供`platform.friends.com`使用，這樣`platform.friends.com`就能代表使用者在朋友應用程式中發佈貼文。

如果您想像一下如何在不使用第三方Cookie的情況下達成此使用案例，使用者將必須執行許多手動步驟。 首先，使用者必須複製新聞文章的連結。 其次，使用者必須分別登入「好友」應用程式。 接著，使用者會按一下「建立貼文」按鈕。 然後，使用者會複製連結並貼到文字欄位中，最後按一下「貼文」。 如您所見，協力廠商Cookie可大幅減少手動步驟，大幅協助使用者體驗。

更一般地，協力廠商Cookie可讓資料儲存在使用者的瀏覽器上，而不要求使用者明確造訪網站。

## 安全問題

雖然Cookie可增強使用者體驗並強化廣告功能，但也可能會引入跨網站請求偽造(CSRF)攻擊等安全漏洞。 例如，如果用戶登錄銀行站點以支付信用卡賬單，而離開該站點而不註銷，然後在同一會話中瀏覽到惡意站點，則可能會發生CSRF攻擊。 惡意網站可能包含對頁面載入時執行的銀行網站提出請求的代碼。 由於使用者仍可驗證至銀行網站，因此工作階段Cookie可用來啟動CSRF攻擊，以啟動從使用者的銀行帳戶傳出的資金轉移事件。 這是因為每當您造訪網站時，所有Cookie都會附加在HTTP要求中。 由於這些安全方面的考慮，谷歌現在正試圖緩解這些擔憂。

## [!DNL Target]如何使用Cookie?

讓我們看看[!DNL Target]如何使用Cookie。 您必須先在網站上安裝[!DNL Target] JavaScript程式庫，才能首先使用[!DNL Target]。 這可讓您將第一方Cookie放置在瀏覽您網站之使用者的瀏覽器上。 當您的使用者與網站互動時，您可以透過JavaScript程式庫將使用者的行為和興趣資料傳遞至[!DNL Target]。 [!DNL Target] JavaScript程式庫使用第一方Cookie來擷取關於使用者的識別資訊，以對應至使用者的行為和興趣資料。 然後，[!DNL Target]會使用此資料來支援您的個人化活動。

Target也（有時）使用第三方Cookie。 如果您擁有多個網站，且網站位於不同網域，且您想要追蹤這些網站的使用者歷程，則可運用跨網域追蹤功能來使用第三方Cookie。 透過在[!DNL Target] JavaScript資料庫中啟用跨網域追蹤，您的帳戶將開始使用第三方Cookie。 當使用者從一個網域跳到另一個網域時，瀏覽器會與[!DNL Target]的後端伺服器通訊，在此程式中，會建立第三方Cookie並放置在使用者的瀏覽器上。 透過使用者瀏覽器上的第三方Cookie,[!DNL Target]可為單一使用者在不同網域間提供一致的體驗。

## 谷歌新的Cookie配方

為了在Cookie跨網站傳送時提供防護以保護使用者，Google計畫新增名為SameSite的IETF標準支援，該標準要求網頁開發人員在Set-Cookie標題中使用SameSite屬性元件來管理Cookie。

有三個不同的值可傳遞至 SameSite 屬性: 嚴格、鬆散或無。

| 值 | 說明 |
| --- | --- |
| 嚴格 | 只有在造訪最初設定的網域時，才能存取具有此設定的 Cookie。也就是說，嚴格會完全封鎖 Cookie，以免跨網站使用。此選項最適合需要高安全性的應用程式，如銀行。 |
| 鬆散 | 只有在相同網站要求或具有非等冪HTTP要求的頂層導覽（例如`HTTP GET`）中，才會傳送具有此設定的Cookie。 因此，如果Cookie可供第三方使用，將會使用此選項，但新增的安全性優勢可保護使用者，避免受到CSRF攻擊的危害。 |
| 無 | 具有此設定的Cookie與目前Cookie的運作方式相同。 |

秉持上述原則，Chrome 80為使用者引進了兩種獨立設定：&quot;SameSite依預設Cookie&quot;和&quot;不含SameSite的Cookie必須是安全狀態。&quot; 這些設定將依預設在Chrome 80中啟用。

![SameSite對話方塊](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite依預設Cookie**:設定後，所有未指定SameSite屬性的Cookie都會自動強制使用 `SameSite = Lax`。
* **不含SameSite的Cookie必須是安全狀態**:設定後，不含SameSite屬性或包含的Cookie `SameSite = None` 必須是安全狀態。在此情境下，安全代表所有瀏覽器要求都必須遵循 HTTPS 通訊協定。未遵守此要求的 Cookie 會遭到拒絕。所有網站都應使用HTTPS來符合此需求。

## Target 遵循 Google 的安全性最佳實務

在Adobe中，我們一律希望支援業界針對安全性和隱私權的最新最佳實務。 我們很高興宣佈[!DNL Target]支援Google推出的新安全性和隱私權設定。

對於「SameSite依預設Cookie」設定，[!DNL Target]會繼續提供個人化，而不會受到您任何影響和干預。 [!DNL Target] 使用第一方 Cookie 且將繼續正常運作，因為 Google Chrome 已套用 `SameSite = Lax` 標幟。

針對「不含SameSite的Cookie必須是安全狀態」選項，如果您未選擇加入[!DNL Target]中的跨網域追蹤功能，[!DNL Target]中的第一方Cookie將會繼續運作。

不過，當您選擇加入使用跨網域追蹤以跨多個網域運用[!DNL Target]時，Chrome會要求為第三方Cookie使用`SameSite = None`和安全標幟。 這表示您必須確保您的網站使用HTTPS通訊協定。 [!DNL Target]中的用戶端程式庫會自動使用HTTPS通訊協定，並將`SameSite = None`和安全標幟附加至[!DNL Target]中的第三方Cookie，以確保所有活動能繼續提供。

## 您需要做什麼?

若要了解讓[!DNL Target]繼續適用於Google Chrome 80+使用者，請參閱下表，其中會顯示下列各欄：

* **Target JavaScript程式庫**:如果您使用at.js 1.** xor at.js 2.** 將您的網站放入。
* **SameSite依預設Cookie =啟用**:若您的使用者已啟用「SameSite依預設Cookie」，這對您會有何影響，而為了繼續正常運作，是否有任何 [!DNL Target] 需要執行的事項。
* **不含SameSite的Cookie必須是安全狀態=啟用**:如果您的使用者已啟用「不含SameSite的Cookie必須是安全狀態」，這對您會有何影響，而為了讓繼續運作，是否有任何 [!DNL Target] 需要執行的事項。

| Target JavaScript程式庫 | SameSite 依預設 Cookie = 啟用 | 不含 SameSite 的 Cookie 必須是安全狀態 = 啟用 |
| --- | --- | --- |
| at.js 1.** xwith第一方Cookie。 | 沒有影響。 | 如果您未使用跨網域追蹤，則不會有影響。 |
| at.js 1.** x並啟用跨網域追蹤。 | 沒有影響。 | 您必須為網站啟用HTTPS通訊協定。<br>[!DNL Target] 使用協力廠商cookie來追蹤使用者，而Google會要求協力廠商cookie具有 `SameSite = None` 和安全標幟。安全標幟要求您的網站必須使用HTTPS通訊協定。 |
| at.js 2.*x* | 沒有影響。 | 沒有影響。 |

## [!DNL Target]需要做什麼？

那麼，我們需要在平台中執行哪些動作來協助您遵守新的Google Chrome 80+ SameSite Cookie原則？

| Target JavaScript程式庫 | SameSite 依預設 Cookie = 啟用 | 不含 SameSite 的 Cookie 必須是安全狀態 = 啟用 |
| --- | --- | --- |
| at.js 1.** xwith第一方Cookie。 | 沒有影響。 | 如果您未使用跨網域追蹤，則不會有影響。 |
| at.js 1.** x並啟用跨網域追蹤。 | 沒有影響。 | at.js 1.** x並啟用跨網域追蹤。 |
| at.js 2.*x* | 沒有影響。 | 沒有影響。 |

## 如果您不使用HTTPS通訊協定移至，會有何影響？

唯一會影響您的使用案例是，如果您使用[!DNL Target]中的跨網域追蹤功能，而透過at.js 1.*x* 不提供跨網域追蹤的立即可用支援。若不改用Google需求的HTTPS，您會發現您網域上的不重複訪客數量會激增，因為Google會捨棄我們使用的第三方Cookie。 由於會捨棄第三方Cookie，因此當使用者從一個網域導覽至另一個網域時，[!DNL Target]將無法為該使用者提供一致且個人化的體驗。 協力廠商Cookie主要用於識別在您擁有的網域間導覽的單一使用者。

## 結論

在產業大幅演化並為消費者打造更安全Web環境的同時，[!DNL Adobe]全心致力於協助客戶提供個人化體驗，確保使用者的安全性和隱私權。 您只需遵循上述最佳實務，並善用[!DNL Target]來遵循Google Chrome的新SameSite Cookie原則。
