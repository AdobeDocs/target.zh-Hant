---
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: 實作 Adobe Analytics 做為 Target (A4T) 的報表來源時，需要數個步驟。
title: Analytics for Target 實作
feature: a4t implementation
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: cafd4fc6c6b93f48afd4368fdf290730535ee0b2
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 50%

---


# Analytics for Target 實作{#analytics-for-target-implementation}

Several steps are required when implementing [!DNL Adobe Analytics] as the reporting source for [!DNL Target] (A4T).

## Implementation steps {#section_73961BAD5BB4430A95E073DE5C026277}

以下各節將說明將此整合部署至您網站所需的步驟。

## 步驟 1: 要求佈建給 Analytics 和 Target

After you implement [!DNL Analytics] as the reporting source for [!DNL Target], you must be provisioned for [!DNL Analytics] and [!DNL Target]. [使用此表單請求布建](http://www.adobe.com/go/audiences)。

## 步驟 2: 設定使用者權限

User account requirements must be met before you can create an [!DNL Analytics]-based activity in [!DNL Target]. 請參閱[使用者權限需求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

## 步驟 3: 實作 Experience Cloud 訪客 ID 服務

訪客 ID 服務可讓您在 [!DNL Adobe Experience Cloud] 解決方案之間識別使用者。您必須實作或移轉至必要的 Experience Cloud 訪客 ID 版本。如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

See [Implement the Experience Cloud ID Service for Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html) in the *Experience Cloud Visitor ID Service* documentation.

## 步驟4: 更新 AppMeasurement for JavaScript 或 s_code

您必須實作或移轉至必要的 appMeasurement.js 版本。如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

如需新實作，請參 [閱Analytics實施指南中的](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html)*JavaScript實施概觀*。

如需移轉，請參 [閱「Analytics實施指南」中的「移轉至JavaScript適](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) 用的AppMeasurement」 **。

## 步驟5:下載並更新at.js

您必須使用生產帳戶實作或移轉至所需版本的at.js。 不需要修改程式碼。

如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

## 步驟6:主機at.js

如果您先前已部署at.js，則可以用更新版本取代現有檔案。 如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

否則，此檔案可以與訪客 ID 服務和 AppMeasurement for JavaScript 檔案一起裝載。這些檔案必須裝載於您網站所有頁面皆能存取的 Web 伺服器上。下一個步驟需要用到這些檔案的路徑。

## Step 7: Reference at.js on all site pages {#step7}

在每個頁面的標籤中新增下列程式碼行，將at.js納入VisitorAPI.js下方：

at.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js必須先於at.js載入。如果您要更新現有的at.js或mbox.js檔案，請務必確認載入順序。

The way the out-of-the-box settings are configured for [!DNL Target] and [!DNL Analytics] integration from an implementation perspective is to use the SDID that is passed from the page to stitch the [!DNL Target] and [!DNL Analytics] request together on the backend automatically for you.

However, if you want more control on how and when to send analytics data related to [!DNL Target] to [!DNL Analytics] for reporting purposes, and you do not want to opt-in to the default settings of having [!DNL Target] and [!DNL Analytics] automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. 注意: 任何 2.1 以下的版本均不支援此方法。

例如:

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此設定具有全域效果，也就是說，at.js 發出的所有呼叫都會在 要求中傳送 **analyticsLogging: &quot;client_side&quot;**，而且會為所有要求傳回分析裝載。[!DNL Target]設定後，傳回的裝載格式如下所示:

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

The payload can then be forwarded to Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). 請注意，對於 [!UICONTROL Auto-Allocate] 和  Auto-Target活動，您也需要轉發sessionId。 如需詳細資訊，請 [參閱「Adobe Target SDK」指南中的](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)*Analytics for Target(A4T)報表* 。

如果不需要全域設定，且偏好使用更隨需提供的方法，則您可將 **analyticsLogging: &quot;client_side&quot;** 傳入，藉此使用 at.js 函數 [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) 來達成此目標。The analytics payload will be returned for only this call and the [!DNL Target] backend will not forward the payload to [!DNL Analytics]. By pursuing this approach, every at.js [!DNL Target] request will not return the payload by default, but instead only when desired and specified.

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

The payload can then be forwarded to [!DNL Analytics] via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## 步驟8: 驗證實作 {#step8}

更新 JavaScript 程式庫之後載入頁面，以確認 呼叫中的 `mboxMCSDID`[!DNL Target] 參數值符合 頁面檢視呼叫中的 `sdid`[!DNL Analytics] 參數值。

在單一頁面應用程式 (SPA) 中，不一定能夠預測呼叫訂單，所以這項確認尤其重要。

**注意:** 這些值必須相符，A4T 才能正常運作。

## 步驟 9: (可選) 移除先前的整合程式碼

建議移除先前的整合，以簡化實作，也不必解決系統之間的差異。您可以移除先前為了 SC 至 T&amp;T 整合而可能部署的任何程式碼，包括 `mboxLoadSCPlugin`。

## 步驟10: 啟用以 Analytics 作為 Target 的報表來源的選項

In [!DNL Target], click **[!UICONTROL Administation > Visual Experience Composer]** and choose either **[!UICONTROL Select per activity]** or **[!UICONTROL Adobe Analytics]** to enable the options.

* **[!UICONTROL 「為每個活動選取」可讓您在建立每個活動時選擇 或 。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL Adobe 會將 Analytics 設為您建立的所有活動的報表來源。]**[!DNL Analytics]

