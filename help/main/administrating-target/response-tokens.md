---
keywords: 回應Token；Token；外掛程式；外掛程式；at.js；回應；平台web sdk；google analytics
description: 瞭解如何在 [!DNL Adobe Target] 中使用回應Token來輸出特定資訊，以便偵錯並與協力廠商工具整合。
title: 什麼是回應Token？如何使用它們？
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 24%

---

# 回應 Token

回應Token可讓您自動將[!DNL Adobe Target]的特定資訊輸出至您品牌的網頁。 此資訊可包含有關活動、選件、體驗、使用者設定檔、地理資訊等詳細資訊。 這些詳細資料提供額外的回應資料，可與內部或第三方工具共用，或用於偵錯。

回應Token可讓您選擇要使用的變數（在索引鍵值配對中），然後啟用這些變數作為[!DNL Target]回應的一部分傳送。 您使用交換器啟用變數，變數會與[!DNL Target]個回應一併傳送，這可以在網路呼叫中驗證。 回應Token也可在[!UICONTROL Preview]模式下運作。

外掛程式和回應Token的主要差異在於，外掛程式會將JavaScript傳送至傳送時執行的頁面。 然而，回應Token會傳送物件，然後可以使用事件接聽程式讀取該物件並據以採取行動。 回應Token方法比較安全，而且在開發和維護第三方整合時較輕鬆。

{{permissions-update}}

>[!NOTE]
>
>回應Token附隨於at.js 1.1版或更新版本提供。

| 鎖定SDK | 建議的動作 |
|--- |--- |
| [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} | 確保您使用Platform Web SDK 2.6.0版或更新版本。 如需有關下載最新版Platform Web SDK的資訊，請參閱[Platform Web SDK概觀](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hant){target=_blank}指南中的&#x200B;*安裝SDK*。 如需每個Platform Web SDK版本中新功能的相關資訊，請參閱[Platform Web SDK概觀](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant)指南中的&#x200B;*發行說明*。 |
| [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=zh-Hant){target=_blank} | 確保您使用 at.js 版本 1.1 或更新版本。如需有關下載最新版 at.js 的資訊，請參閱[下載 at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=zh-Hant){target=_blank}。如需每個 at.js 版本中新功能的相關資訊，請參閱 [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank}。<br>對於使用 at.js 的客戶，建議採用回應 Token，而不要使用外掛程式。mbox.js （現已棄用）中有部分外掛程式所依賴的內部方法，但at.js中卻沒有，雖然可以傳送這些外掛程式，但卻會失敗。 |

## 使用回應Token {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. 確保您使用Platform Web SDK 2.6.0版（或更新版本）或at.js版本1.1 （或更新版本）。

   如需詳細資訊：

   * **Platform Web SDK**：請參閱[Platform Web SDK總覽](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hant)指南中的&#x200B;*安裝SDK*。
   * **at.js**：請參閱[下載at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=zh-Hant){target=_blank}。

1. 在[!DNL Target]中，按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Response Tokens]**。

1. 啟用所需的回應Token，例如`activity.id`和`offer.id`。

   依預設有下列參數可用:

   | 類型 | 參數 | 附註 |
   |--- |--- |--- |
   | 內建的輪廓 | `profile.activeActivities` | 傳回訪客合格可使用的 `activityIds` 陣列。這會隨著使用者合格而增加。例如，在包含兩個[!DNL Target]請求（傳送兩個不同的活動）的頁面上，第二個請求會包含兩個活動。 |
   |  | `profile.isFirstSession` | 傳回 &quot;true&quot; 或 &quot;false&quot;。 |
   |  | `profile.isNewSession` | 傳回 &quot;true&quot; 或 &quot;false&quot;。 |
   |  | `profile.daysSinceLastVisit` | 傳回訪客上次造訪後所經過的天數。 |
   |  | `profile.tntId` | 傳回訪客的 tntID |
   |  | `profile.marketingCloudVisitorId` | 傳回訪客的 Experience Cloud 訪客 ID。 |
   |  | `profile.thirdPartyId` | 傳回訪客的第三方 ID。 |
   |  | `profile.categoryAffinity` | 傳回訪客最喜愛的類別。 |
   |  | `profile.categoryAffinities` | 以字串形式傳回訪客前 5 名類別的陣列。 |
   | 活動 | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | 目前活動的詳細資料。<br>請注意，優惠引數的值是在體驗層級上評估的。 |
   | 地理 | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | 請參閱[地理](/help/main/c-target/c-audiences/c-target-rules/geo.md)，以取得在活動中使用地理鎖定目標的詳細資訊。 |
   | 流量分配方法<br> （僅適用於[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]活動。） | `experience.trafficAllocationId` | 如果訪客從「控制」流量中收到體驗，則傳回0；如果訪客從「已鎖定目標」流量分佈中收到體驗，則傳回1。 |
   |  | `experience.trafficAllocationType` | 傳回「控制」或「已鎖定目標」。 |

   使用者輪廓屬性和客戶屬性也顯示在清單中。

   >[!NOTE]
   >
   >含特殊字元的參數不會顯示在清單中。僅支援英數字元和底線。

1. （條件式）若要使用設定檔引數做為回應Token，但引數尚未透過[!DNL Target]要求傳遞，因此，尚未載入[!DNL Target] UI，您可以使用[!UICONTROL Add Response Token]按鈕將設定檔新增至UI。

   按一下&#x200B;**[!UICONTROL Add Response Token]**，提供權杖名稱，然後按一下&#x200B;**[!UICONTROL Activate]**。

1. 建立活動。

## 接聽回應並讀取回應Token

您用來接聽[!DNL Target]回應和讀取回應Token的處理程式會因您是[!DNL Platform Web SDK]或at.js實作而異。

### 使用Handle物件類別的![Adobe Experience Platform Web SDK badge](/help/main/assets/platform.png) [!DNL Platform Web SDK] {#platform-web-sdk}

使用Handle物件類別（具有中繼資料物件與資料物件）來接聽[!DNL Target]回應並讀取回應Token。

下列回應範例直接將[!DNL Platform Web SDK]自訂事件處理常式新增至HTML頁面（表格說明程式碼中使用的物件）：

| 物件 | 資訊 |
| --- | --- |
| 型別 — Personalization.decision | 決定是由[!DNL Target]或Offer Decisioning提供者所做。 |
| DecisionProvider - TGT | TGT-[!DNL Target]。 [!DNL Target]提供回應Token中繼資料和值給頁面。 |
| 中繼 | 傳遞至頁面的中繼資料。 |
| 資料 | 傳遞給頁面的中繼資料值。 |

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

### 使用自訂事件的![at.js badge](/help/main/assets/atjs.png) at.js

使用[at.js自訂事件](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/atjs-custom-events.html?lang=zh-Hant){target=_blank}接聽[!DNL Target]回應並讀取回應Token。

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

## 回應Token FAQ {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**需要什麼角色才能啟動或停用回應 Token?**

回應權杖只能由具有[!DNL Target] [!UICONTROL Administrator]角色的使用者啟用或停用。

**如果我執行[!DNL Platform Web SDK] 2.6.0 （或更早版本）會發生什麼事？**

您無權存取回應Token。

**如果我執行at.js 1.0 （或更早版本）會發生什麼事？**

您會看到回應Token，但at.js無法使用。

**我可以同時啟用[!DNL Target Classic]外掛程式和回應Token嗎？**

外掛程式和回應Token可並行使用；不過，外掛程式未來將停止使用。

**回應Token是透過所有[!DNL Target]回應傳遞，還是僅透過傳遞活動的[!DNL Target]回應傳遞？**

回應Token僅能透過傳遞活動的[!DNL Target]個回應來傳遞。

**我的[!DNL Target Classic]外掛程式包含JavaScript。 如何使用回應 Token 來複寫其功能?**

移轉至回應Token時，此型別的JavaScript必須保留在程式碼基底或標籤管理解決方案中。 您可以使用[!DNL Platform Web SDK]或[!DNL at.js]自訂事件來觸發此程式碼，並將回應Token值傳遞至JavaScript函式。

**我的設定檔/客戶屬性參數為何沒有顯示在回應 Token 清單中?**

[!DNL Target]通常會每15分鐘重新整理一次引數。 此重新整理取決於使用者動作，而且只有在您檢視回應Token頁面時，才會重新整理資料。 如果您的引數未顯示在回應權杖清單中，[!DNL Target]尚未重新整理資料。

此外，如果您的引數包含非英數字元或底線以外的任何符號，則引數不會出現在清單中。 目前僅支援英數和底線字元。

**如果回應Token使用已刪除的設定檔指令碼或設定檔引數，仍會傳送內容嗎？**

回應 Token 會從使用者設定檔中擷取資訊，然後傳送該資訊。如果您刪除設定檔指令碼或參數，這不代表該資訊已從使用者設定檔中移除。使用者設定檔仍然具有與設定檔指令碼對應的資料。 回應Token會繼續傳遞內容。 對於沒有將該資訊儲存在其設定檔中的使用者，或新訪客，該Token不會傳遞，因為資料不存在於其設定檔中。

[!DNL Target]不會自動關閉權杖。 如果您刪除設定檔指令碼，且不想再傳送 Token，則必須自行關閉 Token。

**我已重新命名設定檔指令碼，但為何使用該指令碼的 Token 仍以舊名稱處於使用中狀態?**

如上所述，回應 Token 會處理使用者已儲存的設定檔資訊。即使您重新命名了個人資料指令碼，造訪過您網站的使用者仍會將舊的個人資料指令碼值儲存在其個人資料中。 代號會繼續挑選已儲存在使用者設定檔中的舊值。 如果您現在想要以新名稱來傳送內容，則必須關閉先前的 Token，並開啟新的 Token。

**如果我的屬性已變更，何時會從清單中移除這些屬性？**

[!DNL Target]會定期執行屬性重新整理。 任何未切換的屬性都會在下次重新整理時移除。 不過，如果您有已切換且已移除的屬性，該指令碼不會從屬性清單中移除，直到您將其切換為關閉為止。 例如，您移除用來做為Token的設定檔指令碼。 刪除或重新命名時，[!DNL Target]只會從清單中移除已切換的屬性。

## 傳送資料至Google Analytics

以下章節說明如何將[!DNL Target]資料傳送至Google Analytics 4。 回應Token傳送的資料也可傳送至其他第三方整合。

### ![AEP badge](/help/main/assets/platform.png)透過Platform Web SDK傳送資料至Google Analytics

在Google Analytics頁面中新增下列程式碼，可透過Platform Web SDK HTML 2.6.0版（或更新版本）傳送資料。

>[!NOTE]
>
>請確定回應Token金鑰值組位於`alloy("sendEvent"`物件下。

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
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
 
        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });
</script>
```

### ![at.js badge](/help/main/assets/atjs.png)透過at.js傳送資料給Google Analytics {#section_04AA830826D94D4EBEC741B7C4F86156}

在 HTML 頁面中新增下列程式碼，即可透過 at.js 將資料傳送至 Google Analytics:

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>

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

        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
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

以下小節提供除錯回應Token的相關資訊：

### ![at.js badge](/help/main/assets/atjs.png) Google Analytics與偵錯

下列程式碼可讓您使用Google Analytics進行偵錯：

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
  
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
  
      gtag('config', 'TAG_ID');
      gtag('event', 'action_name', {'eventCategory': 'target',
          'eventAction': experienceNames, 'eventLabel': activityNames
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

### 使用等同於ttMeta外掛程式進行偵錯

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

## ![at.js](/help/main/assets/atjs.png)訓練影片：回應Token和at.js自訂事件 {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

以下影片說明如何使用回應Token和at.js自訂事件，共用從[!DNL Target]到協力廠商系統的設定檔資訊。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL Administration]功能表UI （先前稱為[!UICONTROL Setup]）已經過重新設計，可提供改良的效能、縮短發布新功能所需的維護時間，並改善整個產品的使用者體驗。 下列影片中的資訊是正確的；不過，選項的位置稍有不同。
>
>影片中提到`option.name`和`option.id`，已分別以`offer.name`和`offer.id`取代。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
