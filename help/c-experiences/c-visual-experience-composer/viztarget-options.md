---
keywords: visual experience composer options;experience composer options;experience options;edit text;edit html;edit text/html;edit background color;background color;insert element;edit link;link;visual experience composer link;edit css class;css class;swap offer;offer swap;swap image;image swap;remove item;item remove;hide item;item hide;rearrange;move element;element move;resize element;element resize;element;expand selection;navigate to this link;navigate link;link navigate;navigate;link;undo;redo;undo/redo
description: 當您在 Adobe Target 可視化體驗撰寫器 (VEC) 中按一下頁面元素時，功能表隨即顯示適用於該元素類型的選項。
title: Adobe Target 可視化體驗撰寫器 (VEC) 選項
feature: vec
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '2403'
ht-degree: 95%

---


# 可視化體驗撰寫器選項{#visual-experience-composer-options}

當您在可視化體驗撰寫器 (VEC) 中按一下頁面元素時，功能表隨即顯示適用於該元素類型的選項。此外，DOM 路徑會顯示在頁面底部，讓您輕鬆導覽頁面結構。

## VEC 選項

各種可視化體驗撰寫器 (VEC) 動作會分組成適當的功能表選項，讓您更快速且更有效率地執行工作:

![VEC 選項功能表](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>可用的選項取決於您編輯的活動類型。

### 編輯  

可使用下列選項: 

#### 文字/HTML {#edit-text-html}

變更元素的 HTML 程式碼，例如文字區域、按鈕或連結的文字。

除了 HTML 程式碼，您可以編輯和插入自訂 JavaScript。

針對 A/B 和體驗鎖定目標活動編輯文字和 HTML 時，有數個 RTF 格式選項可供使用。您可選擇字型、選取字型樣式、變更文字對齊方式，以及其他標準文字格式化選項。修改 HTML 時，您可在 HTML 的程式碼檢視和 RTF 編輯之間切換。

以下是可巢狀的 HTML5 標記:

| 標記 | 允許的巢狀標記 |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

#### 背景色彩

使用檢色器來選取或設定背景顏色。您可以選取一個色票，然後使用 RGB 值或色彩十六進位代碼調整它。檢色器中的紅色 x 可讓背景透明化。

**注意:** 此選項無法供設定了背景影像的元素使用。

#### 樣式 {#styles}

使用[!UICONTROL 樣式]面板檢視或編輯所選元素的現有樣式的值。您也可以新增其他樣式。

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

[!UICONTROL 樣式]面板會顯示在 VEC 的右側。此面板包含可讓您編輯或新增至所選元素的樣式清單。如果您習慣使用階層式樣式表 (CSS) 或如果您收到來自開發人員的程式碼，即時 CSS 編輯器可讓您檢視變更及新增樣式。

![樣式面板](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

當您套用不同的樣式時，在您對任何區段進行變更後，只要按一下顯示於[!UICONTROL 樣式]面板右上角的[!UICONTROL 還原]圖示，即可隨時還原變更。請注意，按一下[!UICONTROL 還原]圖示會還原目前區段面板上的所有變更。

展開每個區段以編輯或新增樣式 (如下所述)。若要儲存變更，請按一下面板頂端的返回圖示以返回面板的主要顯示，然後按一下&#x200B;**[!UICONTROL 儲存]**。

請注意，主要面板上以及各個區段面板的每個選項旁會顯示藍點，代表您已對對應的樣式做出變更。這可讓您在按一下[!UICONTROL 儲存]前輕鬆檢閱變更。

>[!NOTE]
>
>版面變更、背景顏色、調整大小和移動的快速動作在 VEC 功能表中也有個別的動作可供使用。這些選項能以個別的動作運用，或者您也可以按照此處所述使用樣式功能表。

* **背景**

   變更背景顏色和影像。

   * 顏色 (指定顏色代碼或使用檢色器)
   * 影像 (從影像選擇器選取影像)
   * 影像來源 (指定外部 URL)
   * 附件
      * 按一下頂端的下拉式清單，選取捲動、固定或本機
      * 按一下底部的下拉式清單，選取重複、重複 x、重複 y、不重複、空格或圓角
   * 片段
      * 按一下頂端的下拉式清單，選取邊框方塊、邊框間距方塊、內容方塊或文字
      * 按一下底部的下拉式清單，選取自動音訊或音訊

* **印刷樣式**

   變更元素的印刷樣式。印刷樣式編輯既快速又簡單。

   雖然 RTF 編輯器 (編輯文字/HTML) 可供進行微調使用，仍可透過此選項使用對整個元素進行變更的快速動作。如果您只要將印刷樣式變更套用至局部文字 (而非全部文字)，請使用 [RTF 編輯器](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)。

   您可以編輯下列印刷樣式:

   * 字型大小
   * 字型寬度
   * 字型樣式
   * 顏色 (指定顏色代碼或使用檢色器)
   * 文字間距
   * 行高
   * 文字對齊方式

* **利潤**

   變更所選元素的邊界。您可以變更上、下、左、右邊界。

   按一下每個邊界的下拉式圖示，以從下列選項中選擇:

   * 自動
   * 值 (拖曳滑桿以設定邊界，或指定每個邊界的像素數量)

   邊界支援正值和負值。

   Target 也支援其他大小單位，例如 rem、pc、em 等。For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **邊框間距**

   變更所選元素的邊框間距。您可以變更上、下、左、右邊框間距。

   拖曳滑桿以設定邊框間距，或為邊框間距指定像素數量。

   邊框間距支援 0 以上的寬度刻度。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **邊框**

   按一下面板頂端的邊框圖示，以變更所選元素的邊界。

   您可以編輯每個邊框的以下樣式 (上、下、左和右):

   * 邊框樣式 (無、隱藏、點狀、虛線、實心或雙線)
   * 邊框顏色 (指定顏色代碼或使用檢色器)
   * 邊框寬度 (拖曳滑桿以選取邊框寬度，或以像素指定寬度)

   邊框支援 0 以上的寬度刻度。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **位置**

   從所選元素的目前位置移動該元素。You can change the element&#39;s top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

   按一下[!UICONTROL 靜態]下拉式清單，以從下列位置選項中選擇:

   * 靜態
   * 相對
   * 絕對
   * 自黏
   * 固定

   按一下每個位置的下拉式圖示，以從下列選項中選擇:

   * 自動
   * 值 (拖曳滑桿以設定元素位置，或指定您要移動元素的像素數量)

   位置支援正值和負值。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **大小**

   變更所選元素的寬度和高度。

   按一下[!UICONTROL 寬度]和[!UICONTROL 高度]旁邊的下拉式圖示，以從下列選項中選擇:

   * 自動
   * 值 (拖曳滑桿以調整元素大小，或指定每個維度的像素數量)

* **篩選**

   拖曳每個篩選器選項的滑桿，或指定想要的百分比:

   * 復古
   * 對比
   * 亮度
   * 灰階
   * 模糊
   * 不透明度
   * 反轉
   * 色調旋轉
   * 飽和

* **CSS 編輯器**

   如果您習慣使用階層式樣式表 (CSS) 或如果您收到來自開發人員的程式碼，即時 CSS 編輯器可讓您檢視變更及新增樣式。

   CSS 編輯器會在樣式面板中顯示您所做的任何變更。如下圖所示，已變更字型大小、上邊框和影像大小:

   ![含有變更的 CSS 編輯器](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   請注意上圖[!UICONTROL 印刷樣式]、[!UICONTROL 邊框]和[!UICONTROL 大小]選項旁邊的藍點。這些點代表您已變更這些區段。如果您開啟這些區段面板，藍點會顯示在您已變更的特定選項旁邊。

   如果您想要的樣式無法依預設在[!UICONTROL 樣式]中取得，您可以輸入自己的程式碼。

   請注意，CSS 編輯器只會顯示目前工作階段的詳細資料。如果您儲存變更然後重新開啟編輯器，即使您再次選取相同的元素，先前變更的相關詳細資料也不會顯示在編輯器中。

   >[!IMPORTANT]
   >
   >您可以使用 CSS 編輯器套用背景影像，但可能會導致忽隱忽現的情形。請在部署前測試您的變更。

#### CSS 類別

指定用於元素的預先定義 CSS 類別。如果選取超過一個元素，請將多個 CSS 類別以空格分隔。

可用於[!UICONTROL 「A/B」]、[!UICONTROL 「自動個人化」]和[!UICONTROL 「多變數測試」]活動。

#### 連結

變更連結中的 URL。

使用「編輯連結」來更新選取器以指向相同的影像元素。不過，不支援連結至不同的影像元素。若要連結至不同的影像元素，請從代碼編輯器刪除原始動作，並使用[!UICONTROL 可視化體驗撰寫器]在其他影像元素上套用動作。

### 插入在前

可使用下列選項: 

#### 影像、HTML 和文字

除了修改現有內容以外，新增任何類型的元素至您的頁面。新增文字、代碼、清單和更多內容來建立完全不同的體驗進行測試。

在頁面上選取元素，然後按一下[!UICONTROL 「插入在前」]，並選擇您要插入影像、HTML 或文字。插入的元素會出現在選取的元素之前。

所插入元素的行為取決於頁面、CSS 和其他頁面組態選項的結構。需要 HTML 才能讓您的頁面正確出現。在插入項目之後，請一律測試您的頁面，以確定它能如預期般顯示。

[!UICONTROL 「建議」]支援[!UICONTROL 「插入在前」]功能，可在 DIV、SECTION 和 ARTICLE 標籤的內容前插入。

**注意:** 插入影像需要啟用 [!DNL Adobe Scene7 Publishing System] 發佈系統，這樣您才會具備影像資料庫的存取權。

#### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以選件方式使用 Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)。

#### 體驗片段

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)。

### 插入在後

可使用下列選項: 

#### 影像、HTML 和文字

除了修改現有內容以外，新增任何類型的元素至您的頁面。新增文字、代碼、清單和更多內容來建立完全不同的體驗進行測試。

在頁面上選取元素，然後按一下[!UICONTROL 「插入在後」]，並選擇您要插入影像、HTML 或文字。插入的元素會出現在選取的元素之後。

所插入元素的行為取決於頁面、CSS 和其他頁面組態選項的結構。需要 HTML 才能讓您的頁面正確出現。在插入項目之後，請一律測試您的頁面，以確定它能如預期般顯示。

[!UICONTROL 「Recommendations」]支援[!UICONTROL 「插入在後」]功能，可在 DIV、SECTION 和 ARTICLE 標籤的內容後插入。

**注意:** 插入影像需要啟用 [!DNL Adobe Scene7 Publishing System] 發佈系統，這樣您才會具備影像資料庫的存取權。

#### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以選件方式使用 Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)。

#### 體驗片段

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)。

### 取代為

可使用下列選項: 

#### 影像

從內容庫選取不同的影像。可用於交換的影像包括上傳至 Experience Cloud 資產資料夾或上傳在 Target 內容庫中的影像。

在初始活動建立期間，顯示的 URL 不是用於傳遞的 URL。在活動同步時，該 URL 會更新為生產 Scene7 URL。

例如，初始 URL 看起來可能如以下範例:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

活動同步之後，傳送 URL 看起來可能如以下範例:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations 在 DIV、SECTION 和 ARTICLE 標記中可支援「取代為」。

**注意:** 交換影像需要 Adobe Scene7 發佈系統帳戶。

#### HTML 選件

從[!UICONTROL 「內容資料庫」]選取不同的選件。

**注意:**[!DNL Target] HTML 選件會儲存在 伺服器上。

HTML 選件的大小最多可以是 256KB。

#### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以選件方式使用 Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)。

#### 體驗片段

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)。

### 配置

可使用下列選項: 

#### 重新排列

將元素拖曳到相同上層元素內的另一個位置或 DIV。其他元素會移動位置，為重新排列的元素騰出空間。

**注意:** 點擊追蹤對重新排列的項目沒有作用。

#### 調整大小

在您的頁面上調整元素的大小。選取[!UICONTROL 「調整大小」]時，元素的右下角便會出現控點，可讓您拖曳該角進行大小調整。按住 Shift 鍵來保持相同的外觀比例。

**注意:** 不能對行內元素調整大小。

#### 移動 {#move}

在頁面上移動元素。與[!UICONTROL 「重新排列」]選項不同，[!UICONTROL 「移動」]選項不會移動其他元素來為已移動的元素騰出空間。使用方向鍵來微調此移動。(計劃的增強功能: 支援以確定已移動的元素不會隱藏在其他元素之後。)

在某些情況下，例如當 CSS 限制需要元素保留在其上層元素內時，您無法將元素移出其上層之外。元素無法移到有下列 CSS 屬性的容器之外: `overflow: hidden`。

#### 隱藏

隱藏元素。白色空間會保留，但移除內容。

#### 移除

移除元素。影像背後的白色空間會移除，而元素所在位置的空間會折疊。

**注意:** 您無法使用此選項移除 &quot;classic&quot; mbox 內的項目 (在 Target Classic 促銷活動內建立的 mbox)。

### 展開區段

除了原始選取的元素以外，請選取上層元素。選取任何上層元素時，系統會自動選取該元素的所有下層。您可以展開選取範圍多次。

### 導覽至連結

開啟連結的目的地。

### 還原/取消復原

在編輯工作階段期間，還原您對活動所進行的變更。您也可以重做先前已還原的變更。

## 考量事項 {#considerations}

* 如果選件包含 HTML 內容，請參閱 [at.js 如何運作](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render)中的「at.js 如何呈現具有 HTML 內容的選件」以取得詳細資訊。

## 使用 DOM 路徑導覽元素 {#dom-path}

當您按一下頁面上的元素時，VEC 選項功能表隨即顯示。此外，當您按一下元素時，對應的 DOM 路徑會顯示於頁面底部。

![DOM 路徑](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

您可以使用 DOM 路徑快速查看有關已選取元素 (類型、ID 和類別) 的資訊，然後向上或向下移動 DOM 路徑以選取想要的元素。

當您將游標暫留在 DOM 路徑上方時，藍色方塊隨即醒目提示 VEC 中的對應元素。當您按一下元素時，橘色方塊隨即醒目提示元素且 VEC 選項功能表隨即顯示 (如上所述)。

您可以使用 DOM 路徑，輕鬆導覽至 VEC 中的任何父項、同層級項目或子項元素。

設定[點擊追蹤](/help/c-activities/r-success-metrics/click-tracking.md)時，也可使用 DOM 路徑功能。