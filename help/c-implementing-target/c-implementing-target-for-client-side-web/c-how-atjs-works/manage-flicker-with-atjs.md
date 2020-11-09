---
keywords: flicker;at.js;implementation;asynchronously;asynchronous;synchronously;synchronous
description: 關於 Adobe Target at.js JavaScript 資料庫如何在頁面或應用程式載入期間防止忽隱忽現的資訊。
title: Adobe Target at.js 處理忽隱忽現情況的方式
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 80%

---


# At.js 處理忽隱忽現情況的方式{#how-at-js-manages-flicker}

關於 Target at.js JavaScript 資料庫如何在頁面或應用程式載入期間防止閃爍的資訊。

忽隱忽現是指預設內容在換成活動內容之前短暫顯示給訪客。忽隱忽現不理想，因為可能造成訪客混淆。

## 使用自動建立的全域mbox {#section_C502170D551C4F52AAFD8E82C41BB63A}

若您在設定 at.js 時啟用了[「自動建立全域 Mbox」](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13)設定，at.js 會透過變更頁面載入時的不透明度設定，來處理忽隱忽現的情形。at.js載入時，會將元素的不透明度設定變更為「0」，`<body>`讓訪客一開始無法看到頁面。接收到 Target 回應後，或若偵測到 Target 要求有錯誤，at.js 會將不透明度重設為「1」。這種做法可確保訪客只能在活動內容套用之後才看得到頁面。

如果您在設定 at.js 時啟用此設定，則 at.js 會將 HTML BODY 樣式不透明度設定為 0。收到來自 Target 的回應之後，at.js 會將 HTML BODY 不透明度重設為 1。

將不透明度設為 0，可隱藏頁面內容以避免忽隱忽現的情形發生，但瀏覽器仍會輸出頁面，並載入 CSS、影像等所有必要資產。

若不透明度設為 0 仍無法在您的實作上順利運作，您也可以透過自訂 `bodyHiddenStyle`，並設為 `body {visibility:hidden !important}`}，來管理忽隱忽現的問題。You can use either value body `{opacity:0 !important}` or `body {visibility:hidden !important}`, whichever works best for your specific circumstance.

下圖顯示 js 1.*x* 和 at.js 2.x。

**at.js 2.x**

![Target 流程: at.js 頁面載入要求](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

如需 `bodyHiddenStyle` 覆寫的詳細資訊，請參閱 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 處理非同步載入 at.js 時忽隱忽現的情形

非同步載入 at.js 可有效避免讓瀏覽器無法呈現；不過，此技術可能導致網頁上忽隱忽現。

您可以使用預先隱藏的程式碼片段來避免忽隱忽現情形，此片段要等到 [!DNL Target] 將相關的 HTML 元素個人化之後才可見。

at.js可以非同步載入，直接內嵌在頁面上，或透過標籤管理器(Adobe Launch、動態標籤管理器(DTM)等)。

如果頁面上內嵌了at.js，則必須先新增程式碼片段，才能載入at.js。 如果您透過標籤管理器載入at.js（此標籤管理器也以非同步方式載入），則必須先新增程式碼片段，再載入標籤管理器。 如果標籤管理器是同步載入的，則指令碼可能會包含在at.js之前的標籤管理器中。

預先隱藏的程式碼片段如下所示:

```
;(function(win, doc, style, timeout) {
  var STYLE_ID = 'at-body-style';

  function getParent() {
    return doc.getElementsByTagName('head')[0];
  }

  function addStyle(parent, id, def) {
    if (!parent) {
      return;
    }

    var style = doc.createElement('style');
    style.id = id;
    style.innerHTML = def;
    parent.appendChild(style);
  }

  function removeStyle(parent, id) {
    if (!parent) {
      return;
    }

    var style = doc.getElementById(id);

    if (!style) {
      return;
    }

    parent.removeChild(style);
  }

  addStyle(getParent(), STYLE_ID, style);
  setTimeout(function() {
    removeStyle(getParent(), STYLE_ID);
  }, timeout);
}(window, document, "body {opacity: 0 !important}", 3000));
```

依預設，此程式碼片段會預先隱藏整個 HTML BODY。在某些情況下，您可能只想預先隱藏特定的 HTML 元素，而非整個頁面。您可以自訂 style 參數來達到此目的。此參數可以換成某些項目，而只預先隱藏頁面的特定區域。

例如，您有兩個區域，分別以 ID container-1 和 container-2 來識別，則 style 可以換成如下內容:

```
#container-1, #container-2 {opacity: 0 !important}
```

並非預設值:

```
body {opacity: 0 !important}
```

## 在at.js 2.x中管理triggerView()的閃爍

使用 `triggerView()` 顯示 SPA 中的目標內容時，會自動提供處理忽隱忽現問題的功能。這表示不需要手動新增預先隱藏邏輯。at.js 2.x 會在套用目標內容之前，預先隱藏需要顯示檢視的位置。

## 使用getOffer()和applyOffer()管理Flicker

因為 `getOffer()` 和 `applyOffer()` 都是低階 API，並沒有內建的忽隱忽現控制項。您可以將選取器或 HTML 元素當作選項傳給 `applyOffer()`，在此情況下，`applyOffer()` 會將活動內容新增至特定元素，不過在叫用 `getOffer()` 和 `applyOffer()` 之前，您必須確定元素已適當隱藏。

```
document.documentElement.style.opacity = "0";
 
adobe.target.getOffer({
    mbox: 'target-global-mbox',
    success: function(offer) {
        adobe.target.applyOffer({
            mbox: 'target-global-mbox',
            offer: offer
        });
 
        document.documentElement.style.opacity = "1";
    },
    error: function() {
        document.documentElement.style.opacity = "1";        
    }
});
```

## 在at.js 1.x中搭配使用mboxCreate()的區域mbox（at.js 2.x不支援）

如果您使用地區 mbox 實作，則可以使用 `mboxCreate()` 搭配您佈建的頁面，類似下列範例程式碼:

```
<div class="mboxDefault">
Some default content
</div>
<script>
mboxCreate('some-mbox');
</script>
```

如果頁面適當地佈建，at.js 會在含有 mboxDefault 類別的元素上切換 CSS「visibility」屬性，以處理忽隱忽現問題。