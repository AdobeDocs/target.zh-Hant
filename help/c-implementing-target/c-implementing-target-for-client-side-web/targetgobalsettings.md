---
description: '有關適用於 at.js 的 targetGlobalSettings() 函數的資訊。 '
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 targetGlobalSettings() 函數的資訊。
seo-title: 有關適用於 Adobe Target at.js JavaScript 資料庫的 targetGlobalSettings() 函數的資訊。
solution: Target
subtopic: 快速入門
title: targetGlobalSettings()
topic: Standard
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# targetGlobalSettings()

您可以使用 `targetGlobalSettings()` 覆寫 at.js 資料庫中的設定，而非在 [!DNL Target] Standard/Premium UI 中或使用 REST API 進行設定。

有些使用案例，特別是當 at.js 是透過 [!DNL Dynamic Tag Management] (DTM) 傳遞，而您想要覆寫部分設定時。

## 設定 {#section_42C759AE9B524A43B8659018677224B8}

您可以覆寫下列設定:

| 設定 | 類型 | 預設值 | 說明 |
|--- |--- |--- |--- |
| clientCode | 字串 | 透過 UI 設定值 | 代表用戶端代碼 |
| serverDomain | 字串 | 透過 UI 設定值 | 代表 Target Edge 伺服器 |
| cookieDomain | 字串 | 如果可能，設為上層網域 | 代表儲存 Cookie 時使用的網域 |
| crossDomain | 字串 | 透過 UI 設定值 | 指出跨網域追蹤是否已啟用。<br>允許的值為:<ul><li>已停用</li><li>已啟用</li><li>僅 x</li></ul> |
| timeout | 數字 | 透過 UI 設定值 | 代表 Target Edge 要求逾時 |
| globalMboxAutoCreate | 布林值 | 透過 UI 設定值 | 指出是否應觸發全域 mbox 要求 |
| visitorApiTimeout | 數字 | 2000 毫秒 = 2 秒 | 代表訪客 API 要求逾時 |
| 已啟用 | 布林值 | true | 指出 at.js 作為資料庫是否已啟用，代表它是否應該執行任何動作。此設定的主要使用案例為選擇退出 Cookie 或會停用 at.js 功能的其他自訂決策 |
| defaultContentHiddenStyle | 字串 | visibility: hidden | 僅用於包住使用類別名稱為「mboxDefault」的 DIV，並透過 `mboxUpdate()`、`mboxCreate()` 或 `mboxDefine()` 執行以隱藏預設內容的 mbox |
| defaultContentVisibleStyle | 字串 | visibility: visible | 僅用於包住使用類別名稱為「mboxDefault」的 DIV，並透過 `mboxUpdate()`、`mboxCreate()` 或 `mboxDefine()` 執行以顯示套用的選件 (若有) 或預設內容的 mbox |
| bodyHiddenStyle | 字串 | body { opacity: 0 } | 僅當 `globalMboxAutocreate === true` 才使用，以將閃爍的機會最小化。<br>如需詳細資訊，請參閱 [at.js 處理忽隱忽現情況的方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)。 |
| bodyHidingEnabled | 布林值 | true | 當 `target-global-mbox` 用來傳遞在 可視化體驗撰寫器中建立的選件時，用來控制閃爍，也稱為視覺選件 |
| imsOrgId | 字串 | IMS 組織 ID | 代表 IMS ORG ID |
| secureOnly | 布林值 | false | 指出 at.js 是否應該僅使用 HTTPS 或根據頁面通訊協定，允許在 HTTP 與 HTTPS 之間切換。 |
| overrideMboxEdgeServer | 布林值 | true (從 at.js 1.6.2 版開始) | 指出應使用 `<clientCode>.tt.omtrdc.net` 網域還是 `mboxedge<clusterNumber>.tt.omtrdc.net` 網域。<br>如果此值為 true，則會將 `mboxedge<clusterNumber>.tt.omtrdc.net` 網域儲存至 Cookie |
| overrideMboxEdgeServerTimeout | 數字 | 1860000 =&gt; 31 分鐘 | 指出包括 `mboxedge<clusterNumber>.tt.omtrdc.net` 值的 Cookie 存留期。 |
| optoutEnabled | 布林值 | false | 指出 Target 是否應該呼叫訪客 API `isOptedOut()` 函數。這屬於裝置圖表啟用的一部分。 |
| selectorsPollingTimeout | 數字 | 5000 毫秒 = 5 秒 | 在 at.js 0.9.6 中，Target 推出了這項新設定，且可以透過 `targetGlobalSettings` 覆寫此設定。<br>`selectorsPollingTimeout` 代表用戶端願意等候選取器所識別的所有元素出現在頁面上的時間。<br>透過可視化體驗撰寫器 (VEC) 建立的活動，其具有的選件包含選取器。 |
| dataProviders | 請參閱下文的「資料提供者」。 | 請參閱下文的「資料提供者」。 | 請參閱下文的「資料提供者」。 |

## 使用狀況 {#section_9AD6FA3690364F7480C872CB55567FB0}

可以在載入 at.js 之前定義此函數，或是在 **[!UICONTROL 「設定]** &gt; **[!UICONTROL 實作]** &gt; **[!UICONTROL 編輯 at.js 設定]** &gt; **[!UICONTROL 程式碼設定]** &gt; **[!UICONTROL 資料庫標題」]** 中定義。

資料庫標頭欄位允許輸入自由格式的 JavaScript。自訂程式碼看起來應該類似於下列範例:

```
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
| [在 Adobe Target 中實作資料提供者](https://helpx.adobe.com/tw/target/kt/using/dataProviders-atjs-technical-video-implement.html) | 實作詳細資料和範例，說明如何使用 Adobe Target 的 dataProviders 功能，從第三方資料提供者擷取資料，並將其傳遞到 Target 請求。 |

`window.targetGlobalSettings.dataProviders` 設定是資料提供者的陣列。

每個資料提供者具有下列結構:

| 機碼 | 類型 | 說明 |
|--- |--- |--- |
| name | 字串 | 提供者的名稱。 |
| version | 字串 | 提供者版本。此機碼將用於提供者演進。 |
| timeout | 數字 | 如果這是網路要求，則代表提供者逾時。此機碼為選用。 |
| provider | 函數 | 包括提供者資料擷取邏輯的函數。<br>函數有單一必要參數: `callback`。callback 參數為函數，僅應該在成功擷取資料或發生錯誤時叫用。<br>callback 預期兩個參數:<ul><li>error: 指出是否發生錯誤。如果各項都正常，則此參數應該設為 null。</li><li>params: JSON 物件，代表將在 Target 要求中傳送的參數。</li></ul> |

下列範例顯示的資料提供者正在使用同步執行:

```
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

```
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

```
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
