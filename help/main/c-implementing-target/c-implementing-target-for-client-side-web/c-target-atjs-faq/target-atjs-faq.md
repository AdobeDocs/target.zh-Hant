---
keywords: at.js faq;at.js 常見問題集;忽隱忽現;載入工器;頁面載入器;跨網域;檔案大小;x-網域;at.js 與 mbox.js;僅限 x;safari;單頁應用程式;缺少選取器;選取器;tt.omtrdc.net;spa;Adobe Experience Manager;AEM;ip 位址;httponly;HttpOnly;安全;ip;Cookie 網域
description: 閱讀有關Adobe的常見問題解答 [!DNL Target] at.js JavaScript庫。
title: at.js的常見問題和答案是什麼？
feature: at.js
role: Developer
exl-id: 937f880a-1842-4655-be44-0a5614c2dbcc
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '2590'
ht-degree: 57%

---

# at.js 常見問題

對有關 [!DNL Adobe Target] at.js JavaScript庫。

## 使用 at.js 或 mbox.js 各有何優點? {#section_FE30D01A577C46ACB0F787B85F5E0F6B}

的 [!DNL at.js] 庫替換 [!DNL mbox.js]。 的 [!DNL mbox.js] 不再支援庫。 然而，對於大多數人來說，[!DNL at.js] 的優點多於 [!DNL mbox.js]。

除了眾多優點以外，[!DNL at.js] 還能改進 Web 實施的頁面載入時間、改進安全性，以及為單頁應用程式提供更好的實施選項。

下圖比較使用 mbox.js 或 at.js 的頁面載入效能。

![](assets/atjs_vesus_mboxjs.png)

如上所示，使用mbox.js時，直到 [!DNL Target] 呼叫完成。 使用 at.js 時，頁面內容在 [!DNL Target] 呼叫起始時就開始載入，不會等到呼叫完成。

## at.js 和 mbox.js 對頁面載入時間有何影響? {#page-load}

許多客戶和顧問都想要知道 [!DNL at.js] 和 [!DNL mbox.js] 對頁面載入時間的影響，尤其是在比較新使用者和再度訪問的使用者時。可惜，有關 [!DNL at.js] 或 [!DNL mbox.js] 如何影響頁面載入時間，由於每一個客戶的實施不同，很難測量和提出具體數字。

但是，如果訪問者API在頁面上存在， [!DNL Target] 更瞭解如何 [!DNL at.js] 和 [!DNL mbox.js] 影響頁面載入時間。

>[!NOTE]
>
>只有當使用全域 mbox 時，「訪客 API」和 [!DNL at.js] 或 [!DNL mbox.js] 才會影響頁面載入時間 (原因在於主體隱藏技術)。訪客 API 整合不影響地區 mbox。

以下小節說明新訪客和再度造訪的訪客的動作序列:

### 新訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js / mbox.js 會載入、剖析和執行。
1. 如果已啟用全域 mbox 自動建立，Target JavaScript 資料庫:

   * 實體化訪客物件。
   * 的 [!DNL Target] 庫嘗試檢索 [!DNL Experience Cloud Visitor ID] 資料。
   * 由於此訪問者是新訪問者，因此訪問者API會向demdex.net發出跨域請求。
   * 之後 [!DNL Experience Cloud Visitor ID] 檢索資料，請求 [!DNL Target] 被炒了。

### 再度訪問的訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js / mbox.js 會載入、剖析和執行。
1. 如果啟用全局框自動建立， [!DNL Target] JavaScript庫：

   * 實體化訪客物件。
   * 的 [!DNL Target] 庫嘗試檢索 [!DNL Experience Cloud Visitor ID] 資料。
   * 訪客 API 會從 Cookie 擷取資料。
   * 之後 [!DNL Experience Cloud Visitor ID] 檢索資料，請求 [!DNL Target] 被炒了。

>[!NOTE]
>
>對於新訪問者，當訪問者API出現時， [!DNL Target] 必須多次翻過電線，以確保 [!DNL Target] 請求包含 [!DNL Experience Cloud Visitor ID] 資料。 回國遊客， [!DNL Target] 越過鐵絲網 [!DNL Target] 的子菜單。

## 從舊版 at.js 升級為版本 1.0.0 之後，為什麼我發現回應時間好像變慢了? {#section_DFBA5854FFD142B49AD87BFAA09896B0}

[!DNL at.js] 1.0.0 版本以及更新版本會平行觸發所有請求。以前的版本會按順序執行請求，這意味著請求會被放入隊列， [!DNL Target] 等待第一個請求完成，然後再轉到下一個請求。

舊版 [!DNL at.js] 執行請求的方式易於發生所謂的「線頭阻塞」。在 [!DNL at.js] 1.0.0 以及更新版本中， 會切換至平行請求執行。[!DNL Target]

如果您檢查 [!DNL at.js] 0.9.1 的網路標籤瀑布圖，則會看到下一個 請求要等到上一個完成時才會開始。[!DNL Target]這個序列不是 [!DNL at.js] 1.0.0和後來，所有請求基本上同時開始。

從響應時間的角度，從數學上來說，這個序列可以這樣求和

<ul class="simplelist"> 
 <li> at.js 0.9.1:所有響應時間 [!DNL Target] 請求=請求響應時間之和 </li> 
 <li> at.js 1.0.0和更高版本：所有響應時間 [!DNL Target] 請求數=請求響應時間的最大值 </li> 
</ul>

的 [!DNL at.js] 庫版本1.0.0更快地完成請求。 此外，[!DNL at.js] 請求為非同步， 不會阻礙頁面呈現。[!DNL Target]即使請求需要幾秒鐘才能完成，您仍會看到呈現的頁面，只有頁面的某些部分被遮蔽，直到 [!DNL Target] 從 [!DNL Target] 邊。

## 我能否載入 [!DNL Target] 庫非同步嗎？ {#section_AB9A0CA30C5440C693413F1455841470}

at.js 1.0.0版本使載入 [!DNL Target] 庫非同步。

若要非同步載入 at.js:

* 建議的方法是通過 [!DNL Adobe Experience Platform]。
* 您也可以在載入 at.js 的指令碼標記中新增 async 屬性，就能非同步載入 at.js。使用類似的功能：

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

您可以使用預隱藏的代碼段來避免閃爍，該代碼段隱藏頁（或指定的部分），然後在at.js和已載入全局請求後顯示它。 您必須在載入 at.js 之前新增此程式碼片段。

如果通過非同步部署at.js [!DNL Adobe Experience Platform] 實現，請確保在實現之前將預隱藏的代碼段直接包含在您的頁面上 [!DNL Target] 使用 [!DNL Adobe Experience Platform] 嵌入代碼。

如果您是透過同步 DTM 實作部署 at.js，可透過頁面頂端觸發的頁面載入規則新增預先隱藏的程式碼片段。

如需詳細資訊，請參閱 [at.js 處理忽隱忽現情況的方式](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/)。

## 與 [!DNL Adobe Experience Manager] 整合(Experience Manager)? {#section_6177AE10542344239753764C6165FDDC}

[!DNL Adobe Experience Manager] 6.2 具有 FP-11577 (或更新版本) 現在支援 [!DNL at.js] 實施與其 [!UICONTROL Adobe Target Cloud Services] 整合。

## 使用 at.js 時如何防止頁面載入忽隱忽現? {#section_4D78AAAE73C24E578C974743A3C65919}

Target 提供幾個方法來防止頁面載入忽隱忽現: 如需詳細資訊，請參閱[使用 at.js 防止忽隱忽現情形](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/)。

## at.js 的檔案大小多大? {#section_6A25C9A14C66441785A7635FEF5C4475}

at.js 檔案下載後大約 109 KB。不過，因為大部分伺服器會自動壓縮檔案，使檔案變小，at.js 在伺服器上壓縮 (使用 GZIP 或其他方法) 和當使用者造訪您的網站而載入時，大約是 34 KB。您安裝 at.js 的伺服器上的壓縮設定，就決定實際壓縮大小。

## at.js 為何比 mbox.js 還大? {#section_AA1C43897E46448FA3E26EEC10ED7E51}

at.js 實作使用單一資料庫 ([!DNL at.js])，而 mbox.js 實作實際上使用兩個資料庫 ([!DNL mbox.js] 和 [!DNL target.js])。所以，at.js 要同時與 mbox.js *和* `target.js` 一起比較才公平。比較兩個版本的 gzip 大小，at.js 1.2 版是 34 KB，而 mbox.js 63 版是 26.2 KB。

at.js 較大，因為它執行的 DOM 剖析比 mbox.js 多很多。這有必要，因為 at.js 在 JSON 回應中是取得「原始」資料，必須轉換成有意義的資料。mbox.js使用 `document.write()` 所有解析都由瀏覽器完成。

儘管檔案較大，但我們的測試指出 at.js 的頁面載入比 mbox.js 更快。此外，從安全形度講，at.js更優越，因為它不會動態載入附加檔案或使用 `document.write`。

## at.js 中有 jQuery 嗎? 因為我的網站上已有 jQuery，我可以移除 at.js 的這部分嗎? {#section_E4604E46E7B34460B8DD6A78D9B476F9}

at.js當前使用jQuery的部分，因此您會在at.js的頂部看到MIT許可證通知。 jQuery 不公開，不會干擾您在頁面上已有的 jQuery 程式庫 (可能是不同版本)。恕不支援移除 at.js 內的 jQuery 程式碼。

## at.js 支援 Safari 和設為 x-only 的跨網域嗎? {#section_114EC271A6E045E1B2183B66F1B71285}

否，如果跨域設定為x-only且Safari禁用了第三方Cookie，則兩者都 [!DNL mbox.js] at.js設定禁用的cookie，並且不會為該特定客戶端的域執行mbox請求。

為了支援 Safari 訪客，較好的 X-Domain 是「已停用」(僅設定第一方 Cookie) 或「已啟用」(在 Safari 上僅設定第一方 Cookie，而在其他瀏覽器上設定第一方和第三方 Cookie)。

## 我能用 [!DNL Target] 我的單頁應用程式中的Visual Experience Composer(VEC)? {#section_459C1BEABD4B4A1AADA6CF4EC7A70DFB}

是，如果使用at.js 2.x,SPA則可將VEC用於。有關詳細資訊，請參見 [單頁(SPA)Visual Experience Composer](/help/main/c-experiences/spa-visual-experience-composer.md)。

## 我能用 [!DNL Adobe Experience Cloud] 是否使用at.js實現的調試器？ {#section_FF3CF4C5FD2F4DB1BF1A6B39DA161637}

是.您也可以使用 mboxTrace 以進行偵錯，或使用瀏覽器的開發人員工具以檢查網路請求，篩選「mbox」以隔離 mbox 呼叫。

## 對於 at.js，mbox 名稱中可以使用特殊字元嗎? {#section_8E31D2E8A27642098934D7DACFB2A600}

可以，與 mbox.js 相同。

## 為什麼在我的網頁上 mbox 不會觸發? {#section_4BA5DA424B734324AAB51E4588FA50F5}

[!DNL Target] 客戶有時使用雲端型例項搭配 [!DNL Target] 進行測試或簡單的概念證明用途。這些網域和許多其他網域均屬於[公用字尾清單](https://publicsuffix.org/list/public_suffix_list.dat)。

如果您使用這些域，則現代瀏覽器不會保存Cookie，除非您自定義 `cookieDomain` 使用targetGlobalSettings()設定。 如需詳細資訊，請參閱[使用雲端型例項搭配 Target](https://developer.adobe.com/target/implement/client-side/target-debugging-atjs/targeting-using-cloud-based-instances/)。

## 使用 at.js 時，可以將 IP 位址用作 Cookie 網域嗎? {#section_8BEEC91A3410459D9E442840A3C88AF7}

可以，只要您使用 [at.js 1.2 版或更新版本](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)。[!DNL Adobe] 但強烈建議您保持最新版本。

>[!NOTE]
>
>如果您使用 at.js 1.2 版或更新版本，則不需要下列範例。

視您使用 [targetGlobalSettings](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) 的方式而定，在下載 at.js 之前，您可能需要另外修改程式碼。例如，假設您的 [!DNL Target] 實施在各種網站上需要稍微不同的設定，且您無法使用自訂 JavaScript 來動態定義這些設定，請在下載檔案之後和上傳至個別網站之前，手動完成這些自訂。

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

## 為何會看到警告訊息，例如「動作缺少選取器」? {#section_C36BED5B16634361A1BA46FCB731489D}

這些消息與 [!DNL at.js] 功能。 [!DNL at.js] 程式庫會嘗試報告 DOM 中找不到的任何事物。

如果您看到此警告訊息，以下為可能的根本原因:

* 正在動態生成該頁，且at.js找不到該元素。
* 正在緩慢生成該頁（由於網路速度慢），且at.js在DOM中找不到選擇器。
* 激活的頁面結構[!UICONTROL y正在運行，已更改。 如果在 ]Visual Experience Composer(VEC)，應收到警告消息。 更新活動，以便找到所有必要的元素。
* 基礎頁是 [!UICONTROL 單頁應用程式] (SPA)或頁面包含的元素在頁面和 [!DNL at.js] 「selector輪詢機制」找不到這些元素。 提高 `selectorsPollingTimeout` 或許有用。如需詳細資訊，請參閱 [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。
* 任何點擊追蹤量度會嘗試將本身新增至每個頁面，而不論設定此量度的 URL。雖然無害，但此狀況會導致這些訊息大量出現。

   為了獲得最佳結果，請下載並使用最新版本的 [!DNL at.js]。有關詳細資訊，請參見 [at.js版本詳細資訊](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank和 [下載地址：.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)。

## 什麼是域t.omtrdc.net [!DNL Target] 伺服器呼叫轉到？ {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] 是 Adobe 之 EDGE 網路的網域名稱，用來接收 Target 的所有伺服器呼叫。

## 為什麼at.js不始終使用HttpOnly和Secure cookie標誌？ {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly 只能透過伺服器端編碼來設定。[!DNL Target]Mbox 之類的 Cookie 是透過 JavaScript 編碼來建立與儲存，因此 無法使用 HttpOnly Cookie 旗標。[!DNL Target][!DNL Target] 在啟用跨域時，確實使用從伺服器端設定的第三方Cookie的HttpOnly。

Secure 只有在頁面是經由 HTTPS 來載入時，能透過 JavaScript 設定。如果頁面一開始是透過 HTTP 載入，JavaScript 無法設定此旗標。此外，如果使用「安全」標誌，則Cookie僅在HTTPS頁上可用。 對於通過HTTPS載入的頁面， [!DNL Target] 設定Secure和SameSite=None屬性。

確保 [!DNL Target] 可以正確跟蹤用戶，並且由於cookie是在客戶端生成的， [!DNL Target] 除上述情況外，不使用這些標誌。

## at.js 觸發網路要求的頻率為何? {#section_57C5235DF7694AF093A845D73EABADFD}

[!DNL Target] 會在伺服器端執行其所有決策。這表示 at.js 會在每次頁面重新載入或叫用 at.js 公用 API 時，觸發網路要求。

## 在最好的情況下，我們能否期望使用者在隱藏、取代，和顯示內容方面，不會受到任何頁面載入上的可見影響? {#section_CB3C566AD61F417FAC0EC5AC706723EB}

at.js嘗試在較長時間內避免預隱藏HTMLBODY或其他DOM元素，但這取決於網路條件和活動設定。 at.js提供 [設定](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}可用於自定義BODY隱藏CSS樣式，這樣，您就不能隱藏整個HTMLBODY，而只能預隱藏頁面的某些部分。 期望是那些部分包含了必須「個人化」的 DOM 元素。

## 在使用者符合活動資格的一般情況下，事件的序列為何? {#section_56E6F448E901403FB77DF02F44C44452}

由於 at.js 要求為非同步 `XMLHttpRequest`，因此我們會執行下列步驟:

1. 頁面載入。
1. at.js 預先隱藏 HTML BODY。有可以預先隱藏特定容器，而非 HTML BODY 的設定。
1. at.js 要求觸發。
1. 在 [!DNL Target] 收到響應， [!DNL Target] 提取CSS選擇器。
1. 使用CSS選擇器， [!DNL Target] 建立STYLE標籤以預隱藏要自定義的DOM元素。
1. 移除預先隱藏 STYLE 的 HTML BODY。
1. [!DNL Target] 開始進行 DOM 元素的輪詢。
1. 如果找到DOM元素， [!DNL Target] 應用DOM更改並刪除元素預隱藏的STYLE。
1. 如果找不到DOM元素，則全局超時將取消隱藏這些元素以避免出現損壞的頁面。

## 當at.js最終取消隱藏活動正在更改的元素時，頁面的內容被完全載入和可見的頻率是多少？ {#section_01AFF476EFD046298A2E17FE3ED85075}

考慮到上述情形，當at.js最終取消隱藏活動正在更改的元素時，頁面的內容已完全載入並可見的頻率是多少？ 換句話說，除了活動內容外，頁面會完全顯示，而活動內容則會在其餘內容顯示後稍微顯示。

at.js 不會讓頁面無法呈現。用戶可能會注意到頁面上的某些空白區域，這些區域表示由 [!DNL Target]。 若要套用的內容並未包含許多遠端資產 (例如 SCRIPT 或 IMG)，則所有內容皆應快速呈現。

## 完全快取的頁面會如何影響上述情況? 其餘頁面內容載入後，活動內容是否更有可能明顯可見? {#section_CE76335A3E0B41CB8253DEE5E060FCDA}

如果頁面快取在接近用戶位置但不接近於 [!DNL Target] 邊緣，該用戶可能會看到一些延遲。 [!DNL Target] 邊緣分佈得很廣，所以大多數時候這不是問題。

## 是否可以顯示主圖影像，然後在短暫的延遲後進行更換? {#section_C25B07B25B854AAE8DEE1623D0FA62A3}

考量到下列情況:

的 [!DNL Target] 超時為5秒。 使用者載入具有自訂主圖影像活動的頁面。at.js 傳送要求以確認是否有要套用的活動，但無初始回應。假設用戶看到英雄影像的常規內容，因為未收到來自 [!DNL Target] 是否存在關聯活動。 四秒後， [!DNL Target] 會返回帶活動內容的響應。

在此階段，是否可以顯示替代版本? 4 秒後，是否可以更換主圖影像且使用者會注意到此影像更換?

起初，主圖影像 DOM 元素會隱藏。在來自 [!DNL Target] 接收，at.js應用DOM更改，如替換IMG和顯示定製的英雄影像。

## at.js 需要什麼 HTML doctype?

at.js 需要 HTML 5 doctype。

此語法為:

`<!DOCTYPE html>`

HTML 5 doctype 可確保頁面以標準模式載入。使用怪異模式載入時，會停用 at.js 所根據的某些 JS API。[!DNL Target]在怪異模式下， 會停用 at.js。
