---
description: '有關適用於 at.js 的 adobe.target.applyOffers(options) 函數的資訊。 '
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.applyOffers(options) 函數的資訊。
seo-title: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.applyOffers(options) 函數的資訊。
solution: Target
subtopic: 快速入門
title: adobe.target.applyOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# adobe.target.applyOffers(options) - at.js 2.x

此函數可讓您套用一個以上由 `adobe.target.getOffers()` 擷取的選件。

>[!NOTE]
>
>此函數於 at.js 2.x 推出。此函數不適用於 at.js 版本 1。*x* 版本不支援此函數。

| 機碼 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| selector | 字串 | 無 | HTML 元素或 CSS 選取器過去會識別 [!DNL Target] 應該放置選件內容的 HTML 元素。如果未提供選取器，[!DNL Target] 會假設我們應該使用的 HTML 元素為 HTML HEAD。 |
| 回應 | 物件 | 是 | 回應來自 `getOffers()` 的物件。<br>請參閱下方的「要求」表格。 |

## 回應

| 欄位名稱 | 說明 |
| --- | --- |
| response &gt; prefetch &gt; views &gt; options &gt; content | 請注意，「選項」的內容並無明確定義，且直接取決於選項類型/範本結構。 |
| response &gt; prefetch &gt; views &gt; options &gt; type | 選項類型。反映「內容」欄位的類型。支援的類型為動作。 |
| response &gt; prefetch &gt; views &gt; state | 不透明的檢視狀態 Token，該 Token 應隨檢視的顯示通知轉送 |
| response &gt; prefetch &gt; views &gt; options &gt; responseTokens | 包含處理目前選項時已收集的 `responseTokens` 地圖。 |
| response &gt; prefetch &gt; views &gt; analytics &gt; payload | 用於用戶端整合的 Analytics 裝載，套用檢視後應該傳送至 Analytics。 |
| response &gt; prefetch &gt; views &gt; trace | 包含所有追蹤資料的物件，這些資料為各檢視的預先擷取呼叫之追蹤資料。<br>追蹤物件也包含追蹤的版本。<br>追蹤物件也包含目前檢視的詳細資訊。 |
| response &gt; prefetch &gt; views &gt; options &gt; eventToken | 系統會為每個選項執行事件記錄。應針對每個已套用的選項，將個別事件 Token 新增至通知 Token 清單中。請注意，一個檢視是由多個選項組成。如果所有選項均已套用並顯示，則需要將所有 `eventTokens` 納入通知中。 |
| response &gt; prefetch &gt; views &gt; name | 人類可讀的檢視名稱。 |
| response &gt; prefetch &gt; views &gt; metrics | 應監看報告量度並向 [!DNL Target] 通知。目前僅支援點擊量度。當有使用者點擊元素，就應收集適當的 `eventTokens` 並傳送通知。 |
| response &gt; prefetch &gt; views &gt; key | 用於識別檢視的機碼或指紋。 |
| response &gt; prefetch &gt; views &gt; id | 檢視的 ID。 |
| response &gt; notifications &gt; id | 通知 ID。 |
| response &gt; notifications &gt; events &gt; type | 通知、點擊或顯示的類型。 |
| response &gt; notifications &gt; events &gt; trace | 通知事件的追蹤。 |
| response &gt; notifications &gt; events &gt; token | 隨通知事件傳送的 Token。 |
| response &gt; notifications &gt; events &gt; timestamp | 隨通知事件傳送的時間戳記。 |
| response &gt; notifications &gt; events &gt; errorCode | 如果通知失敗，錯誤碼會指出失敗的原因。 |
| response &gt; notifications &gt; events | 已記錄或無法記錄的目前通知事件。 |
| response &gt; notifications | 指出已記錄或失敗的通知。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; trace | 包含個別 mbox 要求之所有追蹤資料的物件。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; responseTokens | 包含特定 mbox 要求執行的 `responseTokens` 地圖。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; option &gt; content | 請注意，「選項」的內容並無明確定義，且直接取決於選項類型/範本結構。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; option &gt; type | 選項類型。反映「內容」欄位的類型。支援的類型為: html、重新導向 、JSON 和動態。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; options | 回應選項。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics &gt; eventToken | 點擊事件的 Token。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics &gt; type | &quot;click&quot; |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics | 包含 `clickThrough` 量度清單。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; mbox | mbox 的名稱。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt;index | 指出回應是針對要求中帶有此索引的 mbox。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; analytics &gt; payload | 用於用戶端整合的 Analytics 裝載，套用 mbox 後應該傳送至 Analytics。(請參閱「啟用 A4T 的促銷活動」一節)。 |
| response &gt; execute &gt; mboxes | 已執行 mbox 的清單。 |
| response &gt; execute &gt; pageLoad &gt; options &gt; content | 請注意，「選項」的內容並無明確定義，且直接取決於選項類型/範本結構。 |
| response &gt; execute &gt; pageLoad &gt; options &gt; type | 選項類型。反映「內容」欄位的類型。支援的類型為: html、重新導向、JSON、動態和動作。 |
| response &gt; execute &gt; pageLoad &gt; options | 未依檢視分組的選項 (target-global-mbox + 含有未依檢視分組的檢視之活動選項)。 |
| response &gt; execute &gt; pageLoad &gt; metrics | 未設定為屬於特定檢視的點擊量度。 |
| response &gt; execute &gt; pageLoad &gt; trace | 包含 PageLoad 要求之所有追蹤資料的物件。 |
| response &gt; execute &gt; pageLoad &gt; analytics &gt; payload | 用於用戶端整合的 Analytics 裝載，套用頁面載入內容後應該傳送至 Analytics。(請參閱「啟用 A4T 的促銷活動」一節)。 |

## applyOffers() 呼叫範例

```
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

## 與 `getOffers()` 和 `applyOffers()` 鏈結的 Promise 呼叫範例，因為這些函數是以 Promise 為基底

```
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
