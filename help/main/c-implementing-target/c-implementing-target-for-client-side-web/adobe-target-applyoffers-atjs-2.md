---
keywords: adobe.target.applyOffers;applyOffers;applyoffers;apply offers;at.js;函數;函數
description: 使用adobe.target.applyOffiss()函式進行Adobe [!DNL Target] at.js JavaScript庫以在響應中應用多個選項。 (at.js 2.x)
title: 如何使用adobe.target.applyOffirs()函式？
feature: at.js
role: Developer
exl-id: a6f4c755-e5a0-4228-90f3-0f9d3b092cd8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 88%

---

# adobe.target.applyOffers(options) - at.js 2.x

此函數可讓您套用一個以上由 `adobe.target.getOffers()` 擷取的選件。

>[!NOTE]
>
>此函數於 at.js 2.x 推出。此函數不適用於 at.js 版本 1。*x* 版本不支援此函數。

| 機碼 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| selector | 字串 | 無 | HTML 元素或 CSS 選取器過去會識別 [!DNL Target] 應該放置選件內容的 HTML 元素。如果未提供選擇器， [!DNL Target] 假定要使用的HTML元素是HTMLHEAD。 |
| 回應 | 物件 | 是 | 回應來自 `getOffers()` 的物件。<br>請參閱下方的「要求」表格。 |

## 回應

>[!NOTE]
>
>咨詢 [交付API文檔](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) 的子菜單。

| 欄位名稱 | 說明 |
| --- | --- |
| response > prefetch > views > options > content | 請注意，「選項」的內容並無明確定義，且直接取決於選項類型/範本結構。 |
| response > prefetch > views > options > type | 選項類型。反映「內容」欄位的類型。支援的類型為動作。 |
| response > prefetch > views > state | 不透明的檢視狀態 Token，該 Token 應隨檢視的顯示通知轉送 |
| response > prefetch > views > options > responseTokens | 包含處理目前選項時已收集的 `responseTokens` 地圖。 |
| response > prefetch > views > analytics > payload | 用於用戶端整合的 Analytics 裝載，套用檢視後應該傳送至 Analytics。 |
| response > prefetch > views > trace | 包含所有追蹤資料的物件，這些資料為各檢視的預先擷取呼叫之追蹤資料。<br>追蹤物件也包含追蹤的版本。<br>追蹤物件也包含目前檢視的詳細資訊。 |
| response > prefetch > views > options > eventToken | 系統會為每個選項執行事件記錄。應針對每個已套用的選項，將個別事件 Token 新增至通知 Token 清單中。請注意，一個檢視是由多個選項組成。如果所有選項均已套用並顯示，則需要將所有 `eventTokens` 納入通知中。 |
| response > prefetch > views > name | 人類可讀的檢視名稱。 |
| response > prefetch > views > metrics | 應監看報告量度並向 [!DNL Target] 通知。目前僅支援點擊量度。當有使用者點擊元素，就應收集適當的 `eventTokens` 並傳送通知。 |
| response > prefetch > views > key | 用於識別檢視的機碼或指紋。 |
| response > prefetch > views > id | 檢視的 ID。 |
| response > notifications > id | 通知 ID。 |
| response > notifications > events > type | 通知、點擊或顯示的類型。 |
| response > notifications > events > trace | 通知事件的追蹤。 |
| response > notifications > events > token | 隨通知事件傳送的 Token。 |
| response > notifications > events > timestamp | 隨通知事件傳送的時間戳記。 |
| response > notifications > events > errorCode | 如果通知失敗，錯誤碼會指出失敗的原因。 |
| response > notifications > events | 已記錄或無法記錄的目前通知事件。 |
| response > notifications | 指出已記錄或失敗的通知。 |
| response > execute > mboxes > mbox > trace | 包含個別 mbox 要求之所有追蹤資料的物件。 |
| response > execute > mboxes > mbox > responseTokens | 包含特定 mbox 要求執行的 `responseTokens` 地圖。 |
| response > execute > mboxes > mbox > option > content | 請注意，「選項」的內容並無明確定義，且直接取決於選項類型/範本結構。 |
| response > execute > mboxes > mbox > option > type | 選項類型。反映「內容」欄位的類型。支援的類型為: html、重新導向 、JSON 和動態。 |
| response > execute > mboxes > mbox > options | 回應選項。 |
| response > execute > mboxes > mbox > metrics > eventToken | 點擊事件的 Token。 |
| response > execute > mboxes > mbox > metrics > type | &quot;click&quot; |
| response > execute > mboxes > mbox > metrics | 包含 `clickThrough` 量度清單。 |
| response > execute > mboxes > mbox > mbox | mbox 的名稱。 |
| response > execute > mboxes > mbox >index | 指出回應是針對要求中帶有此索引的 mbox。 |
| response > execute > mboxes > mbox > analytics > payload | 用於用戶端整合的 Analytics 裝載，套用 mbox 後應該傳送至 Analytics。(請參閱「啟用 A4T 的促銷活動」一節)。 |
| response > execute > mboxes | 已執行 mbox 的清單。 |
| response > execute > pageLoad > options > content | 請注意，「選項」的內容並無明確定義，且直接取決於選項類型/範本結構。 |
| response > execute > pageLoad > options > type | 選項類型。反映「內容」欄位的類型。支援的類型為: html、重新導向、JSON、動態和動作。 |
| response > execute > pageLoad > options | 未依檢視分組的選項 (target-global-mbox + 含有未依檢視分組的檢視之活動選項)。 |
| response > execute > pageLoad > metrics | 未設定為屬於特定檢視的點擊量度。 |
| response > execute > pageLoad > trace | 包含 PageLoad 要求之所有追蹤資料的物件。 |
| response > execute > pageLoad > analytics > payload | 用於用戶端整合的 Analytics 裝載，套用頁面載入內容後應該傳送至 Analytics。(請參閱「啟用 A4T 的促銷活動」一節)。 |

## applyOffers() 呼叫範例

```javascript
adobe.target.applyOffers({response:{
  "execute": {
    "pageLoad": {
      "options": [{
        "type": "html",
        "content": "page-load"
      },
      {
        "type": "actions",
        "content": [{
          "type": "setHtml",
          "content": "<h1>Container 1</h1>",
          "selector": "#container1",
          "cssSelector": "#container1"
        },
        {
          "type": "setHtml",
          "content": "<h3>Container 3</h3>",
          "selector": "#container3",
          "cssSelector": "#container3"
        }]
      }],
 
 
      "metrics": [{
        "type": "click",
        "selector": "#container1",
        "eventToken": "page-load-click-metric" 
      }]
    }
  }
}});
```

## 承諾連結的示例調用 `getOffers()` 和 `applyOffers()`，因為這些函式基於Promise

```javascript
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```

有關如何使用getOffires()的更多示例，請參閱getOffires [文檔](https://experienceleague.adobe.com/docs/target/using/implement-target/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html)

### 頁面載入請求示例


```javascript
adobe.target.getOffers({
    request: {
        execute: {
            pageLoad: {}
        }
    }
}).
then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```

