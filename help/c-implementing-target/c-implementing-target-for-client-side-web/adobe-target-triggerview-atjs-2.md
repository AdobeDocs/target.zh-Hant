---
description: '有關適用於 at.js 的 adobe.target.triggerView (viewName, options) 函數的資訊。 '
keywords: adobe. target. righerView；觸發器檢視；觸發器檢視；觸發器檢視；at. js；函數；函數；ViewName；檢視名稱；檢視名稱
seo-description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.triggerView (viewName, options) 函數的資訊。
seo-title: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.triggerView (viewName, options) 函數的資訊。
solution: Target
subtopic: 快速入門
title: adobe.target.triggerView (viewName, options)
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# adobe.target.triggerView (viewName, options) - at.js 2.x

每當新頁面載入或頁面上的元件重新呈現時，就可呼叫此函數。應為單頁應用程式 (SPA) 實作 `adobe.target.triggerView()`，以便使用可視化體驗撰寫器 (VEC) 來建立 A/B 測試和體驗鎖定目標 (XT) 活動。如果沒有在網站上 `adobe.target.triggerView()` 實作，VEC 就無法用於 SPA。如需詳細資訊，請參閱[實作單頁應用程式](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

>[!NOTE]
>
>此函數於 at.js 2.x 推出。此函數不適用於 at.js 版本 1。*x* 版本不支援此函數。

| 參數 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| viewName | 字串 | 是 | 傳入任何名稱作為要代表檢視的字串類型。此檢視名稱會顯示在 VEC 的[!UICONTROL 「修改]」面板中，供行銷人員建立動作和執行其 A/B 和 XT 活動。 |
| options | 物件 | 無 |  |
| options &gt; page | 布林值 | 無 | **TRUE:** page 的預設值為 true。當 page=true，會傳送通知至 [!DNL Target] 後端以增加曝光計數。<br>如果沒有與檢視相關聯的活動體驗或活動度量，則不會傳送任何通知。<br>**FALSE:** 當 page=false，不會傳送通知以增加曝光計數。只有當您想重新呈現頁面上含有某個選件的元件時，才應使用此項目。 |

## 範例：True

`triggerView()` 呼叫以傳送通知至Target後端，以遞增活動印象和其他度量。

```
adobe.target.triggerView("homeView")
```

## 範例：False

`triggerView()` 呼叫未傳送通知至Target後端以用於曝光計數。

```
adobe.target.triggerView("homeView", {page: false})
```
