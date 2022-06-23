---
keywords: mboxCreate;mboxcreate;mbox 建立;at.js;函數;函數
description: 將mboxCreate()函式用於Adobe [!DNL Target] at.js JavaScript庫，用mboxDefault類名向最近的DIV應用提供。 (at.js 1.x)
title: 如何使用mboxCreate()函式？
feature: at.js
role: Developer
exl-id: 821ad97a-345a-4e56-9be6-ab1c7d3a651d
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 76%

---

# mboxCreate(mbox,params) - at.js 1.x

執行要求並將選件套用至具有 mboxDefault 類別名稱的最接近 DIV。

>[!NOTE]
>
>此函數僅適用於 at.js 1.*x* 版。自 at.js 2.x 版起已棄用此函數。如果與 at.js 2.x 搭配使用，此函數會傳回預設內容。

此函式內置於 [!DNL at.js] 主要是為了緩解 [!DNL mbox.js] （現在不建議使用） [!DNL at.js]。 `mboxCreate()` 較新的替代方案是 `adobe.target.applyOffer()`/ `adobe.target.getOffer()` 或 Angular 指令。

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

* [偵錯](https://developer.adobe.com/target/implement/client-side/target-debugging-atjs/target-debugging-atjs/)有一些不同。
* 避免選件程式碼需要同步，封鎖呼叫。

   例如，設定後續進入頁面之網站程式碼或其他 mbox 所使用 JavaScript 變數的選件。

* 叫用 `<div class="mboxDefault"></div>` 之前請確認已有 `mboxCreate()`，因為 [!DNL at.js] 不會為您新增此項目。

* 不建議將空白的 top-of-page `mboxCreate()` 函數用作全域 mbox。

   [!DNL at.js] 中自動建立的全域 mbox 是較好的選項，因為它可透過 `<head>` 觸發，且較容易傳回內容。
