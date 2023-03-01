---
keywords: 回應Token; Token；外掛程式；at.js；回應；平台Web Sdk
description: 了解如何在 [!DNL Adobe Target] 輸出特定資訊，以偵錯並與第三方工具整合。
title: 什麼是回應Token？如何使用？
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: 3ac61272ee1ccd72a8670966f181e7798cbe9f76
workflow-type: tm+mt
source-wordcount: '1669'
ht-degree: 27%

---

# 回應 Token

回應Token可讓您自動輸出 [!DNL Adobe Target] 至您品牌的網頁。 此資訊可包含活動、選件、體驗、使用者設定檔、地理資訊等的詳細資訊。 這些詳細資料提供額外的回應資料，可與內部或第三方工具共用，或用於除錯。

回應Token可讓您選擇要使用的變數（以索引鍵值配對表示），然後啟用這些變數以隨附於 [!DNL Target] 回應。 您可使用開關啟用變數，變數的傳送方式為 [!DNL Target] 回應，可在網路呼叫中驗證。 回應Token也可在 [!UICONTROL 預覽] 模式。

外掛程式和回應Token之間的主要差異，在於外掛程式會將JavaScript傳送至傳送時執行的頁面。 但是，回應Token會傳送物件，然後可使用事件接聽程式來讀取並採取行動。 回應代號方法更安全，且可更輕鬆開發和維護協力廠商整合。

>[!NOTE]
>
>回應Token可與at.js 1.1版或更新版本搭配使用。

| Target SDK | 建議的動作 |
|--- |--- |
| [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} | 請確定您使用的是Platform Web SDK 2.6.0版或更新版本。 如需下載最新版Platform Web SDK的相關資訊，請參閱 [安裝SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html){target=_blank} 在 *平台Web SDK概述* 指南。 如需各版Platform Web SDK中新功能的相關資訊，請參閱 [發行說明](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html) 在 *平台Web SDK概述* 指南。 |
| [at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/){target=_blank} | 確保您使用 at.js 版本 1.1 或更新版本。如需有關下載最新版at.js的資訊，請參閱 [下載at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}. For information about new functionality in each version of at.js, see [at.js Version Details](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.<br>對於使用 at.js 的客戶，建議採用回應 Token，而不要使用外掛程式。有些外掛程式需仰賴存在於mbox.js中的內部方法（現已淘汰），但不存在於at.js中，但系統會傳送但失敗。 |

## 使用回應Token {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. 請確定您使用的是Platform Web SDK 2.6.0版（或更新版）或at.js 1.1版（或更新版）。

   如需詳細資訊：

   * **平台Web SDK**:請參閱 [安裝SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) 在 *平台Web SDK概述* 指南。
   * **at.js**:請參閱 [下載at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}.

1. 在 [!DNL Target]，按一下 **[!UICONTROL 管理]** > **[!UICONTROL 回應Token]**.

   ![response_tokens-new image](assets/response_tokens-new.png)

1. 啟動所需的回應Token，例如 `activity.id` 和 `offer.id`.

   依預設有下列參數可用:

   | 類型 | 參數 | 附註 |
   |--- |--- |--- |
   | 內建的設定檔 | `profile.activeActivities` | 傳回訪客合格可使用的 `activityIds` 陣列。這會隨著使用者合格而增加。例如，在含有兩個 [!DNL Target] 傳送兩個不同活動的請求，第二個請求包含兩個活動。 |
   |  | `profile.isFirstSession` | 傳回 &quot;true&quot; 或 &quot;false&quot;。 |
   |  | `profile.isNewSession` | 傳回 &quot;true&quot; 或 &quot;false&quot;。 |
   |  | `profile.daysSinceLastVisit` | 傳回訪客上次造訪後所經過的天數。 |
   |  | `profile.tntId` | 傳回訪客的 tntID |
   |  | `profile.marketingCloudVisitorId` | 傳回訪客的 Experience Cloud 訪客 ID。 |
   |  | `profile.thirdPartyId` | 傳回訪客的第三方 ID。 |
   |  | `profile.categoryAffinity` | 傳回訪客最喜愛的類別。 |
   |  | `profile.categoryAffinities` | 以字串形式傳回訪客前 5 名類別的陣列。 |
   | 活動 | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | 目前活動的詳細資料。<br> 請注意，系統會在體驗層級評估選件參數的值。 |
   | 地理 | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | 請參閱[地理](/help/main/c-target/c-audiences/c-target-rules/geo.md)，以取得在活動中使用地理鎖定目標的詳細資訊。 |
   | 流量分配方法<br>(適用於 [!UICONTROL 自動鎖定目標] 和 [!UICONTROL Automated Personalization] 活動。) | `experience.trafficAllocationId` | 如果訪客從「控制」流量中收到體驗，則傳回0；如果訪客從「已鎖定目標」流量分佈收到體驗，則傳回1。 |
   |  | `experience.trafficAllocationType` | 傳回「控制」或「已鎖定」。 |

   使用者設定檔屬性和客戶屬性也顯示在清單中。

   >[!NOTE]
   >
   >含特殊字元的參數不會顯示在清單中。僅支援英數字元和底線。

1. （條件性）若要使用設定檔參數作為回應Token，但參數尚未透過 [!DNL Target] 請求，因此未載入 [!DNL Target] UI，您可以使用 [!UICONTROL 新增回應Token] 按鈕，將設定檔新增至UI。

   按一下 **[!UICONTROL 新增回應Token]**，提供代號名稱，然後按一下 **[!UICONTROL 啟動]**.

   ![response_token_create image](assets/response_token_create.png)

1. 建立活動。

## 接聽回應並讀取回應Token

您用來監聽的程式 [!DNL Target] 回應和讀取回應Token會因您是否有 [!DNL Platform Web SDK] 或at.js實作。

### ![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png) [!DNL Platform Web SDK] 使用Handle對象類 {#platform-web-sdk}

使用Handle對象類，該類具有要偵聽的元資料對象和資料對象 [!DNL Target] 回應並讀取回應token。

下列回應範例新增 [!DNL Platform Web SDK] 直接到「HTML」頁的自訂事件處理程式（該表說明了代碼中使用的對象）:

| 物件 | 資訊 |
| --- | --- |
| 類型 — 個人化.decision | 是否由 [!DNL Target] 或Offer decisioning提供者。 |
| DecisionProvider - TGT | TGT-[!DNL Target]. [!DNL Target] 提供回應Token中繼資料和值至頁面。 |
| Meta | 傳遞至頁面的中繼資料。 |
| 資料 | 傳遞至頁面的中繼資料的值。 |

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

### ![at.js徽章](/help/main/assets/atjs.png) at.js使用自訂事件

使用 [at.js 自訂事件](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/)接聽 回應並讀取回應 Token。{target=_blank}[!DNL Target]

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

## 回應Token常見問題集 {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**需要什麼角色才能啟動或停用回應 Token?**

回應Token只能由使用 [!DNL Target] [!UICONTROL 管理員] 角色。

**如果我在執行 [!DNL Platform Web SDK] 2.6.0（或更舊版本）?**

您無權存取回應Token。

**如果我執行的是at.js 1.0（或更舊版本），會發生什麼事？**

您看到回應Token，但at.js無法使用。

**[!DNL Target Classic]我可以同時使用 外掛程式和回應 Token 嗎?**

外掛程式和回應Token可同時使用；不過，未來將會淘汰外掛程式。

**是否透過 [!DNL Target] 僅通過 [!DNL Target] 傳送活動的回應？**

回應Token只能透過 [!DNL Target] 傳送活動的回應。

**我的 [!DNL Target Classic] 外掛程式包含JavaScript。 如何使用回應 Token 來複寫其功能?**

移轉至回應Token時，此類JavaScript必須保留在程式碼基底或標籤管理解決方案中。 您可以使用 [!DNL Platform Web SDK] 或 [!DNL at.js] 自訂事件，並將回應Token值傳遞至您的JavaScript函式。

**我的設定檔/客戶屬性參數為何沒有顯示在回應 Token 清單中?**

[!DNL Target] 通常每15分鐘重新整理一次參數。 此重新整理會視使用者動作而定，且只有在您檢視回應Token頁面時才會重新整理資料。 如果您的參數未顯示在回應Token清單中， [!DNL Target] 尚未刷新資料。

此外，如果參數包含非英數字元或底線以外的任何符號，則該參數不會出現在清單中。 目前僅支援英數和底線字元。

**如果回應Token使用已刪除的設定檔指令碼或設定檔參數，仍會傳送內容嗎？**

回應 Token 會從使用者設定檔中擷取資訊，然後傳送該資訊。如果您刪除設定檔指令碼或參數，這不代表該資訊已從使用者設定檔中移除。使用者設定檔仍有與設定檔指令碼對應的資料。 回應Token會繼續傳送內容。 若使用者的設定檔中未儲存該資訊，或是新訪客，則不會傳送該Token，因為資料不存在於其設定檔中。

[!DNL Target] 不會自動關閉代號。 如果您刪除設定檔指令碼，且不想再傳送 Token，則必須自行關閉 Token。

**我已重新命名設定檔指令碼，但為何使用該指令碼的 Token 仍以舊名稱處於使用中狀態?**

如上所述，回應 Token 會處理使用者已儲存的設定檔資訊。即使您重新命名設定檔指令碼，造訪過您網站的使用者的設定檔中仍會儲存舊的設定檔指令碼值。 代號會繼續擷取已儲存在使用者設定檔中的舊值。 如果您現在想要以新名稱來傳送內容，則必須關閉先前的 Token，並開啟新的 Token。

**如果屬性已變更，何時會從清單中移除？**

[!DNL Target] 會定期重新整理屬性。未開啟的任何屬性都會在下次重新整理時移除。 不過，如果您有已開啟且已移除的屬性，該指令碼不會從屬性清單中移除，除非您將其關閉。 例如，您移除了當作Token的設定檔指令碼。 [!DNL Target]只有在刪除或重新命名已關閉的屬性時， 才會從清單中移除這些屬性。

## 傳送資料至Google Analytics

以下各節將說明如何傳送 [!DNL Target] 資料至Google Analytics。 回應Token所傳送的資料也可傳送至其他第三方整合。

### ![AEP徽章](/help/main/assets/platform.png) 透過Platform Web SDK傳送資料至Google Analytics

Google Analytics可在HTML頁面中新增下列程式碼，以透過Platform Web SDK 2.6.0版（或更新版本）傳送資料。

>[!NOTE]
>
>請確定回應Token索引鍵值組位於 `alloy(“sendEvent”` 物件。

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

### ![at.js徽章](/help/main/assets/atjs.png) 透過at.js傳送資料至Google Analytics {#section_04AA830826D94D4EBEC741B7C4F86156}

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

以下小節提供偵錯回應Token的相關資訊：

### ![at.js徽章](/help/main/assets/atjs.png) Google Analytics和除錯

下列程式碼可讓您使用Google Analytics除錯：

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

### 使用等同於ttMeta外掛程式進行除錯

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

## ![at.js](/help/main/assets/atjs.png) 訓練影片：回應Token和at.js自訂事件 {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

以下影片說明如何使用回應Token和at.js自訂事件，共用來自 [!DNL Target] 協力廠商系統。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]選單 UI (之前稱為[!UICONTROL 設定]) 已經過重新設計，可提供改良的效能、縮短發佈新功能所需的維護時間，並改善整個產品的使用者體驗。 以下視頻中的資訊正確；不過，選項的位置稍有不同。
>
>影片提及 `option.name` 和 `option.id`，其取代為 `offer.name` 和 `offer.id`，分別為。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
