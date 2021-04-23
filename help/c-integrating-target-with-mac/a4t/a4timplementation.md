---
keywords: A4T;Adobe Analytics;Analytics 型活動;Analytics 報表套裝;報表套裝;Analytics Target 整合;設定報表套裝
description: 請依照實施 [!DNL Target] (A4T) in your Adobe [!DNL Target] 和Adobe Analytics解決方案的Analytics所需的步驟進行。
title: 如何實作 [!DNL Target] (A4T)的Analytics?
feature: 目標分析 (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 30%

---

# [!DNL Target]實作的分析

將[!DNL Adobe Analytics]實作[!DNL Adobe Target](A4T)的報告來源時，需要幾個步驟。

## 實施步驟{#section_73961BAD5BB4430A95E073DE5C026277}

以下各節將說明將此整合部署至您網站所需的步驟。

## 步驟 1: 要求佈建給 Analytics 和 Target

將[!DNL Analytics]實作為[!DNL Target]的報告源後，必須為[!DNL Analytics]和[!DNL Target]預配。 [使用此表單請求布建](http://www.adobe.com/go/audiences)。

## 步驟 2: 設定使用者權限

必須先符合使用者帳戶需求，您才能在[!DNL Target]中建立以[!DNL Analytics]為基礎的活動。 請參閱[使用者權限需求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

## 步驟 3: 實作 Experience Cloud 訪客 ID 服務

訪客 ID 服務可讓您在 [!DNL Adobe Experience Cloud] 解決方案之間識別使用者。實作或移轉至Experience Cloud訪客ID的必要版本。 如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

請參閱&#x200B;*Experience Cloud訪客ID服務*&#x200B;檔案中的[實作Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html)Experience CloudID服務。

## 步驟4: 更新 AppMeasurement for JavaScript 或 s_code

實作或移轉至所需版本的appMeasurement.js。 如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

如需新實作，請參閱&#x200B;*Analytics實作指南*&#x200B;中的[JavaScript實作概觀](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html)。

如需移轉，請參閱&#x200B;*Analytics實施指南*&#x200B;中的[移轉至JavaScript適用的AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html)。

## 步驟5:下載並更新at.js

使用您的生產帳戶實作或移轉至所需版本的at.js。 不需要修改程式碼。

如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

## 步驟6:主機at.js

如果您先前已部署at.js，則可以用更新版本取代現有檔案。 如需詳細資訊，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的「實作需求」。

否則，此檔案可以與訪客 ID 服務和 AppMeasurement for JavaScript 檔案一起裝載。這些檔案必須裝載於您網站所有頁面皆能存取的 Web 伺服器上。下一個步驟需要用到這些檔案的路徑。

## 步驟7:所有網站頁面{#step7}上的參考at.js

在每個頁面的標籤中新增下列程式碼行，將at.js納入VisitorAPI.js下方：

at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js必須先於at.js載入。 如果您要更新現有的at.js或mbox.js檔案，請務必確認載入順序。

從實作的角度來看，[!DNL Target]和[!DNL Analytics]整合的預設設定是使用從頁面傳遞的SDID，自動將後端的[!DNL Target]和[!DNL Analytics]要求接合在一起。

您可以控制如何及何時將與[!DNL Target]相關的分析資料傳送至[!DNL Analytics]以利報告。 如果您不想選擇預設設定，讓[!DNL Target]和[!DNL Analytics]透過SDID自動接合分析資料，請透過&#x200B;**window.targetGlobalSettings**&#x200B;設定&#x200B;**analyticsLogging = client_side**。 注意: 任何 2.1 以下的版本均不支援此方法。

例如:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此設定具有全域效果，這表示at.js進行的每個呼叫都有&#x200B;**analyticsLogging:在[!DNL Target]請求中傳送的&quot;client_side&quot;**，並會針對每個請求傳回分析裝載。 設定此選項時，傳回的裝載格式如下：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然後，可透過[資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)將裝載轉送至Analytics。 對於「自動分配」和「自動目標」活動，您也必須轉發sessionId。 如需詳細資訊，請參閱&#x200B;*Adobe TargetSDK*&#x200B;指南中的[Analytics for Target(A4T)reporting](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

如果不需要全域設定，而更偏好隨選方法，請傳入&#x200B;**analyticsLogging:&quot;client_side&quot;**。 [](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)僅會傳回此呼叫的分析裝載，且[!DNL Target]後端不會將裝載轉送至[!DNL Analytics]。 依循此方法，每個at.js [!DNL Target]請求預設會傳回裝載，但只會在需要並指定時才傳回。

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

然後，可以通過[資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)將裝載轉發到[!DNL Analytics]。

## 步驟8: 驗證實作 {#step8}

更新 JavaScript 程式庫之後載入頁面，以確認 呼叫中的 `mboxMCSDID`[!DNL Target] 參數值符合 頁面檢視呼叫中的 `sdid`[!DNL Analytics] 參數值。

請務必確認這些值在「單頁應用程式」(SPA)中是否相符，因為呼叫的順序並不總是可預測。

**注意：**  A4T必須符合這些值才能正常運作。

## 步驟 9: (可選) 移除先前的整合程式碼

Adobe建議您移除先前的整合，以簡化實作，並消除系統間不一致的問題。 您可以移除您為舊版SC部署的任何程式碼至T&amp;T整合，包括`mboxLoadSCPlugin`。

## 步驟10: 啟用以 Analytics 作為 Target 的報表來源的選項

在[!DNL Target]中，按一下「管理」>「Visual Experience Composer」]**，然後選擇「Select per activity」（每活動）]**&#x200B;或「**[!UICONTROL Adobe Analytics」]**&#x200B;以啟用選項。**[!UICONTROL **[!UICONTROL 

* **[!UICONTROL 「為每個活動選取」可讓您在建立每個活動時選擇 或 。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL Adobe 會將 Analytics 設為您建立的所有活動的報表來源。]**[!DNL Analytics]
