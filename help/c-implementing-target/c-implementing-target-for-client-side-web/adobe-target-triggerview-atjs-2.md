---
description: 'at. js的adobe. target. righerView(ViewName、options)函數相關資訊。 '
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: Adobe Target at. js JavaScript程式庫的adobe. target. righerView(ViewName、選項)函數的相關資訊。
seo-title: Adobe Target at. js JavaScript程式庫的adobe. target. righerView(ViewName、選項)函數的相關資訊。
solution: Target
subtopic: 快速入門
title: adobe.target.triggerView (viewName, options)
topic: Standard
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# adobe. target. righerView(ViewName，options)- at. js2.x

每當新頁面載入或頁面上的元件重新呈現時，就可呼叫此函數。應為單頁應用程式 (SPA) 實作 `adobe.target.triggerView()`，以便使用可視化體驗撰寫器 (VEC) 來建立 A/B 測試和體驗鎖定目標 (XT) 活動。如果沒有在網站上 `adobe.target.triggerView()` 實作，VEC 就無法用於 SPA。如需詳細資訊，請參閱[單頁應用程式實作](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

>[!NOTE]
>
>此函數是以. js2.x導入。此函數不適用於. js第版。*x* 版本不支援此函數。

| 參數 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| viewName | 字串 | 是 | 傳入任何名稱作為要代表檢視的字串類型。此檢視名稱會顯示在 VEC 的[!UICONTROL 「修改]」面板中，供行銷人員建立動作和執行其 A/B 和 XT 活動。 |
| options | 物件 | 無 |
| options &gt; page | 布林值 | 無 | **TRUE:** page 的預設值為 true。當 page=true，會傳送通知至 [!DNL Target] 後端以增加曝光計數。<br>**FALSE：** 當page= false時，不會傳送通知以增加曝光計數。只有當您想重新呈現頁面上含有某個選件的元件時，才應使用此項目。 |

## 會將通知傳送至 Target 後端以增加曝光計數的 `triggerView()` 呼叫範例

```
adobe.target.triggerView("homeView")
```

## 不將通知傳送至 Target 後端以增加曝光計數的的 `triggerView()` 呼叫範例

```
adobe.target.triggerView("homeView", {page: false})
```
