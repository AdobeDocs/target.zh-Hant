---
keywords: at.js 版本;at.js 版本;單一頁面應用程式;spa;跨網域;跨網域
description: 瞭解如何從Adobe升級 [!DNL Target] at.js 1.x到at.js 2.x。檢查系統流圖，瞭解新函式和已棄用函式等。
title: 如何從at.js 1.x版升級到2.x版？
feature: at.js
role: Developer
exl-id: f5ec6bf1-f38c-4681-a6c1-b862272ee55d
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '2874'
ht-degree: 88%

---

# 從 at.js 1.*x* 升級為 at.js 2.*x*

[!DNL Adobe Target] 中的最新版 at.js 提供豐富的功能，讓貴公司能以新世代用戶端技術為基礎進行個人化。本次的新版本著重於升級 at.js，進而與單一頁面應用程式 (SPA) 產生和諧互動。

以下是幾個使用 at.js 2.*x* 特有 (舊版未提供) 的優點:

* 可在頁面載入時快取所有選件，以減少對單一伺服器呼叫發出的多個伺服器呼叫。
* 大幅改善一般使用者在網站上的體驗，因為選件能透過快取立即顯示，避免傳統伺服器呼叫引發的延遲時間。
* 簡單的單行程式碼和一次性開發人員設定，讓行銷人員可透過 VEC 在 SPA 上建立和執行 A/B 和 (XT) 活動。

## at.js 2.*x* 系統圖表

下列圖表可協助您瞭解 at.js 2.*x* 搭配檢視的工作流程，以及如何藉由這套工作流程增強 SPA 整合。如需 at.js 2.*x* 中所使用概念的詳細介紹，請參閱[實作單頁應用程式](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/)。

![使用 at.js 2.*x*](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png) 的 Target 流程

| 呼叫 | 詳細資料 |
| --- | --- |
| 1 | 如果使用者已通過驗證，呼叫會傳回 [!DNL Experience Cloud ID]，而另一個呼叫會同步客戶 ID。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>也能使用將頁面上實作的程式碼片段預先隱藏的選項，以非同步方式載入 at.js。 |
| 3 | 提出頁面載入要求，包含所有已設定的參數 (MCID、SDID 和客戶 ID)。 |
| 4 | 個人資料指令碼執行，然後注入個人資料存放區。存放區會從受眾資料庫中請求合格受眾 (例如，從 Adobe Analytics、受眾管理等共用的受眾)。<br>客戶屬性會透過批次程序傳送至個人資料存放區。 |
| 5 | [!DNL Target] 會根據 URL 要求參數和個人資料，決定可針對目前頁面和未來檢視傳回哪些活動和體驗給訪客。 |
| 6 | 目標內容會傳回至頁面，選擇性地包括其他個人化的個人資料值。<br>目前頁面上目標內容會儘快出現，不會有忽隱忽現的預設內容。<br>針對在瀏覽器中快取的使用者 SPA 動作顯示檢視的目標內容，以便在透過 `triggerView()` 觸發檢視時立刻套用，不需額外的伺服器呼叫。 |
| 7 | Analytics 資料傳送至「資料收集」伺服器。 |
| 8 | 目標資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 Analytics for Target (A4T) 報表來檢視 <br>Analytics 資料。 |

現在，SPA 上只要是有實作 `triggerView()` 的位置，系統都會從快取擷取檢視和動作並向使用者顯示，不需要伺服器呼叫。`triggerView()` 也會對 [!DNL Target] 後端發出通知要求，以便增加和記錄曝光計數。

![Target 流程 at.js 2.*x* triggerView](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 呼叫 | 詳細資料 |
| --- | --- |
| 1 | 系統在 SPA 中呼叫 `triggerView()`，以便呈現檢視和套用動作來修改視覺元素。 |
| 2 | 從快取讀取檢視的目標內容。 |
| 3 | 目標內容會儘快出現，不會有忽隱忽現的預設內容。 |
| 4 | 通知要求會傳送至 [!DNL Target] 個人資料存放區，以計算活動中的訪客數和增加量度。 |
| 5 | Analytics 資料傳送至資料收集伺服器。 |
| 6 | Target 資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 A4T 報表來檢視 Analytics 資料。 |

## 部署 at.js 2.*x* {#deploy-atjs-200}

1. 部署 at.js 2.*x* 通過標籤 [[!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) 擴展。

   >[!NOTE]
   >
   > 使用中的標籤部署at.js [!DNL Adobe Experience Platform] 是首選方法。

   或

   使用 Target UI 手動下載 at.js 2.*x*，並使用[您所選擇的方法](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/how-to-deployatjs/)進行部署。

## 棄用的 at.js 函數

at.js 2.*x* 已棄用多個函數。

>[!IMPORTANT]
>
>如果部署 at.js 2.*x* 時您的網站上仍使用這些已棄用的函數，便會顯示主控台警告。建議的升級做法是在預備環境中測試 at.js 2.*x* 部署，並確實逐一瀏覽每個記錄到主控台中的警告，並將棄用的函數轉譯為 at.js 2.*x* 中推出的新函數。

已棄時的函數及其對應的新函數如下所列。如需完整的函數清單，請參閱 [at.js 函數](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-functions/)。

>[!NOTE]
>at.js 2 *x* 不再自動預先隱藏標示為 `mboxDefault` 的元素。因此客戶必須在網站上或透過標籤管理程式，手動提供預先隱藏邏輯。

### mboxCreate(mbox,params)

**說明**:

執行要求並將選件套用至具有 `mboxDefault` 類別名稱的最接近 DIV。

**範例**:

```
<div class="mboxDefault">
  default content to replace by offer
</div>
<script>
  mboxCreate('mboxName','param1=value1','param2=value2');
</script>
```

**at.js 2.*x* 等同項目**

`mboxCreate(mbox, params)` 的替代函數為 `getOffer()` 和 `applyOffer()`。

**範例**:

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  var el = document.currentScript.previousElementSibling;
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2"
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: el,
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      el.style.visibility = "visible";
    }
  });
</script> 
```

### mboxDefine() 和 mboxUpdate()

**說明**:

在元素與 mbox 名稱之間建立內部對應，但是不執行要求。與 `mboxUpdate()` 搭配使用，會執行要求並將選件套用至 `mboxDefine()` 中的 nodeId 所識別的元素。也可用來更新 `mboxCreate` 起始的 mbox。

**範例**:

```
<div id="someId" class="mboxDefault"></div>
<script>
 mboxDefine('someId','mboxName','param1=value1','param2=value2');
 mboxUpdate('mboxName','param3=value3','param4=value4');
</script>
```

**at.js 2 *x* 等同項目**:

`mboxDefine()` 和 `mboxUpdate` 的替代函數為 `getOffer()` 和 `applyOffer()`，而 `applyOffer()` 中會使用選取器選項。此做法可讓您使用任何 CSS 選取器將選件對應至元素，而非只能使用帶有 ID 的選取器。

**範例**:

```
<div id="someId" class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2",
      param3: "value3",
      param4: "value4" 
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: "#someId",
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      var el = document.getElementById("someId");
      el.style.visibility = "visible";
    }
  });
</script>
```

### adobe.target.registerExtension()

**說明**:

提供標準方式來註冊特定的延伸模組。

此函數不再受支援且不應使用。

## 2 中棄用、新增和支援的 at.js 函數摘要.*x*

| 方法 | 支援? | 新增? | 已過時? <br> (將顯示預設內容) |
| --- | --- | --- | --- |
| `getOffer()` | 是 |  |  |
| `getOffers()` |  | 是 |  |
| `applyOffer()` | 是 |  |  |
| `applyOffers()` |  | 是 |  |
| `triggerView()` |  | 是 |  |
| `trackEvent()` | 是 |  |  |
| `mboxCreate()` |  |  | 是 |
| `mboxDefine()`<br>`mboxUpdate()` |  |  | 是 |
| `targetGlobalSettings()` | 是 |  |  |
| `Data Providers` | 是 |  |  |
| `targetPageParams()` | 是 |  |  |
| `targetPageParamsAll()` | 是 |  |  |
| `registerExtension()` |  |  | 是 |
| `At.js Custom Events` | 是 |  |  |

## 限制和圖說

請留意下列限制和圖說:

### 轉換追蹤

客戶使用 `mboxCreate()` 追蹤轉換時必須使用 `trackEvent()` 或 `getOffer()`。

### 選件傳送

客戶若沒有將 `mboxCreate()` 取代為 `getOffer()` 或 `applyOffer()`，選件可能不會傳送。

### at.js 2.*x* 是否能在某些頁面上使用，並在其他頁面上使用 at.js 1.*x* 在其他頁面上嗎？

可以，使用不同版本和資料庫的頁面中會保留訪客設定檔。Cookie 格式相同。

### at.js 2.*x* 使用的新 API

at.js 2 *x* 使用新的 API，我們稱之為「傳送 API」。若要針對 at.js 是否正確呼叫 [!DNL Target] Edge 伺服器進行除錯，您可以將瀏覽器上「開發人員工具」的「網路」索引標籤篩選為「傳送」、「`tt.omtrdc.net`」或您的用戶端代碼。您也會發現 [!DNL Target] 傳送的是 JSON 裝載而非機碼值組。

### 不再使用 Target 全域 mbox

在 at.js 2.*x* 中，網路呼叫中不會再出現「`target-global-mbox`」。我們已改為將傳送至 [!DNL Target] 伺服器的 JSON 裝載中的「`target-global-mbox`」語法取代為「`execute > pageLoad`」，如下所示:

```
{
  "id": {
    // ...
  },
  "context": {
    "channel": "web",
    // ...
  },
  "execute": {
    "pageLoad": {}
  }
}
```

基本上，推出全域 mbox 概念的目的，是用來告知 [!DNL Target] 是否要在頁面載入時擷取選件和內容。因此我們在最新版本中讓這個用途更加明確。

### at.js 中的全域 mbox 名稱仍重要嗎?

客戶可以通過 [!UICONTROL 目標>管理>實施>編輯at.js設定]。 此設定供 [!DNL Target] Edge 伺服器用來將 execute > pageLoad 轉譯為 [!DNL Target] UI 中顯示的全域 mbox 名稱。這麼做可讓客戶繼續使用伺服器端 API、表單式撰寫器、設定檔指令碼，以及使用全域 mbox 名稱建立對象。我們強烈建議您確保在 [!UICONTROL 「管理」>「視覺體驗作曲家」] 頁面，以防您仍有使用at.js 1的頁面。*x*，如下圖所示。

![修改 at.js 對話方塊](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

和

![自訂全域 mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

### 需要為 at.js 2.*x* 開啟自動建立全域 mbox 設定嗎?

在大多數情況下需要。此設定可告知 at.js 2.*x* 在頁面載入時向 [!DNL Target] Edge 伺服器引發要求。由於全域 mbox 已轉譯為 execute > pageLoad，因此如果您想在頁面載入時觸發要求，便應開啟此設定。

### 即使沒有從 at.js 2.*x* 指定 Target 全域 mbox 名稱，現有的 VEC 活動仍會繼續運作嗎?

會，因為 execute > pageLoad 在 [!DNL Target] 後端上的處理方式如同 `target-global-mbox`。

### 如果我的表單式活動目標鎖定為 `target-global-mbox`，這些活動是否仍會繼續運作?

會，因為 execute > pageLoad 在 [!DNL Target] Edge 伺服器上的處理方式如同 `target-global-mbox`。

### 支援和不支援的 at.js 2.*x* 設定

| 設定 | 支援? |
| --- | --- |
| X-Domain | 無 |
| 自動建立全域 mbox | 是 |
| 全域 mbox 名稱 | 是 |

### at.js 2.x 中的跨網域追蹤支援 {#cross-domain}

跨網域追蹤能夠拼接不同網域之間的訪客。由於必須為各個網域建立新 Cookie，因此在訪客從某個網域導覽至另一個網域時，就很難加以追蹤。為實現跨網域追蹤，[!DNL Target] 使用協力廠商 Cookie 來追蹤網域之間的訪客。這可讓您建立橫跨 `siteA.com` 和 `siteB.com` 的 Target 活動，而且當訪客在各個唯一網域導覽時，訪客會維持相同的體驗。此功能與 Target 的第三方和第一方 Cookie 行為整合。

>[!NOTE]
>
>at.js 2.*x* 不提供跨網域追蹤的立即可用支援。at.js 2.*x* 可透過 Experience Cloud ID (ECID) 資料庫 v4.3.0+ 支援跨網域追蹤。

在 Target 中，協力廠商 Cookie 會儲存在 `<CLIENTCODE>.tt.omtrdc.net` 中。第一方 Cookie 會儲存在 `clientdomain.com` 中。第一個要求會傳回 HTTP 回應標頭，此標頭嘗試設定名為 `mboxSession` 和 `mboxPC` 的第三方 Cookie，之後傳回附有額外參數 (`mboxXDomainCheck=true`) 的重新導向要求。若瀏覽器接受協力廠商 Cookie，則重新導向請求會包含這些 Cookie 並傳回體驗。這個工作流程之所以可行，是因為我們使用 HTTP GET 方法。

不過，at.js 2.*x* 已不再使用 HTTP GET，而是改用 HTTP POST。您現在可透過 at.js 2.*x* 使用 HTTP POST，將 JSON 裝載傳送至 Target Edge 伺服器。這表示檢查瀏覽器是否支援第三方 Cookie 的重新導向要求現在已失效。這是因為 HTTP GET 要求為等冪交易，而 HTTP POST 是非等冪交易且不得任意重複。因此，at.js 2.*x* 中的跨網域追蹤不再提供立即可用支援。只有 at.js 1.*x* 才提供跨網域追蹤的立即可用支援。

如果要使用跨域跟蹤，必須安裝 [ECID庫v4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html??lang=zh-Hant) 與at.js 2結合。*x* 使用供跨網域追蹤功能時。 ECID 資料庫的存在是為了管理可用來識別訪客 (甚至是跨網域) 的持續 ID。

>[!NOTE]
>
>安裝 ECID 資料庫 v4.3.0+ 和 at.js 2.*x* 後，您將能建立橫跨多個唯一網域的活動以及追蹤使用者的活動。請記得，此功能僅適用於工作階段過期之後。

### 支援自動建立全域 mbox

此設定可告知 at.js 2.*x* 在頁面載入時向 [!DNL Target] Edge 伺服器引發要求。由於全域 mbox 已轉譯為 execute > pageLoad，且會由 [!DNL Target] Edge 伺服器加以解譯，因此顧客如果希望在頁面載入時觸發要求，便應開啟此功能。

### 支援全域 mbox 名稱

客戶可以通過 [!UICONTROL 目標>管理>實施>編輯]。 此設定供 [!DNL Target] Edge 伺服器用來將 execute > pageLoad 轉譯為輸入的全域 mbox 名稱。這麼做可讓客戶繼續使用伺服器端 API、表單式撰寫器、設定檔指令碼，以及建立鎖定全域 mbox 為目標的對象。

### 以下 at.js 自訂事件適用於 `triggerView()`，還是僅適用於 `applyOffer()` 或 `applyOffers()`?

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

是的，at.js 自訂事件也適用於 `triggerView()`。

### 上面說我打電話 `triggerView()` 帶有&amp;lbrase`“page” : “true”`&amp;rbrace;，它將向 [!DNL Target] 後端，增加印象。 那麼也會造成設定檔指令碼執行嗎?

對 [!DNL Target] 後端發出預先擷取呼叫時，會執行設定檔指令碼，接著會加密受影響的設定檔資料，然後傳回用戶端。叫用含有 `{"page": "true"}` 的 `triggerView()` 後，會傳送通知並附上加密的設定檔資料。此時 [!DNL Target] 後端會將設定檔資料解密並儲存至資料庫中。

### 呼叫 `triggerView()` 之前需要新增預先隱藏程式碼以處理忽隱忽現情況嗎?

不需要，您不需要在呼叫 `triggerView()` 之前新增預先隱藏程式碼。at.js 2 *x* 會在顯示和套用檢視之前，處理預先隱藏和忽隱忽現的邏輯。

### 這是第1條。*x* at.js 2中不支援建立訪問群體的參數。*x*? {#audience-parameters}

以下at.js 1.x參數是 *不* 當前支援在使用at.js 2時建立受眾。*x* 中的頁面載入要求:

* browserHeight
* browserWidth
* browserTimeOffset
* screenHeight
* screenWidth
* screenOrientation
* colorDepth
* devicePixelRatio
* vst。*參數([下面](#vst))

### at.js 2 *x* 不支援使用 vst.* 參數 {#vst}

客戶在at.js 1。*x* 能用vst*mbox參數以建立受眾。 這是at.js 1的意外副作用。*x* 發送的mbox參數 [!DNL Target] 後端。 遷移到at.js 2後。*x*，因為at.js 2，所以無法再使用這些參數建立訪問群體。*x* 以不同方式發送mbox參數。

## at.js 相容性

下表說明 at.js。2.*x* 與不同活動類型、整合、功能和at.js函式的相容性。

### 活動類型 {#types}

| 類型 | 支援? |
| --- | --- |
| A/B 測試 | 是 |
| 自動分配 | 是 |
| 自動鎖定目標 | 是 |
| 體驗鎖定目標 | 是 |
| 多變數測試 | 是 |
| 自動個人化 | 是 |
| 建議 | 是 |

>[!NOTE]
>
>所有修改皆已套用至 `Page Load Event` 時，可透過 at.js 2.*x* 和 VEC 支援自動鎖定目標活動。修改已新增至特定視圖時，僅支援 A/B 測試、自動分配和體驗鎖定目標 (XT) 活動。

### 整合 {#integrations}

| 類型 | 支援? |
| --- | --- |
| 目標分析 (A4T) | 是 |
| 對象 | 是 |
| 客戶屬性 | 是 |
| AEM 體驗片段 | 是 |
| [!DNL Adobe Experience Platform] 擴展 | [是](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) |
| 除錯程式 | 是 |
| Auditor | 尚未針對 at.js 2.*x* 更新規則 |
| 選擇加入 | 無。[at.js 版本 2.1.0](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) 支援 [GDPR 的選擇加入支援](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/)。 |
| 採用 Adobe Target 技術的 AEM 增強型個人化 | 無 |

### 功能

| 功能 | 支援? |
| --- | --- |
| X域 | 無 |
| 屬性/工作區 | 是 |
| QA 連結 | 是 |
| 表單式體驗撰寫器 | 是 |
| 可視化體驗撰寫器 (VEC) | 是 |
| 自訂程式碼 | 是 |
| 回應 Token | [是](#response-tokens) |
| 點擊追蹤 | 是 |
| 多活動傳送 | 是 |
| targetGlobalSettings | 支援 (但不支援跨網域) |
| at.js 方法 | 除了下列會顯示預設內容的方法以外均支援: <br>`mboxCreate()`<br>`mboxUpdate()`<br>`mboxDefine()`<br>。 |

### 查詢字串參數

| 參數 | 支援? |
| --- | --- |
| `?mboxDisable` | 是 |
| `?mboxDisable` | 是 |
| `?mboxTrace` | 是 |
| `?mboxSession` | 無 |
| `?mboxOverride.browserIp` | 是 |

## 回應 Token {#response-tokens}

at.js 2 *x*，就像 at.js 1.*x*，使用自訂事件 `at-request-succeeded` 來呈現回應 Token。如需使用 `at-request-succeeded` 自訂事件的程式碼範例，請參閱[回應 Token](/help/main/administrating-target/response-tokens.md)。

## at.js 1.*x* 參數到at.js 2。*x* 的裝載對應 {#payload-mapping}

本節概述 at.js 1.*x* 與 at.js 2.*x* 之間的對應。

探索參數對應之前，請注意這些資料庫版本使用的端點已變更:

* at.js 1 *x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at.js 2 *x* - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

另一項顯著差異為:

* at.js 1 *x* - 用戶端代碼是路徑的一部分
* at.js 2 *x* - 用戶端代碼會以查詢字串參數的形式傳送，例如:
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

以下各節列出每個 at.js 1.*x* 參數、其描述以及相應的2。*x* JSON負載（如果適用）:

### at_property

(at.js 1.*x* 參數)

用於[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### mboxHost

(at.js 1)*x* 參數)

Target 資料庫執行所在位置的頁面網域。

at.js 2 *x* JSON 裝載:

```
{
  "context": {
    "browser": {
       "host": "test.com"
    }
  }
}
```

### webGLRenderer

(at.js 1)*x* 參數)

瀏覽器的 WEB GL 轉譯器功能我們的裝置偵測機制會使用此功能，判斷訪客的裝置是否為桌上型電腦、iPhone、Android 裝置等。

at.js 2 *x* JSON 裝載:

```
{
  "context": {
    "browser": {
       "webGLRenderer": "AMD Radeon Pro 560X OpenGL Engine"
    }
  }
}
```

### mboxURL

(at.js 1)*x* 參數)

頁面 URL。

at.js 2 *x* JSON 裝載:

```
{
  "context": {
    "address": {
       "url": "http://test.com"
    }
  }
}
```

### mboxReferrer

(at.js 1)*x* 參數)

頁面轉介者。

at.js 2 *x* JSON 裝載:

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox (名稱) 等於全域 mbox

(at.js 1)*x* 參數)

傳遞 API 已無全域 mbox 概念。在 JSON 裝載中，您必須使用 `execute > pageLoad`。

at.js 2 *x* JSON 裝載:

```
{
  "execute": {
    "pageLoad": {
       "parameters": ....
       "profileParameters": ...
       .....
    }
  }
}
```

### mbox (名稱) *不*&#x200B;等於全域 mbox

(at.js 1)*x* 參數)

若要使用 mbox 名稱，請將其傳遞至 `execute > mboxes`。mbox 需要索引和名稱。

at.js 2 *x* JSON 裝載:

```
{
  "execute": {
    "mboxes": [{
       "index": 0,
       "name": "some-mbox",
       "parameters": ....
       "profileParameters": ...
       .....
    }]
  }
}
```

### mboxId

(at.js 1)*x* 參數)

已不再使用。

### mboxCount

(at.js 1)*x* 參數)

已不再使用。

### mboxRid

(at.js 1)*x* 參數)

下游系統用來協助進行偵錯的要求 ID。

at.js 2 *x* JSON 裝載:

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

(at.js 1)*x* 參數)

已不再使用。

### mboxSession

(at.js 1)*x* 參數)

工作階段 ID 會以查詢字串參數 (`sessionId`) 的形式傳送至傳送 API 端點。

### mboxPC

(at.js 1)*x* 參數)

TNT ID 會傳遞至 `id > tntId`。

at.js 2 *x* JSON 裝載:

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1)*x* 參數)

Marketing Cloud 訪客 ID 會傳遞至 `id > marketingCloudVisitorId`。

at.js 2 *x* JSON 裝載:

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### `vst.aaaa.id`和`vst.aaaa.authState`

(at.js 1)*x* 參數)

客戶 ID 應傳遞至 `id > customerIds`。

at.js 2 *x* JSON 裝載:

```
{
  "id": {
    "customerIds": [{
       "id": "1232131",
       "integrationCode": "aaaa",
       "authenticatedState": "....."
     }]
  }
  ....
}
```

### mbox3rdPartyId

(at.js 1)*x* 參數)

用來連結不同 Target ID 的客戶協力廠商 ID。

at.js 2 *x* JSON 裝載:

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

(at.js 1)*x* 參數)

SDID (也稱為補充資料 ID)。應傳遞至 `experienceCloud > analytics > supplementalDataId`。

at.js 2 *x* JSON 裝載:

```
{
  "experienceCloud": {
    "analytics": {
      "supplementalDataId": "1212321132123131"
    }
  }
  ....
}
```

### vst.trk

(at.js 1)*x* 參數)

Analytics 追蹤伺服器。應傳遞至 `experienceCloud > analytics > trackingServer`。

at.js 2 *x* JSON 裝載:

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServer": "analytics.test.com"
    }
  }
  ....
}
```

### vst.trks

(at.js 1)*x* 參數)

Analytics 追蹤伺服器安全。應傳遞至 `experienceCloud > analytics > trackingServerSecure`。

at.js 2 *x* JSON 裝載:

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServerSecure": "secure-analytics.test.com"
    }
  }
  ....
}
```

### mboxMCGLH

(at.js 1)*x* 參數)

Audience Manager 位置提示。應傳遞至 `experienceCloud > audienceManager > locationHint`。

at.js 2 *x* JSON 裝載:

```
{
  "experienceCloud": {
    "audienceManager": {
      "locationHint": 9
    }
  }
  ....
}
```

### mboxAAMB

(at.js 1)*x* 參數)

Audience Manager Blob。應傳遞至 `experienceCloud > audienceManager > blob`。

at.js 2 *x* JSON 裝載:

```
{
  "experienceCloud": {
    "audienceManager": {
      "blob": "2142342343242342"
    }
  }
  ....
}
```

### mboxVersion

(at.js 1)*x* 參數)

版本會透過版本參數以查詢字串參數的形式傳送。

## 培訓視頻：at.js 2 *x* 架構圖 ![概述徽章](/help/main/assets/overview.png)

at.js 2 *x* 增強了 Adobe Target 對 SPA 的支援，並與其他 Experience Cloud 解決方案整合。本影片說明整合方式。

>[!VIDEO](https://video.tv.adobe.com/v/26250)

請參閱 [瞭解at.js 2。*x* 作品](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) 的子菜單。
