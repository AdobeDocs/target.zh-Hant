---
keywords: mbox.js changes;mbox.js versions
description: 本頁面顯示每個 mbox.js 版本的變更。
title: mbox.js 版本詳細資料
feature: null
subtopic: Getting Started
uuid: 5f8e0511-637b-4c17-bb19-aa7f4d7c98ea
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '2320'
ht-degree: 98%

---


# mbox.js 版本詳細資料{#mbox-js-version-details}

本頁面顯示每個 mbox.js 版本的變更。

>[!NOTE]
>
>建議所有的 mbox.js 使用者升級至 57 版或更新版本。當 `target.js` 無法載入時，部分使用者遇到逾時問題。版本 57 已修正該問題。不過，如果您使用 [!DNL Experience Cloud Visitor ID] 服務，則需要 58 版或更新版本。

Target 回應來自您頁面呼叫的方法，取決於您所使用的 Target 資料庫、是否實作訪客 ID，以及是否有訪客 ID。如需詳細資訊，請參閱[各資料庫版本的 Target 呼叫回應](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/call-responses-library-version.md#concept_A95A4758A1E7405D947E9B4BCB5D62F0)。

>[!NOTE]
>
>將不再開發 mbox.js 資料庫。所有客戶應該從 mbox.js 移轉至 at.js。如需詳細資訊，請參閱[從 mbox.js 移轉至 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

## mbox.js 版本 63 {#section_ED8EFCF653A845ED8927F759578C4A33}

**Target 版本:** 17.7.1

[!DNL mbox.js] 63 版現在已可用。如需詳細資訊，請參閱[下載 mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/target-download-config-mbox.md)。

[!DNL mbox.js] 版本 63 中包括下列增強功能和修正:

* 修正使用 `mboxDefine()` 和 `mboxUpdate()` 產生 SDID 時的問題。這只會影響頁面上有訪客 API 的用戶端。

## mbox.js 版本 62 {#section_723A9119FE204183847D3B0929A99B41}

* 修正在 Google Chrome 瀏覽器中檢視時，重新導向活動中的閃爍問題。
* 已新增 `secureOnly` 設定，指出 mbox.js 是否應該僅使用 HTTPS 或根據頁面通訊協定，允許在 HTTP 與 HTTPS 之間切換。這是進階的設定，預設值為 False。

## mbox.js 61 版 {#section_F3B59C5578B64883AE013B9342151193}

**Target 版本:** 16.7.2

**發行日期:** 2016 年 7 月 28 日

mbox.js 版本 61 包含下列增強功能:

* JavaScript 日期 API 中的 mboxSession ID 產生演算法，現在會產生隨機字串，而非使用時間戳記加上隨機字串。
* 下列詳細資料只有在您的頁面上有訪客 API 時才適用:

   * [!DNL mbox.js]版本 61 不會覆寫訪客 API `loadTimeout` 屬性。用戶端可以使用 `visitorApiPageDisplayTimeout` + `visitorApiTimeout` 來控制訪客 API 整合。
   * 已新增 `optoutEnabled` 設定以支援未來的 Adobe Experience Cloud 選擇退出功能。預設值為 false。如果此屬性已啟用，所有要求會非同步對 [!DNL /ajax] 端點執行，就如同 60 版。
   * 主體隱藏已預設停用。只有在全域 mbox 自動建立已啟用和主體隱藏已啟用時，Target 才會使用主體隱藏。
   * 如果沒有 Experience Cloud 訪客 ID Cookie，所有要求會對第一個頁面載入上的 [!DNL /ajax] 非同步執行。在第二個頁面載入上，Target 會使用一般的流程，因為已出現訪客 ID 值。
   * 如果您使用 Adobe Analytics 做為活動的報表來源，若您使用的是 mbox.js 61 版 (或更新版本) 或 at.js 0.9.1 版 (或更新版本)，則不需在活動建立期間指定追蹤伺服器。mbox.js 或 at.js 資料庫會自動傳送追蹤伺服器值至 [!DNL Target]。在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。

## mbox.js 版本 60 {#section_3BDAB885FA13444A8D35940A4BFF5825}

**Target 版本:** 16.4.1

**發行日期:** 2016 年 4 月 21 日

預設不會隱藏頁面內容。只有在啟用「自動建立全域 mbox」選項時，60 版才會隱藏頁面內容。此版本使用 CSS `opacity:0` 屬性來隱藏頁面，而非使用 `display:none`。這可確保正確傳送回應式網站並符合 [!DNL at.js]。

您可以使用兩個設定來啟用主體隱藏:

* `bodyHidingEnabled`預設值為 false，表示 HTML BODY 未隱藏。

* bodyHiddenStyle

   預設值為 `body{opacity:0}`。此值可以變更為其他不同值，例如 `body{display:none}`。

這些設定可以透過包括一些項目來覆寫，例如:

```
<script> 
window.targetGlobalSettings = { 
 bodyHidingEnabled: true, 
 bodyHiddenStyle: "body{opacity:0}", 
 visitorApiPageDisplayTimeout: 2000 
}; 
</script>
```

頁面隱藏技術使用樣式標記來新增和移除樣式。這可確保在頁面隱藏程式碼執行之後，網站的樣式保持不變。

**DTM 使用者:** 請注意，這會防止您使用自動匯入選項，因為沒有其他方式可在 Target UI 中儲存上述組態。您將必須使用上述指示，然後將內容貼上至「自訂」主機選項中的程式碼方塊中。

另外在 60 版中，如果存在 Experience Cloud 訪客 ID 服務的 [!DNL visitorAPI.js] 檔案，則會透過 AJAX 端點請求所有 mbox。這是必要的，因為訪客 API 方法是非同步的。此方法有個好處，就是可大幅降低「開始轉譯」時間，因為 mbox 請求不會封鎖轉譯。不過，這也代表所有 [!DNL Target] 選件內容都以非同步方式執行，因此也必須據以編寫所有選件程式碼。包含 `document.write` 及其他程式碼，且假設其在初始頁面載入上執行的選件，將無法如預期般執行。

* V60 非同步呼叫

   使用 v60 搭配訪客 ID 服務時，所有 mbox 呼叫都會非同步進行。這是 mbox 一直以來運作方式的變更，因此，如果升級至此版本請注意。檢閱[文件的](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#section_B586360A3DD34E2995AE25A18E3FB953)非同步考量事項 [!DNL at.js] 小節 ([!DNL at.js] 也使用非同步呼叫) 來瞭解部分風險。
* 新訪客案例可能會閃爍

   使用 v58 到 v60 搭配訪客 ID 服務時，mbox 呼叫將等候訪客 ID 設定 (或等候發生逾時) 才觸發。這會發生在新訪客的第一個頁面載入上。

## mbox.js 版本 59 {#section_FF0E70C4C17E402D8374DE428C5D996E}

**Target 版本:** 16.2.1

**發行日期:** 2016 年 2 月 17 日

mbox.js 59 版包含下列增強功能:

* 停用的 Mbox 已降低至 30 分鐘
* 與頁面隱藏/取消隱藏相關的問題已修正

   此版本並非如 58 版使用 `display:none` 來隱藏頁面，而是使用 `opacity:0`。如此可解決回應式設計網站中，由先前用來隱藏頁面之方法所產生的問題。

## mbox.js 版本 58 {#section_5070B0D1C87F4937BB97727923DD36C7}

**Target 版本:** 15.7.1

**發行日期:** 2015 年 7 月 30 日

如果您使用 Analytics 做為 Target 的報表來源，則需要此 mbox.js 版本，另外針對「個人資料和對象」也強烈建議使用此 mbox.js 版本。

mbox.js 58 版可以確保在進行 Target 呼叫前，Experience Cloud 訪客 ID 服務會傳回訪客 ID。這可確保透過「個人資料和對象」核心服務共用的對象資料，可用於訪客作業的第一次 Target 呼叫。為了避免傳回測試內容前的預設內容發生忽隱忽現的情形，Target 會隱藏 `<BODY>` 直到訪客 ID 服務返回為止。`display:none` 用於隱藏頁面。

此項更新同時修正了使用 Analytics 做為 Target 的報表來源時，造成 Analytics 中針對僅包含一個頁面的造訪，所報告的訪客數誇大的問題。

Mbox.js 會設定逾時值，以免訪客 ID 服務未傳回。訪客 ID 服務的逾時值是 500 毫秒 (0.5 秒)。另一個逾時則設定 `<BODY>` 標籤的隱藏時間上限。該預設值是 500 毫秒 (0.5 秒)。您可在每個頁面的 mbox.js 參考之前插入下列程式碼，藉以變更這些逾時值:

```
<script> 
window.targetGlobalSettings = { 
 visitorApiTimeout: 500, 
 visitorApiPageDisplayTimeout: 500 
}; 
</script> 
```

Mbox.js 版本 58 和更新版本會在出現 HTML `BODY` 標記之後，立即對全域 mbox 執行非 JavaScript 內容。針對全域 mbox 的 `<script>` 標籤內的 JavaScript 內容會在觸發 `DOMContentLoaded` 事件之後執行。這個內容傳遞順序可確保全域 mbox 的 JavaScript 內容受到傳遞並正確呈現。

## mbox.js 版本 57 {#section_6BA1CDBF75B14A94B59E8624ACF583D4}

**Target 版本:** 15.4.1

**發行日期:** 2015 年 4 月 21 日

此版本中進行了下列變更:

* 為 Target Standard 自動建立的全域 mbox 回應不再使用 document.write() 或建立`<div>`元素。

   This removes the requirement for the mbox.js file to be the last item in the `<head>` of the page. 升級至此新版本時，建議進行強式 QA。

   此項變更可能造成傳送某些選件類型時的行為變更。以下是需要考慮的特定條件:

   * 以「外掛程式選件」之一部分傳回的 HTML 內容不會正確轉譯，但該選件中的 JavaScript 可如預期般執行。
   * 傳回至全域 mbox 的 JavaScript 選件可在 `<script>` 標籤中內嵌 JavaScript 程式碼，或透過 `src` 屬性引用。

      若要這麼做，請新增 `async` 屬性至指令碼呼叫，如下所示:

      `<script src='external-url' async='true'></script>`

      請注意 `async` 屬性在 Internet Explorer 中的支援有限 (詳細情形請參閱: [https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility](https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility))，因此您應從包含這些第三方指令碼的測試中排除使用舊版 IE 的訪客。

* 修正 56 版中由於 mbox.js 的額外 JavaScript 區段變更而呈報的問題。額外 JavaScript 區段中的所有程式碼再度適用於全域範圍。

mbox.js 57 版不支援下列功能:

* 在 Target Standard 中產生的自動建立之全域 mbox，無法搭配來自 Target Classic 的托管選件類型運作。托管選件類型包括「您網站上的選件」以及「Test&amp;Target 外部選件」。

   這表示在 Target Classic 中，如果您需要這些選件之一時，絕對不能選取來自 Target Standard 的自動建立之全域 mbox。
* 僅支援 JavaScript 外掛程式。

   如果外掛程式的選件結合了 JavaScript 程式碼和 HTML，則 JavaScript 程式碼仍可執行，但 HTML 內容不會顯示。

mbox.js 57 版也包含重要修正:

* 修正 SiteCatalyst 外掛程式在 mbox.js 56 版中無法運作的問題。
* 修正由於範圍變更而導致的額外 JavaScript 錯誤。
* 回復變更為 mboxFactory 的建構函式。

## mbox.js 版本 56 {#section_C4F4A53584B741FF9FD907D81CB7E164}

**Target 版本:** 15.1.2

**發行日期:** 2015 年 2 月 17 日

>[!NOTE]
>
>當 `target.js` 無法載入時，部分使用者遇到逾時問題。版本 57 已修正該問題。不過，如果您使用 [!DNL Experience Cloud Visitor ID] 服務，則需要 58 版或更新版本。

此版本中進行了下列變更:

* 對 Premium Recommendations 進行了變更，以支援在全域 mbox 中傳遞參數
* 新增 5 秒逾時至 target.js 載入呼叫。在極少數情況下，檔案不會載入，頁面仍會轉譯但不顯示任何 Target Standard 活動。
* 移動「額外 JavaScript」為在全域 mbox 前執行

   v56+ 中的所有設定都使用命名空間。如果在「額外 JavaScript」中有宣告函數，前面都必須加上 `window`。

   例如:

   `function foo {`

   `}`

   改為:

   `window.foo = function() {`

   `}`

   應全域存取的任何變數也都必須在前面加上 `window`。

* 新增名為「em-disabled」的 Cookie，如果在傳送期間無法載入 target.js，便由 mbox.js 提供此 Cookie 給使用者。此 Cookie 可避免使用 Visual Experience Composer 建立的選件在網站上轉譯。具有此 Cookie 的使用者看不到測試內容，也不會計算在那些活動報表中。所有其他選件內容 (例如來自 Target Classic 的促銷活動) 仍會繼續載入。Cookie 從載入失敗起的存留期為 30 分鐘。

## mbox 55 版

**Target 版本:** 15.1

**發行日期:** 2015 年 1 月 19 日

修改 53 版，加入 IE 修正。

## mbox 54 版

**Target 版本:** 14.9.2

**發行日期:** 2014 年 9 月 30 日

將全域 mbox 實作從 document.write 變更為 AJAX。如此，mbox.js 檔案就不需要是頁面之`<head>`小節。此版本僅可透過 API 取得。用戶端可下載並使用此 mbox.js 檔案。有些網站使用此實作時會發生內容忽隱忽現的問題，因此請在網站上驗證整合。

## mbox 53 版

**Target 版本:** 14.9.1

**發行日期:** 2014 年 9 月 14 日

修正 Target 頁面參數在 Internet Explorer 中無法正確引發的問題。

## mbox 52 版

**Target 版本:** 14.8

**發行日期:** 2014 年 8 月 14 日

mboxParameter 函數現在可用於 Target Standard 和 Premium。

修正 Analytics 追蹤在 IE 9 和 11 中無法運作的問題。此項變更僅影響 Analytics 的使用者。

現在您可以使用 targetPageParams() 函數，以陣列、JSON 物件或逗號分隔清單 (舊版支援) 的形式[傳遞參數](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md)至 target-global-mbox。

重新命名 M2PcId 以及與 VisitorId 相關的所有項目。

允許清除已註冊 mbox 的 defaultDiv。

## mbox 51 版

**Target 版本:** 14.6

**發行日期:** 2014 年 6 月 25 日

修正在頂層網域為兩個字元的網站中，設定錯誤 Cookie 的問題。

修正 mbox.js 中傳回雜湊值的小錯誤。

## mbox 50 版

改進 Target Standard 和 Target Classic 間的同步處理。

## mbox 49 版

改進 Internet Explorer 10 的巢狀 mbox 支援。

## mbox 48 版

新增支援 Adobe Analytics 做為 Adobe Target 的報表來源。

## mbox 47 版

mbox.js 現在支援在 Target Standard 中使用自訂的全域 mbox 名稱。

## mbox 46 版

新增 Target Standard 單行程式碼實作的 Experience Cloud 訪客 ID 服務完整支援。如此可啟用伺服器端的 Adobe Analytics 整合以及 Experience Cloud 共用描述檔。

修正在 IE10 文件模式中傳送內容的問題。

## mbox 45 版

新增 Experience Cloud 訪客 ID 服務的完整支援。如此可啟用伺服器端的 Adobe Analytics 整合以及 Experience Cloud 共用描述檔。

## mbox 44 版

由 mboxVizTarget 新增 URL 的參數:

mboxDOMLoaded

## mbox 43 版

新增 Target Standard 支援。

## mbox 42 版

新增 Experience Cloud 共用訪客 ID 服務的初始支援。

## mbox 41 版

* 透過僅 x 設定，停用第一方 Cookie 以改進載入時間並防止連續頁面重新整理

   如果對 Target 的呼叫無法及時傳回，會設定逾時 Cookie。比起僅使用第三方 Cookie，這個方法比較快。僅使用第三方 Cookie 時，在等候 Target 伺服器的良好回應時，頁面會不斷重新整理。

* 修正流量限制，僅在啟用 mbox.js 時發生

   如果客戶的 mbox.js 有流量限制就會發生這個問題，導致逾時設定無法作用。這會導致在等候 Target 伺服器的良好回應時，頁面不斷重新整理。

* 修正 SiteCalyst 外掛程式為一律使用 Ajax fetcher

   在此項變更前，在某些情況下，依賴外掛程式載入時間的 Test&amp;Target 對 SiteCatalyst 外掛程式可能觸發會抹除頁面的 document.write。

## mbox 38 版

新增頁面型 SiteCatalyst 與 Test&amp;Target 整合的支援 (必須啟用)

## mbox 37 版

編碼 URL 索引鍵

## mbox 36 版

變更 mbox 為使用 tt.omtrdc.net

## mbox 35 版

* Mbox 除錯現在一律為遠端
* 新增 mboxTime 參數。此參數是自紀元以來使用者看到它的 GMT 時間，以毫秒為單位。這只會計算一次。

## mbox 34 版

* 一律嘗試取得最新的預設 div，而非參考快取版本。

   這修正了快取預設內容 div 由於 mboxUpdate (這提供預設 div 的內容) 而不在 DOM 中的問題。

* mbox.getDefaultDiv 有新的選用布林參數。若為 true，則傳回目前的預設 div。若為 false，則傳回最後快取的預設 div。
* 更新 mbox.loaded 為支援 Ajax 載入
* mboxURL 參數現在使用 encodeURIComponent 編碼，而非 escape
* 測試瀏覽器是否支援 encodeURIComponent，若不支援則顯示預設內容。也移除了下列 mbox.js 組態選項:
   * encode\_mbox\_parameters
   * mbox\_signal\_support
