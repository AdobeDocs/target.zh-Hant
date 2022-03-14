---
keywords: google;samesite;cookies;chrome 80;ietf
description: 瞭解Adobe [!DNL Target] 處理隨GoogleChrome版本80而引入的SameSite IETF標準，以及您需要做什麼來遵守這些策略。
title: 如何 [!DNL Target] 處理Google的Samesite Cookie政策？
feature: Privacy & Security
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1948'
ht-degree: 7%

---

# Google Chrome SameSite Cookie 原則

Google將在預設情況下，開始為Chrome 80的用戶實施新的cookie政策。 Chrome 80定於2020年初發佈。 本文介紹您需要瞭解的有關新SameSite Cookie策略的所有資訊，以及如何 [!DNL Adobe Target] 支援這些策略，以及您如何 [!DNL Target] 遵守GoogleChrome的新SameSite Cookie策略。

從Chrome 80開始，Web開發人員必須明確指定哪些Cookie可以跨網站工作。 這是Google計畫為改善網路隱私和安全而發佈的多項聲明中的第一項。

鑑於Facebook在隱私和安全方面一直處於熱門地位，Apple和Google等其他主要參與者迅速抓住機會創造新的身份，成為隱私和安全捍衛者。 Apple率先通過ITP 2.1和ITP 2.2宣佈今年年初對其cookie政策進行了修改。在ITP 2.1中，Apple完全阻止第三方Cookie，並僅將在瀏覽器上建立的Cookie保存七天。 在ITP 2.2中，Cookie只保存一天。 Google的宣佈遠沒有Apple的那麼激進，但這是朝著相同的最終目標邁出的第一步。 有關Apple政策的詳細資訊，請參見 [Apple智慧跟蹤預防(ITP)2.x](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## 什麼是Cookie，以及它們的使用方式？

在深入瞭解Google對Cookie策略的更改之前，讓我們先瞭解一下Cookie是什麼以及它們的使用方式。 簡言之，Cookie是儲存在Web瀏覽器中的用於記住用戶屬性的小型文本檔案。

Cookie很重要，因為它們增強了用戶瀏覽Web時的體驗。 例如，如果您正在電子商務網站上購物，並在購物車中添加某些內容，但不在該訪問中登錄或購買，則Cookie會記住您的物品，並將它們保存在購物車中，供您下次訪問。 或者，想像一下，如果每次訪問您喜愛的社交媒體網站時，您都被迫重新輸入用戶名和密碼。 Cookie也解決了這個問題，因為它們儲存有助於站點識別您身份的資訊。 這些類型的Cookie稱為第一方Cookie，因為它們是由您訪問的網站建立和使用的。

第三方Cookie也存在。 為了更好地理解它們，讓我們考慮以下示例：

假設一家名為「好友」的社交媒體公司提供了一個「共用」按鈕，其他網站實施該按鈕，讓「好友」用戶在「好友」訂閱源上共用該網站的內容。 現在，用戶會在使用「共用」按鈕的新聞網站上閱讀新聞文章，然後按一下該按鈕自動在其「好友」帳戶上發佈。

為了實現此目的，瀏覽器從中取取「好友共用」按鈕 `platform.friends.com` 當新聞文章被載入時。 在此過程中，瀏覽器將包含用戶登錄憑據的好友cookie附加到朋友伺服器請求。 這樣，好友就可以在其訂閱源中代表用戶發佈新聞文章，而無需用戶登錄。

這都可以通過使用第三方Cookie來實現。 在這種情況下，第三方Cookie將保存在瀏覽器上， `platform.friends.com`，所以 `platform.friends.com` 可以代表用戶在「好友」應用中發帖。

如果您想像一下，如何在沒有第三方Cookie的情況下實現此使用情形，用戶將必須執行大量手動步驟。 首先，用戶必須複製新聞文章的連結。 其次，用戶必須單獨登錄朋友應用。 然後，用戶將按一下「建立帖子」按鈕。 然後，用戶將複製並貼上文本欄位中的連結，最後按一下「發佈」。 正如您所看到的，第三方Cookie極大地幫助了用戶體驗，因為手動步驟可以大大減少。

更一般地說，第三方Cookie使資料能夠儲存在用戶的瀏覽器上，而不需要用戶明確訪問網站。

## 安全問題

雖然cookie增強了用戶體驗和功能廣告，但它們也會引入諸如跨站點請求偽造(CSRF)攻擊等安全漏洞。 例如，如果用戶登錄到銀行站點以支付信用卡賬單並離開該站點而不註銷，然後在同一會話中瀏覽到惡意站點，則可能會發生CSRF攻擊。 惡意站點可能包含向銀行站點發出請求的代碼，該請求在頁面載入時執行。 由於用戶仍然被驗證到銀行站點，因此會話cookie可用於啟動CSRF攻擊以從用戶的銀行帳戶啟動資金轉移事件。 這是因為，無論您何時訪問站點，都會在HTTP請求中附加所有Cookie。 由於這些安全問題，Google正在試圖緩解這些問題。

## 如何 [!DNL Target] 用曲奇嗎？

儘管說了這麼多，讓我們看看 [!DNL Target] 使用cookie。 為了讓你 [!DNL Target] 首先，您需要安裝 [!DNL Target] 站點上的JavaScript庫。 這樣，您就可以在訪問站點的用戶的瀏覽器中放置第一方cookie。 當用戶與網站交互時，您可以將用戶的行為和興趣資料傳遞給 [!DNL Target] 通過JavaScript庫。 的 [!DNL Target] JavaScript庫使用第一方Cookie提取有關用戶的標識資訊，以映射到用戶的行為和興趣資料。 此資料然後由 [!DNL Target] 為個性化活動提供動力。

目標還（有時）使用第三方Cookie。 如果您擁有多個位於不同域上的網站，並且希望跟蹤這些網站的用戶行程，則可以通過利用跨域跟蹤來使用第三方Cookie。 通過在 [!DNL Target] JavaScript庫，您的帳戶將開始使用第三方Cookie。 當用戶從一個域跳到另一個域時，瀏覽器與 [!DNL Target]，在此過程中，將建立第三方cookie並將其放在用戶的瀏覽器上。 通過用戶瀏覽器上的第三方Cookie, [!DNL Target] 能夠跨不同域為單個用戶提供一致的體驗。

## Google新餅乾食譜

為了在跨站點發送Cookie時提供保護，以便保護用戶，Google計畫添加對IETF標準SameSite的支援，該標準要求Web開發人員使用Set-Cookie標頭中的SameSite屬性元件來管理Cookie。

有三個不同的值可傳遞至 SameSite 屬性: 嚴格、鬆散或無。

| 值 | 說明 |
| --- | --- |
| 嚴格 | 只有在造訪最初設定的網域時，才能存取具有此設定的 Cookie。也就是說，嚴格會完全封鎖 Cookie，以免跨網站使用。對於銀行等需要高安全性的應用程式而言，此選項最為合適。 |
| 鬆散 | 具有此設定的Cookie僅在同一站點請求或具有非冪等HTTP請求的頂級導航上發送，如 `HTTP GET`。 因此，如果第三方可以使用cookie，但增加了安全優勢，保護用戶不受CSRF攻擊的傷害，則將使用此選項。 |
| 無 | 具有此設定的Cookie與Cookie當前的工作方式相同。 |

考慮到上述情況，Chrome 80為用戶引入了兩種獨立設定：&quot;SameSite by default cookies&quot;和&quot;Cookies without SameSite必須安全。&quot; 預設情況下，這些設定將在Chrome 80中啟用。

![「同一站點」對話框](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **預設情況下，SameSiteCookie**:設定後，所有未指定SameSite屬性的Cookie將自動被強制使用 `SameSite = Lax`。
* **沒有SameSite的Cookie必須是安全的**:設定時，不帶SameSite屬性或帶 `SameSite = None` 必須安全。 在此情境下，安全代表所有瀏覽器要求都必須遵循 HTTPS 通訊協定。未遵守此要求的 Cookie 會遭到拒絕。所有網站都應使用HTTPS來滿足此要求。

## Target 遵循 Google 的安全性最佳實務

在Adobe，我們始終希望支援業界在安全和隱私方面的最新最佳做法。 我們高興地宣佈 [!DNL Target] 支援Google引入的新安全和隱私設定。

對於「預設Cookie」設定， [!DNL Target] 將繼續提供個性化服務，而不受您的影響和干預。 [!DNL Target] 使用第一方 Cookie 且將繼續正常運作，因為 Google Chrome 已套用 `SameSite = Lax` 標幟。

對於「Cookies without SameSite be secure」選項，如果您未選擇加入中的跨域跟蹤功能 [!DNL Target]，第一個 [!DNL Target] 會繼續工作。

但是，當您選擇使用跨域跟蹤來利用 [!DNL Target] 跨多個域，Chrome需要 `SameSite = None` 和用於第三方Cookie的安全標誌。 這意味著您必須確保您的站點使用HTTPS協定。 中的客戶端庫 [!DNL Target] 將自動使用HTTPS協定並附加 `SameSite = None` 並將標籤保護到第三方Cookie [!DNL Target] 確保所有活動繼續開展。

## 您需要做什麼?

要理解你需要做什麼 [!DNL Target] 繼續為GoogleChrome 80+用戶工作，請參閱下表，您將看到其中的以下列：

* **目標JavaScript庫**:如果您使用at.js 1。*x* 或at.js 2。*x* 在你的網站上。
* **預設情況下SameSite Cookie =已啟用**:如果您的用戶啟用了「預設情況下為SameSite Cookie」，它將如何影響您，以及您是否需要執行任何操作 [!DNL Target] 繼續工作。
* **沒有SameSite的Cookie必須是安全的=已啟用**:如果您的用戶啟用了「沒有SameSite的Cookie必須是安全的」，它會對您產生什麼影響，您是否需要執行任何操作 [!DNL Target] 繼續工作。

| 目標JavaScript庫 | SameSite 依預設 Cookie = 啟用 | 不含 SameSite 的 Cookie 必須是安全狀態 = 啟用 |
| --- | --- | --- |
| at.js 1.*x* 吃第一場曲奇。 | 沒有影響。 | 如果不使用跨域跟蹤，則不會影響。 |
| at.js 1 *x* 啟用跨域跟蹤。 | 沒有影響。 | 必須為站點啟用HTTPS協定。<br>[!DNL Target] 使用第三方cookie跟蹤用戶，而Google要求第三方cookie `SameSite = None` 和安全標誌。 「安全」標誌要求您的站點必須使用HTTPS協定。 |
| at.js 2.*x* | 沒有影響。 | 沒有影響。 |

## 什麼是 [!DNL Target] 需要做嗎？

那麼，我們需要在我們的平台中做些什麼來幫助您遵守新的GoogleChrome 80+ SameSite Cookie策略？

| 目標JavaScript庫 | SameSite 依預設 Cookie = 啟用 | 不含 SameSite 的 Cookie 必須是安全狀態 = 啟用 |
| --- | --- | --- |
| at.js 1 *x* 吃第一場曲奇。 | 沒有影響。 | 如果不使用跨域跟蹤，則不會影響。 |
| at.js 1 *x* 啟用跨域跟蹤。 | 沒有影響。 | at.js 1 *x* 啟用跨域跟蹤。 |
| at.js 2 *x* | 沒有影響。 | 沒有影響。 |

## 如果您不轉移到使用HTTPS協定，會產生什麼影響？

影響您的唯一用例是，如果您在 [!DNL Target] 通過at.js 1。*x* 不提供跨網域追蹤的立即可用支援。如果不轉到Google要求的HTTPS，您將看到域中的唯一訪問者數量激增，因為我們使用的第三方cookie將被Google丟棄。 因為第三方餅乾會被丟棄， [!DNL Target] 當用戶從一個域導航到另一個域時，將無法為該用戶提供一致且個性化的體驗。 第三方cookie主要用於標識在您擁有的域中導航的單個用戶。

## 結論

隨著行業在為消費者打造更安全的網路方面大步前進， [!DNL Adobe] 絕對致力於幫助客戶以確保最終用戶安全和隱私的方式提供個性化體驗。 您只需遵循上述最佳做法並利用 [!DNL Target] 遵守GoogleChrome的新SameSite Cookie策略。
