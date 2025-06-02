---
keywords: 可視化體驗撰寫器; 可視化體驗撰寫器最佳作法; 可視化體驗撰寫器限制; 可視化體驗撰寫器警告; VEC 最佳作法; VEC
description: 瞭解使用[!UICONTROL Visual Experience Composer] (VEC)時的最佳實務，讓您的體驗如預期般運作。
title: 什麼是[!UICONTROL Visual Experience Composer]最佳作法和限制？
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: 197aa3a0ab060481120abd0d12cdb7b581369929
workflow-type: tm+mt
source-wordcount: '2512'
ht-degree: 81%

---

# [!UICONTROL Visual Experience Composer]最佳作法和限制

下列最佳作法可協助讓您的體驗如預期般運作。在[!DNL Adobe Target]中使用[!UICONTROL Visual Experience Composer] (VEC)時，您也應注意其他秘訣和限制。

## 最佳實務 {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

以下是使用VEC時的最佳作法：

### 將at.js參考置於頁面`<head>`區段的頂端。

如果您也使用「訪客API服務」，請將訪客API指令碼放在at.js上方。

### 您可以在帳戶層級（已針對在帳戶中建立的所有活動啟用）或是在個別活動層級啟用增強體驗撰寫器。

若要在帳戶層級上啟用增強體驗撰寫器，請按一下「[!UICONTROL Administration > Visual Experience Composer]」，然後將開關切換至「開啟」位置。

在視覺化體驗撰寫器中建立活動時，若要在活動層級上啟用增強體驗撰寫器，請按一下「[!UICONTROL Configure > URL]」，然後將開關切換至「開啟」位置。

### 如果不會在網站的安全頁面上載入「增強視覺化體驗撰寫器」，您可以將特定的IP位址加入允許清單。

載入增強視覺化體驗撰寫器的問題可透過加入下列IP位址允許清單來解決。 這些 IP 位址用於 Adobe 的伺服器，用於增強體驗撰寫器 Proxy。只有針對活動編輯才需要這些資訊。您網站的訪客不需要將這些IP位址加入允許清單。

美國： 52.55.99.45、54.80.158.92和54.204.197.253

歐洲、中東和非洲(EMEA)： 52.51.238.221、52.210.199.44和54.72.56.50

亞太地區(APAC)： 52.193.67.35、54.199.198.109和54.199.241.57

### 對於可能成為良好測試/目標候選項的最上層元素及其他任何元素，請使用唯一的 ID。

直接在 body 元素內的任何項目都應該有唯一的 ID。如果新元素插入 body 中，而程式碼散佈周圍，則至少可較容易辨識上層元素。

Adobe Target 不需要 ID，但使用 ID 可讓以體驗撰寫器所建立的體驗更可靠。傳送體驗時，Target 會使用 CSS 選取器來修改您的內容。當您編輯體驗時，可視化體驗撰寫器會將選取器錨定到最靠近所修改 HTML 元素的上代 (具有非 null id 屬性)。因此，不建議使用任何會設定或修改 HTML ID 屬性的機制 (包括 JavaScript 程式庫)。雖然這些 ID 可供 Target 體驗撰寫器用來建立活動，但如果 JavaScript 修改 ID，則建立體驗時所使用的 ID 可能在體驗執行時無法使用。如果沒有 ID 可用，錨定到 ID 的選取器會失敗。

### 使用可輕鬆辨識的名稱來命名 CSS 類別。

在可視化體驗撰寫器中編輯 CSS 時，最好使用描述性類別名稱以輕鬆辨識類別。這有助於確保您編輯所需的 CSS 類別，且頁面如預期般地顯示。

隱藏或移除元素時，請勿使用 `!important` CSS 屬性。

如果 1!important1 CSS 屬性存在，則在傳送期間由 target.js 所做的變更，將會被網站的 CSS 規則所覆寫。

### 避免使用 HTML 表格作為頁面配置。

Target Standard 和 Premium 使用 JavaScript 來格式化頁面。很難使用 JavaScript 來修改表格式配置。此外，表格式配置可能不會以相同方式出現在所有瀏覽器中。為了獲得最佳結果，請使用 CSS 來建立頁面配置。

### 儘量不使用 iFrame。

最好儘量不要使用 iFrame，以簡化頁面和測試管理。可視化體驗撰寫器可能在 iFrame 內套用一些動作，但某些動作 (例如調整大小) 無法正常運作。使用多個 iFrame 的頁面很難管理和調整大小。因此，測試含有許多 iFrame 的頁面可能會發生問題。

### 在 DOM 準備就緒後，請儘快排列所有 DOM 修改。

如果無法在 target.js 套用體驗之前套用您的修改，內容傳送會中斷。只有當目標元素的階層中出現 DOM 變更時，才會發生此狀況。

### 在錨點元素中只使用純文字或影像標記。

`<a>Anchor Text</a>`

OR

`<a href=""> <img src=""> </img> </a>`

### 在內嵌元素內避免有區塊層級元素。

區塊層級元素不應該用於內嵌元素內，例如錨點、span 等等。這樣做會造成內嵌元素失去高度和寬度，導致可視化體驗撰寫器中的套版工具可能無法正常運作。

### 請勿在網站中使用 base 標記來解析 URL 和連結。

VEC會使用更新連結的Proxy伺服器，在幕後操控網站。 如果您新增 base 標記，則瀏覽器會再次解析代理伺服器所使用的 URL，URL 會看似中斷。

### 使用「編輯 HTML」來操作 DOM 結構可能會破壞選取器。

例如，如果您已採取兩個動作:

* 已新增類別至元素 1
* 已編輯元素 1 的 HTML

每一項變更都會在可視化體驗撰寫器中建立新元素。因為第二個動作會修改元素 1，如果您刪除元素 1，第二個動作便沒有任何項目需要修改，因此變更不再有作用。

換句話說，如果您使用文字新增元素，然後在個別的動作中使用不同文字編輯了該元素，則代碼編輯器會將這兩個動作顯示為個別的元素。編輯元素時，您會建立可修改您原始建立元素的新元素，包含編輯的文字。如果您之後刪除原始元素，編輯後文字將找不到編輯後的元素，因此將不會顯示。第二個元素會維持在元素的清單中，但它不會影響頁面，因為它變更的元素已不再存在。

請參閱[可視化體驗撰寫器中使用的元素選取器](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)。

### 透過RTF編輯器來設計文字元素的樣式時，請使用`<b>`和`<i>`標籤。

* 對於粗體文字，請使用 `<b>` 而非 `<strong>`。
* 對於斜體文字，請使用 `<i>` 而非 `<em>`。

`<strong>` 和 `<em>` 標記可能會造成非預期的結果。

### 移除表單欄位時請小心。

某些表單欄位可能是提交時的必要欄位。移除這些表單欄位會影響提交。

### 請勿在指令碼內包含`mboxCreate`。

因為 `mboxCreate` 會使用`document.write`，不建議在指令碼內包含 `mboxCreate`。請改用 `mboxDefine` 和 `mboxUpdate`，以達到相同目的。

### 如果 html 片段需要 JavaScript 程式碼才能初始化，請勿使用 Target Standard 來更新此 html 片段。

在頁面元件上 (例如 Slider、Carousel 等) 執行動作時 (編輯 HTML)，傳送可能看似中斷。可視化體驗撰寫器會在 JavaScript 將頁面元件個體化之後，執行此動作。

不過，當頁面的內容傳送給訪客時，則會在元件個體化之前套用此動作。因此，此元件的功能在傳送時可能會中斷，也可能不會。功能取決於此頁面上用來定義元件的指令碼的本質。

如果您測試傳送，且第一次可行，並不保證持續可行。可能有 (或沒有) 競爭狀況。

* 如果有競爭狀況，則傳送會時好時壞。
* 如果沒有競爭狀況，則永遠可行。

將頁面測試多次，以確定傳送正常運作。

### 請勿在網站中使用 base 標記來解析 URL 和連結。

當您使用增強體驗撰寫器時，網站會由代理伺服器在幕後操作，此伺服器會更新所有連結 url，讓 url 能夠在代理中運作。如果您新增 base 標記，所有這些 URL 會由瀏覽器解析而看似中斷。

### 網站中可能用於鎖定目標的重要文字，應該放在元素的 HTML 程式碼內。

例如，假設您的程式碼如下，則無法在 VEC 中將 Shopping Cart 文字鎖定為目標:

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart"> 
   <img alt="Shopping Cart"src="/images/ico-cart.gif"></img> 
   Shopping Cart: 
   <span id="HeaderCartQtyTotal">
      0 
  </span> 
  Items 
  <span id="HeaderCartPriceTotal"></span> 
</a>
```

在此範例中，VEC 中選取整個錨點元素，如果執行鎖定目標，將對其他元素造成不利影響。

### 請勿在JavaScript程式碼中使用`top`或`self`變數。

當增強體驗撰寫器已啟用時，top 和 self 變數的值會更新，以停用 iframe 爆破。使用 X-frame-options 標頭來新增 iframe 爆破，而非自訂 JavaScript 程式碼。

### 如果載入頁面時增加參數，一定要測試網站。

例如，為了開啟 www.abc.com，使用下列 url 參數:

`www.abc.com?mboxEdit=1&mboxDisable=1`

這些參數允許在 iframe 中編輯。

新增這類參數之後，請確定網站可以正常載入。

### 確定頁面在 iframe 中正常開啟。

在網站上「關閉」iframe 爆破技術，並檢查是否在虛擬頁面的 iframe 內正常開啟。例如：

```html
<!DOCTYPE 
<html> 
<html> 
<head> 
  <meta charset="utf-8"> 
  <meta name="viewport" content="width=device-width"> 
  <title>JS Bin</title> 
</head> 
<body> 
  <iframe src="https://www.homedepot.com"</iframe> 
</body> 
</html>
```

## 注意事項 {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

使用[!UICONTROL Visual Experience Composer]設計活動時，請注意下列警告。

### 「移動」功能不支援 z-index。

因為沒有 z-index 功能，被移動的元素無法移至另一個元素上方。如需詳細資料，請參閱[限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

### 重新排列元素會影響點擊追蹤。

如果標示為點擊追蹤的元素重新排列，則重新排列過的元素會改變路徑。因此，點擊追蹤的對象就變成原始元素重新排列之前所在位置中的元素。

這是因為用於傳送活動內容的程式碼和用於追蹤點擊的程式碼，同時位於傳送至頁面的一段程式碼內。如果您瀏覽至另一個頁面並設定點擊追蹤，則活動內容程式碼和點擊追蹤程式碼都會傳送至該頁面。如果點擊追蹤頁面的頁面結構類似於執行測試的頁面，則測試內容也可能出現在點擊追蹤頁面上。

### 在身為mbox的`<div>`中插入元素可能沒有作用。

如果 mbox 包含產品建議，假如 mbox 實作不正確，則插入元素可能以 insertBefore 出現，而不是 insertAfter。

### 編輯父元素和子元素兩者時，請先編輯父元素。

如果您在元素上交換影像動作，然後在其父元素上編輯文字或 HTML，可能會發生傳送問題最佳工作流程是先編輯父元素，再於子元素上交換影像。

### 無法選取以 mbox 為子元素的頁面元素。

例如，假設頁面包含:

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

在體驗中不應該選取外圍 div，因為寫入頁面程式碼中的 mbox 仍會呼叫 Target 並接收回應。此回應會干擾已預定給更大頁面元素的回應。

### 客戶環境中可能封鎖代理 IP。

如果您在非上線網站上使用增強體驗撰寫器，例如預備環境，假設網站封鎖 RIP，則您可能會看到逾時和拒絕存取的錯誤。

### 新增多個頁面時，體驗邊欄和頁面邊欄會同時開啟。結果會縮短可視化體驗撰寫器以最佳方式顯示網站的寬度。因此，可自動重排的網站在縮小的空間中，可能開始以非預期的方式出現。

暫行解決方法是按一下頂端的 ＜ 形箭號圖示，以收合體驗邊欄和頁面邊欄。

## 限制 {#section_F33C2EA27F2E417AA036BC199DD6C721}

使用VEC時，請考量下列限制：

### 處理與Chrome擴充功能原則變更的VEC相容性。

由於Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}中更新了[V3資訊清單原則，在瀏覽器剖析原始DOM之前，擴充功能無法再修改原始DOM。 因此，某些安全性指令碼（例如iframe-busting實作）可能會阻擋頁面在VEC中載入。

為確保相容性，當頁面載入[!DNL Target] iframe內時，應有條件地停用這些指令碼。 透過檢查`window.adobeVecExtension`物件的存在可以安全地完成此程式，此物件是在VEC載入期間由[!DNL Target]插入。

下列程式碼片段是iframe-busting程式碼的範例，這類程式碼會造成網頁無法在VEC中載入：

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

### 您無法將元素移到後面接著CSS屬性的容器之外。

元素無法移到後面有 CSS 屬性的容器之外。

### 您無法選取要重新排列的[!UICONTROL Button]元素。

無法直接選取[!UICONTROL Button]個元素來重新排列。 若要啟用重新排列，請將按鈕置於較大的容器內。

### Mbox 上只能使用交換產品建議。

mbox內不允許執行編輯類別和重新排列等動作。

### 請勿重新排列和移動同一個元素。

如果元素移至另一個位置，而您選取父容器並嘗試重新排列子元素，則已移動的元素不受影響，一樣停留在原處。重新排列可能不會如預期般地展現。

### 「交換影像動作」在輪播的影像上沒有作用。

假設頁面包含輪播，其中有六個影像，而您想要將一個影像和輪播的第二個影像對調，則「交換影像」動作沒有作用。

暫行解決方法是選取父容器，並使用「編輯 HTML」動作來編輯輪播的 HTML，以更新所需影像的影像來源。

### 在 mbox 中無法調整影像大小。

如果您在 mbox 元素中交換影像，然後嘗試根據 mbox 元素大小來調整該影像的大小，則不允許重新調整大小。

### 交換影像之後，無法選取「編輯」動作。

交換影像之後，無法編輯 Scene7 URL。

### 無法編輯含有外部來源的 HTML 元素。

例如: Video、audio 標記、embed、iFrame、frame。

### 如果錨點元素包含純文字或影像標記以外的其他任何項目，則點擊追蹤無法運作。

例如，假如元素包含 JavaScript，則點擊追蹤無法運作。

### 頁面必須接受 URL 參數，可視化體驗撰寫器才能運作。

某些網站會剔除頁面的任何 URL 參數。但是，可視化體驗撰寫器需要這些參數。

### 在 html 中使用指令碼時，從外部存取的任何變數和函式都應該在 window 命名空間下宣告。

當頁面載入後，指令碼會在 target.js 的範圍內執行。因此，無法從指令碼區塊之外存取區域性宣告的任何變數或函式。

*不正確:*

```html
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*正確:*

```html
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

### 從內容庫(Scene7)插入影像並編輯HTML會破壞影像URL。

在 &#39;customHeaderMessage&#39; div 內新增錨點元素和一些虛構文字:

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

選取此 div，使用「插入元素」動作插入影像，作為此虛構文字的同層級元素。

插入影像之後，看起來如下:

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

移除虛構文字段。

### VEC中的customCode動作不適用於Internet Explorer 8。

由於 IE8 處理指令碼內容時的限制，target.js 在 IE8 中不支援此動作。在暫行解決方法上，如果頁面包含 jQuery，且在 window 物件上全域公開，則 target.js 可以使用傳遞 customCode 動作。請確定已定義 window.jQuery 和 window.jQuery.fn.prepend。

### 只有在建立體驗的頁面或重新導向的頁面上，才支援點擊追蹤。

雖然「瀏覽」模式可以在「點擊追蹤」VEC 中使用，但無法用於頁面上新增點擊追蹤。
