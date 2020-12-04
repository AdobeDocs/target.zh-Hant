---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 targetGlobalSettings() 函數的資訊。
title: targetGlobalSettings()
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 38%

---


# targetGlobalSettings()

您可以使用 `targetGlobalSettings()` 覆寫 at.js 資料庫中的設定，而非在 [!DNL Target] Standard/Premium UI 中或使用 REST API 進行設定。

有些使用案例，特別是當 at.js 是透過 [!DNL Dynamic Tag Management] (DTM) 傳遞，而您想要覆寫部分設定時。

## 設定 {#section_42C759AE9B524A43B8659018677224B8}

您可以覆寫下列設定:

### bodyHiddenStyle

* **類型:** 字串
* **預設值**:body { opacity:0 }
* **說明**:僅用於 `globalMboxAutocreate === true` 將閃爍的可能性降到最低。

   如需詳細資訊，請參閱 [at.js 處理忽隱忽現情況的方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)。

### bodyHidingEnabled

* **類型**:布林值
* **預設值**:true
* **說明**:當用來傳送在Visual Experience Composer中 `target-global-mbox` 建立的選件（亦稱為視覺選件）時，用來控制閃爍。

### clientCode

* **類型:** 字串
* **預設值**:透過UI設定的值。
* **說明**:代表用戶端代碼。

### cookieDomain

* **類型:** 字串
* **預設值**:如果可能，請設為頂層網域。
* **說明**:代表儲存Cookie時使用的網域。

### crossDomain

* **類型:** 字串
* **預設值**:透過UI設定的值。
* **說明**:指出是否啟用跨網域追蹤。 允許的值包括：停用、啟用或僅限x-only。

### cspScriptNonce

* **類型**:請參 [閱下方的內容安全](#content-security) 政策。
* **預設值**:請參 [閱下方的內容安全](#content-security) 政策。
* **說明**:請參 [閱下方的內容安全](#content-security) 政策。

### cspStyleNonce

* **類型**:請參 [閱下方的內容安全](#content-security) 政策。
* **預設值**:請參 [閱下方的內容安全](#content-security) 政策。
* **說明**:請參 [閱下方的內容安全](#content-security) 政策。

### dataProviders

* **類型**:請參 [閱下方的資料](#data-providers) 提供者。
* **預設值**:請參 [閱下方的資料](#data-providers) 提供者。
* **說明**:請參 [閱下方的資料](#data-providers) 提供者。

### defaultContentHiddenStyle

* **類型:** 字串
* **預設值**:可見性：隱藏
* **說明**:僅用於包裝使用DIV與類別名稱&quot;mboxDefault&quot;並透過、或執行以隱 `mboxCreate()`藏預 `mboxUpdate()`設 `mboxDefine()` 內容的mbox。

### defaultContentVisibleStyle

* **類型:** 字串
* **預設值**:可見性：visel
* **說明**:僅用於包裝使用DIV與類別名稱「mboxDefault」並透過、 `mboxCreate()``mboxUpdate()``mboxDefine()` 或顯示套用的選件（如果有或預設內容）的mbox。

### deviceIdLifetime

* **類型**:數字
* **預設值**:6324480000 ms = 2年
* **說明**:Cookie中持 `deviceId` 續的時間量。

>[!NOTE]
>
>deviceIdLifetime設定在at.js 2.3.1版或更新版本中可覆寫。

### 已啟用

* **類型**:布林值
* **預設值**:true
* **說明**:啟用後，會自 [!DNL Target] 動執行擷取體驗的要求和轉譯體驗的DOM操作。 此外， [!DNL Target] 呼叫可透過 `getOffer(s)` /手動執行 `applyOffer(s)`。

   停用時， [!DNL Target] 不會自動或手動執行請求。

### globalMboxAutoCreate

* **類型**:數字
* **預設值**:透過UI設定的值。
* **說明**:指出全域mbox請求是否應引發。

### imsOrgId

* **類型**:Sting
* **預設值**:true
* **說明**:代表IMS組織ID。

### optoutEnabled

* **類型**:布林值
* **預設值**:false
* **說明**:指出Target是否應呼叫訪客API `isOptedOut()` 函式。 這屬於裝置圖表啟用的一部分。

### overrideMboxEdgeServer

* **類型**:布林值
* **預設值**:true(true開頭為at.js 1.6.2版
* **說明**:指出我們應使用網 `<clientCode>.tt.omtrdc.net` 域或網 `mboxedge<clusterNumber>.tt.omtrdc.net` 域。

   如果此值為 true，則會將 `mboxedge<clusterNumber>.tt.omtrdc.net` 網域儲存至 Cookie. 當使用at.js 1.8.2和at.js 2.3.1之前的at.js版本時，目前無法使用 [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) 。如果這是您的問題，請考 [慮將at.js更新為較新](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) 、支援的版本。

### overrideMboxEdgeServerTimeout

* **類型**:數字
* **預設值**:1860000 => 31分鐘
* **說明**:指出包含值的Cookie存 `mboxedge<clusterNumber>.tt.omtrdc.net` 留期。

### pageLoadEnabled

* **類型**:布林值
* **預設值**:true
* **說明**:啟用後，會自動擷取必須在頁面載入時傳回的體驗。

### secureOnly

* **類型**:布林值
* **預設值**:false
* **說明**:指出at.js應僅使用HTTPS，還是允許根據頁面通訊協定在HTTP和HTTPS之間切換。

### selectorsPollingTimeout

* **類型**:數字
* **預設值**:5000 ms = 5 s
* **說明**:在at.js 0.9.6中，引 [!DNL Target] 入此可透過覆寫的新設定 `targetGlobalSettings`。

   The `selectorsPollingTimeout` setting represents how long the client is willing to wait for all the elements identified by selectors to appear on the page.

   透過可視化體驗撰寫器 (VEC) 建立的活動，其具有的選件包含選取器。

### serverDomain

* **類型:** 字串
* **預設值**:透過UI設定的值。
* **說明**:代表Target邊緣伺服器。

### serverState

* **類型**:請參 [閱下方的Hybrid](#server-state) personalization。
* **預設值**:請參 [閱下方的Hybrid](#server-state) personalization。
* **說明**:請參 [閱下方的Hybrid](#server-state) personalization。

### timeout

* **類型**:數字
* **預設值**:透過UI設定的值。
* **說明**:代表邊緣 [!DNL Target] 請求逾時。

### viewsEnabled

* **類型**:布林值
* **預設值**:true
* **說明**:啟用後，會自動擷取必須在頁面載入時傳回的檢視。 at.js 2支援檢視。*x* 版。

### visitorApiTimeout

* **類型**:數字
* **預設值**:2000 ms = 2 s
* **說明**:代表訪 [!UICONTROL 客API請求] 逾時。

## 使用狀況 {#section_9AD6FA3690364F7480C872CB55567FB0}

This function can be defined before at.js is loaded or in **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

資料庫標頭欄位允許輸入自由格式的 JavaScript。自訂程式碼看起來應該類似於下列範例:

```javascript
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## 資料提供者 {#data-providers}

此設定可讓客戶收集來自第三方資料提供者 (例如 Demandbase、BlueKai 和自訂服務) 的資料，並在全域 mbox 要求中以 mbox 參數的形式傳遞資料至 Target。它透過非同步和同步要求，以支援來自多個提供者的資料收集。使用此方法可讓您方便管理預設頁面內容的忽隱忽現情形，同時對每個提供者包含獨立的逾時計算，以限制對頁面效能的影響

>[!NOTE]
>
>[!DNL at.js] 1.3 或更新版本才支援資料提供者功能。

以下影片包含更多資訊:

| 影片 | 說明 |
|--- |--- |
| [使用 Adobe Target 中的資料提供者](https://helpx.adobe.com/tw/target/kt/using/dataProviders-atjs-feature-video-use.html) | 資料提供者這項功能可以讓您輕鬆將資料從第三方傳入 Target。第三方可能是氣象服務、DMP，甚至是您自己的 Web 服務。接著，您就能使用此資料來建立對象、鎖定內容及擴充訪客設定檔。 |
| [實作 Adobe Target 中的資料提供者](https://helpx.adobe.com/tw/target/kt/using/dataProviders-atjs-technical-video-implement.html) | 實作詳細資料和範例，說明如何使用 Adobe Target 的 dataProviders 功能，從第三方資料提供者擷取資料，並將其傳遞到 Target 請求。 |

`window.targetGlobalSettings.dataProviders` 設定是資料提供者的陣列。

每個資料提供者具有下列結構:

| 機碼 | 類型 | 說明 |
|--- |--- |--- |
| name | 字串 | 提供者的名稱。 |
| version | 字串 | 提供者版本。此機碼將用於提供者演進。 |
| timeout | 數字 | 如果這是網路要求，則代表提供者逾時。此機碼為選用。 |
| provider | 函數 | 包括提供者資料擷取邏輯的函數。<br>函數有單一必要參數: `callback`。callback 參數為函數，僅應該在成功擷取資料或發生錯誤時叫用。<br>callback 預期兩個參數:<ul><li>error: 指出是否發生錯誤。如果各項都正常，則此參數應該設為 null。</li><li>params: JSON 物件，代表將在 Target 要求中傳送的參數。</li></ul> |

下列範例顯示的資料提供者正在使用同步執行:

```javascript
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

在 at.js 處理 `window.targetGlobalSettings.dataProviders` 之後，Target 要求將包含新參數: `t1=1`。

如果您要新增至 Target 要求的參數是從第三方服務 (例如 Bluekai、Demandbase 等等) 擷取，以下是範例:

```javascript
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

at.js 處理 `window.targetGlobalSettings.dataProviders` 之後，Target 要求將包含其他參數: `t2=2`、`t1=1` 和 `t3=3`。

下列範例使用資料提供者來收集天氣 API 資料，並將資料以參數形式在 Target 要求中傳送。Target 要求會將額外的參數，例如 `country` 和 `weatherCondition`。

```javascript
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

使用 `dataProviders` 設定時，請考慮下列各項:

* 如果新增至 `window.targetGlobalSettings.dataProviders` 的資料提供者非同步，則會並行執行。訪客 API 要求將與新增至 `window.targetGlobalSettings.dataProviders` 的函數並行執行，以允許最低的等候時間。
* at.js 不會嘗試將資料快取。如果資料提供者擷取資料一次，則資料提供者應該確定已將該資料快取，並且當叫用該提供者函數時，可做為第二個叫用的快取資料。

## Content Security Policy {#content-security}

at.js 2.3.0+支援在套用傳送的Target選件時，在附加至頁面DOM的SCRIPT和STYLE標籤上設定「內容安全性原則」不可用。

在載入at.js 2.3.0+之前， `targetGlobalSettings.cspScriptNonce` 應先在 `targetGlobalSettings.cspStyleNonce` SCRIPT和STYLEnonces中設定。 請參閱下列範例：

```javascript
...
<head>
 <script nonce="<script_nonce_value>">
window.targetGlobalSettings = {
  cspScriptNonce: "<csp_script_nonce_value>",
  cspStyleNonce: "<csp_style_nonce_value>"
};
 </script>
 <script nonce="<script_nonce_value>" src="at.js"></script>
...
</head>
...
```

在指 `cspScriptNonce` 定 `cspStyleNonce` 和設定後，at.js 2.3.0+會在套用Target選件時，將這些屬性設為附加至DOM的所有SCRIPT和STYLE標籤上的nonce屬性。

## 混合個人化 {#server-state}

`serverState` 是at.js v2.2+中可用的設定，可在實作Target的混合整合時用來最佳化頁面效能。 混合整合意指您在用戶端上同時使用at.js v2.2+和伺服器端的傳送API或Target SDK來傳送體驗。 `serverState` 讓at.js v2.2+能夠直接從伺服器端擷取並傳回至用戶端的內容套用體驗，做為所提供頁面的一部分。

### 先決條件

您必須有混合整合 [!DNL Target]。

* **伺服器端**: 您必須使用新的 [傳送API](https://developers.adobetarget.com/api/delivery-api/) 或 [Target SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs)。
* **用戶端**:您必須使 [用at.js 2.2版或更新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

### 程式碼範例

若要進一步瞭解其運作方式，請參閱下列您在伺服器上的程式碼範例。 程式碼假設您使用 [Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk)。

```javascript
// First, we fetch the offers via Target Node.js SDK API, as usual
const targetResponse = await targetClient.getOffers(options);
// A successfull response will contain Target Delivery API request and response objects, which we need to set as serverState
const serverState = {
  request: targetResponse.request,
  response: targetResponse.response
};
// Finally, we should set window.targetGlobalSettings.serverState in the returned page, by replacing it in a page template, for example
const PAGE_TEMPLATE = `
<!doctype html>
<html>
<head>
  ...
  <script>
    window.targetGlobalSettings = {
      overrideMboxEdgeServer: true,
      serverState: ${JSON.stringify(serverState, null, " ")}
    };
  </script>
  <script src="at.js"></script>
</head>
...
</html>
`;
// Return PAGE_TEMPLATE to the client ...
```

檢視預回 `serverState` 遷的範例物件JSON外觀如下：

```
{
 "request": {
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "context": {
   "channel": "web",
   "timeOffsetInMinutes": 0
  },
  "experienceCloud": {
   "analytics": {
    "logging": "server_side",
    "supplementalDataId": "7D3AA246CC99FD7F-1B3DD2E75595498E"
   }
  },
  "prefetch": {
   "views": [
    {
     "address": {
      "url": "my.testsite.com/"
     }
    }
   ]
  }
 },
 "response": {
  "status": 200,
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "client": "testclient",
  "edgeHost": "mboxedge21.tt.omtrdc.net",
  "prefetch": {
   "views": [
    {
     "name": "home",
     "key": "home",
     "options": [
      {
       "type": "actions",
       "content": [
        {
         "type": "setHtml",
         "selector": "#app > DIV.app-container:eq(0) > DIV.page-container:eq(0) > DIV:nth-of-type(2) > SECTION.section:eq(0) > DIV.container:eq(1) > DIV.heading:eq(0) > H1.title:eq(0)",
         "cssSelector": "#app > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(2) > SECTION:nth-of-type(1) > DIV:nth-of-type(2) > DIV:nth-of-type(1) > H1:nth-of-type(1)",
         "content": "<span style=\"color:#FF0000;\">Latest</span> Products for 2020"
        }
       ],
       "eventToken": "t0FRvoWosOqHmYL5G18QCZNWHtnQtQrJfmRrQugEa2qCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
       "responseTokens": {
        "profile.memberlevel": "0",
        "geo.city": "dublin",
        "activity.id": "302740",
        "experience.name": "Experience B",
        "geo.country": "ireland"
       }
      }
     ],
     "state": "J+W1Fq18hxliDDJonTPfV0S+mzxapAO3d14M43EsM9f12A6QaqL+E3XKkRFlmq9U"
    }
   ]
  }
 }
}
```

頁面載入瀏覽器後，at.js會立即套用所有選件， [!DNL Target] 而不 `serverState` 會針對邊緣觸發任何網路呼 [!DNL Target] 叫。 此外，at.js只會預先隱藏內容擷取伺服器端提供選件的DOM元素，因此會對頁面載入效能和使用者體驗產生積極影響。 [!DNL Target]

### 重要附註

Consider the following when using `serverState`:

* 目前，at.js v2.2僅支援透過serverState提供以下體驗：

   * 在頁面載入時執行的VEC建立活動。
   * 預先擷取的檢視。

      若是使用 [!DNL Target] Views的SPA `triggerView()` 和at.js API, at.js v2.2會快取伺服器端預先擷取之所有View的內容，並在每個View觸發時立即套用這些內容 `triggerView()`，而不會再對Target觸發任何額外的內容擷取呼叫。

   * **注意**: 目前，不支援在伺服器端擷取的mbox `serverState`。

* 套用選 `serverState `件時，at.js會考慮並設定 `pageLoadEnabled` , `viewsEnabled` 例如，如果設定為false，則不會套用「頁面載入 `pageLoadEnabled` 選件」。

   若要開啟這些設定，請啟用「管理 **[!UICONTROL >實作] >編輯 [!UICONTROL >啟]**&#x200B;用載入頁面」中的切換。

   ![頁面載入啟用的設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* 如果您在傳回的 `serverState` 內容中 `<script>` 使用和使用標籤，請確定您的HTML內容 `<\/script>` 使用而非 `</script>`。 如果您使 `</script>`用，瀏覽器會解 `</script>` 譯為內嵌SCRIPT的結尾，並可能中斷HTML頁面。

### 其他資源

若要進一步瞭解 `serverState` 運作方式，請查看下列資源：

* [程式碼範例](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [單頁應用程式(SPA)範例應用程式 `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo)。
