---
keywords: 概覽和參考資料；webkit;Cookie；第一方；第三方；第一方；第三方
description: 了解 [!DNL Target] Cookie行為（第一方Cookie、具有第一方Cookie的第三方Cookie，或獨立的第三方Cookie）。
title: 我可以在哪裡找到 [!DNL Target] Cookie的相關資訊？
feature: at.js
role: Developer
exl-id: 1c4e5b0b-8ae4-4526-aea0-318a33f4d247
source-git-commit: e773db20ac593108aa3e54aae1bcb2c0f713e387
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 58%

---

# Target Cookie

Cookie 的行為取決於其屬於第一方 Cookie、具有第一方 Cookie 的第三方 Cookie，或是獨立的第三方 Cookie。

>[!NOTE]
>
>本主題包含 `mboxSession` 和 `mboxPC` 的相關資訊。實作最佳實務建議您不要將敏感資訊與Cookie資料連結或儲存：`mboxSession`或`mboxPC`。

另請參閱[刪除Target Cookie](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md)。

## 何時使用第一方或第三方 Cookie {#section_F71B29420C004A7FA3B1921E619B326E}

您的網站設定會決定您要使用何種 Cookie。嘗試了解第一方和第三方Cookie時，請務必了解[!DNL Target]的運作方式。 如需詳細資訊，請參閱[How [!DNL Adobe Target] Works](/help/c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584) 。

cookie 有三種主要的使用狀況:

1. 單一網域。

   所有測試都會在一個頂層網域（`www.domain.com`、`store.domain.com`、`anysub.domain.com`等）中進行。

   方法：僅使用第一方Cookie（預設）。

1. 使用者橫跨網域，您也想要在這些網域中追蹤和測試其行為。

   範例: 一位使用者造訪您的網站進行購物，但透過 Yahoo 商店簽出。三種方式 (與您的帳戶代表一起決定最佳方式):

   * 啟用第一方和第三方 Cookie。
   * 僅啟用第三方Cookie（罕見，但有將mbox Cookie保留在網域外的優點）。
   * 僅啟用第一方 Cookie，並在跨網域時傳遞 `mboxSession` 參數。

      必須將`mboxSession`參數傳遞至登陸頁面，並從JavaScript資料庫(Adobe Experience Platform Web SDK或at.js)參照。 該頁面不能是中繼重新導向器頁面。

1. 您只會在第三方網站上使用 adbox 或 Flashbox。

   兩種方法（與您的客戶代表合作，決定最佳方法）:

   * 啟用第一方和第三方 Cookie。

      Flashbox 及動態創作元素需要第一方和第三方 Cookie。

   * 僅啟用第三方 Cookie。

      此方式僅用於其中執行之 AdBox 不含 Onsite 定位的罕見個案。

## 第一方 Cookie 行為 {#section_CE6313D979EA4D0897D2F661E7A8AFA7}

第一方 Cookie 儲存在 [!DNL clientdomain.com]，其中 `clientdomain` 為您的網域。

JavaScript程式庫會產生一個`mboxSession ID`，並將其儲存在[!DNL Target] Cookie中。 第一個mbox回應會包含選件和JavaScript，以將應用程式產生的`mboxPC ID`儲存於mbox的Cookie。

>[!NOTE]
>
>[!DNL Experience Cloud Visitor ID] 一律會設定 [!DNL AMCV_###@AdobeOrg] 第一方 Cookie。

## 第三方 Cookie 行為 {#section_4C3A83990BF8415BB1806602D84AED48}

第三方 Cookie 儲存在 [!DNL clientcode.tt.omtrdc.net]，而第一方 Cookie 儲存在 [!DNL clientdomain.com]，其中 `clientdomain` 為您的網域。

JavaScript程式庫會產生`mboxSession ID`。 第一個位置請求會傳回 HTTP 回應標頭，此標頭會嘗試設定名為 `mboxSession` 和 `mboxPC` 的第三方 Cookie，之後會傳回附有額外參數 (`mboxXDomainCheck=true`) 的重新導向請求。

若瀏覽器接受第三方 Cookie，則重新導向請求會包含這些 Cookie 並傳回選件。

若瀏覽器拒絕第三方 Cookie，則重新導向請求不會包含這些 Cookie，而網頁上的所有置會顯示預設內容。由於未設定 Cookie，因此每個頁面請求會再次發生上述相同的程序。

>[!NOTE]
>
>如未封鎖第三方 Cookie，則會設定 [!DNL demdex.net] Cookie。

## 第三方和第一方 Cookie 行為 {#section_F0C9AD8BFDF8457A999C4A07A0F7A981}

第三方 Cookie 儲存在 [!DNL clientcode.tt.omtrdc.net]，而第一方 Cookie 儲存在 [!DNL clientdomain.com]，其中 `clientdomain` 為您的網域。

JavaScript程式庫會產生`mboxSession ID`。 第一個位置請求會傳回 HTTP 回應標頭，此標頭會嘗試設定名為 `mboxSession` 和 `mboxPC` 的第三方 Cookie，之後會傳回附有額外參數 (`mboxXDomainCheck=true`) 的重新導向請求。

若瀏覽器接受第三方 Cookie，則重新導向請求會包含這些 Cookie 並傳回選件。

部分瀏覽器會拒絕第三方 Cookie。如果第三方 Cookie 被封鎖，第一方 Cookie 仍會運作。[!DNL Target] 會嘗試傳送第三方 Cookie，如果無法傳送，則 [!DNL Target] 只能追蹤用戶端的特定網域。如果第三方Cookie遭到封鎖，除非跨網域的連結附加`mboxSession`，否則就不能跨網域追蹤。 在這種情況下會設定另一個第一方 Cookie，並與之前的網域第一方 Cookie 同步。

## Cookie 設定 {#section_B498B8D1A34A444BBF84CC720EE9D87F}

Cookie 具有各種預設設定。您可以視需要變更這些設定，但Cookie持續時間除外。 變更 Cookie 設定時，請洽詢您的帳戶代表。

| 設定 | 資訊 |
|--- |--- |
| Cookie 名稱 | mbox。 |
| Cookie 網域 | 您從中提供內容的第一層與第二層網域。因為是從您公司的網域提供，所以Cookie是第一方Cookie。<br>範例: `mycompany.com`. |
| 伺服器網域 | `clientcode.tt.omtrdc.net`，使用您帳戶的用戶端代碼。 |
| Cookie 持續時間 | 自上次登入後兩週，Cookie仍會保留在訪客的瀏覽器上。 您無法變更 Cookie 持續時間。 |
| P3P 原則 | 此 Cookie 會依大部分瀏覽器中預設設定的要求，以 P3P 原則進行發佈。P3P原則會向提供Cookie的瀏覽器指出，以及資訊的使用方式。 |

Cookie會保留各種值，以管理您的訪客體驗促銷活動的方式：

| 值 | 定義 |
|--- |--- |
| session ID | 每個使用者作業會有一個唯一 ID。依預設，此ID會持續30分鐘。 |
| pc ID | 每位訪客瀏覽器的半永久性 ID。持續 14 天。 |
| check | 用來決定訪客是否支援 Cookie 的簡單測試值。每次訪客請求頁面時都會進行設定。 |
| disable | 如果訪客的載入時間超過JavaScript程式庫檔案中設定的逾時時間，則設定此選項。 依預設，此值會持續一小時。 |

## Apple WebKit追蹤變更對Safari訪客[!DNL Target]的影響 {#section_2A2E5730ED7D4A0985C904AFEA310AAE}

**追蹤如 [!DNL Adobe Target] 何運作？**

| Cookie | 詳細資料 |
|--- |--- |
| 第一方網域 | 適用於[!DNL Target]客戶的標準實作。 「mbox」Cookie 設定在客戶的網域中。 |
| 第三方追蹤 | 在[!DNL Target]和[!DNL Adobe Audience Manager](AAM)中，第三方追蹤對於廣告和鎖定目標使用案例非常重要。 第三方追蹤需要跨網站指令碼技術。[!DNL Target] 使用 `clientcode.tt.omtrd.net` 網域中設定的兩個 Cookie:「mboxSession」和「mboxPC」。 |
**Apple 採用什麼方法?**

從 Apple: 

「智慧型追蹤預防是新的 WebKit 功能，可進一步限制 Cookie 和其他網站資料，以減少跨網站追蹤。」

「這就是所謂的跨網站追蹤，而 `example-tracker.com` 使用的 Cookie 稱為第三方 Cookie。在我們的測試中，我們發現的熱門網站都有超過 70 個這種追蹤器，全部都安靜地收集使用者的資料。」

| 方法 | 詳細資料 |
|--- |--- |
| 智慧型追蹤預防 | 如需詳細資訊，請參閱 WebKit Open Source Web Browser Engine 網站上的[智慧型追蹤預防](https://webkit.org/blog/7675/intelligent-tracking-prevention/)。 |
| Cookie | Safari 如何處理 Cookie:<ul><li>使用者直接存取的網域上不存在的第三方 Cookie 永不儲存。這不是新的行為。Safari 尚不支援第三方 Cookie。</li><li>使用者直接存取的網域上所設定的第三方 Cookie 會在 24 小時後清除。</li><li>如果第一方網域已分類為跨網站追蹤使用者，則會在 30 天後清除第一方 Cookie。在線上將使用者送往不同網域的大型公司可能會發生此問題。Apple尚未明確說明這些網域的確切分類方式，或網域如何判斷是否已分類為跨網站追蹤使用者。</li></ul> |
| 使用「機器學習」來辨別跨網站的網域 | 從 Apple:<br>機器學習分類器：機器學習模型用於根據收集的統計資料，分類哪些私人控制的最上層網域可以跨網站追蹤使用者。從各種收集的統計資料中，有三個向量出現強烈訊號，表示應該根據目前的追蹤實務來分類: 一些唯一網域下的子資源、一些唯一網域下的子範圍，以及重新導向到的一些唯一網域。資料收集和分類全都在裝置上進行。<br>不過，如果使用者與 `example.com` 作為最上層網域（通常稱為第一方網域）的互動，「智慧型追蹤預防」會將此視為訊號，認為使用者對網站有興趣，並依此時間軸的說明暫時調整其行為：<br>如果使用者過去24小時 `example.com` 進行互動，當是第三方時，即可使 `example.com` 用其Cookie。此作法允許「在Y上以我的X帳戶登入」登入案例。<ul><li>作為頂級網域來造訪的網域不受影響。 例如，OKTA 網站</li><li>跨多個唯一網域來識別作為目前頁面之子網域或子範圍的網域。</li></ul> |

**對Adobe有何影響？**

| 受影響的功能 | 詳細資料 |
|--- |--- |
| 支援選擇退出 | Apple 的 WebKit 追蹤變更會暫停選擇退出支援。<br>[!DNL Target] 選擇退出會在 `clientcode.tt.omtrdc.net` 網域中使用 Cookie。如需更多詳細資料，請參閱[隱私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)。<br>[!DNL Target] 支援兩種選擇退出：<ul><li>由用戶端決定 (用戶端管理選擇退出連結)。</li><li>透過[!DNL Adobe]選擇讓使用者退出所有客戶的所有[!DNL Target]功能。</li></ul>兩種方法都使用第三方 Cookie。 |
| [!DNL Target] 活動 | 客戶可以為其[!DNL Target]帳戶選擇其[設定檔存留期長度](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md)（最多90天）。 問題是如果帳戶的設定檔存留期超過30天，且第一方Cookie因客戶的網域已標示為跨網站追蹤而被清除，則Safari訪客的行為會在[!DNL Target]中的以下幾方面受到影響：<br>**[!DNL Target]報表&#x200B;**:如果Safari使用者進入活動，在30天後回訪，然後轉換，則該使用者會計為兩個訪客和一個轉換。<br>[!DNL Analytics]對於使用 作為報表來源 (A4T) 的活動，也同樣是此行為。<br>**&#x200B;設定檔與活動成員資格&#x200B;**:<ul><li>第一方 Cookie 到期時會清除設定檔資料。</li><li>第一方 Cookie 到期時會清除活動成員資格。</li><li> [!DNL Target]對於採用第三方 Cookie 實作或第一方和第三方 Cookie 實作的帳戶， 在 Safari 中沒有作用。這不是新的行為。Safari有段時間未允許第三方Cookie。</li></ul><br>**建議**:如果擔心客戶網域可能標示為跨工作階段追蹤訪客，最好將設定檔存留期設為30天或更少 [!DNL Target]。此限制可確保在Safari和所有其他瀏覽器中以類似方式追蹤使用者。 |
