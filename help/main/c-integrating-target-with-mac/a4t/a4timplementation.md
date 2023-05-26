---
keywords: A4T；Adobe Analytics；Analytics型活動；Analytics報表套裝；報表套裝；Analytics Target整合；設定報表套裝；at.js；atjs；adobe experience platform web sdk；aep web sdk；平台web sdk
description: 請依照為實作Analytics所需的步驟操作 [!DNL Target] (A4T)在您的Adobe中 [!DNL Target] 和Adobe Analytics解決方案。
title: 如何實作Analytics for [!DNL Target] (A4T)？
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 26%

---

# Analytics for[!DNL Target]實作

實作時需要執行數個步驟 [!DNL Adobe Analytics] 作為的報表來源 [!DNL Adobe Target] (A4T)。 此程式會因您是否要使用實作A4T [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) 或使用at.js。

## ![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png) Adobe Experience Platform Web SDK實作的實作步驟 {#platform}

如果您打算使用Platform Web SDK，以下幾節將說明將此整合部署至您的網站所需的步驟：

### 步驟1：請求布建 [!DNL Analytics] 和 [!DNL Target]

實作A4T之前，您必須先布建給 [!DNL Analytics] 和 [!DNL Target]. [使用此表單來要求布建帳戶](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### 步驟 2: 設定使用者權限

必須符合使用者帳戶需求，您才能根據以下專案建立活動： [!DNL Analytics] 在 [!DNL Target]. 請參閱[使用者權限需求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步驟3：建立邊緣組態

建立Edge組態，使用 [!DNL Adobe Experience Platform] 使用「邊緣組態」工具。 設定 [[!DNL Analytics] and [!DNL Target] 邊緣組態設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### 步驟4：安裝和設定Platform Web SDK

開始傳遞 [!DNL Target] 體驗與套用 [!DNL Analytics] 基於追蹤和分析目的， [安裝](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) 和 [設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) 網站頁面上的Platform Web SDK。

### 步驟5：啟用使用A4T的選項

在 [!DNL Target] UI，按一下 **[!UICONTROL 管理]** > **[!UICONTROL 視覺化體驗撰寫器]**，然後選擇以下任一選項 **[!UICONTROL 為每個活動選取]** 或 **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL 「為每個活動選取」可讓您在建立每個活動時選擇 或 。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL Adobe 會將 Analytics 設為您建立的所有活動的報表來源。]**[!DNL Analytics]

## ![at.js徽章](/help/main/assets/atjs.png) at.js實作的實作步驟{#section_73961BAD5BB4430A95E073DE5C026277}

如果您打算使用at.js，以下幾節將說明將此整合部署至您的網站所需的步驟：

### 步驟 1: 要求佈建給 Analytics 和 Target

實作之後 [!DNL Analytics] 作為的報表來源 [!DNL Target]，您必須布建給 [!DNL Analytics] 和 [!DNL Target]. [使用此表單來要求布建帳戶](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### 步驟 2: 設定使用者權限

您必須符合使用者帳戶需求，才能建立 [!DNL Analytics]中的活動 [!DNL Target]. 請參閱[使用者權限需求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步驟 3: 實作 Experience Cloud 訪客 ID 服務

訪客 ID 服務可讓您在 [!DNL Adobe Experience Cloud] 解決方案之間識別使用者。實作或移轉至必要的Experience Cloud訪客ID版本。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

另請參閱 [實作目標的Experience CloudID服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) 在 *Experience Cloud訪客ID服務* 說明檔案。

### 步驟4: 更新 AppMeasurement for JavaScript 或 s_code

實作或移轉至必要的appMeasurement.js版本。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

如需新的實作，請參閱 [JavaScript實施概觀](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) 在 *Analytics實作指南*.

如需移轉，請參閱 [移轉至JavaScript適用的AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) 在 *Analytics實作指南*.

### 步驟5：下載並更新at.js

使用您的生產帳戶實作或移轉至必要的at.js版本。 不需要修改程式碼。

如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

### 步驟6：託管at.js

如果您先前已部署at.js，則可以使用更新版本取代現有檔案。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

否則，此檔案可以與訪客 ID 服務和 AppMeasurement for JavaScript 檔案一起裝載。這些檔案必須裝載於您網站所有頁面皆能存取的 Web 伺服器上。下一個步驟需要用到這些檔案的路徑。

### 步驟7：在所有網站頁面上參照at.js {#step7}

將at.js加到VisitorAPI.js之下，請在每個頁面的標籤中新增下列程式碼行：

at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

必須先載入VisitorAPI.js，才能載入at.js。 如果您要更新現有的at.js檔案，請務必驗證載入順序。

的預設設定 [!DNL Target] 和 [!DNL Analytics] 整合從實作角度來看，就是使用從頁面傳遞的SDID來拼接 [!DNL Target] 和 [!DNL Analytics] 自動在後端一起請求。

您可以控制如何及何時傳送與相關的分析資料 [!DNL Target] 至 [!DNL Analytics] 以供製作報表之用。 如果您不想選擇加入的預設設定為 [!DNL Target] 和 [!DNL Analytics] 透過SDID、設定自動彙整分析資料 **analyticsLogging = client_side** 透過 **window.targetGlobalSettings**. 注意: 任何 2.1 以下的版本均不支援此方法。

例如:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此設定具有全域效果，這表示由at.js進行的每個呼叫都具有 **analyticsLogging： &quot;client_side&quot;** 傳送於 [!DNL Target] 會針對每個請求傳回請求和分析裝載。 設定此選項時，傳回的裝載格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

接著，裝載可透過 [資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). 針對「自動分配」和「自動鎖定目標」活動，您也必須轉送sessionId。 如需詳細資訊，請參閱 [Analytics for Target (A4T)報表](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} 在 *ADOBE TARGET SDK* 指南。

如果不需要全域設定，且偏好使用更隨需提供的方法，請使用at.js函式 [getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html){target=_blank} 透過傳入 **analyticsLogging： &quot;client_side&quot;**. 只會針對此呼叫傳回分析裝載，且 [!DNL Target] 後端未將裝載轉送到 [!DNL Analytics]. 透過採取此方法，每個at.js [!DNL Target] request預設會傳回裝載，但只有在需要和指定時才會傳回。

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

然後，可將裝載轉送至 [!DNL Analytics] 透過 [資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### 步驟8: 驗證實作 {#step8}

更新 JavaScript 程式庫之後載入頁面，以確認 呼叫中的 `mboxMCSDID`[!DNL Target] 參數值符合 頁面檢視呼叫中的 `sdid`[!DNL Analytics] 參數值。

確認這些值與單頁應用程式(SPA)中的值相符尤為重要，因為後者的呼叫順序並不一定可預測。

>[!NOTE]
>
>A4T需要這些值的相符專案才能正常運作。

### 步驟 9: (可選) 移除先前的整合程式碼

Adobe建議您移除先前的整合，以簡化實作，也不必解決系統之間的差異。 您可以移除先前為了SC至T&amp;T整合而部署的任何程式碼，包括 `mboxLoadSCPlugin`.

### 步驟10: 啟用以 Analytics 作為 Target 的報表來源的選項

在 [!DNL Target]，按一下 **[!UICONTROL 管理>報表]** 並選擇 **[!UICONTROL 為每個活動選取]** 或 **[!UICONTROL Adobe Analytics]** 以啟用選項。

* **[!UICONTROL 「為每個活動選取」可讓您在建立每個活動時選擇 或 。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL Adobe 會將 Analytics 設為您建立的所有活動的報表來源。]**[!DNL Analytics]


