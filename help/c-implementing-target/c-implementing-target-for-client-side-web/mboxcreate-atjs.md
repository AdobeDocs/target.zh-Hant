---
keywords: mboxCreate;mboxcreate;mbox create;at.js;functions;function
description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 mboxCreate(mbox,params) 函數的資訊。
title: mboxCreate(mbox,params) - at.js 1.x
feature: at.js
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---


# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

執行要求並將選件套用至具有 mboxDefault 類別名稱的最接近 DIV。

>[!NOTE]
>
>此函數僅適用於 at.js 1.*x* 版。自 at.js 2.x 版起已棄用此函數。如果與 at.js 2.x 搭配使用，此函數會傳回預設內容。

此函數多半會內建在 [!DNL at.js]，以便於從 [!DNL mbox.js] 到 [!DNL at.js] 的轉變。`mboxCreate()` 較新的替代方案是 `adobe.target.applyOffer()`/ `adobe.target.getOffer()` 或 Angular 指令。

## 範例

```javascript
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## 附註

`mboxCreate()` 現在使用「json」端點而非「standard」端點，且非同步觸發。因此:

* [偵錯](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F)有一些不同。
* 避免選件程式碼需要同步，封鎖呼叫。

   例如，設定後續進入頁面之網站程式碼或其他 mbox 所使用 JavaScript 變數的選件。

* 叫用 `<div class="mboxDefault"></div>` 之前請確認已有 `mboxCreate()`，因為 [!DNL at.js] 不會為您新增此項目。

* 不建議將空白的 top-of-page `mboxCreate()` 函數用作全域 mbox。

   [!DNL at.js] 中自動建立的全域 mbox 是較好的選項，因為它可透過 `<head>` 觸發，且較容易傳回內容。