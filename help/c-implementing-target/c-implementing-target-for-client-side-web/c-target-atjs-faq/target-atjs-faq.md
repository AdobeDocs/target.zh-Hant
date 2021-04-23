---
keywords: at.js faq;at.js 常見問題集;忽隱忽現;載入工器;頁面載入器;跨網域;檔案大小;x-網域;at.js 與 mbox.js;僅限 x;safari;單頁應用程式;缺少選取器;選取器;tt.omtrdc.net;spa;Adobe Experience Manager;AEM;ip 位址;httponly;HttpOnly;安全;ip;Cookie 網域
description: 閱讀有關Adobe [!DNL Target] at.js JavaScript程式庫之常見問題的解答。
title: at.js有哪些常見問題和答案？
feature: at.js
role: Developer
exl-id: 937f880a-1842-4655-be44-0a5614c2dbcc
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2700'
ht-degree: 92%

---

# at.js 常見問題

關於 at.js 常見問題的回答。

## 使用 at.js 或 mbox.js{#section_FE30D01A577C46ACB0F787B85F5E0F6B} 各有何優點? 

雖然 [!DNL at.js] 已取代 [!DNL mbox.js]，但我們仍持續支援 [!DNL mbox.js]。然而，對於大多數人來說，[!DNL at.js] 的優點多於 [!DNL mbox.js]。

除了眾多優點以外，[!DNL at.js] 還能改進 Web 實施的頁面載入時間、改進安全性，以及為單頁應用程式提供更好的實施選項。

下圖比較使用 mbox.js 或 at.js 的頁面載入效能。

![](assets/atjs_vesus_mboxjs.png)

如上圖所示，使用 mbox.js 時，頁面內容要等到 [!DNL Target] 呼叫完成之後才會開始載入。使用 at.js 時，頁面內容在 [!DNL Target] 呼叫起始時就開始載入，不會等到呼叫完成。

## at.js 和 mbox.js 對頁面載入時間有何影響? {#page-load}

許多客戶和顧問都想要知道 [!DNL at.js] 和 [!DNL mbox.js] 對頁面載入時間的影響，尤其是在比較新使用者和再度訪問的使用者時。可惜，有關 [!DNL at.js] 或 [!DNL mbox.js] 如何影響頁面載入時間，由於每一個客戶的實施不同，很難測量和提出具體數字。

不過，如果頁面上有「訪客 API」，我們就能更充分的瞭解 [!DNL at.js] 和 [!DNL mbox.js] 如何影響頁面載入時間。

>[!NOTE]
>
>只有當使用全域 mbox 時，「訪客 API」和 [!DNL at.js] 或 [!DNL mbox.js] 才會影響頁面載入時間 (原因在於主體隱藏技術)。訪客 API 整合不影響地區 mbox。

以下小節說明新訪客和再度造訪的訪客的動作序列:

### 新訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js / mbox.js 會載入、剖析和執行。
1. 如果已啟用全域 mbox 自動建立，Target JavaScript 資料庫:

   * 實體化訪客物件。
   * Target 資料庫會嘗試擷取 Experience Cloud 訪客 ID 資料。
   * 因為這是新訪客，「訪客 API」會向 demdex.net 發出跨網域請求。
   * 擷取 Experience Cloud 訪客 ID 資料之後，即會觸發對 Target 的要求。

### 再度訪問的訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js / mbox.js 會載入、剖析和執行。
1. 如果已啟用全域 mbox 自動建立，Target JavaScript 資料庫:

   * 實體化訪客物件。
   * Target 資料庫會嘗試擷取 Experience Cloud 訪客 ID 資料。
   * 訪客 API 會從 Cookie 擷取資料。
   * 擷取 Experience Cloud 訪客 ID 資料之後，即會觸發對 Target 的要求。

>[!NOTE]
>
>對於新訪客，當「訪客 API」存在時，Target 必須通過網路許多次，以確定 Target 請求包含 Experience Cloud 訪客 ID 資料。對於再度訪問的訪客，Target 只會通過網路到 Target 來擷取個人化內容。

## 從舊版 at.js 升級為版本 1.0.0 之後，為什麼我發現回應時間好像變慢了? {#section_DFBA5854FFD142B49AD87BFAA09896B0}

[!DNL at.js] 1.0.0 版本以及更新版本會平行觸發所有請求。舊版會循序執行請求，亦即請求會放入佇列中，Target 會等待第一個請求完成之後，再繼續處理下一個請求。

舊版 [!DNL at.js] 執行請求的方式易於發生所謂的「線頭阻塞」。在 [!DNL at.js] 1.0.0 以及更新版本中，Target 會切換至平行請求執行。

如果您檢查 [!DNL at.js] 0.9.1 的網路標籤瀑布圖，則會看到下一個 Target 請求要等到上一個完成時才會開始。[!DNL at.js] 1.0.0 以及更新版本就不是如此，所有請求基本上是同時開始。

從回應時間的角度來看，在數學上，這可以如下計算總和

<ul class="simplelist"> 
 <li> at.js 0.9.1: 所有 Target 請求的回應時間 = 請求回應時間的總和 </li> 
 <li> at.js 1.0.0 以及更新版本: 所有 Target 請求的回應時間 = 最長的請求回應時間 </li> 
</ul>

如您所見，[!DNL at.js] 1.0.0 能更快完成請求。此外，[!DNL at.js] 請求為非同步，Target 不會阻礙頁面呈現。即使請求需要幾秒才完成，您仍會看到呈現的頁面，在 Target 收到來自 Target 邊緣的回應之前，頁面只會有某些部分空白。

## 我是否可以非同步載入[!DNL Target]庫？{#section_AB9A0CA30C5440C693413F1455841470}

at.js 1.0.0 版可讓您非同步載入 Target 資料庫。

若要非同步載入 at.js:

* 建議方法是透過 Adobe Launch 或 Adobe Dynamic Tag Manager (DTM) 等標籤管理員進行。如需詳細資訊，請參閱[在Launch](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/index.html)教學課程中實作網站Experience Cloud的[新增Adobe Target](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html)一課。
* 您也可以在載入 at.js 的指令碼標記中新增 async 屬性，就能非同步載入 at.js。您應該使用如下的指令碼:

   ```
   <script src="<URL to at.js>" async></script>
   ```

* 您也可以使用此程式碼來非同步載入 at.js:

   ```
   var script = document.createElement('script'); 
   script.async = true; 
   script.src = "<URL to at.js>"; 
   document.head.appendChild(script);
   ```

非同步載入 at.js 可有效避免讓瀏覽器無法呈現；不過，此技術可能導致網頁上忽隱忽現。

您可以使用預先隱藏的程式碼片段來避免忽隱忽現情形， 它會隱藏頁面 (或指定部分)，然後在 at.js 和全域要求完全載入後顯示內容。您必須在載入 at.js 之前新增此程式碼片段。

如果您透過非同步的Launch實作部署at.js，請務必在啟動內嵌程式碼之前，直接將預先隱藏的程式碼片段加入您的頁面，如[在網站中實作啟動教學課程](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/index.html)的「新增目標預先隱藏程式碼片段](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html#add-the-target-pre-hiding-snippet)」一節所述。[

如果您是透過同步 DTM 實作部署 at.js，可透過頁面頂端觸發的頁面載入規則新增預先隱藏的程式碼片段。

如需詳細資訊，請參閱 [at.js 處理忽隱忽現情況的方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)。

## at.js 與 Adobe Experience Manager 整合 (AEM) 相容嗎?{#section_6177AE10542344239753764C6165FDDC}

[!DNL Adobe Experience Manager] 6.2 具有 FP-11577 (或更新版本) 現在支援 [!DNL at.js] 實作與其 [!UICONTROL Adobe Target Cloud Services] 整合。如需詳細資訊，請參閱 *Adobe Experience Manager 6.2* 文件中的[功能套件](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html)和[與 Adobe Target 整合](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html)。

## 使用 at.js{#section_4D78AAAE73C24E578C974743A3C65919} 時如何防止頁面載入忽隱忽現? 

Target 提供幾個方法來防止頁面載入忽隱忽現: 如需詳細資訊，請參閱[使用 at.js 防止忽隱忽現情形](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md#concept_AA168574397D4474B993EEAB90865EBA)。

## at.js{#section_6A25C9A14C66441785A7635FEF5C4475} 的檔案大小多大? 

at.js 檔案下載後大約 109 KB。不過，因為大部分伺服器會自動壓縮檔案，使檔案變小，at.js 在伺服器上壓縮 (使用 GZIP 或其他方法) 和當使用者造訪您的網站而載入時，大約是 34 KB。您安裝 at.js 的伺服器上的壓縮設定，就決定實際壓縮大小。

## at.js 為何比 mbox.js{#section_AA1C43897E46448FA3E26EEC10ED7E51} 還大? 

at.js 實作使用單一資料庫 ([!DNL at.js])，而 mbox.js 實作實際上使用兩個資料庫 ([!DNL mbox.js] 和 [!DNL target.js])。所以，at.js 要同時與 mbox.js *和* `target.js` 一起比較才公平。比較兩個版本的 gzip 大小，at.js 1.2 版是 34 KB，而 mbox.js 63 版是 26.2 KB。

at.js 較大，因為它執行的 DOM 剖析比 mbox.js 多很多。這有必要，因為 at.js 在 JSON 回應中是取得「原始」資料，必須轉換成有意義的資料。mbox.js 使用 `document.write()`，所有剖析均由瀏覽器完成。

儘管檔案較大，但我們的測試指出 at.js 的頁面載入比 mbox.js 更快。此外，在安全性方面，at.js 較優秀，因為不會動態載入額外檔案，或使用 `document.write`。

## at.js 中有 jQuery 嗎? 因為我的網站上已有 jQuery，我可以移除 at.js 的這部分嗎? {#section_E4604E46E7B34460B8DD6A78D9B476F9}

at.js 目前使用部分的 jQuery，因此，您在 at.js 頂端會看到 MIT 授權通知。jQuery 不公開，不會干擾您在頁面上已有的 jQuery 程式庫 (可能是不同版本)。恕不支援移除 at.js 內的 jQuery 程式碼。

## at.js 支援 Safari 和設為 x-only 的跨網域嗎? {#section_114EC271A6E045E1B2183B66F1B71285}

否，如果跨網域設為 x-only，且 Safari 已停用第三方 Cookie，則 [!DNL mbox.js] 和 at.js 會設定已停用的 Cookie，且不會對該特定用戶端的網域執行任何 mbox 請求。

為了支援 Safari 訪客，較好的 X-Domain 是「已停用」(僅設定第一方 Cookie) 或「已啟用」(在 Safari 上僅設定第一方 Cookie，而在其他瀏覽器上設定第一方和第三方 Cookie)。

## 我可以並列執行 at.js 與 mbox.js 嗎? {#section_4DCAF38DBAEB430CA486FAEFAE0E0A29}

在相同頁面上不可以。不過，在實作和測試 [!DNL at.js] 時，您可以在某些頁面上執行 [!DNL at.js]，而在其他頁面上執行 [!DNL mbox.js]，直到完全驗證 [!DNL at.js] 為止。

## 我可以在單頁應用程式中使用[!DNL Target] Visual Experience Composer嗎？{#section_459C1BEABD4B4A1AADA6CF4EC7A70DFB}

可以，若您使用 at.js 2.x，便可針對 SPA 使用 VEC。如需詳細資訊，請參閱[單頁應用程式 (SPA) 可視化體驗撰寫器](/help/c-experiences/spa-visual-experience-composer.md)。

## 我可以對 at.js 實施使用 Adobe Experience Cloud Debugger 嗎? {#section_FF3CF4C5FD2F4DB1BF1A6B39DA161637}

是.您也可以使用 mboxTrace 以進行偵錯，或使用瀏覽器的開發人員工具以檢查網路請求，篩選「mbox」以隔離 mbox 呼叫。

## 對於 at.js，mbox 名稱中可以使用特殊字元嗎? {#section_8E31D2E8A27642098934D7DACFB2A600}

可以，與 mbox.js 相同。

## 為什麼在我的網頁上 mbox 不會觸發? {#section_4BA5DA424B734324AAB51E4588FA50F5}

 客戶有時使用雲端型例項搭配 [!DNL Target]Target 進行測試或簡單的概念證明用途。這些網域和許多其他網域均屬於[公用字尾清單](https://publicsuffix.org/list/public_suffix_list.dat)。

如果您使用這些網域，則現代瀏覽器不會儲存 Cookie，除非您使用 targetGlobalSettings() 自訂 `cookieDomain` 設定。如需詳細資訊，請參閱[使用雲端型例項搭配 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566)。

## 使用 at.js 時，可以將 IP 位址用作 Cookie 網域嗎? {#section_8BEEC91A3410459D9E442840A3C88AF7}

可以，只要您使用 [at.js 1.2 版或更新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。不過，強烈建議您取得最新版本。

>[!NOTE]
>
>如果您使用 at.js 1.2 版或更新版本，則不需要下列範例。

視您使用 [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 的方式而定，在下載 at.js 之前，您可能需要另外修改程式碼。例如，假設您的 [!DNL Target] 實施在各種網站上需要稍微不同的設定，且您無法使用自訂 JavaScript 來動態定義這些設定，請在下載檔案之後和上傳至個別網站之前，手動完成這些自訂。

下列範例可讓您使用 `targetGlobalSettings()` at.js 函數，插入程式碼片段來支援 IP 位址:

此範例適用於單一 IP 位址:

```
if (window.location.hostname === '123.456.78.9') { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

此範例適用於 IP 位址範圍:

```
if (/^123\.456\.78\..*/g.test(window.location.hostname)) { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

## 為何會看到警告訊息，例如「動作缺少選取器」?  {#section_C36BED5B16634361A1BA46FCB731489D}

這些訊息與 [!DNL at.js] 功能無關。[!DNL at.js] 程式庫會嘗試報告 DOM 中找不到的任何事物。

如果您看到此警告訊息，以下為可能的根本原因:

* 頁面是動態建立的，at.js找不到元素。
* 頁面建立緩慢（由於網路速度緩慢），且at.js無法在DOM中找到選擇器。
* 執行活動的頁面結構已變更。如果您在可視化體驗撰寫器 (VEC) 中重新開啟活動，應該會看到警告訊息。您應該更新活動，以便找到所有必要元素。
* 基礎頁面是單頁應用程式 (SPA) 的一部分，或頁面包含的元素出現在頁面很下方，而 [!DNL at.js]「選取器輪詢機制」找不到這些元素。提高 `selectorsPollingTimeout` 或許有用。如需詳細資訊，請參閱 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。
* 任何點擊追蹤量度會嘗試將本身新增至每個頁面，而不論設定此量度的 URL。雖然無害，但此狀況會導致這些訊息大量出現。

   為了獲得最佳結果，請下載並使用最新版本的 [!DNL at.js]。如需詳細資訊，請參閱 [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)和[下載 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_1E1F958F9CCC4E35AD97581EFAF659E2)。

## [!DNL Target]伺服器呼叫前往的網域tt.omtrdc.net是什麼？{#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] 是 Adobe 之 EDGE 網路的網域名稱，用來接收 Target 的所有伺服器呼叫。

## 為何 at.js 和 mbox.js 不使用 HttpOnly 與 Secure Cookie 旗標? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly 只能透過伺服器端編碼來設定。Mbox 之類的 Target Cookie 是透過 JavaScript 編碼來建立與儲存，因此 Target 無法使用 HttpOnly Cookie 旗標。

Secure 只有在頁面是經由 HTTPS 來載入時，能透過 JavaScript 設定。如果頁面一開始是透過 HTTP 載入，JavaScript 無法設定此旗標。此外，如果 Secure 旗標已使用，則只有 HTTPS 頁面可使用 Cookie。

為確保 Target 能正確追蹤使用者，且由於 Cookie 都是在用戶端產生，Target 不會使用這兩種旗標。

## at.js 觸發網路要求的頻率為何?  {#section_57C5235DF7694AF093A845D73EABADFD}

Adobe Target 會在伺服器端執行其所有決策。這表示 at.js 會在每次頁面重新載入或叫用 at.js 公用 API 時，觸發網路要求。

## 在最好的情況下，我們能否期望使用者在隱藏、取代，和顯示內容方面，不會受到任何頁面載入上的可見影響? {#section_CB3C566AD61F417FAC0EC5AC706723EB}

at.js 會試圖長時間避免預先隱藏 HTML BODY 或其他 DOM 元素，但這取決於網路條件或活動設定。at.js 提供的[設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)可用於自訂隱藏 CSS 樣式的 BODY 設定，如此一來您就可以僅預先隱藏頁面的某些部份，而不用隱藏整個 HTML BODY。期望是那些部分包含了必須「個人化」的 DOM 元素。

## 在使用者符合活動資格的一般情況下，事件的序列為何?  {#section_56E6F448E901403FB77DF02F44C44452}

由於 at.js 要求為非同步 `XMLHttpRequest`，因此我們會執行下列步驟:

1. 頁面載入。
1. at.js 預先隱藏 HTML BODY。有可以預先隱藏特定容器，而非 HTML BODY 的設定。
1. at.js 要求觸發。
1. 收到 Target 回應後，Target 會擷取 CSS 選取器。
1. Target 會使用 CSS 選取器，建立 STYLE 標記以預先隱藏要自訂的 DOM 元素。
1. 移除預先隱藏 STYLE 的 HTML BODY。
1. Target 開始進行 DOM 元素的輪詢。
1. 若找到 DOM 元素，Target 會套用 DOM 變更，且系統會移除預先隱藏 STYLE 的元素。
1. 若找不到 DOM 元素，則全域逾時會取消隱藏元素，以避免頁面中斷。

## at.js 最後取消隱藏活動正在變更的元素時，頁面內容完全載入和顯示的頻率為何? {#section_01AFF476EFD046298A2E17FE3ED85075}

考量到上述情況，at.js 最後取消隱藏活動正在變更的元素時，頁面內容完全載入和顯示的頻率為何? 換句話說，除了活動內容外，頁面會完全顯示，而活動內容則會在其餘內容顯示後稍微顯示。

at.js 不會讓頁面無法呈現。使用者可能會注意到頁面上有一些空白區域，其代表 Target 將自訂的元素。若要套用的內容並未包含許多遠端資產 (例如 SCRIPT 或 IMG)，則所有內容皆應快速呈現。

## 完全快取的頁面會如何影響上述情況? 其餘頁面內容載入後，活動內容是否更有可能明顯可見?  {#section_CE76335A3E0B41CB8253DEE5E060FCDA}

若頁面快取在靠近使用者位置的 CDN 上，但不靠近 Target Edge，則使用者可能會看到一些延遲。Target Edge 在全球均勻分佈，因此大多數情況下這都不會是問題。

## 是否可以顯示主圖影像，然後在短暫的延遲後進行更換?  {#section_C25B07B25B854AAE8DEE1623D0FA62A3}

考量到下列情況:

Target 逾時為 5 秒。使用者載入具有自訂主圖影像活動的頁面。at.js 傳送要求以確認是否有要套用的活動，但無初始回應。假設使用者看見了主圖影像的一般內容，由於並未從 Target 收到任何關於相關活動是否存在的回應，4 秒後，Target 會傳回包含活動內容的回應。

在此階段，是否可以顯示替代版本? 4 秒後，是否可以更換主圖影像且使用者會注意到此影像更換?

起初，主圖影像 DOM 元素會隱藏。收到來自 Target 的回應後，at.js 會套用 DOM 變更 (例如取代 IMG 和顯示自訂的主圖影像)。

## at.js 需要什麼 HTML doctype?

at.js 需要 HTML 5 doctype。

此語法為:

`<!DOCTYPE html>`

HTML 5 doctype 可確保頁面以標準模式載入。使用怪異模式載入時，會停用 at.js 所根據的某些 JS API。在怪異模式下，Target 會停用 at.js。
