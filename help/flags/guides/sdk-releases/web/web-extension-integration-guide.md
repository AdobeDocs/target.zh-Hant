---
title: Web整合指南的旗標擴充功能
description: 瞭解如何將Flags擴充功能與適用於網頁應用程式的Adobe Experience Platform Web SDK (Alloy)整合。
hide: true
source-git-commit: 9c6f2b72f964b06da51e1f3655545147d7240a93
workflow-type: tm+mt
source-wordcount: '1180'
ht-degree: 7%

---

# 標示網頁的副檔名 {#web-extension-integration-guide}

本指南說明如何將Flags擴充功能與適用於網頁應用程式的Adobe Experience Platform Web SDK (Alloy)整合。 Flags擴充功能可為Web體驗啟用功能標幟管理和控制的轉出。

## 先決條件 {#prerequisites}

在實作Flags擴充功能之前，請確定您擁有：

* 在[Adobe Experience Platform資料彙集](https://experience.adobe.com/#/data-collection)中設定的Web屬性
* 已安裝Adobe Experience Platform Web SDK擴充功能
* Adobe Experience Cloud組織ID
* 存取組織中的旗標

### 必要權限 {#required-permissions}

確定您擁有下列屬性權利：

* 開發
* 管理擴充功能

## 擴充功能相依性 {#extension-dependencies}

Flags擴充功能需要下列Adobe Experience Platform擴充功能：

| 延伸 | 說明 | 必要 |
|---|---|---|
| Adobe Experience Platform Web SDK | 提供核心功能，包括Edge Network通訊和身分管理 | 是 |

在安裝Flags擴充功能之前，請確認此擴充功能已安裝在您的資料收集Web屬性中。

## 在資料收集中設定標幟副檔名 {#configure}

### 安裝擴充功能 {#install-extension}

1. 使用您的Adobe ID憑證登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至&#x200B;**資料彙集** > **標籤**。
1. 選取所需的標籤屬性。
1. 瀏覽至&#x200B;**擴充功能** > **目錄**。
1. 搜尋&#x200B;**旗標**&#x200B;並選取擴充功能卡。
1. 選取&#x200B;**安裝**。

### 設定擴充功能設定 {#configure-settings}

安裝Flags擴充功能時，您會前往設定頁面。 完成下列設定:

| 設定 | 說明 | 必要 |
|---|---|---|
| 用戶端 ID | 旗標中應用程式的唯一識別碼。 | 是 |

### 儲存並發佈 {#save-publish}

1. 選取&#x200B;**儲存**&#x200B;以儲存您的擴充功能組態。
1. 依照發佈流程部署您的變更：
   1. 將擴充功能新增至程式庫。
   1. 建置到您的開發環境。
   1. 使用Adobe Experience Platform Debugger進行驗證。
   1. 提升至測試與生產。

## 將Tags內嵌程式碼新增至您的網站 {#embed-code}

發佈標籤程式庫後，您必須將內嵌程式碼新增至您的網站。 內嵌程式碼是`<script>`標籤，可載入Tags程式庫和所有已設定的擴充功能，包括Flags擴充功能。

### 複製內嵌程式碼 {#copy-embed-code}

1. 在資料收集中，導覽至您的Web屬性。
1. 在左側導覽中選取&#x200B;**環境**。
1. 在您的目標環境（開發、測試或生產）的列中，選取&#x200B;**安裝**&#x200B;欄下的方塊圖示。
1. 在&#x200B;**網頁安裝指示**&#x200B;對話方塊中，標籤預設為非同步內嵌程式碼。
1. 選取「**複製**」圖示，將內嵌程式碼複製到剪貼簿。
1. 選取&#x200B;**關閉**&#x200B;以關閉強制回應視窗。

>[!NOTE]
>
>每個環境都有唯一的內嵌程式碼URL。 如需詳細資訊，請參閱環境。

### 實作內嵌程式碼 {#implement-embed-code}

在HTML頁面的`<head>`元素中新增內嵌程式碼。 內嵌程式碼應放置在依賴Tags程式庫的其他指令碼之前：

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>

  <!-- Adobe Experience Platform Tags embed code -->
  <script src="https://assets.adobedtm.com/yourcompany/your-property/launchENxxxxxxxxxxx.min.js" async></script>
</head>
<body>
  <!-- Your page content -->
</body>
</html>
```

>[!NOTE]
>
>將`src` URL取代為您的環境頁面中的實際內嵌程式碼。 URL包含您的公司識別碼、屬性識別碼和環境識別碼（例如，`launch-EN123456789abcdef.min.js`）。

### 使用標籤元件評估標幟 {#tags-components}

Flags擴充功能提供標籤原生評估介面。

| 元件 | 類型 | 說明 |
|---|---|---|
| 功能已啟用 | 條件 | 傳回是否為目前的使用者/內容啟用功能 |
| 功能標幟 | 資料元素 | 傳回布林值或完整功能物件 |

## 初始化SDK {#initialize-sdk}

載入標籤程式庫時，標籤擴充功能會自動初始化。 此擴充功能會在以下位置公開使用者端：

```javascript
window._flagClient
```

### 等待使用者端整備 {#client-readiness}

標籤會以非同步方式載入。 從自訂程式碼呼叫SDK方法之前，請等候使用者端初始化：

```javascript
window.flagClientReady
  .then(function () {
    const enabled = window._flagClient.isFeatureEnabled('my-feature', context);
    // Use enabled to select the feature or fallback behavior.
  })
  .catch(function (error) {
    console.error('Flags initialization failed:', error);
  });
```

## 評估內容 {#evaluation-context}

`FeatureEvaluationContext`包含身分（評估、A/B分組和分析所需）和選用的目標定位屬性（用於規則比對）。

| 屬性 | 必要 | 說明 |
|---|---|---|
| `identityNamespace` | 是 | 身分名稱空間（請參閱[Adobe身分名稱空間](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/namespaces)）。 通用值： `ECID`、`Email`、`CRMId`。 |
| `identityId` | 是 | 目前使用者的身分值。 |
| `attributes` | 否 | `Record<string, string[]>`. 索引鍵是旗標規則所使用的內容屬性名稱（例如`locale`、`platform`）。 值是該索引鍵的候選屬性值清單。 |

在Tags元件中，於條件或資料元素UI中設定身分預設值。 當第二個引數為一般屬性對應時，Feature Flag資料元素也會透過`getVar(name, attributes)`接受執行階段屬性。

### 使用情況 {#usage}

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: 'your-visitor-ecid',
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};
```

## API 參考資料 {#api-reference}

### isFeatureEnable {#is-feature-enabled}

`isFeatureEnabled`會傳回指定內容的旗標功能是開啟還是關閉。 傳遞`featureKey`和`FeatureEvaluationContext`。 請參閱[評估內容](#evaluation-context)。 使用&#x200B;**功能已啟用**&#x200B;標籤條件，或在初始化後從自訂程式碼呼叫`window._flagClient.isFeatureEnabled(...)`。

**簽章**

```javascript
isFeatureEnabled(featureKey: string, context: FeatureEvaluationContext): boolean
```

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | string | 要在旗標中評估的功能索引鍵 |
| `context` | FeatureEvaluationContext | 身分（必要）和選用的目標定位屬性。 請參閱[評估內容](#evaluation-context)。 |

### 建立功能標幟資料元素 {#create-data-element}

當您在規則或自訂程式碼中需要可用為`%Data Element Name%`的旗標值時，請使用資料元素。

**步驟**

1. 在您的屬性中，移至&#x200B;**資料元素**&#x200B;並選取&#x200B;**新增資料元素**。
1. 在&#x200B;**建立資料元素**&#x200B;畫面上，設定標籤欄位：

   | 欄位 | 值 |
   |---|---|
   | 名稱 | 描述性名稱（例如`checkout flag`） |
   | 延伸 | 旗標 |
   | 資料元素型別 | 功能標幟 |

1. 設定&#x200B;**旗標**&#x200B;擴充功能欄位：

   | 欄位 | 必要 | 說明 |
   |---|---|---|
   | 功能鍵 | 是 | 唯一的旗標索引鍵（例如`checkout_flag`） |
   | 傳回類型 | 是 | **布林值(true/false)** — 已啟用/已停用，或&#x200B;**功能物件（完整詳細資料）** — 完整承載，包括`meta` |

1. 選取&#x200B;**儲存**。

**傳回型別**

| 傳回型別 | 解析為 |
|---|---|
| 布林值 (true/false) | 如果啟用`true`，否則`false` |
| 功能物件（完整詳細資料） | 已完整評估功能裝載，或未滿足規則時則為`null` |

### 使用資料元素 {#use-data-element}

在規則中 — 以名稱參照，例如`%Test Flag%`。

在自訂程式碼中 — 使用`_satellite.getVar`。 使用執行階段屬性，傳遞平面屬性對應作為第二個引數來評估：

```javascript
var isEnabled = _satellite.getVar('Test Flag', {
  locale: ['en-US'],
  platform: ['web']
});

if (isEnabled) {
  // your custom code
} else {
  // your default code
}
```

### getFeature {#get-feature}

當您需要啟用/停用以外的中繼資料時，`getFeature`會傳回評估的功能裝載。

使用具有&#x200B;**傳回型別的**&#x200B;功能旗標&#x200B;**資料元素：功能物件（完整詳細資料）** — 請參閱[建立功能旗標資料元素](#create-data-element) — 或在`flagClientReady`解析後從自訂程式碼呼叫`window._flagClient.getFeature(...)`。

**簽章**

```javascript
getFeature(featureKey: string, context: FeatureEvaluationContext): FeatureResult | null
```

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | string | 要在旗標中評估的功能索引鍵 |
| `context` | FeatureEvaluationContext | 身分（必要）和目標定位屬性。 請參閱[評估內容](#evaluation-context)。 |

**回應**

*功能結果*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `id` | 數字 | 數值功能識別碼。 功能層級控制項的`-1`。 |
| `key` | 字串\| null | 功能鍵。 功能層級控制項的`null`。 |
| `featureGroupKey` | 字串\| null | 功能群組索引鍵（可用時） |
| `meta` | 字串\| null | 可用時提供功能中繼資料 |
| `analyticsParam` | AnalyticsParam \| null | 已評估功能的Analytics詳細資料 |

*AnalyticsParam*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `featureGroupId` | 數字 | 數值功能群組識別碼 |
| `featureId` | 數字 | 數值功能識別碼 |
| `variantId` | 數字\| null | 變體識別碼（`0`用於控制） |

**控制組行為**

| 藍本 | isFeatureEnable | getFeature | Analytics事件isFeatureEnabled | Analytics事件getFeature |
|---|---|---|---|---|
| 處理 | `true` | 一般結果 | 是 | 是 |
| 功能層級控制項 | `false` | 哨兵(`id: -1`， `key: null`) | 是(`variantId: 0`) | 是 |
| 條件不符/找不到 | `false` | `null` | 無 | 無 |

**範例**

```javascript
var feature = _flagClient.getFeature('new-testflag', {
  identityNamespace: 'ECID',
  identityId: visitorEcid,
  attributes: {
    locale: ['en-US']
  }
});

var meta = feature && feature.meta;
if (meta) {
  // your custom code
} else {
  // your default code
}
```

### extensionVersion {#extension-version}

傳回Flags副檔名的版本字串。

**簽章**

```javascript
_flagClient.extensionVersion(): string
```

**範例**

```javascript
const version = _flagClient.extensionVersion();
console.log(`Flags extension version: ${version}`);
```

## API摘要 {#api-summary}

| API | 傳回值 |
|---|---|
| 功能標幟（Tags資料元素、布林值） | 布林值 |
| 功能標幟（Tags資料元素、物件） | 功能物件或`null` |
| `window.flagClientReady` | Promise — 等待擴充功能初始化 |
| `window._flagClient.isFeatureEnabled(featureKey, context)` | 布林值 |
| `window._flagClient.getFeature(featureKey, context)` | 功能物件或`null` |
| `window._flagClient.extensionVersion()` | 擴充功能版本字串 |

## 錯誤處理 {#error-handling}

擴充功能可妥善處理錯誤：

| 藍本 | 行為 |
|---|---|
| 網路在初始化時無法使用 | SDK會使用退避重試3次初始擷取，且初始化失敗。 `window.flagClientReady`和`_satellite.getVar(...)`拒絕了`Failed to initialize Flag`；`window._flagClient`仍為`undefined`。 |
| 內容中缺少身分 | 評估擲回錯誤；同時提供`identityNamespace`和`identityId` |
| 找不到功能 | `getFeature`傳回`null`；`isFeatureEnabled`傳回`false` |

```javascript
try {
  const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
} catch (error) {
  console.error('Evaluation failed:', error.message);
  // Use default value
}
```

## 最佳做法 {#best-practices}

### 提供一致的身分 {#consistent-identity}

在評估中使用相同的身分名稱空間和ID，以百分比轉出進行一致的分段。

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: identity,
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};

const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
```

### 適當地處理缺少的特徵 {#handle-missing}

找不到特徵或評估失敗時，請一律提供後援行為。

```javascript
const feature = _flagClient.getFeature('new-testflag', context);

if (feature && feature.meta) {
  // your custom code
} else {
  // Feature not enabled - use default code
}
```

### 在頁面載入後評估 {#evaluate-after-load}

在呼叫API之前，請確定標籤程式庫和旗標擴充功能已初始化。 在規則、**功能旗標**&#x200B;資料元素中使用&#x200B;**程式庫已載入**&#x200B;事件，或等待`flagClientReady`：

```javascript
window.flagClientReady.then(function () {
  var isEnabled = window._flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
});
```

## 另請參閱 {#see-also}

* [建立您的第一個功能標幟](../../feature-flags/create-your-first-feature-flag.md)
* [功能標幟和功能群組中的對象](../../audience/audience-in-feature-flags-and-feature-groups.md)
* [報告](../../feature-flags/reporting.md)

<!-- -->
