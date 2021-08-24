---
keywords: A4T;Adobe Analytics;Analytics型活動；Analytics報表套裝；報表套裝；Analytics Target整合；設定報表套裝；at.js;atjs;adobe experience platform web sdk;aep web sdk；平台web sdk
description: 請依照為 [!DNL Target] (A4T) in your Adobe [!DNL Target] 和Adobe Analytics解決方案實作Analytics所需的步驟操作。
title: 如何為 [!DNL Target] (A4T)實作Analytics?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '1142'
ht-degree: 25%

---

# Analytics for[!DNL Target]實施

實作[!DNL Adobe Analytics]作為[!DNL Adobe Target](A4T)的報表來源時，需要執行數個步驟。 程式會依您使用[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)實作A4T或使用at.js而有所不同。

## ![Adobe Experience Platform Web SDK徽](/help/assets/platform.png) 章Adobe Experience Platform Web SDK實作的實作步驟 {#platform}

如果您打算使用Platform Web SDK，以下章節說明將此整合部署至您的網站所需的步驟：

### 步驟1:請求為[!DNL Analytics]和[!DNL Target]進行布建

實作A4T之前，您必須先布建[!DNL Analytics]和[!DNL Target]。 [使用此表單來請求布建](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES)。

### 步驟 2: 設定使用者權限

必須符合使用者帳戶需求，才能根據[!DNL Target]中的[!DNL Analytics]建立活動。 請參閱[使用者權限需求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步驟3:建立Edge設定

使用[!DNL Adobe Experience Platform]使用邊配置工具建立邊配置。 配置[[!DNL Analytics] and [!DNL Target] 邊緣配置設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html)。

### 步驟4:安裝及配置Platform Web SDK

若要開始傳送[!DNL Target]體驗並套用[!DNL Analytics]以用於追蹤和分析用途，請在您的網頁上[安裝](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)和[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html)Platform Web SDK。

### 步驟5:啟用使用A4T的選項

在[!DNL Target] UI中，按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL 可視化體驗撰寫器]**，然後選擇&#x200B;**[!UICONTROL Select per activity]**&#x200B;或&#x200B;**[!UICONTROL Adobe Analytics]**。

* **[!UICONTROL 「為每個活動選取」可讓您在建立每個活動時選擇 或 。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL Adobe 會將 Analytics 設為您建立的所有活動的報表來源。]**[!DNL Analytics]

## ![at.js](/help/assets/atjs.png) 徽章at.js實作的實作步驟{#section_73961BAD5BB4430A95E073DE5C026277}

如果您打算使用at.js，以下小節將此整合部署至您的網站所需的步驟說明：

### 步驟 1: 要求佈建給 Analytics 和 Target

將[!DNL Analytics]實作為[!DNL Target]的報表來源後，必須為[!DNL Analytics]和[!DNL Target]布建。 [使用此表單來請求布建](https://www.adobe.com/go/audiences_tw)。

### 步驟 2: 設定使用者權限

必須先滿足用戶帳戶要求，然後才能在[!DNL Target]中建立基於[!DNL Analytics]的活動。 請參閱[使用者權限需求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步驟 3: 實作 Experience Cloud 訪客 ID 服務

訪客 ID 服務可讓您在 [!DNL Adobe Experience Cloud] 解決方案之間識別使用者。實作或移轉至必要的Experience Cloud訪客ID版本。 如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

請參閱&#x200B;*Experience Cloud訪客ID服務*&#x200B;檔案中的[實作Target的Experience CloudID服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html)。

### 步驟4: 更新 AppMeasurement for JavaScript 或 s_code

實作或移轉至必要的appMeasurement.js版本。 如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

若為新實作，請參閱&#x200B;*Analytics實作指南*&#x200B;中的[JavaScript實作概述](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html)。

如需移轉，請參閱&#x200B;*Analytics實作指南*&#x200B;中的[移轉至JavaScript適用的AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html)。

### 步驟5:下載和更新at.js

使用您的生產帳戶實作或移轉至必要的at.js版本。 不需要修改程式碼。

如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

### 步驟6:托管at.js

如果您先前已部署at.js，則可以以用更新的版本取代現有的檔案。 如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

否則，此檔案可以與訪客 ID 服務和 AppMeasurement for JavaScript 檔案一起裝載。這些檔案必須裝載於您網站所有頁面皆能存取的 Web 伺服器上。下一個步驟需要用到這些檔案的路徑。

### 步驟7:在所有網頁上參考at.js {#step7}

在每一頁的標籤中新增下列程式碼行，將at.js加到VisitorAPI.js下方：

at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js必須在at.js之前載入。 如果您更新現有的at.js檔案，請務必驗證載入順序。

從實作觀點來看，[!DNL Target]和[!DNL Analytics]整合的預設設定是使用從頁面傳遞的SDID，自動將[!DNL Target]和[!DNL Analytics]要求拼接在後端上。

您可以控制將[!DNL Target]相關分析資料傳送至[!DNL Analytics]以用於報表用途的方式和時機。 如果您不想選擇加入讓[!DNL Target]和[!DNL Analytics]透過SDID自動拼接分析資料的預設設定，請透過&#x200B;**window.targetGlobalSettings**&#x200B;設定&#x200B;**analyticsLogging = client_side**。 注意: 任何 2.1 以下的版本均不支援此方法。

例如:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此設定具有全域效果，這表示at.js發出的每個呼叫都有&#x200B;**analyticsLogging:在[!DNL Target]要求內傳送的&quot;client_side&quot;**，並會針對每個要求傳回分析裝載。 設定此選項時，傳回的裝載格式如下：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

接著，裝載可透過[資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)轉送至Analytics。 對於自動分配和自動鎖定目標活動，您也必須轉送sessionId。 如需詳細資訊，請參閱&#x200B;*Adobe Target SDK*&#x200B;指南中的[Analytics for Target(A4T)報表](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

如果不需要全域設定，且偏好使用更隨需提供的方法，請將&#x200B;**analyticsLogging傳入，以使用at.js函式[getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md):&quot;client_side&quot;**。 系統只會針對此呼叫傳回分析裝載，且[!DNL Target]後端不會將裝載轉送至[!DNL Analytics]。 透過採用此方法，每個at.js [!DNL Target]要求預設會傳回裝載，但只會在需要和指定時傳回。

例如:

```javascript
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

```javascript
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

接著，裝載可透過[資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)轉送至[!DNL Analytics]。

### 步驟8: 驗證實作 {#step8}

更新 JavaScript 程式庫之後載入頁面，以確認 呼叫中的 `mboxMCSDID`[!DNL Target] 參數值符合 頁面檢視呼叫中的 `sdid`[!DNL Analytics] 參數值。

請務必確認這些值在單頁應用程式(SPA)中是否相符，因為其中的呼叫順序不一定可預測。

>[!NOTE]
>
>A4T必須有這些值的比對才能正常運作。

### 步驟 9: (可選) 移除先前的整合程式碼

Adobe建議您移除先前的整合，以簡化實作，並消除系統間差異的必要性。 您可以移除先前為SC至T&amp;T整合而部署的任何程式碼，包括`mboxLoadSCPlugin`。

### 步驟10: 啟用以 Analytics 作為 Target 的報表來源的選項

在[!DNL Target]中，按一下「**[!UICONTROL 管理>可視化體驗撰寫器]**」，然後選擇「為每個活動&#x200B;]**選取」或「**[!UICONTROL  Adobe Analytics ]**」以啟用選項。**[!UICONTROL 

* **[!UICONTROL 「為每個活動選取」可讓您在建立每個活動時選擇 或 。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL Adobe 會將 Analytics 設為您建立的所有活動的報表來源。]**[!DNL Analytics]


