---
description: 實作 Adobe Analytics 做為 Target (A4T) 的報表來源時，需要數個步驟。
keywords: A4T;Adobe Analytics;Analytics 型活動;Analytics 報表套裝;報表套裝;Analytics Target 整合;設定報表套裝
seo-description: 實作 Adobe Analytics 做為 Target (A4T) 的報表來源時，需要數個步驟。
seo-title: Analytics for Target 實作
solution: Target
title: Analytics for Target 實作
topic: Premium
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Analytics for Target 實作{#analytics-for-target-implementation}

實作 Adobe Analytics 做為 Target (A4T) 的報表來源時，需要數個步驟。

## 實施步驟 {#section_73961BAD5BB4430A95E073DE5C026277}

下表說明將此整合部署至網站所需的步驟。

## 步驟 1: 要求佈建給 Analytics 和 Target

將 Analytics 實作成 Target 的報表來源之後，您必須佈建給 Analytics 和 Target。[使用此表單請求布建](http://www.adobe.com/go/audiences)。

## 步驟 2: 設定使用者權限

必須符合使用者帳戶需求，您才能在 Adobe Target 中建立 Adobe Analytics 型活動。請參閱[使用者權限需求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

## 步驟 3: 實作 Experience Cloud 訪客 ID 服務

訪客 ID 服務可讓您在 Experience Cloud 解決方案之間識別使用者。您必須實作或移轉至必要的 Experience Cloud 訪客 ID 版本。如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

請參閱 Experience Cloud 訪客 ID 服務說明文件中的[實作 Experience Cloud ID Service for Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html)。

## 步驟4: 更新 AppMeasurement for JavaScript 或 s_code

您必須實作或移轉至必要的 appMeasurement.js 版本。如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

如需新實作，請參 [閱Analytics實施指南中的](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html)*JavaScript實施概觀*。

如需移轉，請參 [閱「Analytics實施指南」中的「移轉至JavaScript適](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) 用的AppMeasurement」 **。

## 步驟 5: 下載並更新 at.js 或 mbox.js

您必須使用生產帳戶來實作或移轉至必要的 at.js 或 mbox.js 版本。不需要修改程式碼。

如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

## 步驟6: 託管 at.js 或 mbox. js

如果先前已部署 at.js 或 mbox. js，您可以用更新的版本取代現有的檔案。如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

否則，此檔案可以與訪客 ID 服務和 AppMeasurement for JavaScript 檔案一起裝載。這些檔案必須裝載於您網站所有頁面皆能存取的 Web 伺服器上。下一個步驟需要用到這些檔案的路徑。

## 步驟 7: 在所有網頁上參照 at.js 或 mbox.js {#step7}

將 at.js 或 mbox.js 加到 VisitorAPI.js 之下，請在每個頁面的標記中新增下列這行程式碼:

at.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

mbox.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

VisitorAPI.js 必須在 at.js 或 mbox.js 之前載入。如果您更新現有的 at.js 或 mbox.js 檔案，務必驗證載入順序。

針對 Target 設定立即可用設定的方法以及就實施觀點而言的 Analytics 整合，就是使用頁面所傳遞的 SDID，自動將 Target 和 Analytics 要求一起拼接在後端上。

不過，如果您想要進一步掌控將 Target 相關分析資料傳送至 Analytics 以用於報表用途的方式和時間，而且您不想選擇加入讓 Target 和 Analytics 透過 SDID 自動拼接分析資料的預設設定，則您可透過 **window.targetGlobalSettings** 設定 **analyticsLogging = client_side**。注意: 任何 2.1 以下的版本均不支援此方法。

例如:

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此設定具有全域效果，也就是說，at.js 發出的所有呼叫都會在 Target 要求中傳送 **analyticsLogging: "client_side"**，而且會為所有要求傳回分析裝載。設定後，傳回的裝載格式如下所示:

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

The payload can then be forwarded to Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

如果不需要全域設定，且偏好使用更隨需提供的方法，則您可將 **analyticsLogging: "client_side"** 傳入，藉此使用 at.js 函數 [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) 來達成此目標。只會針對此呼叫傳回分析裝載，且 Target 後端不會將裝載轉送至 Analytics。透過採用此方法，所有 at.js Target 要求都不會根據預設傳回裝載，而是只會在需要和指定時傳回。

例如:

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

此呼叫會叫用回應，您可從中擷取分析裝載。

回應如下所示:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

The payload can then be forwarded to Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## 步驟8: 驗證實作 {#step8}

更新 JavaScript 程式庫之後載入頁面，以確認 Target 呼叫中的 mboxMCSDID 參數值符合 Analytics 頁面檢視呼叫中的 sdid 參數值。

在單一頁面應用程式 (SPA) 中，不一定能夠預測呼叫訂單，所以這項確認尤其重要。

**注意:** 這些值必須相符，A4T 才能正常運作。

## 步驟 9: (可選) 移除先前的整合程式碼

建議移除先前的整合，以簡化實作，也不必解決系統之間的差異。您可以移除先前為了 SC 至 T&amp;T 整合而可能部署的任何程式碼，包括 `mboxLoadSCPlugin`。

## 步驟10: 啟用以 Analytics 作為 Target 的報表來源的選項

在 Target 中，按一下[!UICONTROL 「設定」 &gt; 「偏好設定」]，然後選擇[!UICONTROL 「為每個活動選取」]或 [!UICONTROL Adobe Analytics] 以啟用選項。

* 「為每個活動選取」可讓您在建立每個活動時選擇 Target 或 Analytics。
* Adobe Analytics 會將 Analytics 設為您建立的所有活動的報表來源。

