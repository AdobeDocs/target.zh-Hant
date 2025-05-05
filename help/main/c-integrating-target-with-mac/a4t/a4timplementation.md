---
keywords: A4T；Adobe Analytics；Analytics型活動；Analytics報表套裝；報表套裝；Analytics Target整合；設定報表套裝；at.js；atjs；adobe experience platform web sdk；aep web sdk；platform web sdk
description: 請依照在您的Adobe [!DNL Target] 和Adobe Analytics解決方案中實作Analytics for [!DNL Target] (A4T)所需的步驟操作。
title: 如何為 [!DNL Target] (A4T)實作Analytics？
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 19%

---

# Analytics for [!DNL Target]實作

實作[!DNL Adobe Analytics]做為[!DNL Adobe Target] (A4T)的報告來源時，需要幾個步驟。 此程式會因您使用[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)或使用at.js實作A4T而有所不同。

## 適用於Adobe Experience Platform Web SDK實作的![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png)實作步驟 {#platform}

如果您打算使用Platform Web SDK，以下幾節將說明將此整合部署至您的網站所需的步驟：

### 步驟1：要求布建[!DNL Analytics]和[!DNL Target]

實作A4T之前，您必須先布建給[!DNL Analytics]和[!DNL Target]。 [使用此表單來要求布建帳戶](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y)。

### 步驟 2: 設定使用者權限

必須符合使用者帳戶需求，您才能在[!DNL Target]中根據[!DNL Analytics]建立活動。 請參閱[使用者權限需求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步驟3：建立Edge設定

使用[!DNL Adobe Experience Platform]使用邊緣組態工具建立Edge組態。 設定[建立和設定資料串流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant)。

### 步驟4：安裝和設定Platform Web SDK

若要開始傳遞[!DNL Target]體驗並套用[!DNL Analytics]以追蹤和分析，請在您的網站頁面上[安裝](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hant)和[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) Platform Web SDK。

### 步驟5：啟用使用A4T的選項

在[!DNL Target] UI中，按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**，然後選擇&#x200B;**[!UICONTROL Select per activity]**&#x200B;或&#x200B;**[!UICONTROL Adobe Analytics]**。

* 建立每個活動時，**[!UICONTROL Select per activity]**&#x200B;可讓您選擇[!DNL Target]與[!DNL Analytics]。
* **[!UICONTROL Adobe Analytics]**&#x200B;將[!DNL Analytics]設為您建立的所有活動的報表來源。

## ![at.js badge](/help/main/assets/atjs.png) at.js實作的實作步驟{#section_73961BAD5BB4430A95E073DE5C026277}

如果您打算使用at.js，以下幾節將說明將此整合部署至您的網站所需的步驟：

### 步驟 1: 要求佈建給 Analytics 和 Target

在您將[!DNL Analytics]實作為[!DNL Target]的報告來源之後，必須布建給[!DNL Analytics]和[!DNL Target]。 [使用此表單來要求布建帳戶](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}。

### 步驟 2: 設定使用者權限

必須符合使用者帳戶需求，您才能在[!DNL Target]中建立[!DNL Analytics]型活動。 請參閱[使用者權限需求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步驟 3: 實作 Experience Cloud 訪客 ID 服務

訪客ID服務可讓您識別[!DNL Adobe Experience Cloud]解決方案中的使用者。 實作或移轉至必要的Experience Cloud訪客ID版本。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

請參閱&#x200B;*Experience Cloud訪客ID服務*&#x200B;檔案中的[實作Experience Cloud的ID服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html?lang=zh-Hant)。

### 步驟4: 更新 AppMeasurement for JavaScript 或 s_code

實作或移轉至必要的appMeasurement.js版本。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

如需新的實作，請參閱&#x200B;*JavaScript實作指南*&#x200B;中的[Analytics實作概觀](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=zh-Hant)。

如需移轉，請參閱&#x200B;*Analytics實作指南*&#x200B;中的[移轉至JavaScript的AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html?lang=zh-Hant)。

### 步驟5：下載並更新at.js

使用您的生產帳戶實作或移轉至必要的at.js版本。 不需要修改程式碼。

如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

### 步驟6：託管at.js

如果您先前已部署at.js，則可以使用更新版本取代現有的檔案。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

否則，此檔案可以與訪客 ID 服務和 AppMeasurement for JavaScript 檔案一起裝載。這些檔案必須裝載於您網站所有頁面皆能存取的 Web 伺服器上。下一個步驟需要用到這些檔案的路徑。

### 步驟7：在所有網頁上參照at.js {#step7}

將at.js加到VisitorAPI.js之下，請在每個頁面的標籤中新增下列這行程式碼：

at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js必須在at.js之前載入。 如果您更新現有的at.js檔案，請務必驗證載入順序。

從實作觀點來看，[!DNL Target]與[!DNL Analytics]整合的預設設定是使用從頁面傳遞的SDID，在後端自動將[!DNL Target]和[!DNL Analytics]要求拼接在一起。

您可以控制如何及何時將與[!DNL Target]相關的分析資料傳送至[!DNL Analytics]以用於報表用途。 如果您不想選擇加入[!DNL Target]和[!DNL Analytics]透過SDID自動拼接分析資料的預設設定，請透過&#x200B;**window.targetGlobalSettings**&#x200B;設定&#x200B;**analyticsLogging = client_side**。 注意: 任何 2.1 以下的版本均不支援此方法。

例如:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此設定具有全域效果，也就是說，at.js發出的所有呼叫都會在[!DNL Target]要求中傳送&#x200B;**analyticsLogging： &quot;client_side&quot;**，而且會為所有要求傳回分析裝載。 設定此選項時，傳回的裝載格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

接著，裝載可透過[資料插入API](https://helpx.adobe.com/tw/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)轉送至Analytics。 針對「自動分配」和「自動鎖定目標」活動，您也必須轉送sessionId。 如需詳細資訊，請參閱&#x200B;*Adobe Target SDK*&#x200B;指南中的[Analytics for Target (A4T)報告](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=zh-Hant){target=_blank}。

如果不需要全域設定，且偏好使用更隨需提供的方法，請傳入&#x200B;**analyticsLogging： &quot;client_side&quot;**&#x200B;以使用at.js函式[getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html?lang=zh-Hant){target=_blank}。 只會針對此呼叫傳回分析裝載，且[!DNL Target]後端不會將裝載轉送至[!DNL Analytics]。 透過採用此方法，每個at.js [!DNL Target]要求都會依預設傳回裝載，但只有在需要和指定時才會傳回。

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

然後可透過[資料插入API](https://helpx.adobe.com/tw/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)將裝載轉送至[!DNL Analytics]。

### 步驟8: 驗證實作 {#step8}

更新JavaScript資料庫後載入您的頁面，以確認[!DNL Target]呼叫中的`mboxMCSDID`引數值符合[!DNL Analytics]頁面檢視呼叫中的`sdid`引數值。

尤其重要的是，確認這些值與單頁應用程式(SPA)中的值相符，因為此處的呼叫順序並不一定可預測。

>[!NOTE]
>
>A4T需要這些值的相符專案才能正常運作。

### 步驟 9: (可選) 移除先前的整合程式碼

Adobe建議您移除先前的整合，以簡化實作，也不必解決系統之間的差異。 您可以移除先前為了SC至T&amp;T整合而部署的任何程式碼，包括`mboxLoadSCPlugin`。

### 步驟10: 啟用以 Analytics 作為 Target 的報表來源的選項

在[!DNL Target]中，按一下&#x200B;**[!UICONTROL Administration > Reporting]**&#x200B;並選擇&#x200B;**[!UICONTROL Select per activity]**&#x200B;或&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;以啟用選項。

* 建立每個活動時，**[!UICONTROL Select per activity]**&#x200B;可讓您選擇[!DNL Target]與[!DNL Analytics]。
* **[!UICONTROL Adobe Analytics]**&#x200B;將[!DNL Analytics]設為您建立的所有活動的報表來源。


