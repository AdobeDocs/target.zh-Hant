---
description: 從at. js1.x升級至at. js2.x
keywords: at.js 版本;單頁應用程式;spa
seo-description: 有關如何從 at.js 1.x 升級至 at.js 2.0.0 版的詳細資訊
seo-title: '從 Adobe Target at.js 1.x 版升級至 at.js 2.0.0 版 '
solution: Target
subtopic: 快速入門
title: 從at. js1.x升級至at. js2.x
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 從at. js1.x升級至at. js2.x {#upgrading-from-atjs-1x-to-atjs-200}

最新版at. js [!DNL Adobe Target] 提供豐富的功能集，讓您的企業對新一代的客戶端技術執行個人化。本次的新版本著重於升級 at.js，進而與單一頁面應用程式 (SPA) 產生和諧互動。

以下是使用at. js2.x在舊版中無法使用的優點：

* 可在頁面載入時快取所有選件，以減少對單一伺服器呼叫發出的多個伺服器呼叫。
* 大幅改善一般使用者在網站上的體驗，因為選件能透過快取立即顯示，避免傳統伺服器呼叫引發的延遲時間。
* 簡單的單行程式碼和一次性開發人員設定，讓行銷人員可透過 VEC 在 SPA 上建立和執行 A/B 和 (XT) 活動。

## at. js2.x系統圖表

下列圖表可協助您瞭解at. js2.x含檢視的工作流程，以及如何增強SPA整合。若要更好地介紹在. js2.x中使用的概念，請參閱 [「單頁應用程式實施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」。

![使用at. js2.x的定位流程](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 呼叫 | 詳細資料 |
| --- | --- |
| 1 | 如果使用者已通過驗證，呼叫會傳回 [!DNL Experience Cloud ID]，而另一個呼叫會同步客戶 ID。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>也能使用將頁面上實作的程式碼片段預先隱藏的選項，以非同步方式載入 at.js。 |
| 3 | 提出頁面載入要求，包含所有已設定的參數 (MCID、SDID 和客戶 ID)。 |
| 4 | 設定檔指令碼執行，然後注入設定檔存放區。存放區會從對象資料庫中請求合格對象 (例如，從 Adobe Analytics、對象管理 等共用的對象)。<br>客戶屬性會透過批次程序傳送至設定檔存放區。 |
| 5 | [!DNL Target] 會根據 URL 要求參數和設定檔資料，決定可針對目前頁面和未來檢視傳回哪些活動和體驗給訪客。 |
| 6 | 目標內容會傳回至頁面，選擇性地包括其他個人化的設定檔值。<br>目前頁面上目標內容會儘快出現，不會有忽隱忽現的預設內容。<br>針對在瀏覽器中快取的使用者 SPA 動作顯示檢視的目標內容，以便在透過 `triggerView()` 觸發檢視時立刻套用，不需額外的伺服器呼叫。 |
| 7 | Analytics 資料傳送至「資料收集」伺服器。 |
| 8 | 目標資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 Analytics for Target (A4T) 報表來檢視 <br>Analytics 資料。 |

現在，SPA 上只要是有實作 `triggerView()` 的位置，系統都會從快取擷取檢視和動作並向使用者顯示，不需要伺服器呼叫。`triggerView()` 也會對 [!DNL Target] 後端發出通知要求，以便增加和記錄曝光計數。

![. js2.x觸發器檢視的目標流程](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 呼叫 | 詳細資料 |
| --- | --- |
| 1 | 系統在 SPA 中呼叫 `triggerView()`，以便呈現檢視和套用動作來修改視覺元素。 |
| 2 | 從快取讀取檢視的目標內容。 |
| 3 | 目標內容會儘快出現，不會有忽隱忽現的預設內容。 |
| 4 | 通知要求會傳送至 [!DNL Target] 設定檔存放區，以計算活動中的訪客數和增加量度。 |
| 5 | Analytics 資料傳送至資料收集伺服器。 |
| 6 | Target 資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 A4T 報表來檢視 Analytics 資料。 |

## 部署at. js2.x {#deploy-atjs-200}

1. 使用Target UI下載. js2.x。

   ![實作詳細資料對話方塊](/help/c-experiences/assets/imp-200.png)

   >[!NOTE]
   >
   >目前尚未支援透過 [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 擴充功能安裝at. js2.x。

## 棄用的 at.js 函數

在at. js2.x中已停用一些函數。

>[!IMPORTANT]
>
>如果在部署. js2.x時，您的網站仍使用這些已不再提倡的函數，則會看到主控台警告。升級時建議使用的方法是在測試環境中測試. js2.x部署，並確實執行每個已登入主控台中的警告，並將停用的函數翻譯為at at. js2.x中引進的新函數。

已棄時的函數及其對應的新函數如下所列。如需完整的函數清單，請參閱 [at.js 函數](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。

>[!NOTE]
>at. js2.x不再自動隱藏 `mboxDefault` 標記的元素。因此客戶必須在網站上或透過標籤管理程式，手動提供預先隱藏邏輯。

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

**at. js2.x等值**

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

**at. js2.x相等**：

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

## 2.0 中棄用、新增和支援的 at.js 函數摘要

| 方法 | 支援? | 新增? | 已過時? <br>(將顯示預設內容) |
| --- | --- | --- | --- |
| `getOffer()` | 是 |
| `getOffers()` | 是 |
| `applyOffer()` | 是 |
| `applyOffers()` | 是 |
| `triggerView()` | 是 |
| `trackEvent()` | 是 |
| `mboxCreate()` | 是 |
| `mboxDefine()`<br>`mboxUpdate()` | 是 |
| `targetGlobalSettings()` | 是 |
| `Data Providers` | 是 |
| `targetPageParams()` | 是 |
| `targetPageParamsAll()` | 是 |
| `registerExtension()` | 是 |
| `At.js Custom Events` | 是 |

## 限制和圖說

請留意下列限制和圖說:

**轉換追蹤**

客戶使用 `mboxCreate()` 追蹤轉換時必須使用 `trackEvent()` 或 `getOffer()`。

**選件傳送**

客戶若沒有將 `mboxCreate()` 取代為 `getOffer()` 或 `applyOffer()`，選件可能不會傳送。

**可以在. js的某些頁面上使用. js2.x。*x*或 mbox.js，可以在不同頁面上使用 at.js 2.0.0 嗎?**

可以，使用不同版本和資料庫的頁面中會保留訪客設定檔。Cookie 格式相同。

**在at. js2.x中不完整支援Adobe Experience Cloud除錯程式**

[!DNL Adobe Experience Cloud Debugger][!UICONROL 支援摘要標籤] 功能和 [!UICONTROL 停用和控制台記錄] 工具，但at. js2.x不支援網路請求和mboxTrace。

這是因為at. js2.x中，會傳送JSON裝載，而非索引鍵值配對。若要檢查 [!DNL Target] 要求，請將瀏覽器上「開發人員工具」的[!UICONTROL 「網路」]索引標籤篩選為「傳送」、「`tt.omtrdc.net`」或您的用戶端代碼。您仍可使用查詢字串參數和授權 Token 來檢查追蹤資料。如需詳細資訊，請參閱 [mboxTrace](/help/c-activities/c-troubleshooting-activities/content-trouble.md)。

**新API用於at. js2.x**

at. js2.x使用新API，我們稱之為傳送API。若要針對 at.js 是否正確呼叫 [!DNL Target] Edge 伺服器進行除錯，您可以將瀏覽器上「開發人員工具」的「網路」索引標籤篩選為「傳送」、「`tt.omtrdc.net`」或您的用戶端代碼。您也會發現 [!DNL Target] 傳送的是 JSON 裝載而非機碼值組。

**不再使用 Target 全域 mbox**

在at. js2.x中，您不會再在網路呼叫中看到「`target-global-mbox`」。我們已改為將傳送至 [!DNL Target] 伺服器的 JSON 裝載中的「`target-global-mbox`」語法取代為「`execute > pageLoad`」，如下所示:

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

**at.js 中的全域 mbox 名稱仍重要嗎?**

客戶可以透過[!UICONTROL 「Target &gt; 設定 &gt; 實作 &gt; 編輯 at.js 設定」]指定全域 mbox 名稱。此設定供 [!DNL Target] Edge 伺服器用來將 execute &gt; pageLoad 轉譯為 [!DNL Target] UI 中顯示的全域 mbox 名稱。這麼做可讓客戶繼續使用伺服器端 API、表單式撰寫器、設定檔指令碼，以及使用全域 mbox 名稱建立對象。強烈建議您確認也已在「[!UICONTROL 設定 &gt; 偏好設定]」頁面中設定同一個全域名稱 (若您仍有頁面使用 at.js 1.*X* 或 mbox.js)，如下圖所示。

![修改 at.js 對話方塊](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

和

![自訂全域 mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

**是否需要為at. js2.x開啓自動建立全域mbox設定？**

在大多數情況下需要。此設定會告訴. js2.x在頁面載入時向 [!DNL Target] 邊緣伺服器觸發請求。由於全域 mbox 已轉譯為 execute &gt; pageLoad，因此如果您想在頁面載入時觸發要求，便應開啟此設定。

**雖然未從at. js2.x指定目標全域mbox名稱，現有的CMS活動仍會繼續運作嗎？**

會，因為 execute &gt; pageLoad 在 [!DNL Target] 後端上的處理方式如同 `target-global-mbox`。

**如果我的表單式活動目標鎖定為`target-global-mbox`，這些活動是否仍會繼續運作?**

會，因為 execute &gt; pageLoad 在 [!DNL Target] Edge 伺服器上的處理方式如同 `target-global-mbox`。

**支援且不支援. js2.x設定**

| 設定 | 支援? |
| --- | --- |
| X-Domain | 無 |
| 自動建立全域 mbox | 是 |
| 全域 mbox 名稱 | 是 |

***不*支援跨網域追蹤**

跨網域追蹤可將兩個相關網站上網域不同的工作階段視為單一工作階段。您可以建立橫跨 [!DNL Target] 和 `siteA.com` 的 `siteB.com` 活動，讓訪客在跨越網域時仍可維持相同的體驗。此功能與 Target 的第三方和第一方 Cookie 行為整合。

在 [!DNL Target] 中，第三方 Cookie 儲存在 `[CLIENTCODE].tt.omtrdc.net` 網域中，而第一方 Cookie 儲存於 `clientdomain.com` 中。第一個要求會傳回 HTTP 回應標頭，此標頭嘗試設定名為 `mboxSession` 和 `mboxPC` 的第三方 Cookie，之後傳回附有額外參數 (`mboxXDomainCheck=true`) 的重新導向要求。若瀏覽器接受第三方 Cookie，則重新導向請求會包含這些 Cookie 並傳回選件。這個工作流程之所以可行，是因為我們使用 HTTP GET 方法。

不過，在at. js2.x中已不再使用HTTP GET，而是使用HTTP POST。現在需透過 at.js 使用 HTTP POST，將 JSON 裝載傳送至 [!DNL Target] Edge 伺服器。這表示檢查瀏覽器是否支援第三方 Cookie 的重新導向要求現在已失效。這是因為 HTTP GET 要求為等冪交易，而 HTTP POST 是非等冪交易且不得任意重複。因此，不再支援at. js2.x中的跨網域追蹤。

**支援自動建立全域 mbox**

此設定會告訴. js2.x在頁面載入時向 [!DNL Target] 邊緣伺服器提出要求。由於全域 mbox 已轉譯為 execute &gt; pageLoad，且會由 [!DNL Target] Edge 伺服器加以解譯，因此顧客如果希望在頁面載入時觸發要求，便應開啟此功能。

**支援全域 mbox 名稱**

客戶可以透過[!UICONTROL 「Target &gt; 設定 &gt; 實作 &gt; 編輯 at.js 設定」]指定全域 mbox 名稱。此設定供 [!DNL Target] Edge 伺服器用來將 execute &gt; pageLoad 轉譯為輸入的全域 mbox 名稱。這麼做可讓客戶繼續使用伺服器端 API、表單式撰寫器、設定檔指令碼，以及建立鎖定全域 mbox 為目標的對象。

**以下 at.js 自訂事件適用於`triggerView()`，還是僅適用於`applyOffer()`或`applyOffers()`?**

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

是的，at.js 自訂事件也適用於 `triggerView()`。

**文中說明呼叫含有`{“page” : “true”}`的`triggerView()`時，系統會傳送通知至[!DNL Target]後端並增加曝光次數。那麼也會造成設定檔指令碼執行嗎?**

對 [!DNL Target] 後端發出預先擷取呼叫時，會執行設定檔指令碼，接著會加密受影響的設定檔資料，然後傳回用戶端。叫用含有 `{"page": "true"}` 的 `triggerView()` 後，會傳送通知並附上加密的設定檔資料。此時 [!DNL Target] 後端會將設定檔資料解密並儲存至資料庫中。

**呼叫`triggerView()`之前需要新增預先隱藏程式碼以處理忽隱忽現情況嗎?**

不需要，您不需要在呼叫 `triggerView()` 之前新增預先隱藏程式碼。at. js2.x會在顯示並套用檢視之前管理隱藏和閃爍的邏輯。

## at.js 相容性

下表說明 at.js。2.0.0 與不同活動類型、整合、功能和 at.js 函數的相容性。

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
>當所有修改套用至. js2.x和CMS時，會支援Auto-Target活動 `Page Load Event`。將修改新增至特定檢視時，僅支援A/B測試、自動分配和體驗定位(XT)活動。

### 整合

| 類型 | 支援? |
| --- | --- |
| 目標分析 (A4T) | 是 |
| 對象 | 是 |
| 客戶屬性 | 是 |
| AEM 體驗片段 | 是 |
| Adobe Launch 擴充功能 | 目前不支援 |
| 除錯程式 | 是 |
| Auditor | 尚未更新at. js2.x的規則 |
| 動態標籤管理 (DTM) | 是 |
| 選擇加入 | 無 |
| 採用 Adobe Target 技術的 AEM 增強型個人化 | 無 |

### 功能

| 功能 | 支援? |
| --- | --- |
| X-Domain | 無 |
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
| `?mboxOverride.browserIp` | 無 |

## 回應 Token {#response-tokens}

at. js2。*x*，就像at. js1。*x*，使用自訂事件 `at-request-succeeded` 來呈現回應Token。如需使用 `at-request-succeeded` 自訂事件的程式碼範例，請參閱 [回應Token](/help/administrating-target/response-tokens.md)。

## at. js1.x參數至at. js2.x裝載對應 {#payload-mapping}

本節概述在. js之間的映射。*x* 和at. js2.x。

在將參數對應至參數對應之前，這些程式庫版本所使用的端點已變更：

* at.js 1。*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at. js2.x- `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

另一個明顯的差異在於：

* at.js 1。*x* -用戶端代碼是路徑的一部分
* at. js2.x-用戶端代碼會以查詢字串參數的形式傳送，例如：
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

下列章節列出每個at. js1。*x* 參數、其描述，以及對應的2.0.0JSON裝載(如果適用)：

### at_ property

(at. js1.*x* 參數)

用於 [企業使用者權限](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### browserHeight

(at. js1.*x* 參數)

訪客瀏覽器視窗的高度。

at. js2.x JSON Payload：

```
{
  "context": {
    "window": {
       "height": 200
    }
  }
}
```

### browserWidth

(at. js1.*x* 參數)

訪客瀏覽器視窗的寬度。

at. js2.x JSON Payload：

```
{
  "context": {
    "window": {
       "width": 200
    }
  }
}
```

### browserTimeOffset

(at. js1.*x* 參數)

時區偏移。

at. js2.x JSON Payload：

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### screenHeight

(at. js1.*x* 參數)

訪客螢幕高度。

at. js2.x JSON Payload：

```
{
  "context": {
    "screen": {
       "height": 200
    }
  }
}
```

### screenWidth

(at. js1.*x* 參數)

訪客螢幕寬度。

at. js2.x JSON Payload：

```
{
  "context": {
    "screen": {
       "width": 200
    }
  }
}
```

### colorDepth

(at. js1.*x* 參數)

訪客螢幕的色彩深度。

at. js2.x JSON Payload：

```
{
  "context": {
    "screen": {
       "colorDepth": 24
    }
  }
}
```

### mboxHost

(at. js1.*x* 參數)

Target程式庫執行之頁面的網域。

at. js2.x JSON Payload：

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

(at. js1.*x* 參數)

瀏覽器的WEB GL轉譯器功能。我們的裝置偵測機制會用來判斷訪客的裝置是桌上型電腦、iPhone、Android裝置等等。

at. js2.x JSON Payload：

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

(at. js1.*x* 參數)

頁面URL。

at. js2.x JSON Payload：

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

(at. js1.*x* 參數)

頁面反向連結。

at. js2.x JSON Payload：

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox(名稱)等於全域mbox

(at. js1.*x* 參數)

傳送API不再具有全域mbox概念。在您必須使用 `execute > pageLoad`的JSON裝載中。

at. js2.x JSON Payload：

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

### mbox(名稱)不 ** 等於全域mbox

(at. js1.*x* 參數)

若要使用mbox名稱，請將其傳遞 `execute > mboxes`至。mbox需要索引和名稱。

at. js2.x JSON Payload：

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

### mboxID

(at. js1.*x* 參數)

已不再使用。

### mboxCount

(at. js1.*x* 參數)

已不再使用。

### mboxLid

(at. js1.*x* 參數)

下游系統使用的請求ID，以協助除錯。

at. js2.x JSON Payload：

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

(at. js1.*x* 參數)

已不再使用。

### mboxSession

(at. js1.*x* 參數)

作業ID會以查詢字串參數(`sessionId`)傳送至傳送API端點。

### mboxPC

(at. js1.*x* 參數)

TNT ID會傳入 `id > tntId`。

at. js2.x JSON Payload：

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at. js1.*x* 參數)

傳遞Marketing Cloud訪客ID `id > marketingCloudVisitorId`。

at. js2.x JSON Payload：

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### vst. aasa. id and vst. aasa. authState

(at. js1.*x* 參數)

應傳遞客戶ID `id > customerIds`。

at. js2.x JSON Payload：

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

(at. js1.*x* 參數)

用於連結不同Target ID的客戶第三方ID。

at. js2.x JSON Payload：

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

(at. js1.*x* 參數)

SDID也稱為補充資料ID。`experienceCloud > analytics > supplementalDataId`應傳入。

at. js2.x JSON Payload：

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

### vst. tk

(at. js1.*x* 參數)

Analytics追蹤伺服器。`experienceCloud > analytics > trackingServer`應傳入。

at. js2.x JSON Payload：

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

### vst. tracks

(at. js1.*x* 參數)

Analytics追蹤伺服器安全。`experienceCloud > analytics > trackingServerSecure`應傳入。

at. js2.x JSON Payload：

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

(at. js1.*x* 參數)

Audience Manager位置提示。`experienceCloud > audienceManager > locationHint`應傳入。

at. js2.x JSON Payload：

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

(at. js1.*x* 參數)

Audience Manager Blob。`experienceCloud > audienceManager > blob`應傳入。

at. js2.x JSON Payload：

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

(at. js1.*x* 參數)

版本會透過版本參數傳送作為查詢字串參數。

## 訓練影片：at. js2.x架構圖表

at. js2.x增強Adobe Target對SPA的支援，並與其他Experience Cloud解決方案整合。本影片說明整合方式。

>[!VIDEO](https://video.tv.adobe.com/v/26250)

如需詳細資訊，請參閱 [瞭解at. js2.x的](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) 如何運作。