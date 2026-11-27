---
keywords: 可視化體驗撰寫器; 可視化體驗撰寫器最佳作法; 可視化體驗撰寫器限制; 可視化體驗撰寫器警告; VEC 最佳作法; VEC
description: 瞭解使用[!UICONTROL 視覺化體驗撰寫器] (VEC)時，讓您的體驗如預期運作的最佳實務。
title: '[!UICONTROL 視覺化體驗撰寫器]有哪些最佳作法和限制？'
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
TQID: 'https://experienceleague.adobe.com/upZDSyuS9VqUmYskNXrlYazhwRHmZGBpSR-cR-qliRs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '2420'
ht-degree: 8%
---
# [!UICONTROL 視覺化體驗撰寫器]最佳作法和限制 {#vec-best-practices}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)中建立體驗時應注意的最佳實務、警告和限制。

>[!ENDSHADEBOX]

遵循這些實務有助於依照預期在[!DNL Adobe Target] **[!UICONTROL 視覺化體驗撰寫器]** (VEC)函式中建立的體驗。 警告和限制說明可能會導致常見問題的行為，因此瞭解這些行為有助於避免問題並維持效能。

## 最佳做法 {#best-practices}

使用VEC時，適用下列作法。

### 啟用[!UICONTROL 增強體驗撰寫器] {#enable-eec}

**[!UICONTROL 增強體驗撰寫器]**&#x200B;可在帳戶層級啟用，以便針對在帳戶中建立的所有活動或個別活動層級啟用。

* **帳戶層級：**&#x200B;按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 視覺化體驗撰寫器]**，然後將&#x200B;**[!UICONTROL 啟用增強體驗撰寫器]**&#x200B;切換至「開啟」位置。
* **活動層級：**&#x200B;在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;中建立活動時，按一下&#x200B;**[!UICONTROL 設定]** > **[!UICONTROL 頁面傳送]**，然後將&#x200B;**[!UICONTROL 啟用增強體驗撰寫器]**&#x200B;切換至「開啟」位置。

### 頁面設定和載入

+++ 將at.js參考置於頁面`<head>`區段的頂端。

如果也使用了&#x200B;**[!UICONTROL 訪客API服務]**，請將訪客API指令碼放在at.js上方。

+++

+++ 如果[!UICONTROL 增強體驗撰寫器]未在網站的安全頁面上載入，允許列出IP位址。

將用於&#x200B;**[!UICONTROL 增強體驗撰寫器]** Proxy的[!DNL Adobe]伺服器IP位址加入允許清單，可解決載入問題。 這些IP位址只有在活動編輯時才需要。 網站的訪客不需要將它們加入允許清單。 IP位址列在[EEC不會載入無法於公用IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#eec-ip-addresses)存取的內部QA URL *疑難排解增強體驗撰寫器的相關問題*。

+++

+++ 請勿在網站中使用base標籤來解析URL和連結。

VEC （包括&#x200B;**[!UICONTROL 增強體驗撰寫器]**）會透過Proxy伺服器在幕後操控網站，該伺服器會更新所有連結URL，讓它們在Proxy中運作。 如果新增base標籤，瀏覽器會再次解析這些URL，所以看起來會損毀。

+++

+++ 請勿在JavaScript程式碼中使用`top`或`self`變數。

啟用&#x200B;**[!UICONTROL 增強體驗撰寫器]**&#x200B;時，`top`和`self`變數的值會更新以停用iframe爆破。 使用X-Frame-Options標頭來新增iframe爆破，而非自訂JavaScript程式碼。

+++

+++ 如果頁面載入時新增引數，一定要測試網站。

例如，下列URL引數是用來開啟`www.abc.com`，以便在iframe中編輯：

`www.abc.com?mboxEdit=1&mboxDisable=1`

新增此類引數後，請確定網站如預期般載入。

+++

+++ 請確定頁面在iframe中正常開啟。

關閉網站上的iframe爆破技巧，並檢查網站是否如預期般在虛擬頁面上的iframe中開啟。 例如：

```html
<!DOCTYPE html>
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

### 頁面標籤

+++ 對於最上層元素，以及任何測試或定位較好候選者的其他元素，請使用唯一的ID。

緊接在body元素內的任何專案都應具有唯一的ID，以便在將新元素插入主體及程式碼四處移動時，至少要輕鬆辨識父元素。

[!DNL Target]不需要ID，但ID會提高使用體驗撰寫器建立之體驗的可靠性。 [!DNL Target]在傳遞體驗時使用CSS選取器修改內容。 編輯體驗時，**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;會將選取器錨定至具有非Null ID屬性的已修改HTML元素的最近祖項。 因此，我們不建議您使用任何機制（包括JavaScript程式庫）來設定或修改HTML ID屬性。 這些ID在建立活動時可供體驗撰寫器使用，但如果JavaScript加以修改，則建立時使用的ID在體驗執行時可能無法使用。 如果ID無法使用，錨定至該ID的選擇器就會失敗。

+++

+++ 使用描述性CSS類別名稱。

在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;中編輯CSS類別時，描述性類別名稱可讓您輕鬆識別類別。 這有助於確保編輯正確的CSS類別，且頁面能如預期般顯示。

+++

+++ 隱藏或移除元素時，請勿使用`!important` CSS屬性。

如果`!important` CSS屬性存在，則網站的CSS規則會覆寫`target.js`在傳遞期間所做的變更。

+++

+++ 避免使用HTML表格作為頁面配置。

[!DNL Target]使用JavaScript來格式化頁面，而使用JavaScript很難修改以表格為基礎的版面。 表格式版面配置在所有瀏覽器中的顯示方式可能也不相同。 為了獲得最佳結果，請使用 CSS 來建立頁面配置。

+++

+++ 儘量不使用 iFrame。

最小化iFrame可簡化頁面和測試管理。 **[!UICONTROL 視覺化體驗撰寫器]**&#x200B;可以在iFrame中套用某些動作，但某些動作（例如調整大小）無法正常運作。 使用多個iFrame的頁面難以管理和調整大小，因此測試iFrame密集型頁面可能會造成問題。

+++

+++ 在錨點元素中僅使用純文字或影像標籤。

錨點元素包含純文字：

`<a>Anchor Text</a>`

或影像標籤：

`<a href=""> <img src=""> </img> </a>`

+++

+++ 在內嵌元素內避免有區塊層級元素。

區塊層級元素不應該用於內嵌元素內，例如錨點和跨距元素。 這樣做會導致內嵌元素失去其高度和寬度，因此&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;中的覆蓋圖工具可能無法如預期運作。

+++

+++ 移除表單欄位時請小心。

提交時某些表單欄位可能是必填欄位，因此移除這些欄位可能會影響提交。

+++

+++ 將可能用於在HTML程式碼中鎖定目標的重要文字保留在元素內。

例如，如果程式碼如下，則無法在VEC中鎖定購物車文字：

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart">
   <img alt="Shopping Cart" src="/images/ico-cart.gif"></img>
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

### 編輯和傳遞

+++ 在DOM準備就緒後儘快排列所有DOM修改。

如果在`target.js`套用體驗之前修改無法套用，內容傳送可能會中斷。 只有當目標元素的階層中出現 DOM 變更時，才會發生此狀況。

+++

+++ 使用「編輯HTML」來操控DOM結構可能會破壞選取器。

例如，會執行兩個動作：

* 類別會新增至元素1。
* 會編輯元素1的HTML。

每次變更都會在VEC中建立新元素。 第二個動作會修改元素1，因此如果元素1被刪除，第二個動作便沒有任何專案需要修改，且變更不再有作用。

同樣地，如果元素是以文字和個別動作新增，接著又以不同文字編輯該元素，則程式碼編輯器會將這兩個動作顯示為個別的元素。 編輯會建立可修改原始元素並包含已編輯文字的新元素。 如果隨後刪除了原始元素，則編輯的文字將找不到要修改的元素且不會顯示。 第二個元素會保留在元素清單中，但因為變更的元素已不存在，所以對頁面沒有影響。

檢視&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;[&#128279;](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#vec-selectors)中使用的元素選取器。

+++

+++ 透過RTF編輯器來設計文字元素的樣式時，請使用`<b>`和`<i>`標籤。

* 對於粗體文字，請使用 `<b>` 而非 `<strong>`。
* 對於斜體文字，請使用 `<i>` 而非 `<em>`。

`<strong>`和`<em>`標籤可能會造成非預期的結果。

+++

+++ 請勿在指令碼內包含`mboxCreate`。

`mboxCreate`使用`document.write`，因此不建議將其包含在指令碼中。 將`mboxDefine`和`mboxUpdate`用於相同目的。

+++

+++ 如果程式碼片段需要HTML程式碼才能初始化，請勿使用[!DNL Target]更新JavaScript程式碼片段。

在滑桿和浮動視窗等頁面元件上執行動作（編輯HTML）時，傳送可能會顯示為已中斷。 VEC會在JavaScript例項化頁面元件後執行動作。 但是，當頁面內容傳送給訪客時，動作會在元件例項化之前套用。 因此，元件的功能在傳送時可能會中斷，也可能不會，端視頁面上定義元件的指令碼而定。

首次生效的傳遞測試無法保證傳遞持續運作，因為可能存在競爭條件：

* 如果有競爭條件，傳送會間歇性運作。
* 如果沒有競爭條件，傳送一律有效。

多次測試頁面，確保傳送可如預期般運作。

+++

## 注意事項 {#caveats}

使用&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;設計活動時，請注意下列事項。

+++ [!UICONTROL 移動]功能不支援z-index。

如果沒有z-index功能，被移動的元素就無法置於另一個元素上方。 如需詳細資料，請參閱[限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

+++

+++ 重新排列元素會影響點擊追蹤。

如果重新排列標籤為點選追蹤的元素，則重新排列的元素的路徑會變更。 因此，系統會在元素上追蹤原始元素重新排列前所在位置的點按。

發生此狀況是因為傳送活動內容的程式碼和追蹤點按的程式碼會包含在傳送至頁面的程式碼片段中。 如果瀏覽不同的頁面並在那裡設定點選追蹤，則兩個程式碼片段都會傳送到該頁面。 如果點選追蹤頁面的頁面結構與測試執行所在頁面的頁面結構類似，則測試內容可能也會出現在點選追蹤頁面上。

+++

+++ 在身為mbox的`<div>`中插入元素可能沒有作用。

如果mbox包含選件且mbox未正確實作，則插入的元素可能會顯示為`insertBefore`，而不是顯示為`insertAfter`。

+++

+++ 同時編輯父元素和子元素時，請先編輯父元素。

如果在元素上交換影像動作，然後編輯其父元素的文字或HTML，則可能會發生傳送問題。 最佳工作流程是先編輯父元素，再於子元素上交換影像。

+++

+++ 請勿選取以mbox為子元素的頁面元素。

例如，如果頁面包含下列程式碼：

```html
<div>
  <div class="mboxDefault" >
  </div>
  <script>mboxCreate('myMbox');
</script>
</div>
```

不應在體驗中選取外部div，因為頁面中以硬式編碼撰寫的mbox仍會呼叫[!DNL Target]並接收回應。 此回應會干擾已預定給更大頁面元素的回應。

+++

+++ 客戶環境中可能會封鎖Proxy IP位址。

如果在非上線網站上使用&#x200B;**[!UICONTROL 增強體驗撰寫器]** （例如中繼環境），如果網站封鎖Proxy IP位址，可能會發生逾時和拒絕存取錯誤。

+++

## 限制 {#section_F33C2EA27F2E417AA036BC199DD6C721}

下列限制適用於使用VEC。

### 頁面需求

+++ 處理VEC與[!DNL Chrome]擴充功能原則變更的相容性。

在Google Chrome[&#128279;](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}中更新的V3資訊清單原則下，擴充功能在瀏覽器剖析原始DOM之前，無法再加以修改。 因此，某些安全性指令碼（例如iframe-busting實作）可能會阻擋頁面在VEC中載入。

為確保相容性，當頁面載入[!DNL Target] iframe內時，有條件地停用這些指令碼。 可透過檢查是否存在`window.adobeVecExtension`物件安全地完成此操作，當VEC載入時，[!DNL Target]會插入該物件。

下列程式碼片段屬於iframe-busting程式碼的範例，可防止網頁在VEC中載入：

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

簡單檢查可驗證網頁是否內嵌於[!DNL Target]中。 程式碼片段如下所示：

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

+++ 頁面必須接受URL引數，VEC才能運作。

有些網站會從頁面中移除任何URL引數，但VEC需要這些引數。

+++

+++ 當指令碼用作HTML的一部分時，請在視窗名稱空間下宣告從外部存取的任何變數和函式。

在頁面載入後，指令碼會在`target.js`的範圍內執行，因此任何在本機宣告的變數或函式無法從指令碼區塊外部存取。

*不正確:*

```html
<script>
  var myVar = 123;
  function myFunc() {
    //
  }
</script>
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

+++ VEC中的`customCode`動作不適用於[!DNL Internet Explorer] 8。

由於IE8處理指令碼內容時的限制，`target.js`在IE8中不支援此動作。 作為因應措施，如果頁面包含jQuery且jQuery在視窗物件上全域公開，則`target.js`可以傳遞`customCode`動作。 確定已定義`window.jQuery`和`window.jQuery.fn.prepend`。

+++

### 重新排列和mbox

**元素無法移到後面有CSS屬性的容器之外。**

+++ 無法選取[!UICONTROL Button]元素來重新排列。

無法直接選取&#x200B;**[!UICONTROL Button]**&#x200B;元素來重新排列。 若要啟用重新排列，請將按鈕置於較大的容器內。

+++

+++ 請勿重新排列和移動相同的元素。

如果元素已移至其他位置，然後選取父容器來重新排列子元素，則移動的元素不受影響，並會保留在其所在位置。 重新排列可能不會如預期般地展現。

+++

+++ Mbox 上只能使用交換產品建議。

不允許在mbox內執行&#x200B;**[!UICONTROL Edit Class]**&#x200B;和&#x200B;**[!UICONTROL Rearrange]**&#x200B;等動作。

+++

### 影像

+++ [!UICONTROL 變更影像]動作不適用於轉盤中的影像。

例如，如果頁面包含具有六個影像的轉盤，而影像要與轉盤的第二個影像交換，則&#x200B;**[!UICONTROL 變更影像]**&#x200B;動作不會運作。

暫行解決方法是選取父容器並使用&#x200B;**[!UICONTROL 編輯HTML]**&#x200B;動作來編輯轉盤的HTML並更新所需影像的影像來源。

+++

+++ 在 mbox 中無法調整影像大小。

如果影像在mbox元素中交換，然後根據mbox元素的大小來調整大小，則不允許重新調整大小。

+++

+++ 交換影像之後，無法選取[!UICONTROL 編輯]動作。

交換影像後，無法編輯Scene7 URL。

+++

+++ 從[!UICONTROL Content]資料庫(Scene7)插入影像並編輯HTML會中斷影像URL。

在`customHeaderMessage` div中新增錨點專案，其中包含一些虛擬文字：

```html
<a href="#">
<span> Dummy text </span>
</a>
```

使用&#x200B;**[!UICONTROL Insert Element]**&#x200B;動作Select此div，將影像插入為虛擬文字的同層級。

插入影像後，程式碼看起來像這樣：

```html
<a href="#">
<span> Dummy text </span>
<img src=""> This is inserted Image. </img>
</a>
```

移除虛構文字段。

+++

### 點選追蹤和外部內容

+++ 如果錨點元素包含純文字或影像標記以外的其他任何項目，則點擊追蹤無法運作。

例如，假如元素包含 JavaScript，則點擊追蹤無法運作。

+++

+++ 只有在建立體驗的頁面或重新導向的頁面上，才支援點擊追蹤。

雖然&#x200B;**[!UICONTROL 瀏覽]**&#x200B;模式可用於VEC中的點選追蹤，但&#x200B;**[!UICONTROL 瀏覽]**&#x200B;模式無法用於在頁面上新增點選追蹤。

+++

+++ 無法編輯具有外部來源的HTML元素。

例如：video、audio標籤、embed、iFrame和frame。

+++
