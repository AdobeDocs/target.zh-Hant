---
keywords: 可視化體驗撰寫器; 可視化體驗撰寫器最佳作法; 可視化體驗撰寫器限制; 可視化體驗撰寫器警告; VEC 最佳作法; VEC
description: 瞭解使用[!UICONTROL Visual Experience Composer] (VEC)時的最佳實務，讓您的體驗如預期般運作。
title: 什麼是[!UICONTROL Visual Experience Composer]最佳作法和限制？
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: 1f2c6bbabf0158672e5f926ffdf9662637cd8416
workflow-type: tm+mt
source-wordcount: '2435'
ht-degree: 37%

---

# [!UICONTROL Visual Experience Composer]最佳作法和限制

為確保您的體驗如預期運作，請在使用[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)時遵循最佳實務。 請注意重要提示和限制，以最大化效能並避免常見問題。

## 最佳實務 {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

以下是使用VEC時的最佳作法：

### 將at.js參考置於頁面`<head>`區段的頂端。

+++檢視詳細資料
如果您也使用[!UICONTROL Visitor API Service]，請將訪客API指令碼放在at.js上方。

+++

### 您可以在帳戶層級（已針對在帳戶中建立的所有活動啟用）或是在個別活動層級啟用[!UICONTROL Enhanced Experience Composer]。

+++檢視詳細資料
若要在帳戶層級啟用[!UICONTROL Enhanced Experience Composer]，請按一下[!UICONTROL [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer]]，然後將[!UICONTROL Enable Enhanced Experience Composer]開關切換到[開啟]位置。

在[!UICONTROL Visual Experience Composer]中建立活動時，若要在活動層級啟用[!UICONTROL Enhanced Experience Composer]，請按一下[!UICONTROL Configure > [!UICONTROL Page Delivery]]，然後將[!UICONTROL Enable Enhanced Experience Composer]切換至[開啟]位置。

+++

### 如果[!UICONTROL Enhanced Experience Composer]無法在您網站的安全頁面上載入，您可以將特定的IP位址加入允許清單。

+++檢視詳細資料
載入[!UICONTROL Enhanced Experience Composer]的問題可藉由將下列IP位址列入允許清單來解決。 這些IP位址是用於用於[!UICONTROL Enhanced Experience Composer] Proxy的[!DNL Adobe]伺服器。 只有針對活動編輯才需要這些資訊。您網站的訪客不需要將這些IP位址加入允許清單。

如需詳細資訊，請參閱[ EEC將不會在&#x200B;*疑難排解增強體驗撰寫器的相關問題*&#x200B;中，載入無法透過公用IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md)存取的內部QA URL。

+++

### 對於可能成為良好測試/目標候選項的最上層元素及其他任何元素，請使用唯一的 ID。

+++詳細資料
緊接在body元素內的任何專案都應該有唯一的ID。 如果新元素插入 body 中，而程式碼散佈周圍，則至少可較容易辨識上層元素。

[!DNL Target]不需要ID，但使用ID會提高使用體驗撰寫器建立之體驗的可靠性。 [!DNL Target]在傳遞體驗時會使用CSS選取器來修改您的內容。 當您編輯體驗時，[!UICONTROL Visual Experience Composer]會將選取器錨定至要修改之HTML元素的最近祖項（具有非null ID屬性）。 因此，不建議使用任何會設定或修改 HTML ID 屬性的機制 (包括 JavaScript 程式庫)。雖然這些ID可供[!DNL Target]體驗撰寫器用於建立活動，但如果JavaScript修改ID，則建立體驗時使用的ID在體驗執行時可能無法使用。 如果沒有 ID 可用，錨定到 ID 的選取器會失敗。

+++

### 使用可輕鬆辨識的名稱來命名 CSS 類別。

+++詳細資料
在[!DNL Visual Experience Composer]中編輯CSS類別時，使用描述性類別名稱讓類別易於識別會很有幫助。 這有助於確保您編輯所需的 CSS 類別，且頁面如預期般地顯示。

隱藏或移除元素時，請勿使用 `!important` CSS 屬性。

如果`!important` CSS屬性存在，`target.js`在傳遞期間所做的變更將會被網站的CSS規則覆寫。

+++

### 避免使用 HTML 表格作為頁面配置。

+++詳細資料
[!DNL Target]使用JavaScript來格式化頁面。 很難使用 JavaScript 來修改表格式配置。此外，表格式配置可能不會以相同方式出現在所有瀏覽器中。為了獲得最佳結果，請使用 CSS 來建立頁面配置。

+++

### 儘量不使用 iFrame。

+++詳細資料
最佳作法是儘量減少iFrame的使用，以簡化頁面和測試管理。 視覺化體驗撰寫器可以在iFrame中套用某些動作，但有些動作（例如調整大小）無法正常運作。 使用多個 iFrame 的頁面很難管理和調整大小。因此，測試含有許多 iFrame 的頁面可能會發生問題。

+++

### 在 DOM 準備就緒後，請儘快排列所有 DOM 修改。

+++詳細資料
如果您的修改無法在`target.js`套用體驗應用程式之前套用，內容傳遞可能會中斷。 只有當目標元素的階層中出現 DOM 變更時，才會發生此狀況。

+++

### 在錨點元素中只使用純文字或影像標記。

+++詳細資料
`<a>Anchor Text</a>`

OR

`<a href=""> <img src=""> </img> </a>`

+++

### 在內嵌元素內避免有區塊層級元素。

+++詳細資料
區塊層級元素不應用於內嵌元素內，例如錨點、範圍等。 這樣做會導致內嵌元素失去其高度和寬度，因此[!UICONTROL Visual Experience Composer]中的覆蓋工具可能無法如預期運作。

+++

### 請勿在網站中使用 base 標記來解析 URL 和連結。

+++詳細資料
VEC會使用可更新連結的Proxy伺服器，在幕後操控網站。 如果您新增 base 標記，則瀏覽器會再次解析代理伺服器所使用的 URL，URL 會看似中斷。

+++

### 使用「編輯 HTML」來操作 DOM 結構可能會破壞選取器。

+++詳細資料
例如，如果您已採取兩個動作：

* 已新增類別至元素 1
* 已編輯元素 1 的 HTML

每次變更都會在VEC中建立新元素。 因為第二個動作會修改元素 1，如果您刪除元素 1，第二個動作便沒有任何項目需要修改，因此變更不再有作用。

換句話說，如果您使用文字新增元素，然後在個別的動作中使用不同文字編輯了該元素，則代碼編輯器會將這兩個動作顯示為個別的元素。編輯元素時，您會建立可修改您原始建立元素的新元素，包含編輯的文字。如果您之後刪除原始元素，編輯後文字將找不到編輯後的元素，因此將不會顯示。第二個元素會維持在元素的清單中，但它不會影響頁面，因為它變更的元素已不再存在。

檢視[!UICONTROL Visual Experience Composer][&#128279;](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)中使用的元素選取器。

+++

### 透過RTF編輯器來設計文字元素的樣式時，請使用`<b>`和`<i>`標籤。

+++詳細資料
* 對於粗體文字，請使用 `<b>` 而非 `<strong>`。
* 對於斜體文字，請使用 `<i>` 而非 `<em>`。

`<strong>` 和 `<em>` 標記可能會造成非預期的結果。

+++

### 移除表單欄位時請小心。

+++詳細資料
提交時某些表單欄位可能是必填欄位。 移除這些表單欄位會影響提交。

+++

### 請勿在指令碼內包含`mboxCreate`。

+++詳細資料
因為`mboxCreate`使用`document.write`，不建議在指令碼中包含`mboxCreate`。 請改用 `mboxDefine` 和 `mboxUpdate`，以達到相同目的。

+++

### 如果使用[!DNL Target]需要HTML程式碼進行初始化，請勿更新其JavaScript程式碼片段。


+++詳細資料
在頁面元件（例如滑桿、浮動視窗等）上執行動作(編輯HTML)時，傳送可能會顯示為已中斷。 VEC會在JavaScript將頁面元件例項化之後執行動作。

不過，當頁面的內容傳送給訪客時，則會在元件個體化之前套用此動作。因此，此元件的功能在傳送時可能會中斷，也可能不會。功能取決於此頁面上用來定義元件的指令碼的本質。

如果您測試傳送，且第一次可行，並不保證持續可行。可能有 (或沒有) 競爭狀況。

* 如果有競爭條件，傳送會間歇性運作。
* 如果沒有競爭條件，傳送一律有效。

將頁面測試多次，以確定傳送正常運作。

+++

### 請勿在網站中使用 base 標記來解析 URL 和連結。

+++詳細資料
當您使用[!UICONTROL Enhanced Experience Composer]時，網站會在幕後由Proxy伺服器操控，該伺服器會更新所有連結URL，讓它們在Proxy中運作。 如果您新增base標籤，瀏覽器會解析所有這些URL，因此這些URL看起來會損毀。

+++

### 網站中可能用於鎖定目標的重要文字，應該放在元素的 HTML 程式碼內。

+++詳細資料
例如，如果您的程式碼如下，就無法在VEC中鎖定購物車文字：

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

在此範例中，會在VEC中選取整個錨點元素，而執行鎖定目標會對其他元素造成負面影響。

+++

### 請勿在JavaScript程式碼中使用`top`或`self`變數。

+++詳細資料
[!UICONTROL Enhanced Experience Composer]啟用時，top和self變數的值會更新，以停用iframe爆破。 使用 X-frame-options 標頭來新增 iframe 爆破，而非自訂 JavaScript 程式碼。

+++

### 如果載入頁面時增加參數，一定要測試網站。

+++詳細資料
例如，為了開啟`www.abc.com`，使用下列URL引數：

`www.abc.com?mboxEdit=1&mboxDisable=1`

這些參數允許在 iframe 中編輯。

新增這類參數之後，請確定網站可以正常載入。

+++

### 確定頁面在 iframe 中正常開啟。

+++詳細資料
關閉網站上的iframe爆破&#39;b5&#39;7b法，並檢查網站是否如預期般在虛擬頁面上的iframe中開啟。 例如：

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

+++

## 注意事項 {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

使用[!UICONTROL Visual Experience Composer]設計活動時，請注意下列警告。

### [!UICONTROL Move]功能不支援z-index。

+++詳細資料
因為沒有z-index功能，被移動的元素無法移至另一個元素上方。 如需詳細資料，請參閱[限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

+++

### 重新排列元素會影響點擊追蹤。

+++詳細資料
如果重新排列標籤為點選追蹤的元素，則重新排列的元素的路徑會變更。 因此，點擊追蹤的對象就變成原始元素重新排列之前所在位置中的元素。

這是因為用於傳送活動內容的程式碼和用於追蹤點擊的程式碼，同時位於傳送至頁面的一段程式碼內。如果您瀏覽至另一個頁面並設定點擊追蹤，則活動內容程式碼和點擊追蹤程式碼都會傳送至該頁面。如果點擊追蹤頁面的頁面結構類似於執行測試的頁面，則測試內容也可能出現在點擊追蹤頁面上。

+++

### 在身為mbox的`<div>`中插入元素可能沒有作用。

+++詳細資料
如果mbox包含選件，如果mbox實作不正確，插入元素可能會顯示為`insertBefore`而非`insertAfter`。

+++

### 編輯父元素和子元素兩者時，請先編輯父元素。

+++詳細資料
如果您在元素上交換影像動作，然後編輯其父元素上的文字或HTML，則可能會發生傳送問題。 最佳工作流程是先編輯父元素，再於子元素上交換影像。

+++

### 無法選取以 mbox 為子元素的頁面元素。

+++詳細資料
例如，如果您的頁面包含：

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

不應在體驗中選取外部div，因為頁面中以硬式編碼撰寫的mbox仍會呼叫[!DNL Target]並收到回應。 此回應會干擾已預定給更大頁面元素的回應。

+++

### 客戶環境中可能會封鎖Proxy IP。

+++詳細資料
如果您在非上線網站上使用[!UICONTROL Enhanced Experienced Composer]，例如預備環境，若網站封鎖RIP，您可能會看到逾時和拒絕存取的錯誤。

+++

## 限制 {#section_F33C2EA27F2E417AA036BC199DD6C721}

使用VEC時，請考量下列限制：

### 正在處理VEC與[!DNL Chrome]擴充功能原則變更的相容性。 {#ext}

+++詳細資料
由於Google Chrome[&#128279;](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}中更新了V3資訊清單原則，在瀏覽器剖析原始DOM之前，擴充功能無法再修改原始DOM。 因此，某些安全性指令碼（例如iframe-busting實作）可能會阻擋頁面在VEC中載入。

為確保相容性，當頁面載入[!DNL Target] iframe內時，應有條件地停用這些指令碼。 透過檢查`window.adobeVecExtension`物件的存在可以安全地完成此程式，此物件是在VEC載入期間由[!DNL Target]插入。

下列程式碼片段是iframe-busting程式碼的範例，這類程式碼會造成網頁無法在VEC中載入：

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

當網頁內嵌於[!DNL Target]中時，可以使用簡單的檢查來進行驗證。 程式碼片段應如下所示：

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

### 您無法將元素移到後面接著CSS屬性的容器之外。

+++詳細資料
元素無法移到後面有CSS屬性的容器之外。

+++

### 您無法選取要重新排列的[!UICONTROL Button]元素。

+++詳細資料
無法直接選取[!UICONTROL Button]個元素來重新排列。 若要啟用重新排列，請將按鈕置於較大的容器內。

+++

### Mbox 上只能使用交換產品建議。

+++詳細資料
不允許在mbox內執行[!UICONTROL Edit Class]和[!UICONTROL Rearrange]等動作。

+++

### 請勿重新排列和移動同一個元素。

+++詳細資料
如果元素已移至其他位置，而您選取父容器並嘗試重新排列子元素，則移動的元素不受影響，並會保留在其所在位置。 重新排列可能不會如預期般地展現。

+++

### [!UICONTROL Change Image]動作不適用於轉盤中的影像。

+++詳細資料
例如，如果您的頁面包含具有六個影像的轉盤，而您想要將影像與轉盤的第二個影像交換，則[!UICONTROL Change Image]動作不會運作。

因應措施是選取父容器並使用[!UICONTROL Edit HTML]動作來編輯轉盤的HTML以更新所需影像的影像來源。

+++

### 在 mbox 中無法調整影像大小。

+++詳細資料
如果您在mbox元素中交換影像，然後嘗試根據mbox元素大小調整該影像的大小，則不允許重新調整大小。

+++

### 交換影像之後，無法選取[!UICONTROL Edit]動作。

+++詳細資料
交換影像之後，無法編輯Scene7 URL。

+++

### 無法編輯具有外部來源的HTML元素。

+++詳細資料
例如：Video、audio標籤、embed、iFrame、frame。

+++

### 如果錨點元素包含純文字或影像標記以外的其他任何項目，則點擊追蹤無法運作。

+++詳細資料
例如，如果元素包含JavaScript，則點選追蹤無法運作。

+++

### 頁面必須接受URL引數，VEC才能運作。

+++詳細資料
有些網站會移除其頁面的任何URL引數。 不過，VEC需要這些引數。

+++

### 在HTML中使用指令碼時，從外部存取的任何變數和函式都應該在window名稱空間下宣告。

+++詳細資料
在頁面載入後，指令碼會在`target.js`的範圍內執行。 因此，無法從指令碼區塊之外存取區域性宣告的任何變數或函式。

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

+++

### 從[!UICONTROL Content]資料庫(Scene7)插入影像並編輯HTML會中斷影像URL。

+++詳細資料
在&#39;customHeaderMessage&#39; div中新增錨點元素，其中包含一些虛擬文字：

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

使用[!UICONTROL Insert Element]動作選取此div，將影像插入為此虛擬文字div的同層級。

插入影像之後，看起來如下:

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

移除虛構文字段。

+++

### VEC中的`customCode`動作不適用於[!DNL Internet Explorer] 8。

+++詳細資料
由於IE8處理指令碼內容時的限制，`target.js`在IE8中不支援此動作。 作為因應措施，如果頁面包含jQuery且在window物件上全域公開，則`target.js`可以使用傳遞`customCode`動作。 請確定已定義`window.jQuery`和`window.jQuery.fn.prepend`。

+++

### 只有在建立體驗的頁面或重新導向的頁面上，才支援點擊追蹤。

+++詳細資料
雖然[!UICONTROL Browse]模式可用於VEC中的點選追蹤，但[!UICONTROL Browse]模式無法用於在頁面上新增點選追蹤。

+++
