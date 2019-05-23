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
source-git-commit: 1be00210754e8fa3237fdbccf48af625c2aafe65

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

## 步驟 7: 在所有網頁上參照 at.js 或 mbox.js

將 at.js 或 mbox.js 加到 VisitorAPI.js 之下，請在每個頁面的 <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 標籤中新增下列這行程式碼:

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

VisitorAPI.js 必須在 at.js 或 mbox.js 之前載入，如果您更新現有的 at.js 或 mbox.js 檔案，務必驗證載入順序。

## 步驟8: 驗證實作

更新 JavaScript 程式庫之後載入頁面，以確認 Target 呼叫中的 mboxMCSDID 參數值符合 Analytics 頁面檢視呼叫中的 sdid 參數值。

在單一頁面應用程式 (SPA) 中，不一定能夠預測呼叫訂單，所以這項確認尤其重要。

**注意:** 這些值必須相符，A4T 才能正常運作。

## 步驟 9: (可選) 移除先前的整合程式碼

建議移除先前的整合，以簡化實作，也不必解決系統之間的差異。您可以移除先前為了 SC 至 T&amp;T 整合而可能部署的任何程式碼，包括 `mboxLoadSCPlugin`。

## 步驟10: 啟用以 Analytics 作為 Target 的報表來源的選項

在 Target 中，按一下[!UICONTROL 「設定」 &gt; 「偏好設定」]，然後選擇[!UICONTROL 「為每個活動選取」]或 [!UICONTROL Adobe Analytics] 以啟用選項。

* 「為每個活動選取」可讓您在建立每個活動時選擇 Target 或 Analytics。
* Adobe Analytics 會將 Analytics 設為您建立的所有活動的報表來源。

