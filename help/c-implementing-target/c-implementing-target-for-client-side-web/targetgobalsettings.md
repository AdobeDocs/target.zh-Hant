---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings；全域設定；at.js；函式；clientCode;clientcode;serverDomain;cookieDomain;crossDomain;crossDomain；逾時；globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenBodyEnabledIms;ImsEnborgId;EneId;ImImIdOneId;OneIdImIdId;OnId;OnIdOnImImOneIdEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;optout;selectorsPollingTimeout;dataProviders；混合個人化；deviceIdLifetime
description: 對Adobe [!DNL Target] at.js JavaScript library to override settings instead of using the [!DNL Target] UI或REST API使用targetGlobalSettings()函式。
title: 如何使用targetGlobalSettings()函式？
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '2332'
ht-degree: 30%

---

# targetGlobalSettings()

您可以使用 `targetGlobalSettings()` 覆寫 at.js 資料庫中的設定，而非在 [!DNL Target] Standard/Premium UI 中或使用 REST API 進行設定。

## 設定 {#section_42C759AE9B524A43B8659018677224B8}

您可以覆寫下列設定:

### bodyHiddenStyle

* **類型:** 字串
* **預設值**:正文{不透明度：0 }
* **說明**:僅當才使 `globalMboxAutocreate === true` 用，以將閃爍的機率最小化。

   如需詳細資訊，請參閱 [at.js 處理忽隱忽現情況的方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)。

### bodyHidingEnabled

* **類型**:布林值
* **預設值**:true
* **說明**:當用來傳遞在可視化 `target-global-mbox` 體驗撰寫器中建立的選件時，用來控制閃爍，也稱為視覺選件。

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
* **說明**:指出是否啟用跨網域追蹤。允許的值為：已停用、已啟用或僅x。

### cspScriptNonce

* **類型**:請參閱 [下方的內容安](#content-security) 全性原則。
* **預設值**:請參閱 [下方的內容安](#content-security) 全性原則。
* **說明**:請參閱 [下方的內容安](#content-security) 全性原則。

### cspStyleNonce

* **類型**:請參閱 [下方的內容安](#content-security) 全性原則。
* **預設值**:請參閱 [下方的內容安](#content-security) 全性原則。
* **說明**:請參閱 [下方的內容安](#content-security) 全性原則。

### dataProviders

* **類型**:請參閱 [下方的](#data-providers) 資料提供者。
* **預設值**:請參閱 [下方的](#data-providers) 資料提供者。
* **說明**:請參閱 [下方的](#data-providers) 資料提供者。

### 決策方法 {#on-device-decisioning}

* **類型:** 字串
* **預設值**:伺服器端
* **其他值**:設備上，混合
* **說明**:請參閱下方的決策方法。

   **決策方法**

   透過裝置上的決策功能，Target推出了名為[!UICONTROL 決策方法]的新設定，指定at.js如何提供您的體驗。 `decisioningMethod`有三個值：僅限伺服器端、僅限裝置上和混合式。 在`targetGlobalSettings()`中設定`decisioningMethod`時，它會作為所有[!DNL Target]決策的預設決策方法。

   **[!UICONTROL 僅限伺服器端]**:

   [!UICONTROL 只有伺] 服器端是當at.js 2.5+實作並部署在Web屬性上時，才會立即設定的預設決策方法。

   使用[!UICONTROL 僅伺服器端]作為預設配置意味著所有決策都在[!DNL Target]邊緣網路上做出，這涉及阻塞伺服器調用。 此方法可以引入增量延遲，但也能提供顯著優點，例如讓您能套用Target的機器學習功能，其中包含[Recommendations](/help/c-recommendations/recommendations.md)、[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)和[自動鎖定目標](/help/c-activities/auto-target/auto-target-to-optimize.md)活動。

   此外，使用Target的使用者設定檔來增強您的個人化體驗，此設定檔可跨工作階段和管道保存，可為您的業務提供強大的成果。

   最後，[!UICONTROL 僅伺服器端]可讓您使用Adobe Experience Cloud並微調可透過Audience Manager和Adobe Analytics區段鎖定的對象。

   **[!UICONTROL 僅限裝置]**:

   [!UICONTROL 只有裝] 置上決策是必須在at.js 2.5+中設定的決策方法，而裝置上決策只應在您的網頁中使用。

   裝置上決策可以超快的速度提供您的體驗和個人化活動，因為決策是由快取規則工件所做，其中包含所有符合裝置上決策資格的活動。

   若要進一步了解哪些活動符合裝置上決策的資格，請參閱支援的功能區段。

   只有在所有需要[!DNL Target]決策的頁面上效能極為關鍵時，才應使用此決策方法。 此外，請記得選取此決策方法時，不符合裝置上決策資格的[!DNL Target]活動將不會傳送或執行。 at.js資料庫2.5+的設定僅會尋找快取規則工件以做出決策。

   **混合**:

    混合at.js 2.5+中必須設定的決策方法，因為必須同時執行裝置上決策和需要對Adobe Target Edge網路進行網路呼叫的活動。

   當您同時管理裝置上的決策活動和伺服器端活動時，思考如何在頁面上部署和布建[!DNL Target]時，可能會有些複雜且繁瑣。 [!DNL Target]採用混合決策方法，可針對需要伺服器端執行的活動，以及何時只需執行裝置上的決策，得知必須在Adobe Target Edge網路進行伺服器呼叫的時機。

   JSON規則工件包含中繼資料，可通知at.jsmbox有執行的伺服器端活動或裝置上的決策活動。 此決策方法可確保您想要快速傳送的活動能透過裝置決策完成，而對於需要更強大ML導向個人化的活動，這些活動可透過Adobe Target Edge網路完成。

### defaultContentHiddenStyle

* **類型:** 字串
* **預設值**:可見性：隱藏
* **說明**:僅用於包住使用類別名稱為「mboxDefault」的DIV，並透過、或執 `mboxCreate()`行以 `mboxUpdate()`隱藏預 `mboxDefine()` 設內容的mbox。

### defaultContentVisibleStyle

* **類型:** 字串
* **預設值**:可見性：可見
* **說明**:僅用於包住使用類別名稱為「mboxDefault」的DIV，並透過、或執行以 `mboxCreate()`顯示套用的選 `mboxUpdate()`件(若 `mboxDefine()` 有)或預設內容的mbox。

### deviceIdLifetime

* **類型**:數字
* **預設值**:63244800000 ms = 2年
* **說明**:Cookie中持 `deviceId` 續存在的時間。

>[!NOTE]
>
>at.js 2.3.1版或更新版本中的deviceIdLifetime設定可覆寫。

### 已啟用

* **類型**:布林值
* **預設值**:true
* **說明**:啟用後，會 [!DNL Target] 自動執行擷取體驗的要求和轉譯體驗的DOM操作。此外，[!DNL Target]呼叫可透過`getOffer(s)` / `applyOffer(s)`手動執行。

   停用時，系統不會自動或手動執行[!DNL Target]請求。

### globalMboxAutoCreate

* **類型**:數字
* **預設值**:透過UI設定的值。
* **說明**:指出是否應觸發全域mbox要求。

### imsOrgId

* **類型**:字串
* **預設值**:true
* **說明**:代表IMS組織ID。

### optinEnabled

* **類型**:布林值
* **預設值**:false
* **說明**: [!DNL Target] 透過支援選擇加入功能， [!DNL Adobe Experience Platform] 以協助支援同意管理策略。選擇加入功能可讓客戶控制引發 [!DNL Target] 標記的方法和時機。也可選擇透過 [!DNL Adobe Experience Platform] 預先核准 [!DNL Target] 標記。若要啟用在[!DNL Target] at.js資料庫中使用選擇加入的功能，請新增`optinEnabled=true`設定。 在[!DNL Adobe Experience Platform]中，您必須以擴充功能安裝檢視，從[!UICONTROL GDPR選擇加入]下拉式清單中選取「啟用」。 如需詳細資訊，請參閱[Adobe Experience Platform檔案](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。 如需與隱私權和資料保護法規(包括歐盟一般資料保護規範(GDPR)和加州消費者隱私法(CCPA))相關之設定的詳細資訊，請參閱[隱私權和資料保護規範](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)。

### optoutEnabled

* **類型**:布林值
* **預設值**:false
* **說明**:指出Target是否應呼叫訪客API `isOptedOut()` 函式。這屬於裝置圖表啟用的一部分。

### overrideMboxEdgeServer

* **類型**:布林值
* **預設值**:true（從at.js版本1.6.2開始）
* **說明**:指出應使用網 `<clientCode>.tt.omtrdc.net` 域或網 `mboxedge<clusterNumber>.tt.omtrdc.net` 域。

   如果此值為 true，則會將 `mboxedge<clusterNumber>.tt.omtrdc.net` 網域儲存至 Cookie. 使用at.js 1.8.2和at.js 2.3.1之前的at.js版本時，目前無法使用[CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md)。如果這是您的問題，請考慮將at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)更新至更新的支援版本。[

### overrideMboxEdgeServerTimeout

* **類型**:數字
* **預設值**:1860000 => 31分鐘
* **說明**:指出包含值的Cookie存 `mboxedge<clusterNumber>.tt.omtrdc.net` 留期。

### pageLoadEnabled

* **類型**:布林值
* **預設值**:true
* **說明**:啟用後，會自動擷取頁面載入時必須傳回的體驗。

### secureOnly

* **類型**:布林值
* **預設值**:false
* **說明**:指出at.js是否應該僅使用HTTPS或根據頁面通訊協定，允許在HTTP與HTTPS之間切換。設為true時，secureOnly也會將Secure和SameSite屬性設為mbox Cookie。

### selectorsPollingTimeout

* **類型**:數字
* **預設值**:5000毫秒= 5秒
* **說明**:在at.js 0.9.6中，推出 [!DNL Target] 了這項新設定，且可以透過覆寫 `targetGlobalSettings`。

   `selectorsPollingTimeout`設定代表用戶端願意等候選取器所識別的所有元素出現在頁面上的時間。

   透過可視化體驗撰寫器 (VEC) 建立的活動，其具有的選件包含選取器。

### serverDomain

* **類型:** 字串
* **預設值**:透過UI設定的值。
* **說明**:代表Target邊緣伺服器。

### serverState

* **類型**:請參 [閱下方](#server-state) 的混合個人化。
* **預設值**:請參 [閱下方](#server-state) 的混合個人化。
* **說明**:請參 [閱下方](#server-state) 的混合個人化。

### timeout

* **類型**:數字
* **預設值**:透過UI設定的值。
* **說明**:代表 [!DNL Target] 邊緣請求逾時。

### viewsEnabled

* **類型**:布林值
* **預設值**:true
* **說明**:啟用後，會自動擷取頁面載入時必須傳回的檢視。at.js 2支援檢視。*x* 中受到支援。

### visitorApiTimeout

* **類型**:數字
* **預設值**:2000毫秒= 2秒
* **說明**:代表訪 [!UICONTROL 客] API要求逾時。

## 使用狀況 {#section_9AD6FA3690364F7480C872CB55567FB0}

可在載入at.js之前定義此函式，或在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**&#x200B;中定義。

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
| 逾時 | 數字 | 如果這是網路要求，則代表提供者逾時。此機碼為選用。 |
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

at.js 2.3.0+支援在套用傳送的Target選件時，在附加至頁面DOM的SCRIPT和STYLE標籤上設定「內容安全性原則」取消。

在at.js 2.3.0+載入前，應在`targetGlobalSettings.cspScriptNonce`和`targetGlobalSettings.cspStyleNonce`中相應設定SCRIPT和STYLE Nonce。 請參閱下列範例：

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

在指定`cspScriptNonce`和`cspStyleNonce`設定後，at.js 2.3.0+會在套用Target選件時附加至DOM的所有SCRIPT和STYLE標籤上，將這些設定設為Nonce屬性。

## 混合個人化 {#server-state}

`serverState` 是at.js v2.2+中可用的設定，可在實作Target的混合整合時用來最佳化頁面效能。混合整合意指您在用戶端上同時使用 at.js v2.2+ 和伺服器端的傳送 API 或 Target SDK 來傳送體驗。`serverState` 讓 at.js v2.2+ 能夠直接從伺服器端擷取並傳回至用戶端的內容套用體驗，做為所提供頁面的一部分。

### 先決條件

您必須有[!DNL Target]的混合整合。

* **伺服器端**:您必須使用新 [的](https://developers.adobetarget.com/api/delivery-api/) 傳送 [API或Target SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs)。
* **用戶端**:您必須使 [用at.js版本2.2或更新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

### 程式碼範例

若要深入了解其運作方式，請參閱下列程式碼範例，讓您在伺服器上看到。 程式碼假設您使用[Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk)。

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

檢視預先擷取的範例`serverState`物件JSON如下所示：

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

在瀏覽器中載入頁面後，at.js會立即套用`serverState`的所有[!DNL Target]選件，而不會對[!DNL Target]邊緣觸發任何網路呼叫。 此外，at.js僅會預先隱藏[!DNL Target]選件可用於從伺服器端擷取之內容中的DOM元素，因此會對頁面載入效能和一般使用者體驗造成正面影響。

### 重要附註

使用`serverState`時，請考量下列事項：

* 目前，at.js v2.2僅支援透過serverState傳送體驗，用於：

   * 在頁面載入時執行的VEC建立活動。
   * 預先擷取檢視。

      若SPA在at.js API中使用[!DNL Target]檢視和`triggerView()`,at.js v2.2會快取伺服器端預先擷取之所有檢視的內容，並在每個檢視透過`triggerView()`觸發時立即套用，而不會再對Target觸發任何其他內容擷取呼叫。

   * **注意**:目前，不支援在伺服器端擷取的mbox  `serverState`。

* 套用`serverState `選件時，at.js會考慮`pageLoadEnabled`和`viewsEnabled`設定，例如，如果`pageLoadEnabled`設定為false，則不會套用頁面載入選件。

   若要開啟這些設定，請啟用&#x200B;**[!UICONTROL Administration] > [!UICONTROL Implementation] > [!UICONTROL Edit] > [!UICONTROL Page Load Enabled]**&#x200B;中的切換按鈕。

   ![啟用頁面載入的設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* 如果您在傳回的內容中使用`serverState`並使用`<script>`標籤，請確定您的HTML內容使用`<\/script>`而非`</script>`。 若您使用`</script>`，瀏覽器會將`</script>`解譯為內嵌指令碼上的結尾，而可能會中斷HTML頁面。

### 其他資源

若要進一步了解`serverState`的運作方式，請查看下列資源：

* [程式碼範例](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [單頁應用程式(SPA)範例應用程 `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo)式。
