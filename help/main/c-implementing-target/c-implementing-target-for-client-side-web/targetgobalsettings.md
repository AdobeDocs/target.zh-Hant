---
keywords: serverstate;targetGlobalSettings;targetGlobalsettings;globalSettings;globalSettings;globalsettings;globalsettings;globalsettings;globalsettings;at.js；函式；clientCode;clientDomain;serverDomain;cookieDomain;cookieDomain;crossDomain;timeout;globalMboxAutoCreate;visiterApiTimeout;defaultContCoConteCeDent;defaultCCCCeCCCeCeCeCe樣式；defaultContentVisibleStyle;bodyHiddenStyle;bodyHiddingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServerTimeout;optout;optout；選擇器輪詢超時；資料提供程式；混合個性化；設備IdLifetime
description: 使用targetGlobalSettings()函式進行Adobe [!DNL Target] at.js JavaScript庫以替代設定，而不是使用 [!DNL Target] UI或REST API。
title: 如何使用targetGlobalSettings()函式？
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '2405'
ht-degree: 29%

---

# targetGlobalSettings()

您可以使用 `targetGlobalSettings()` 覆寫 at.js 資料庫中的設定，而非在 [!DNL Target] Standard/Premium UI 中或使用 REST API 進行設定。

## 設定 {#section_42C759AE9B524A43B8659018677224B8}

您可以覆寫下列設定:

### bodyHiddenStyle

* **類型:** 字串
* **預設值**:正文{不透明度：0 }
* **說明**:僅在 `globalMboxAutocreate === true` 盡量降低閃爍的可能性。

   如需詳細資訊，請參閱 [at.js 處理忽隱忽現情況的方式](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/)。

### bodyHidingEnabled

* **類型**:布爾型
* **預設值**:真
* **說明**:用於控制閃爍 `target-global-mbox` 用於提供在Visual Experience Composer中建立的優惠，也稱為可視優惠。

### clientCode

* **類型:** 字串
* **預設值**:通過UI設定的值。
* **說明**:表示客戶端代碼。

### cookieDomain

* **類型:** 字串
* **預設值**:如果可能，請設定為頂級域。
* **說明**:表示保存Cookie時使用的域。

### crossDomain

* **類型:** 字串
* **預設值**:通過UI設定的值。
* **說明**:指示是否啟用跨域跟蹤。 允許的值包括：已禁用、已啟用或僅x。

### cspScriptNonce

* **類型**:請參閱 [內容安全策略](#content-security) 下。
* **預設值**:請參閱 [內容安全策略](#content-security) 下。
* **說明**:請參閱 [內容安全策略](#content-security) 下。

### cspStyleNonce

* **類型**:請參閱 [內容安全策略](#content-security) 下。
* **預設值**:請參閱 [內容安全策略](#content-security) 下。
* **說明**:請參閱 [內容安全策略](#content-security) 下。

### dataProviders

* **類型**:請參閱 [資料提供程式](#data-providers) 下。
* **預設值**:請參閱 [資料提供程式](#data-providers) 下。
* **說明**:請參閱 [資料提供程式](#data-providers) 下。

### 決策方法 {#on-device-decisioning}

* **類型:** 字串
* **預設值**:伺服器端
* **其他值**:設備上，混合
* **說明**:請參閱下面的「決策方法」。

   **決策方法**

   在設備上進行決策時，Target引入了一個新設定，稱為 [!UICONTROL 決策方法] 這就決定了at.js是如何傳遞你的體驗的。 的 `decisioningMethod` 有三個值：僅伺服器端、僅設備端和混合型。 當 `decisioningMethod` 設定為 `targetGlobalSettings()`，它充當所有 [!DNL Target] 決定。

   **[!UICONTROL 僅伺服器端]**:

   [!UICONTROL 僅伺服器端] 是當在Web屬性上實現和部署at.js 2.5+時從框中設定的預設決策方法。

   使用 [!UICONTROL 僅伺服器端] 預設配置表示對 [!DNL Target] 邊緣網路，涉及阻塞伺服器呼叫。 此方法可以引入增量延遲，但也提供了顯著的優勢，例如讓您能夠應用Target的機器學習功能，包括 [Recommendations](/help/main/c-recommendations/recommendations.md)。 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （美聯社） [自動目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活動。

   此外，使用Target的用戶配置檔案增強您的個性化體驗，可為您的業務提供強大的結果。

   最後， [!UICONTROL 僅伺服器端] 讓您使用Adobe Experience Cloud和通過Audience Manager和Adobe Analytics段可以針對的微調觀眾。

   **[!UICONTROL 僅限設備上]**:

   [!UICONTROL 僅限設備上] 是必須在at.js 2.5+中設定的決策方法，當設備上的決策只應在整個網頁中使用時。

   設備上決策可以以超快的速度提供您的體驗和個性化活動，因為決策來自快取的規則項目，其中包含符合設備上決策資格的所有活動。

   要瞭解有關哪些活動符合設備上決策的詳細資訊，請參閱支援的功能部分。

   僅當效能在所有需要決策的頁面中都非常關鍵時，才應使用此決策方法 [!DNL Target]。 此外，請記住，當選擇此判定方法時， [!DNL Target] 不符合設備上決策資格的活動將不會交付或執行。 at.js庫2.5+配置為僅查找快取的規則項目以做出決策。

   **混合**:

   [!UICONTROL 混合] 是在必須執行設備上決策和需要網路呼叫到Adobe Target邊緣網路的活動時，必須在at.js 2.5+中設定的決策方法。

   在管理設備上決策活動和伺服器端活動時，在思考如何部署和調配時可能會有些複雜和繁瑣 [!DNL Target] 在你的網頁上。 以混合作為判定方法， [!DNL Target] 知道何時必須為需要伺服器端執行的活動向Adobe Target邊緣網路進行伺服器呼叫，以及何時只執行設備上的決定。

   JSON規則項目包括元資料，用於通知at.js框是否具有正在運行的伺服器端活動或設備上的決策活動。 此決策方法可確保您想要快速交付的活動通過設備決策完成，對於需要更強大的ML驅動個性化的活動，這些活動通過Adobe Target邊緣網路完成。

### defaultContentHiddenStyle

* **類型:** 字串
* **預設值**:可見性：隱藏
* **說明**:僅用於包裝使用類名為「mboxDefault」的DIV並通過 `mboxCreate()`。 `mboxUpdate()`或 `mboxDefine()` 隱藏預設內容。

### defaultContentVisibleStyle

* **類型:** 字串
* **預設值**:可見性：可見
* **說明**:僅用於包裝使用類名為「mboxDefault」的DIV並通過 `mboxCreate()`。 `mboxUpdate()`或 `mboxDefine()` 顯示應用的優惠（如果有）或預設內容。

### 設備IdLifetime

* **類型**:數字
* **預設值**:6324480000毫秒= 2年
* **說明**:時間量 `deviceId` 在Cookie中保留。

>[!NOTE]
>
>在at.js版本2.3.1或更高版本中，deviceIdLifetime設定是可覆蓋的。

### 已啟用

* **類型**:布爾型
* **預設值**:真
* **說明**:啟用時， [!DNL Target] 自動執行檢索體驗的請求和呈現體驗的DOM操作。 而且， [!DNL Target] 可通過 `getOffer(s)` / `applyOffer(s)`。

   禁用後， [!DNL Target] 請求不是自動或手動執行的。

### globalMboxAutoCreate

* **類型**:數字
* **預設值**:通過UI設定的值。
* **說明**:指示是否應觸發全局mbox請求。

### imsOrgId

* **類型**:斯廷
* **預設值**:真
* **說明**:表示IMS ORG ID。

### 啟用選項

* **類型**:布爾型
* **預設值**:假
* **說明**: [!DNL Target] 通過 [!DNL Adobe Experience Platform] 幫助支援您的同意管理策略。 選擇加入功能可讓客戶控制引發 [!DNL Target] 標記的方法和時機。也可選擇透過 [!DNL Adobe Experience Platform] 預先核准 [!DNL Target] 標記。在中啟用選擇加入功能 [!DNL Target] at.js庫，添加 `optinEnabled=true` 的子菜單。 在 [!DNL Adobe Experience Platform] 必須從 [!UICONTROL GDPR選擇加入] 下拉清單。 查看 [Adobe Experience Platform文檔](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) 的子菜單。 有關此設定的詳細資訊，如與隱私和資料保護法規有關，包括歐盟的一般資料保護法規(GDPR)和加利福尼亞消費者隱私法(CCPA)，請參見 [隱私和資料保護法規](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/)。

### optoutEnabled

* **類型**:布爾型
* **預設值**:假
* **說明**:指示目標是否應調用訪問者API `isOptedOut()` 的子菜單。 這屬於裝置圖表啟用的一部分。

### overrideMboxEdgeServer

* **類型**:布爾型
* **預設值**:true(以at.js 1.6.2版開頭為true)
* **說明**:指示我們是否應使用 `<clientCode>.tt.omtrdc.net` 域或 `mboxedge<clusterNumber>.tt.omtrdc.net` 。

   如果此值為 true，則會將 `mboxedge<clusterNumber>.tt.omtrdc.net` 網域儲存至 Cookie. 當前未使用 [名稱](https://developer.adobe.com/target/before-implement/implement-cname-support-in-target/) 使用at.js 1.8.2和at.js 2.3.1之前的at.js版本時，如果這是您的問題，請考慮 [更新at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) 到更新的受支援版本。

### overrideMboxEdgeServerTimeout

* **類型**:數字
* **預設值**:1860000 => 31分鐘
* **說明**:指示包含 `mboxedge<clusterNumber>.tt.omtrdc.net` 值。

### pageLoadEnabled

* **類型**:布爾型
* **預設值**:真
* **說明**:啟用後，自動檢索必須在頁面載入時返回的體驗。

### secureOnly

* **類型**:布爾型
* **預設值**:假
* **說明**:指示at.js是否應僅使用HTTPS或是否允許基於頁協定在HTTP和HTTPS之間切換。 如果設定為true，則secureOnly還會將Secure和SameSite屬性設定為mbox cookie。

### selectorsPollingTimeout

* **類型**:數字
* **預設值**:5000毫秒= 5秒
* **說明**:在at.js 0.9.6中， [!DNL Target] 引入了此新設定，可通過 `targetGlobalSettings`。

   的 `selectorsPollingTimeout` 設定表示客戶端願意等待選定器標識的所有元素出現在頁面上的時間。

   透過可視化體驗撰寫器 (VEC) 建立的活動，其具有的選件包含選取器。

### serverDomain

* **類型:** 字串
* **預設值**:通過UI設定的值。
* **說明**:表示目標邊緣伺服器。

### 伺服器狀態

* **類型**:請參閱 [混合個性化](#server-state) 下。
* **預設值**:請參閱 [混合個性化](#server-state) 下。
* **說明**:請參閱 [混合個性化](#server-state) 下。

### 遙測已啟用 {#telemetry}

* **類型**:布爾型
* **預設值**:真
* **說明**:啟用後， [!DNL Adobe] 收集SDK功能使用情況和效能遙測資料。 不會收集個人資料。

### timeout

* **類型**:數字
* **預設值**:通過UI設定的值。
* **說明**:表示 [!DNL Target] 邊緣請求超時。

### 視圖已啟用

* **類型**:布爾型
* **預設值**:真
* **說明**:啟用後，自動檢索必須在頁面載入時返回的視圖。 at.js 2支援視圖。*x* 中受到支援。

### visitorApiTimeout

* **類型**:數字
* **預設值**:2000毫秒= 2秒
* **說明**:表示 [!UICONTROL 訪問者API] 請求超時。

## 使用狀況 {#section_9AD6FA3690364F7480C872CB55567FB0}

可以在載入at.js之前或在中定義此函式 **[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!UICONTROL 編輯at.js設定]** > **[!UICONTROL 代碼設定]** > **[!UICONTROL 庫標題]**。

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
| 名稱 | 字串 | 提供者的名稱。 |
| version | 字串 | 提供者版本。此機碼將用於提供者演進。 |
| 超時 | 數字 | 如果這是網路要求，則代表提供者逾時。此機碼為選用。 |
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

## 內容安全性政策 {#content-security}

at.js 2.3.0+支援在應用已傳送的目標提供時，在SCRIPT和附加到頁DOM的STYLE標籤上設定內容安全策略不可用。

應在中設定SCRIPT和STYLE選項 `targetGlobalSettings.cspScriptNonce` 和 `targetGlobalSettings.cspStyleNonce` 相應地，在at.js 2.3.0+載入之前。 請參閱以下示例：

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

之後 `cspScriptNonce` 和 `cspStyleNonce` 指定設定，at.js 2.3.0+將這些設定設定為應用目標提供時附加到DOM的所有SCRIPT和STYLE標籤上的nonce屬性。

## 混合個性化 {#server-state}

`serverState` 是at.js v2.2+中提供的設定，當實現Target的混合整合時，可用於優化頁面效能。 混合整合意指您在用戶端上同時使用 at.js v2.2+ 和伺服器端的傳送 API 或 Target SDK 來傳送體驗。`serverState` 讓 at.js v2.2+ 能夠直接從伺服器端擷取並傳回至用戶端的內容套用體驗，做為所提供頁面的一部分。

### 先決條件

您必須將 [!DNL Target]。

* **伺服器端**:必須使用新 [傳遞API](https://developers.adobetarget.com/api/delivery-api/) 或 [目標SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs)。
* **客戶端**:必須使用 [at.js 2.2或更高版本](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)。

### 代碼示例

要更好地瞭解此操作的工作原理，請參閱下面在伺服器上將提供的代碼示例。 代碼假定您使用 [目標節點.js SDK](https://github.com/adobe/target-nodejs-sdk)。

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

示例 `serverState` 視圖預取的對象JSON如下所示：

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

在瀏覽器中載入頁面後， at.js將應用所有 [!DNL Target] 提供 `serverState` 立即，不向任何網路呼叫 [!DNL Target] 邊。 此外，at.js僅預隱藏其 [!DNL Target] 內容獲取的伺服器端提供了服務，因此會對頁面載入效能和最終用戶體驗產生積極影響。

### 重要說明

使用時請考慮以下事項 `serverState`:

* 目前， at.js v2.2僅支援通過serverState為以下對象提供體驗：

   * VEC建立的活動，在頁載入中執行。
   * 預取的視圖。

      在使SPA用 [!DNL Target] 視圖和 `triggerView()` 在at.js API中， at.js v2.2快取伺服器端預取的所有視圖的內容，並在每個視圖觸發時立即應用這些內容 `triggerView()`，也不會向Target觸發任何其他內容提取調用。

   * **注釋**:當前，中不支援在伺服器端檢索的框 `serverState`。

* 應用時 `serverState `提供，at.js考慮 `pageLoadEnabled` 和 `viewsEnabled` 設定，例如，如果 `pageLoadEnabled` 設定為false。

   要開啟這些設定，請啟用切換 **[!UICONTROL 管理] > [!UICONTROL 實施] > [!UICONTROL 編輯] > [!UICONTROL 已啟用頁面載入]**。

   ![啟用頁面載入設定](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* 如果您使用 `serverState` 使用 `<script>` 返回的內容中的標籤，確保您的HTML內容使用 `<\/script>` 而不是 `</script>`。 如果您使用 `</script>`，瀏覽器解釋 `</script>` 作為內聯SCRIPT的結尾，它可能會中斷HTML頁。

### 其他資源

瞭解詳情 `serverState` 工作，檢出以下資源：

* [程式碼範例](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [單頁應用程式(SPA)示例應用 `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo)。
