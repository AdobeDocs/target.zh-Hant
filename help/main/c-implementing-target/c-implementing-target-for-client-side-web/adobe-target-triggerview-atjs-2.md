---
keywords: adobe.target.triggerView;triggerView;triggerview;trigger view;at.js;函數;函數;viewName;viewname;檢視名稱
description: 使用adobe.target.triggerView()函式進行Adobe [!DNL Target] at.js JavaScript庫，用於單頁應用程式(SPA)。 (at.js 2.x)
title: 如何使用adobe.target.triggerView()函式？
feature: at.js
role: Developer
exl-id: 619d5166-d1d9-49a6-9807-338544782e66
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 84%

---

# adobe.target.triggerView (viewName, options) - at.js 2.x

每當新頁面載入或頁面上的元件重新呈現時，就可呼叫此函數。應為單頁應用程式 (SPA) 實作 `adobe.target.triggerView()`，以便使用可視化體驗撰寫器 (VEC) 來建立 A/B 測試和體驗鎖定目標 (XT) 活動。如果沒有在網站上 `adobe.target.triggerView()` 實作，VEC 就無法用於 SPA。如需詳細資訊，請參閱[實作單頁應用程式](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

>[!NOTE]
>
>此函數於 at.js 2.x 推出。此函數不適用於 at.js 版本 1。*x* 版本不支援此函數。

| 參數 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| viewName | 字串 | 是 | 傳入任何名稱作為要代表檢視的字串類型。此檢視名稱會顯示在 VEC 的[!UICONTROL 「修改]」面板中，供行銷人員建立動作和執行其 A/B 和 XT 活動。 |
| options | 物件 | 無 |  |
| options > page | 布林值 | 無 | **TRUE:** page 的預設值為 true。當 page=true，會傳送通知至 [!DNL Target] 後端以增加曝光計數。<br>當 `triggerView` 調用，但選項>頁設定為false時除外。<br>**FALSE:** 當 page=false，不會傳送通知以增加曝光計數。只有當您想重新呈現頁面上含有某個選件的元件時，才應使用此項目。 |

## 範例: True

將通知傳送至 Target 後端以增加活動曝光次數和其他量度的 `triggerView()` 呼叫。

```javascript
adobe.target.triggerView("homeView")
```

## 範例: False

不將通知傳送至 Target 後端以增加曝光計數的 `triggerView()` 呼叫。

```javascript
adobe.target.triggerView("homeView", {page: false})
```
