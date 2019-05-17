---
description: 當您按一下Visual Experience Composer(CMS)中的頁面元素時，功能表會顯示該元素類型可用的選項。
keywords: 可視化體驗撰寫器選項; 體驗撰寫器選項; 體驗選項; 編輯文字; 編輯 html; 編輯文字/HTML; 編輯背景顏色; 背景顏色; 插入元素; 編輯連結; 連結; 可視化體驗撰寫器連結; 編輯 CSS; 類別; CSS 類別; 交換選件; 選件交換; 交換影像; 影像交換; 移除項目; 項目移除; 隱藏項目; 項目隱藏; 重新排列; 移動元素; 元素移動; 調整元素大小; 元素調整大小; 元素; 展開選取範圍; 導覽至此連結; 導覽連結; 連結導覽; 導覽; 復原; 重做; 復原/重做
seo-description: 當您按一下Adobe Target Visual Experience Composer(CMS)中的頁面元素時，功能表會顯示該元素類型可用的選項。
seo-title: Adobe Target Visual Experience Composer(CMS)選項
solution: Target
title: 可視化體驗撰寫器選項
topic: Standard
uuid: efd672ae-c684-455f-8ec1-0efcfe1e9534
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 可視化體驗撰寫器選項{#visual-experience-composer-options}

當您按一下Visual Experience Composer(CMS)中的頁面元素時，功能表會顯示該元素類型可用的選項。此外，DOM路徑會顯示在頁面底部，讓您輕鬆瀏覽頁面結構。

## CMS選項

各種Visual Experience Composer(CMS)動作都有分組的功能表選項，讓您的工作更快速、更有效率：

![CMS選項選單](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>可用的選項取決於您編輯的活動類型。

### 編輯  

可使用下列選項: 

#### 文字/HTML {#edit-text-html}

變更元素的 HTML 程式碼，例如文字區域、按鈕或連結的文字。

除了 HTML 程式碼，您可以編輯和插入自訂 JavaScript。

針對 A/B 和體驗鎖定目標活動編輯文字和 HTML 時，有數個 RTF 格式選項可供使用。[!UICONTROL ][!UICONTROL ]您可選擇字型、選取字型樣式、變更文字對齊方式，以及其他標準文字格式化選項。修改 HTML 時，您可在 HTML 的程式碼檢視和 RTF 編輯之間切換。

可巢狀內嵌下列HTML標籤：

| 標記 | 允許的巢狀標記 |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

#### 背景色彩

使用檢色器來選取或設定背景顏色。您可以選取一個色票，然後使用 RGB 值或色彩十六進位代碼調整它。檢色器中的紅色 x 可讓背景透明化。

**注意:** 此選項無法供設定了背景影像的元素使用。

#### 樣式

使用 [!UICONTROL 「樣式] 」面板可檢視或編輯所選元素的現有樣式值。您也可以新增其他樣式。

若要存取 [!UICONTROL 「樣式] 」面板，請從CMS中按一下頁面元素，然後按一下 **[!UICONTROL 「編輯]** &gt; **[!UICONTROL 樣式]**」。

[!UICONTROL 「樣式] 」面板會顯示在CMS的右側。面板包含可讓您編輯或新增至選取元素的樣式清單。即時CSS編輯器可讓您檢視變更並新增樣式，如果您習慣使用階層式樣式表(CSS)或從開發人員接收程式碼。

![樣式面板](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

當您套用不同樣式時，您可以按一下 [!UICONTROL 「回復] 」圖示，在您對任何區段進行變更後，按一下 [!UICONTROL 「樣式] 」面板右上角顯示的「回復」圖示。請注意，按一下 [!UICONTROL 「回復] 」圖示會回復目前區段面板上的所有變更。

展開每個區段以編輯或新增樣式，如下所述。若要儲存變更，請按一下面板頂端的「返回」圖示，返回面板的主顯示器，然後按一下 **[!UICONTROL 「儲存]**」。

請注意，主面板上的藍色點和各種區段面板上的每個選項都表示您已變更對應樣式。這可讓您輕鬆地在按一下 [!UICONTROL 「儲存]」前檢閱變更。

>[!NOTE]
>
>您也可以在「CMS」功能表中，快速執行版面變更、背景顏色、調整大小和移動動作。這些選項可當成個別動作使用，或者您可以使用「樣式」功能表，如此處所述。

* **印刷樣式**

   變更元素的印刷樣式。印刷樣式編輯既快速又簡單。

   雖然rich text Editor(Edit Text/HTML)可供微調，但可透過此選項快速執行對整個元素的變更。如果您想要將印刷樣式變更套用到部分文字(而非全文)，請使用 [rich text Editor](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)。

   您可以編輯下列印刷樣式樣式：

   * 字體大小
   * 字體權重
   * 字體樣式
   * 顏色(指定顏色代碼或使用檢色器)
   * 字詞間距
   * 線條高度
   * 文字對齊

* **利潤**

   變更所選元素的邊界。您可以變更左側、右側、底部和頂端邊界。

   按一下每個邊界的下拉式圖示，從下列選項中選擇：

   * 自動
   * 值(拖曳滑桿以設定邊界或指定每個邊界的像素數目)
   邊界支援正面和負值。

   Target也支援其他大小單位，例如rem、pc、em等。如需這些單位的詳細資訊，請參閱 [網頁樣式表CSS提示與秘訣](https://www.w3.org/Style/Examples/007/units.en.html)。

* **填補空間**

   變更選取元素的間距。您可以變更左側、右側、底部和頂端間距。

   拖曳滑桿以設定間距，或指定像素的像素數目。

   Pading支援寬度從Onward縮放。

   Target也支援 [其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em等。

* **邊框**

   按一下面板頂端的邊框圖示，即可變更選取的元素邊框。

   您可以針對每個邊框(上、右、底和左)編輯下列樣式：

   * 邊框樣式(無、隱藏、點狀、虛線、實心或雙重)
   * 邊框顏色(指定顏色代碼或使用檢色器)
   * 邊框寬度(拖曳滑桿以選取邊框寬度或指定寬度)
   邊框支援寬度從Onward縮放。

   Target也支援 [其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em等。

* **位置**

   從目前位置移動選取的元素。您可以變更元素的頂端、底部、向左、向右和 [Z索引](https://www.w3schools.com/cssref/pr_pos_z-index.asp) 位置。

   按一下 [!UICONTROL 「靜態」] 下拉式清單，從下列位置選項中選擇：

   * 靜態
   * 相對
   * 絕對
   * 自黏
   * 已修正
   按一下每個位置的下拉式圖示，從下列選項中選擇：

   * 自動
   * 值(拖曳滑桿以定位元素或指定要移動元素的像素數目)
   位置支援正面和負值。

   Target也支援 [其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em等。

* **大小**

   變更選取的元素寬度和高度。

   按一下 [!UICONTROL 「寬度] 」和 [!UICONTROL 「高度」] 旁邊的下拉式圖示，可從下列選項中選擇：

   * 自動
   * 值(拖曳滑桿以調整元素大小或指定每個維度的像素數目)

* **篩選**

   拖曳滑桿至每個篩選選項或指定所需百分比：

   * Sepia
   * 對比
   * 亮度
   * 灰階等級
   * 模糊
   * 不透明度
   * 反轉
   * 色相旋轉
   * Satiate

* **CSS編輯器**

   如果您習慣使用階層式樣式表(CSS)或從開發人員接收程式碼，即時CSS編輯器可讓您檢視變更並新增樣式。

   「CSS編輯器」會顯示您在「樣式」面板中所做的任何變更。如下圖所示，字體大小、頂端邊框和影像大小已變更：

   ![CSS編輯器及其變更](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   注意上圖中 [!UICONTROL 「印刷樣式」]、 [!UICONTROL 「邊框」]和「 [!UICONTROL 大小] 」選項旁的藍色點。這些點表示您已對這些區段進行變更。如果開啓這些區域面板，您變更的特定選項旁會顯示藍色點。

   [!UICONTROL 如果樣式中預設沒有預設樣式，您可以輸入自己的程式碼]。

   請注意，CSS編輯器只會顯示目前作業的詳細資料。如果您儲存變更然後重新開啓編輯器，則先前變更的詳細資訊不會顯示在編輯器中，即使您再次選取相同的元素亦然。

   >[!Important]
   >
   >您可以使用CSS編輯器套用背景影象，但可能會造成閃爍。部署前先測試您的變更。

#### CSS 類別

指定用於元素的預先定義 CSS 類別。如果選取超過一個元素，請將多個 CSS 類別以空格分隔。

可用於[!UICONTROL 「A/B」]、[!UICONTROL 「自動個人化」]和[!UICONTROL 「多變數測試」]活動。

#### 連結

變更連結中的 URL。

使用「編輯連結」來更新選取器以指向相同的影像元素。不過，不支援連結至不同的影像元素。若要連結至不同的影像元素，請從代碼編輯器刪除原始動作，並使用[!UICONTROL 可視化體驗撰寫器]在其他影像元素上套用動作。

### 插入在前

可使用下列選項: 

#### 影像、HTML和文字

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

#### 影像、HTML和文字

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

Recommendations支援在DIV、區段和文章標記中取代「取代」。

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

#### 移動

在頁面上移動元素。與[!UICONTROL 「重新排列」]選項不同，[!UICONTROL 「移動」]選項不會移動其他元素來為已移動的元素騰出空間。使用方向鍵來微調此移動。(計劃的增強功能: 支援以確定已移動的元素不會隱藏在其他元素之後。)

在某些情況下，例如當 CSS 限制需要元素保留在其上層元素內時，您無法將元素移出其上層之外。

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

## 使用DOM路徑導覽元素 {#dom-path}

當您按一下頁面上的元素時，會顯示「CMS選項」功能表。此外，當您按一下元素時，對應的DOM路徑就會顯示在頁面底部。

![DOM路徑](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

您可以使用DOM路徑快速查看所選元素(類型、ID和類別)的相關資訊，並向上或向下移動DOM路徑以選取所需元素。

當您將滑鼠指標暫留在DOM路徑上時，藍色方塊會反白標示CMS中對應的元素。當您按一下元素時，橘色方塊會反白顯示元素，並依上述說明顯示CMS選項選單。

您可以使用DOM路徑，輕鬆導覽至CMS中的任何父、側邊或子元素。

設定 [點按追蹤](/help/c-activities/r-success-metrics/click-tracking.md)時也可使用DOM路徑功能。