---
description: 從at. js升級。* x*至at. js2。* x*
keywords: at. js版本；at. js版本；單一頁面應用程式；spa；跨網域；跨網域
seo-description: 有關如何從Adobe Target at. js升級的詳細資訊。* x* to at. js2.0.0版
seo-title: 從Adobe Target升級至. js第版。* x*至at. js第版。*x*
solution: Target
subtopic: 快速入門
title: 從at. js升級。* x*至at. js2。* x*
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Upgrading from at.js 1.*x* to at.js 2.*x* {#upgrading-from-atjs-1x-to-atjs-200}

[!DNL Adobe Target] 中的最新版 at.js 提供豐富的功能，讓貴公司能以新世代用戶端技術為基礎進行個人化。本次的新版本著重於升級 at.js，進而與單一頁面應用程式 (SPA) 產生和諧互動。

Here are some benefits of using at.js 2.*x* that are not available in previous versions:

* 可在頁面載入時快取所有選件，以減少對單一伺服器呼叫發出的多個伺服器呼叫。
* 大幅改善一般使用者在網站上的體驗，因為選件能透過快取立即顯示，避免傳統伺服器呼叫引發的延遲時間。
* 簡單的單行程式碼和一次性開發人員設定，讓行銷人員可透過 VEC 在 SPA 上建立和執行 A/B 和 (XT) 活動。

## at.js 2。*x* 系統圖解

The following diagrams help you understand the workflow of at.js 2.*x* with Views and how this enhances the SPA integration. To get a better introduction of the concepts used in at.js 2.*x*, see [Single Page Application implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![使用at. js2.*x的定位流程*](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

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

![. js2.*x* 觸發器檢視的目標流程](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 呼叫 | 詳細資料 |
| --- | --- |
| 1 | 系統在 SPA 中呼叫 `triggerView()`，以便呈現檢視和套用動作來修改視覺元素。 |
| 2 | 從快取讀取檢視的目標內容。 |
| 3 | 目標內容會儘快出現，不會有忽隱忽現的預設內容。 |
| 4 | 通知要求會傳送至 [!DNL Target] 設定檔存放區，以計算活動中的訪客數和增加量度。 |
| 5 | Analytics 資料傳送至資料收集伺服器。 |
| 6 | Target 資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 A4T 報表來檢視 Analytics 資料。 |

## 部署 at.js 2.*x* {#deploy-atjs-200}

1. 部署 at.js 2.*x* 透過 [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 擴充功能。

   >[!NOTE]
   >
   > 使用Adobe Launch部署at. js是偏好的方法。

   或

   手動下載. js2。*x* 使用Target UI，並使用您選擇的 [方法部署它](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md)。

## 棄用的 at.js 函數

There are several functions that have been deprecated in at.js 2.*x*.

>[!IMPORTANT]
>
>If these deprecated functions are still used on your site when at.js 2.*x* is deployed, you will see console warnings. The recommended approach when upgrading is to test the deployment of at.js 2.*x* in a staging environment and make sure to go through each and every warning that has been logged in the console and translate the deprecated functions to new functions introduced in at.js 2.*x*.

已棄時的函數及其對應的新函數如下所列。如需完整的函數清單，請參閱 [at.js 函數](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。

>[!NOTE]
>at.js 2。*x* 不再自動隱藏 `mboxDefault` 標記的元素。因此客戶必須在網站上或透過標籤管理程式，手動提供預先隱藏邏輯。

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

**at. js2。*x*相當**

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

**at. js2。*x*相當**：

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

### 可以在. js2。*x* 會在. js的某些頁面上使用。*x* 或 mbox.js，可以在不同頁面上使用 at.js 2.x 嗎?

可以，使用不同版本和資料庫的頁面中會保留訪客設定檔。Cookie 格式相同。

### New API use in at.js 2.*x*

at.js 2。*x* 使用新API，我們稱之為傳送API。若要針對 at.js 是否正確呼叫 [!DNL Target] Edge 伺服器進行除錯，您可以將瀏覽器上「開發人員工具」的「網路」索引標籤篩選為「傳送」、「`tt.omtrdc.net`」或您的用戶端代碼。您也會發現 [!DNL Target] 傳送的是 JSON 裝載而非機碼值組。

### 不再使用 Target 全域 mbox

在 at.js 2.*x*，您不會再在網路呼叫中看到「`target-global-mbox`」。我們已改為將傳送至 [!DNL Target] 伺服器的 JSON 裝載中的「`target-global-mbox`」語法取代為「`execute > pageLoad`」，如下所示:

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

客戶可以透過[!UICONTROL 「Target &gt; 設定 &gt; 實作 &gt; 編輯 at.js 設定」]指定全域 mbox 名稱。此設定供 [!DNL Target] Edge 伺服器用來將 execute &gt; pageLoad 轉譯為 [!DNL Target] UI 中顯示的全域 mbox 名稱。這麼做可讓客戶繼續使用伺服器端 API、表單式撰寫器、設定檔指令碼，以及使用全域 mbox 名稱建立對象。強烈建議您確認也已在「[!UICONTROL 設定 &gt; 偏好設定]」頁面中設定同一個全域名稱 (若您仍有頁面使用 at.js 1.*X* 或 mbox.js)，如下圖所示。

![修改 at.js 對話方塊](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

和

![自訂全域 mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

### Does the auto-create global mbox setting need to be turned on for at.js 2.*x*?

在大多數情況下需要。This setting tells at.js 2.*x* to fire a request to the [!DNL Target] edge servers upon page load. 由於全域 mbox 已轉譯為 execute &gt; pageLoad，因此如果您想在頁面載入時觸發要求，便應開啟此設定。

### Will existing VEC activities continue to work, even though the target global mbox name is not specified from at.js 2.*x*?

會，因為 execute &gt; pageLoad 在 [!DNL Target] 後端上的處理方式如同 `target-global-mbox`。

### 如果我的表單式活動目標鎖定為 `target-global-mbox`，這些活動是否仍會繼續運作?

會，因為 execute &gt; pageLoad 在 [!DNL Target] Edge 伺服器上的處理方式如同 `target-global-mbox`。

### Supported and non-supported at.js 2.*x* Settings

| 設定 | 支援? |
| --- | --- |
| X-Domain | 無 |
| 自動建立全域 mbox | 是 |
| 全域 mbox 名稱 | 是 |

### Cross-domain tracking support in at.js 2.x {#cross-domain}

跨網域追蹤可讓跨不同網域的訪客脫穎而出。因為必須為每個網域建立新Cookie，因此在訪客從網域瀏覽至網域時很難追蹤訪客。To accomplish cross-domain tracking, [!DNL Target] uses a third-party cookie to track visitors across domains. This allows you to create a Target activity that spans `siteA.com` and `siteB.com` and visitors remain in the same experience when they navigate across unique domains. 此功能與 Target 的第三方和第一方 Cookie 行為整合。

>[!NOTE]
>
>在at. js的方塊中不支援跨網域追蹤。*x* 版本不支援此函數。在. js中支援跨網域追蹤。*x* 透過Experience Cloud ID(ECID)程式庫v4.3.0+。

In Target, the third-party cookie is stored in `<CLIENTCODE>.tt.omtrdc.net`. The first-party cookie is stored in `clientdomain.com`. 第一個要求會傳回 HTTP 回應標頭，此標頭嘗試設定名為 `mboxSession` 和 `mboxPC` 的第三方 Cookie，之後傳回附有額外參數 (`mboxXDomainCheck=true`) 的重新導向要求。如果瀏覽器接受第三方Cookie，則重新導向請求會包含這些Cookie，並傳回體驗。這個工作流程之所以可行，是因為我們使用 HTTP GET 方法。

However, in at.js 2.*x*, HTTP GET is no longer used and instead we use HTTP POST. HTTP POST現在可透過. js使用。*x* 將JSON裝載傳送至Target Edge伺服器。這表示檢查瀏覽器是否支援第三方 Cookie 的重新導向要求現在已失效。這是因為HTTP GET請求是理想的交易，而HTTP POST是非必要的，不可任意重復。因此，在at. js中追蹤跨網域。*x* 不再支援x。只有. js1。*x* 提供跨網域追蹤的立即可用支援。

If you want to use cross-domain tracking, you must install the [ECID library v4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) in conjunction with at.js 2.*x* 版本不支援此函數。ECID程式庫存在，可管理用於識別訪客跨網域的永久性ID。安裝ECID程式庫v4.3.0+和at. js之後。*x*，您將能夠建立跨獨特網域以及追蹤使用者的活動。

### 支援自動建立全域 mbox

This setting tells at.js 2.*x* to fire a request to the [!DNL Target] edge servers on page-load. 由於全域 mbox 已轉譯為 execute &gt; pageLoad，且會由 [!DNL Target] Edge 伺服器加以解譯，因此顧客如果希望在頁面載入時觸發要求，便應開啟此功能。

### 支援全域 mbox 名稱

客戶可以透過[!UICONTROL 「Target &gt; 設定 &gt; 實作 &gt; 編輯 at.js 設定」]指定全域 mbox 名稱。此設定供 [!DNL Target] Edge 伺服器用來將 execute &gt; pageLoad 轉譯為輸入的全域 mbox 名稱。這麼做可讓客戶繼續使用伺服器端 API、表單式撰寫器、設定檔指令碼，以及建立鎖定全域 mbox 為目標的對象。

### 以下 at.js 自訂事件適用於 `triggerView()`，還是僅適用於 `applyOffer()` 或 `applyOffers()`?

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

是的，at.js 自訂事件也適用於 `triggerView()`。

### 文中說明呼叫含有 `triggerView()` 的 `{“page” : “true”}` 時，系統會傳送通知至 [!DNL Target] 後端並增加曝光次數。那麼也會造成設定檔指令碼執行嗎?

對 [!DNL Target] 後端發出預先擷取呼叫時，會執行設定檔指令碼，接著會加密受影響的設定檔資料，然後傳回用戶端。叫用含有 `{"page": "true"}` 的 `triggerView()` 後，會傳送通知並附上加密的設定檔資料。此時 [!DNL Target] 後端會將設定檔資料解密並儲存至資料庫中。

### 呼叫 `triggerView()` 之前需要新增預先隱藏程式碼以處理忽隱忽現情況嗎?

不需要，您不需要在呼叫 `triggerView()` 之前新增預先隱藏程式碼。at.js 2。*x* 會在顯示並套用檢視之前，管理隱藏和閃爍邏輯。

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
>Auto-Target activities are supported through at.js 2.*x* and the VEC when all modifications are applied to the `Page Load Event`. 修改已新增至特定視圖時，僅支援 A/B 測試、自動分配和體驗鎖定目標 (XT) 活動。

### 整合 {#integrations}

| 類型 | 支援? |
| --- | --- |
| 目標分析 (A4T) | 是 |
| 對象 | 是 |
| 客戶屬性 | 是 |
| AEM 體驗片段 | 是 |
| Adobe Launch 擴充功能 | [是](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) |
| 除錯程式 | 是 |
| Auditor | Rules have not yet been updated for at.js 2.*x* |
| 動態標籤管理 (DTM) | 是 |
| 選擇加入 | 無。Opt-in support for [GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) is supported in [at.js version 2.1.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
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

at.js 2。*x*，就像 at.js 1。*x*，使用自訂事件 `at-request-succeeded` 來呈現回應 Token。如需使用 `at-request-succeeded` 自訂事件的程式碼範例，請參閱[回應 Token](/help/administrating-target/response-tokens.md)。

## at.js 1。*x* 參數至at. js2。*x* payload對應 {#payload-mapping}

本節概述 at.js 1.*x* 和at. js2.*x*。

探索參數對應之前，請注意這些資料庫版本使用的端點已變更:

* at.js 1。*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at.js 2。*x* - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

另一項顯著差異為:

* at.js 1。*x* - 用戶端代碼是路徑的一部分
* at.js 2。*x* -用戶端代碼會以查詢字串參數的形式傳送，例如：
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

以下各節列出每個 at.js 1。*x* 參數、其定義和對應 2.0.0 JSON 裝載 (若適用):

### at_property

(at.js 1.*x* 參數)

用於[企業使用者權限](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

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

(at.js 1.*x* 參數)

訪客的瀏覽器視窗高度。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

訪客的瀏覽器視窗寬度。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

時區時差。

at.js 2。*x* JSON裝載：

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### screenHeight

(at.js 1.*x* 參數)

訪客的畫面高度。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

訪客的畫面寬度。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

訪客的畫面色彩深度。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

Target 資料庫執行所在位置的頁面網域。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

瀏覽器的 WEB GL 轉譯器功能我們的裝置偵測機制會使用此功能，判斷訪客的裝置是否為桌上型電腦、iPhone、Android 裝置等。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

頁面 URL。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

頁面轉介者。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

傳遞 API 已無全域 mbox 概念。在 JSON 裝載中，您必須使用 `execute > pageLoad`。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

若要使用 mbox 名稱，請將其傳遞至 `execute > mboxes`。mbox 需要索引和名稱。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

已不再使用。

### mboxCount

(at.js 1.*x* 參數)

已不再使用。

### mboxRid

(at.js 1.*x* 參數)

下游系統用來協助進行偵錯的要求 ID。

at.js 2。*x* JSON裝載：

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

(at.js 1.*x* 參數)

已不再使用。

### mboxSession

(at.js 1.*x* 參數)

工作階段 ID 會以查詢字串參數 (`sessionId`) 的形式傳送至傳送 API 端點。

### mboxPC

(at.js 1.*x* 參數)

TNT ID 會傳遞至 `id > tntId`。

at.js 2。*x* JSON裝載：

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1.*x* 參數)

Marketing Cloud 訪客 ID 會傳遞至 `id > marketingCloudVisitorId`。

at.js 2。*x* JSON裝載：

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### `vst.aaaa.id`和`vst.aaaa.authState`

(at.js 1.*x* 參數)

客戶 ID 應傳遞至 `id > customerIds`。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

用來連結不同 Target ID 的客戶協力廠商 ID。

at.js 2。*x* JSON裝載：

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

(at.js 1.*x* 參數)

SDID (也稱為補充資料 ID)。應傳遞至 `experienceCloud > analytics > supplementalDataId`。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

Analytics 追蹤伺服器。應傳遞至 `experienceCloud > analytics > trackingServer`。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

Analytics 追蹤伺服器安全。應傳遞至 `experienceCloud > analytics > trackingServerSecure`。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

Audience Manager 位置提示。應傳遞至 `experienceCloud > audienceManager > locationHint`。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

Audience Manager Blob。應傳遞至 `experienceCloud > audienceManager > blob`。

at.js 2。*x* JSON裝載：

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

(at.js 1.*x* 參數)

版本會透過版本參數以查詢字串參數的形式傳送。

## Training video: at.js 2.*x* architectural diagram

at.js 2。*x* 增強了Adobe Target對SPA的支援，並與其他Experience Cloud解決方案整合。本影片說明整合方式。

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=chi_hant)

See [Understanding how at.js 2.*x* 適用於](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) 更多資訊。