---
keywords: A4T;Adobe Analytics；基於分析的活動；分析報告套件；報告套件；分析目標整合；配置報告套件；at.js;atjs;adobe體驗平台web sdk;aep web sdk；平台web sdk
description: 按照實施Analytics所需的步驟執行 [!DNL Target] (A4T)在您的Adobe [!DNL Target] 和Adobe Analytics解決方案。
title: 如何實施分析 [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: 3c64945eb1898457a9d6a3e7bbfa64420bf1250a
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 25%

---

# Analytics for[!DNL Target]實作

實施時需要幾個步驟 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。 進程因您是否使用 [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) 或者用at.js

## ![Adobe Experience PlatformWeb SDK徽章](/help/main/assets/platform.png) Adobe Experience PlatformWeb SDK實施步驟 {#platform}

以下各節介紹在計畫使用平台Web SDK時將此整合部署到站點所需的步驟：

### 步驟1:請求預配 [!DNL Analytics] 和 [!DNL Target]

在實施A4T之前，必須為 [!DNL Analytics] 和 [!DNL Target]。 [使用此表單請求設定](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES)。

### 步驟 2: 設定使用者權限

必須先滿足用戶帳戶要求，然後才能根據 [!DNL Analytics] 在 [!DNL Target]。 請參閱[使用者權限需求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 第3步：建立邊配置

使用 [!DNL Adobe Experience Platform] 使用邊配置工具。 配置 [[!DNL Analytics] and [!DNL Target] 邊緣配置設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html)。

### 第4步：安裝和配置平台Web SDK

開始交付 [!DNL Target] 經驗和應用 [!DNL Analytics] 為了跟蹤和分析， [安裝](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) 和 [配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) 網站頁上的平台Web SDK。

### 第5步：啟用使用A4T的選項

在 [!DNL Target] UI，按一下 **[!UICONTROL 管理]** > **[!UICONTROL 視覺體驗作曲家]**，然後選擇 **[!UICONTROL 按活動選擇]** 或 **[!UICONTROL Adobe Analytics]**。

* **[!UICONTROL 「為每個活動選取」可讓您在建立每個活動時選擇 或 。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL Adobe 會將 Analytics 設為您建立的所有活動的報表來源。]**[!DNL Analytics]

## ![at.js徽章](/help/main/assets/atjs.png) at.js實施的實施步驟{#section_73961BAD5BB4430A95E073DE5C026277}

如果計畫使用at.js，以下各節將介紹將此整合部署到站點所需的步驟：

### 步驟 1: 要求佈建給 Analytics 和 Target

實施後 [!DNL Analytics] 作為 [!DNL Target]，必須為 [!DNL Analytics] 和 [!DNL Target]。 [使用此表單請求設定](https://www.adobe.com/go/audiences_tw)。

### 步驟 2: 設定使用者權限

必須先滿足用戶帳戶要求，然後才能建立 [!DNL Analytics]基於的活動 [!DNL Target]。 請參閱[使用者權限需求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步驟 3: 實作 Experience Cloud 訪客 ID 服務

訪客 ID 服務可讓您在 [!DNL Adobe Experience Cloud] 解決方案之間識別使用者。實施或遷移到所需的Experience Cloud訪問者ID版本。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

請參閱 [實現目標Experience CloudID服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) 的 *Experience Cloud訪問者ID服務* 文檔。

### 步驟4: 更新 AppMeasurement for JavaScript 或 s_code

實施或遷移到所需的appMeasurement.js版本。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

有關新實施，請參見 [JavaScript實現概述](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) 的 *分析實施指南*。

有關遷移，請參見 [遷移到JavaScript的AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) 的 *分析實施指南*。

### 第5步：下載並更新at.js

使用生產帳戶實施或遷移到所需的at.js版本。 不需要修改程式碼。

如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

### 步驟6:主機at.js

如果以前部署了at.js，則可以用更新的版本替換現有檔案。 如需詳細資訊，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

否則，此檔案可以與訪客 ID 服務和 AppMeasurement for JavaScript 檔案一起裝載。這些檔案必須裝載於您網站所有頁面皆能存取的 Web 伺服器上。下一個步驟需要用到這些檔案的路徑。

### 第7步：所有網站頁上的at.js引用 {#step7}

在VisitorAPI.js下添加at.js，方法是在每頁的標籤中添加以下代碼行：

at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

必須在at.js之前載入VisitorAPI.js。 如果要更新現有的at.js檔案，請確保驗證載入順序。

預設設定 [!DNL Target] 和 [!DNL Analytics] 從實施的角度來說，整合是使用從頁面傳遞的SDID來縫合 [!DNL Target] 和 [!DNL Analytics] 自動將請求連在一起。

您可以控制如何和何時發送與 [!DNL Target] 至 [!DNL Analytics] 報告用途。 如果您不想選擇預設設定， [!DNL Target] 和 [!DNL Analytics] 通過SDID自動編輯分析資料，設定 **analyticsLogging = client_side** 通過 **window.targetGlobalSettings**。 注意: 任何 2.1 以下的版本均不支援此方法。

例如:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此設定具有全局效果，這意味著at.js發出的每個調用 **analyticsLogging:&quot;客戶端&quot;** 在 [!DNL Target] 請求，並為每個請求返回分析負載。 設定此選項時，返回的負載的格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然後，可通過 [資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)。 對於「自動分配」和「自動目標」活動，還必須轉發sessionId。 有關詳細資訊，請參見 [目標(A4T)報告分析](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/) 的 *Adobe TargetSDK* 的子菜單。

如果不需要全局設定，而更可取的是按需方法，請使用at.js函式 [getOffires()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/) 通過 **analyticsLogging:&quot;客戶端&quot;**。 僅為此呼叫返回分析負載，並且 [!DNL Target] 後端未將負載轉發到 [!DNL Analytics]。 通過採用這種方法，每個at.js [!DNL Target] 預設情況下，請求將返回負載，但只有在需要並指定時才返回。

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

然後，可以將負載轉發到 [!DNL Analytics] 通過 [資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)。

### 步驟8: 驗證實作 {#step8}

更新 JavaScript 程式庫之後載入頁面，以確認 呼叫中的 `mboxMCSDID`[!DNL Target] 參數值符合 頁面檢視呼叫中的 `sdid`[!DNL Analytics] 參數值。

確認這些值是否與單頁應用程式(SPA)中的調用順序並不總是可預測的值匹配尤為重要。

>[!NOTE]
>
>要使A4T正確運行，需要匹配這些值。

### 步驟 9: (可選) 移除先前的整合程式碼

Adobe建議您刪除以前的整合，以簡化實施，並消除對系統之間差異的排除。 您可以刪除為以前的SC到T&amp;T整合部署的任何代碼，包括 `mboxLoadSCPlugin`。

### 步驟10: 啟用以 Analytics 作為 Target 的報表來源的選項

在 [!DNL Target]按一下 **[!UICONTROL 「管理」>「視覺體驗作曲家」]** 選擇 **[!UICONTROL 按活動選擇]** 或 **[!UICONTROL Adobe Analytics]** 的子菜單。

* **[!UICONTROL 「為每個活動選取」可讓您在建立每個活動時選擇 或 。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL Adobe 會將 Analytics 設為您建立的所有活動的報表來源。]**[!DNL Analytics]


