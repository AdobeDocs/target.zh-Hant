---
keywords: 響應令牌；令牌；插件；插件；at.js；響應；平台web sdk
description: 瞭解如何在 [!DNL Adobe Target] 輸出特定於調試的資訊，並與第三方工具整合。
title: 什麼是響應令牌以及如何使用它們？
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1676'
ht-degree: 28%

---

# 回應 Token

響應令牌允許您自動輸出特定於 [!DNL Adobe Target] 你品牌的網頁。 此資訊可包括有關活動、服務、體驗、用戶配置檔案、地理資訊等的詳細資訊。 這些詳細資訊提供了額外的響應資料，以便與內部或第三方工具共用或用於調試。

響應令牌允許您選擇要使用的變數（鍵值對中），然後允許它們作為 [!DNL Target] 回應。 使用開關啟用變數，並且變數與 [!DNL Target] 響應，可在網路呼叫中驗證。 響應令牌也在 [!UICONTROL 預覽] 的子菜單。

插件和響應令牌之間的一個關鍵區別是，插件將JavaScript傳遞到傳遞時執行的頁面。 但是，響應令牌會傳遞一個對象，該對象隨後可以被讀取並使用事件偵聽器對其執行操作。 響應令牌方法更安全，並允許更方便地開發和維護第三方整合。

>[!NOTE]
>
>響應令牌隨at.js 1.1或更高版本提供。

| 目標SDK | 建議的操作 |
|--- |--- |
| [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/) | 確保您正在使用Platform Web SDK 2.6.0或更高版本。 有關下載最新版本的Platform Web SDK的資訊，請參見 [安裝SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) 的 *平台Web SDK概述* 的子菜單。 有關平台Web SDK每個版本中新功能的資訊，請參見 [發行說明](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html) 的 *平台Web SDK概述* 的子菜單。 |
| [at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/) | 確保您使用 at.js 版本 1.1 或更新版本。如需有關下載最新版 at.js 的資訊，請參閱[下載 at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)。如需每個 at.js 版本中新功能的相關資訊，請參閱 [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)。<br>對於使用 at.js 的客戶，建議採用回應 Token，而不要使用外掛程式。某些依賴mbox.js（現已棄用）中存在但at.js中不存在的內部方法的插件將被發送但失敗。 |

## 使用響應令牌 {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. 確保您使用的是Platform Web SDK 2.6.0版（或更高版本）或at.js 1.1版（或更高版本）。

   有關詳細資訊：

   * **平台Web SDK**:請參閱 [安裝SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) 的 *平台Web SDK概述* 的子菜單。
   * **at.js**:請參閱 [下載地址：.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)。

1. 在 [!DNL Target]按一下 **[!UICONTROL 管理]** > **[!UICONTROL 響應令牌]**。

   ![](assets/response_tokens-new.png)

1. 激活所需的響應令牌，如 `activity.id` 和 `offer.id`。

   依預設有下列參數可用:

   | 類型 | 參數 | 附註 |
   |--- |--- |--- |
   | 內建的設定檔 | `profile.activeActivities` | 傳回訪客合格可使用的 `activityIds` 陣列。這會隨著使用者合格而增加。例如，在包含兩個 [!DNL Target] 請求提供兩個不同的活動，第二個請求包括兩個活動。 |
   |  | `profile.isFirstSession` | 傳回 &quot;true&quot; 或 &quot;false&quot;。 |
   |  | `profile.isNewSession` | 傳回 &quot;true&quot; 或 &quot;false&quot;。 |
   |  | `profile.daysSinceLastVisit` | 傳回訪客上次造訪後所經過的天數。 |
   |  | `profile.tntId` | 傳回訪客的 tntID |
   |  | `profile.marketingCloudVisitorId` | 傳回訪客的 Experience Cloud 訪客 ID。 |
   |  | `profile.thirdPartyId` | 傳回訪客的第三方 ID。 |
   |  | `profile.categoryAffinity` | 傳回訪客最喜愛的類別。 |
   |  | `profile.categoryAffinities` | 以字串形式傳回訪客前 5 名類別的陣列。 |
   | 活動 | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | 目前活動的詳細資料。<br> 請注意，服務參數的值將在經驗級別進行評估。 |
   | 地理 | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | 請參閱[地理](/help/main/c-target/c-audiences/c-target-rules/geo.md)，以取得在活動中使用地理鎖定目標的詳細資訊。 |
   | 流量分配方法<br>(適用於 [!UICONTROL 自動目標] 和 [!UICONTROL Automated Personalization] 活動。) | `experience.trafficAllocationId` | 如果訪問者從「控制」流量中獲得了經驗，則返回0；如果訪問者從「目標」流量分佈中獲得了經驗，則返回1。 |
   |  | `experience.trafficAllocationType` | 返回「控制」或「目標」。 |

   使用者設定檔屬性和客戶屬性也顯示在清單中。

   >[!NOTE]
   >
   >含特殊字元的參數不會顯示在清單中。僅支援英數字元和底線。

1. （條件）將配置檔案參數用作響應令牌，但參數尚未通過 [!DNL Target] 請求，因此未載入到 [!DNL Target] UI，您可以使用 [!UICONTROL 添加響應令牌] 按鈕將配置檔案添加到UI中。

   按一下 **[!UICONTROL 添加響應令牌]**，提供標籤名稱，然後按一下 **[!UICONTROL 激活]**。

   ![](assets/response_token_create.png)

1. 建立活動。

## 偵聽響應和讀取響應令牌

您用於偵聽的流程 [!DNL Target] 響應和讀取響應標籤因您是否具有 [!DNL Platform Web SDK] 或at.js實現。

### ![Adobe Experience PlatformWeb SDK徽章](/help/main/assets/platform.png) [!DNL Platform Web SDK] 使用Handle對象類 {#platform-web-sdk}

使用Handle對象類，該類具有要偵聽的元資料對象和資料對象 [!DNL Target] 響應並讀取響應令牌。

以下響應示例添加 [!DNL Platform Web SDK] 自定義事件處理程式直接到HTML頁（該表說明了代碼中使用的對象）:

| 物件 | 資訊 |
| --- | --- |
| 類型 — 個性化.decision | 是否由 [!DNL Target] 或Offer decisioning提供程式。 |
| 決策提供程式 — TGT | TGT-[!DNL Target]. [!DNL Target] 將響應令牌元資料和值提供給頁面。 |
| 元 | 傳遞到頁面的元資料。 |
| 資料 | 傳遞到頁面的元資料的值。 |

```html
<html>

<head>
 ...
 <script src="alloy.js"></script>
 <script>
  {
   "requestId": "4d0a7cfd-952c-408c-b3b8-438edc38250a",
   "handle": [{
    "type": "personalization:decisions",
    "payload": [{
     "id": "....",
     "scope": "__view__",
     "scopeDetails": {
      "decisionProvider": "TGT",
      "activity": {
       "id": "..."
      },
      "experience": {
       "id": "...."
      }
     },
     "items": [{
      "id": "123",
      "schema": "https://ns.adobe.com/personalization/dom-action",
      "meta": {
       "activity.id": "...",
       "activity.name": "...",
       "profile.foo": "...",
       "profile.bar": "..."
      },
      "data": {
       "id": "123",
       "type": "setHtml",
       "selector": "#foo",
       "prehidingSelector": "#foo",
       "content": "<div>Hello world</div>"
      }
     }]
    }]
   }]
  }
  });
 </script>
</head>

<body>
 ...
</body>

</html>
```

### ![at.js徽章](/help/main/assets/atjs.png) at.js使用自定義事件

使用 [at.js 自訂事件](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/)接聽 回應並讀取回應 Token。[!DNL Target]

下列程式碼範例直接將 [!DNL at.js] 自訂事件處理常式新增至 HTML 頁面:

```html
<html> 
  <head> 
    .... 
    <script src="at.js"></script> 
    <script> 
      document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
        console.log("Request succeeded", e.detail); 
      }); 
    </script> 
  <head> 
  <body> 
  ... 
  </body> 
</html>
```

## 響應令牌常見問題 {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**需要什麼角色才能啟動或停用回應 Token?**

響應令牌只能由使用 [!DNL Target] [!UICONTROL 管理員] 角色。

**如果我在逃 [!DNL Platform Web SDK] 2.6.0（或更早版本）?**

您無權訪問響應令牌。

**如果我在.js 1.0（或更低版本）運行，會發生什麼情況？**

您看到響應令牌，但at.js無法使用它們。

**[!DNL Target Classic]我可以同時使用 外掛程式和回應 Token 嗎?**

插件和響應令牌可並行提供；但是，將來將不建議使用插件。

**是否通過所有 [!DNL Target] 僅通過 [!DNL Target] 提供活動的響應？**

響應令牌僅通過 [!DNL Target] 傳遞活動的響應。

**我的 [!DNL Target Classic] 插件包括JavaScript。 如何使用回應 Token 來複寫其功能?**

遷移到響應令牌時，此類型的JavaScript必須保留在代碼庫或標籤管理解決方案中。 您可以使用 [!DNL Platform Web SDK] 或 [!DNL at.js] 自定義事件並將響應令牌值傳遞給JavaScript函式。

**我的設定檔/客戶屬性參數為何沒有顯示在回應 Token 清單中?**

[!DNL Target] 通常每15分鐘刷新一次參數。 此刷新取決於用戶操作，只有在查看響應令牌頁時才刷新資料。 如果您的參數未顯示在響應標籤清單中， [!DNL Target] 尚未刷新資料。

此外，如果參數包含非字母數字字元或除下划線以外的任何符號，則該參數不會出現在清單中。 目前僅支援英數和底線字元。

**如果響應令牌使用已刪除的配置檔案指令碼或配置檔案參數，它是否仍在傳遞內容？**

回應 Token 會從使用者設定檔中擷取資訊，然後傳送該資訊。如果您刪除設定檔指令碼或參數，這不代表該資訊已從使用者設定檔中移除。用戶配置檔案仍具有與配置檔案指令碼對應的資料。 響應令牌繼續傳送內容。 對於沒有在其配置檔案中保存該資訊的用戶，或者對於新訪問者，由於資料不在其配置檔案中，因此不會傳遞該令牌。

[!DNL Target] 不會自動關閉標籤。 如果您刪除設定檔指令碼，且不想再傳送 Token，則必須自行關閉 Token。

**我已重新命名設定檔指令碼，但為何使用該指令碼的 Token 仍以舊名稱處於使用中狀態?**

如上所述，回應 Token 會處理使用者已儲存的設定檔資訊。即使您更名了您的配置檔案指令碼，訪問過您網站的用戶仍然將舊的配置檔案指令碼值保存在其配置檔案中。 令牌繼續提取已保存在用戶配置檔案中的舊值。 如果您現在想要以新名稱來傳送內容，則必須關閉先前的 Token，並開啟新的 Token。

**如果屬性已更改，何時從清單中刪除這些屬性？**

[!DNL Target] 會定期重新整理屬性。未切換的任何屬性在下次刷新時都會被刪除。 但是，如果您有一個已切換並已刪除的屬性，則在您將其關閉之前，不會將該指令碼從屬性清單中刪除。 例如，您刪除了用作令牌的配置檔案指令碼。 [!DNL Target]只有在刪除或重新命名已關閉的屬性時， 才會從清單中移除這些屬性。

## 將資料發送到Google Analytics

以下各節介紹如何發送 [!DNL Target] 資料到Google Analytics。 通過響應令牌發送的資料也可以發送到其他第三方整合。

### ![AEP徽章](/help/main/assets/platform.png) 通過平台Web SDK向Google Analytics發送資料

Google Analytics可以通過Platform Web SDK 2.6.0版（或更高版本）在HTML頁中添加以下代碼來發送資料。

>[!NOTE]
>
>確保響應令牌密鑰值對位於 `alloy(“sendEvent”` 的雙曲餘切值。

```
<script type="text/javascript"> 
   (function(i, s, o, g, r, a, m) { 
   i['GoogleAnalyticsObject'] = r; 
   i[r] = i[r] || function() { 
   (i[r].q = i[r].q || []).push(arguments) 
   }, i[r].l = 1 * new Date(); 
   
   
   a = s.createElement(o), 
   m = s.getElementsByTagName(o)[0]; 
   a.async = 1; 
   a.src = g; 
   m.parentNode.insertBefore(a, m) 
   })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
   ga('create', 'Google Client Id', 'auto'); 
</script> 
<script type="text/javascript">
   alloy("sendEvent", {
   
   
   })
   .then(({ renderedPropositions, nonRenderedPropositions }) => {
   // concatenate all the propositions
   const propositions = [...renderedPropositions, ...nonRenderedPropositions];
   // extractResponseTokens() extract the meta from item -> meta
   const tokens = extractResponseTokens(propositions);
   const activityNames = []; 
   const experienceNames = []; 
   const uniqueTokens = distinct(tokens); 
   
   
   uniqueTokens.forEach(token => { 
   activityNames.push(token["activity.name"]); 
   experienceNames.push(token["experience.name"]); 
   }); 
   
   
   ga('send', 'event', { 
   eventCategory: "target", 
   eventAction: experienceNames, 
   eventLabel: activityNames 
   }); 
   
   
   });
</script>
```

### ![at.js徽章](/help/main/assets/atjs.png) 通過at.js向Google Analytics發送資料 {#section_04AA830826D94D4EBEC741B7C4F86156}

在 HTML 頁面中新增下列程式碼，即可透過 at.js 將資料傳送至 Google Analytics:

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
<script type="text/javascript"> 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
    var tokens = e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
 
    var activityNames = []; 
    var experienceNames = []; 
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      activityNames.push(token["activity.name"]); 
      experienceNames.push(token["experience.name"]); 
    }); 
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
    }); 
  }); 
 
  function isEmpty(val) { 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## 除錯

以下各節提供有關調試響應令牌的資訊：

### ![at.js徽章](/help/main/assets/atjs.png) Google Analytics和調試

以下代碼允許您使用Google Analytics進行調試：

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
<script type="text/javascript"> 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
    var tokens = e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
 
    var activityNames = []; 
    var experienceNames = []; 
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      activityNames.push(token["activity.name"]); 
      experienceNames.push(token["experience.name"]); 
    }); 
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
    }); 
  }); 
 
  function isEmpty(val) { 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
```

### 使用ttMeta插件的等效項進行調試

將下列程式碼新增至 HTML 頁面，即可建立等同於 ttMeta 的外掛程式作為偵錯用途:

```javascript
<script type="text/javascript" > 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function (e) { 
    window.ttMETA= typeof(window.ttMETA)!="undefined" ? window.ttMETA : []; 
 
    var tokens=e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
     
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      window.ttMETA.push({ 
        'CampaignName': token["activity.name"], 
        'CampaignId' : token["activity.id"], 
        'RecipeName': token["experience.name"], 
        'RecipeId': token["experience.id"], 
        'OfferId': token["offer.id"], 
        'OfferName': token["offer.name"], 
        'MboxName': e.detail.mbox}); 
      console.log(ttMETA); 
    }); 
  }); 
 
  function isEmpty(val){ 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## ![at.js](/help/main/assets/atjs.png) 培訓視頻：響應令牌和at.js自定義事件 {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

以下視頻說明了如何使用響應令牌和at.js自定義事件共用來自 [!DNL Target] 第三方系統。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]選單 UI (之前稱為[!UICONTROL 設定]) 已經過重新設計，可提供改良的效能、縮短發佈新功能所需的維護時間，並改善整個產品的使用者體驗。 以下視頻中的資訊正確；但是，選項的位置稍有不同。
>
>視頻提到 `option.name` 和 `option.id`，已替換為 `offer.name` 和 `offer.id`的下界。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
