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
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Analytics for Target 實作{#analytics-for-target-implementation}

實作 Adobe Analytics 做為 Target (A4T) 的報表來源時，需要數個步驟。

## 實施步驟 {#section_73961BAD5BB4430A95E073DE5C026277}

下表說明將此整合部署至網站所需的步驟。

## 步驟 1: 要求佈建給 Analytics 和 Target

將 Analytics 實作成 Target 的報表來源之後，您必須佈建給 Analytics 和 Target。[請使用此表單來布](http://www.adobe.com/go/audiences)建。

## 步驟 2: 設定使用者權限

必須符合使用者帳戶需求，您才能在 Adobe Target 中建立 Adobe Analytics 型活動。請參閱[使用者權限需求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

## 步驟 3: 實作 Experience Cloud 訪客 ID 服務

訪客 ID 服務可讓您在 Experience Cloud 解決方案之間識別使用者。您必須實作或移轉至必要的 Experience Cloud 訪客 ID 版本。如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

請參閱 Experience Cloud 訪客 ID 服務說明文件中的[實作 Experience Cloud ID Service for Target](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-target.html)。

## 步驟4: 更新 AppMeasurement for JavaScript 或 s_code

您必須實作或移轉至必要的 appMeasurement.js 版本。如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

若為新的實作，請參閱 [Analytics JavaScript 實作](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html)。

若為移轉，請參閱[移轉至 AppMeasurement for JavaScript](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=appmeasure_mjs_migrate)。

## 步驟 5: 下載並更新 at.js 或 mbox.js

您必須使用生產帳戶來實作或移轉至必要的 at.js 或 mbox.js 版本。不需要修改程式碼。

如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

## 步驟6: 託管 at.js 或 mbox. js

如果先前已部署 at.js 或 mbox. js，您可以用更新的版本取代現有的檔案。如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

否則，此檔案可以與訪客 ID 服務和 AppMeasurement for JavaScript 檔案一起裝載。這些檔案必須裝載於您網站所有頁面皆能存取的 Web 伺服器上。下一個步驟需要用到這些檔案的路徑。

## 步驟 7: 在所有網頁上參照 at.js 或 mbox.js {#step7}

在每個頁面上的標籤中新增下列程式碼行，在VisitorAPI. js下方包含at. js或mbox. js：

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

VisitorAPI. js在at. js或mbox. js之前是很重要的。如果您要更新現有at. js或mbox. js檔案，請確定您確認載入順序。

從實施觀點設定Target與Analytics整合的預設設定是使用從頁面傳遞的SDID，將Target與Analytics請求自動整合在後端。

However, if you want more control on how and when to send analytics data related to Target to Analytics for reporting purposes, and you do not want to opt-in to the default settings of having Target and Analytics automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. 注意：2.1以下的任何版本不支援此方法。

例如:

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

This set up has a global effect, which means that every call made by at.js will have **analyticsLogging: "client_side"** sent within the Target requests and an analytics payload will be returned for every request. 設定此項目時，傳回的裝載格式如下所示：

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

The payload can then be forwarded to Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

If a global setting is not desired and a more on-demand approach is preferable, then you can use the at.js function [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) to achieve this by passing in **analyticsLogging: "client_side"**. 只有此呼叫才會傳回分析裝載，而Target後端則不會轉送付費至Analytics。透過採用此方法，每個at. js Target請求都不會預設傳回負載，但只有在需要和指定時才會傳回。

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

此呼叫會叫用您可以擷取分析裝載的回應。

回應看起來如下所示：

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

