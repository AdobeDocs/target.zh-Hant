---
keywords: 可視體驗作曲家選項；經驗編輯選項；編輯文本；編輯文本/html；編輯背景顏色；插入連結；連結；連結；可視體驗合成器連結；編輯類；css類；交換圖；換行圖；移除項；移除項；移除項；移除項；移動項；元素；調整元素；展開選擇；連結導航；導航；連結；撤消；重做；撤消/重做；自定義事件；Web元件；提供決策；offer decisioning
description: 瀏覽中的選項 [!DNL Adobe Target] [!UICONTROL 視覺體驗作曲家] (VEC)。
title: 如何使用 [!UICONTROL 視覺體驗作曲家] (VEC)選項？
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: 20db97843e2b60f3186d46f7b70d2b2bc35acaf4
workflow-type: tm+mt
source-wordcount: '2907'
ht-degree: 63%

---

# 可視化體驗撰寫器選項

按一下 [!DNL Adobe Target] [!UICONTROL 視覺體驗作曲家] (VEC)，菜單顯示可用於該元素類型的選項。 此外，DOM 路徑會顯示在頁面底部，讓您輕鬆導覽頁面結構。

各種 [!UICONTROL 視覺體驗作曲家] (VEC)操作將在相應的菜單選項中分組，以便更快、更高效地執行作業：

![VEC 選項功能表](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>可用選項取決於您正在建立或編輯的活動類型。

## [!UICONTROL 編輯]

可使用下列選項: 

### [!UICONTROL 文字/HTML] {#edit-text-html}

變更元素的 HTML 程式碼，例如文字區域、按鈕或連結的文字。

除了 HTML 程式碼，您可以編輯和插入自訂 JavaScript。

針對 A/B 和體驗鎖定目標活動編輯文字和 HTML 時，有數個 RTF 格式選項可供使用。您可選擇字型、選取字型樣式、變更文字對齊方式，以及其他標準文字格式化選項。修改 HTML 時，您可在 HTML 的程式碼檢視和 RTF 編輯之間切換。

以下是可巢狀的 HTML5 標記:

| 標記 | 允許的巢狀標記 |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`。 `<ol>`。 `<menu>`。 `<h1-h6>`。 `<p>` |
| `<label>` | `<p>` |

### [!UICONTROL 背景色彩]

使用檢色器來選取或設定背景顏色。您可以選取一個色票，然後使用 RGB 值或色彩十六進位代碼調整它。檢色器中的紅色 x 可讓背景透明化。

**注意:** 此選項無法供設定了背景影像的元素使用。

### [!UICONTROL 樣式] {#styles}

使用[!UICONTROL 樣式]面板檢視或編輯所選元素的現有樣式的值。您也可以新增其他樣式。

訪問 [!UICONTROL 樣式] 面板，按一下VEC內的頁面元素，然後按一下 **[!UICONTROL 編輯]** > **[!UICONTROL 樣式]**。

[!UICONTROL 樣式]面板會顯示在 VEC 的右側。此面板包含可讓您編輯或新增至所選元素的樣式清單。如果您習慣使用階層式樣式表 (CSS) 或如果您收到來自開發人員的程式碼，即時 CSS 編輯器可讓您檢視變更及新增樣式。

![樣式面板](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

在應用不同樣式時，您始終可以通過按一下 [!UICONTROL 還原] 表徵圖，顯示在 [!UICONTROL 樣式] 的子菜單。 按一下 [!UICONTROL 還原] 表徵圖將恢復當前部分面板上的所有更改。

展開每個區段以編輯或新增樣式 (如下所述)。要保存更改，請按一下 [!UICONTROL 後退] 表徵圖，返回面板的主顯示，然後按一下 **[!UICONTROL 保存]**。

主面板上的藍點以及各個截面面板上每個選項旁邊的藍點表示您已更改了相應樣式。 此可視指示器使您在按一下前可以輕鬆查看更改 [!UICONTROL 保存]。

>[!NOTE]
>
>版面變更、背景顏色、調整大小和移動的快速動作在 VEC 功能表中也有個別的動作可供使用。這些選項可用作單獨的操作，也可以使用「樣式」菜單，如此處所述。

* **[!UICONTROL 背景]**

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

* **[!UICONTROL 印刷樣式]**

   變更元素的印刷樣式。印刷樣式編輯既快速又簡單。

   儘管富格文本編輯器(「編輯文本/HTML」)可用於微調，但通過此選項可以執行快速操作來更改整個元素。 如果您只要將印刷樣式變更套用至局部文字 (而非全部文字)，請使用 [RTF 編輯器](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)。

   您可以編輯下列印刷樣式:

   * [!UICONTROL 字型大小]
   * [!UICONTROL 字型寬度]
   * [!UICONTROL 字型樣式]
   * [!UICONTROL 顏色] （指定顏色代碼或使用顏色選取器）
   * [!UICONTROL 文字間距]
   * [!UICONTROL 行高]
   * [!UICONTROL 文字對齊方式]

* **[!UICONTROL 利潤]**

   變更所選元素的邊界。您可以變更上、下、左、右邊界。

   按一下每個邊界的下拉式圖示，以從下列選項中選擇:

   * [!UICONTROL 自動]
   * [!UICONTROL 值] （拖動滑塊設定邊距或指定每個邊距的像素數）

   邊界支援正值和負值。

   Target還支援其他大小單位，如rem、pc和em。 有關這些設備的詳細資訊，請參見 [Web樣式表CSS提示和技巧](https://www.w3.org/Style/Examples/007/units.en.html)。

* **[!UICONTROL 邊框間距]**

   變更所選元素的邊框間距。您可以變更上、下、左、右邊框間距。

   拖曳滑桿以設定邊框間距，或為邊框間距指定像素數量。

   邊框間距支援 0 以上的寬度刻度。

   目標還支援 [其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，如rem 、 pc 、 em。

* **[!UICONTROL 邊框]**

   按一下面板頂端的邊框圖示，以變更所選元素的邊界。

   您可以編輯每個邊框的以下樣式 (上、下、左和右):

   * [!UICONTROL 邊框樣式] （無、隱藏、虛線、虛線、實線或雙線）
   * [!UICONTROL 邊框顏色] （指定顏色代碼或使用顏色選取器）
   * [!UICONTROL 邊框寬度] (拖動滑塊以選擇邊框寬度或指定寬度（以像素為單位）

   邊框支援 0 以上的寬度刻度。

   目標還支援 [其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，如rem 、 pc 、 em。

* **[!UICONTROL 位置]**

   從所選元素的目前位置移動該元素。可以更改元素的頂部、底部、左側、右側和 [Z指數](https://www.w3schools.com/cssref/pr_pos_z-index.asp) 位置。

   按一下[!UICONTROL 靜態]下拉式清單，以從下列位置選項中選擇:

   * [!UICONTROL 靜態]
   * [!UICONTROL 相對]
   * [!UICONTROL 絕對]
   * [!UICONTROL 自黏]
   * [!UICONTROL 固定]

   按一下每個位置的下拉式圖示，以從下列選項中選擇:

   * [!UICONTROL 自動]
   * [!UICONTROL 值] （拖動滑塊以定位元素或指定要移動元素的像素數）

   位置支援正值和負值。

   目標還支援 [其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，如rem 、 pc 、 em。

* **[!UICONTROL 大小]**

   變更所選元素的寬度和高度。

   按一下[!UICONTROL 寬度]和[!UICONTROL 高度]旁邊的下拉式圖示，以從下列選項中選擇:

   * [!UICONTROL 自動]
   * [!UICONTROL 值] （拖動滑塊以調整元素大小或指定每個維的像素數）

* **[!UICONTROL 篩選]**

   拖曳每個篩選器選項的滑桿，或指定想要的百分比:

   * [!UICONTROL 復古]
   * [!UICONTROL 對比]
   * [!UICONTROL 亮度]
   * [!UICONTROL 灰階]
   * [!UICONTROL 模糊]
   * [!UICONTROL 不透明度]
   * [!UICONTROL 反轉]
*
[!UICONTROL  色調旋轉]
   * [!UICONTROL 飽和]

* **[!UICONTROL CSS 編輯器]**

   如果您習慣使用階層式樣式表 (CSS) 或如果您收到來自開發人員的程式碼，即時 CSS 編輯器可讓您檢視變更及新增樣式。

   CSS 編輯器會在樣式面板中顯示您所做的任何變更。如下圖所示，已變更字型大小、上邊框和影像大小:

   ![含有變更的 CSS 編輯器](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   請注意上圖[!UICONTROL 印刷樣式]、[!UICONTROL 邊框]和[!UICONTROL 大小]選項旁邊的藍點。這些點表示您已更改了這些部分。 如果您開啟這些區段面板，藍點會顯示在您已變更的特定選項旁邊。

   如果您想要的樣式無法依預設在[!UICONTROL 樣式]中取得，您可以輸入自己的程式碼。

   CSS編輯器僅顯示當前會話的詳細資訊。 如果您儲存變更然後重新開啟編輯器，即使您再次選取相同的元素，先前變更的相關詳細資料也不會顯示在編輯器中。

   >[!IMPORTANT]
   >
   >您可以使用 CSS 編輯器套用背景影像，但可能會導致忽隱忽現的情形。請在部署前測試您的變更。

### [!UICONTROL CSS 類別]

指定用於元素的預先定義 CSS 類別。如果選取超過一個元素，請將多個 CSS 類別以空格分隔。

可用於[!UICONTROL 「A/B」]、[!UICONTROL 「自動個人化」]和[!UICONTROL 「多變數測試」]活動。

### [!UICONTROL 連結]

變更連結中的 URL。

使用「編輯連結」來更新選取器以指向相同的影像元素。不過，不支援連結至不同的影像元素。若要連結至不同的影像元素，請從代碼編輯器刪除原始動作，並使用[!UICONTROL 可視化體驗撰寫器]在其他影像元素上套用動作。

## [!UICONTROL 插入在前]

可使用下列選項: 

### [!UICONTROL 提供決定]

添加 [建立的提供 [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}，以向使用offer decisioning的客戶提供最佳優惠和體驗。

**注：** 此選項在編輯或建立時可用 [手 [!UICONTROL A/BTest]](/help/main/c-activities/t-test-ab/test-ab.md#types) 或 [[!UICONTROL 體驗目標]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動。 此選項不適用於其他活動類型。

如需詳細資訊，請參閱[使用報價決策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL 影像]。 [!UICONTROL HTML], [!UICONTROL 文本]

除了修改現有內容以外，新增任何類型的元素至您的頁面。新增文字、代碼、清單和更多內容來建立完全不同的體驗進行測試。

在頁面上選取元素，然後按一下[!UICONTROL 「插入在前」]，並選擇您要插入影像、HTML 或文字。插入的元素會出現在選取的元素之前。

所插入元素的行為取決於頁面、CSS 和其他頁面組態選項的結構。需要 HTML 才能讓您的頁面正確出現。在插入項目之後，請一律測試您的頁面，以確定它能如預期般顯示。

[!UICONTROL 「建議」]支援[!UICONTROL 「插入在前」]功能，可在 DIV、SECTION 和 ARTICLE 標籤的內容前插入。

**注意:** 插入影像需要啟用 [!DNL Adobe Scene7 Publishing System] 發佈系統，這樣您才會具備影像資料庫的存取權。

### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以選件方式使用 Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL 體驗片段]

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL 插入在後]

可使用下列選項: 

### [!UICONTROL 提供決定]

添加 [建立的提供 [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}，以向使用offer decisioning的客戶提供最佳優惠和體驗。

**注：** 此選項在編輯或建立時可用 [手 [!UICONTROL A/BTest]](/help/main/c-activities/t-test-ab/test-ab.md#types) 或 [[!UICONTROL 體驗目標]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動。 此選項不適用於其他活動類型。

如需詳細資訊，請參閱[使用報價決策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL 影像]。 [!UICONTROL HTML], [!UICONTROL 文本]

除了修改現有內容以外，新增任何類型的元素至您的頁面。新增文字、代碼、清單和更多內容來建立完全不同的體驗進行測試。

在頁面上選取元素，然後按一下[!UICONTROL 「插入在後」]，並選擇您要插入影像、HTML 或文字。插入的元素會出現在選取的元素之後。

所插入元素的行為取決於頁面、CSS 和其他頁面組態選項的結構。需要 HTML 才能讓您的頁面正確出現。在插入項目之後，請一律測試您的頁面，以確定它能如預期般顯示。

[!UICONTROL 「Recommendations」]支援[!UICONTROL 「插入在後」]功能，可在 DIV、SECTION 和 ARTICLE 標籤的內容後插入。

**注意:** 插入影像需要啟用 [!DNL Adobe Scene7 Publishing System] 發佈系統，這樣您才會具備影像資料庫的存取權。

### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以選件方式使用 Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL 體驗片段]

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL 替換內容]

可使用下列選項: 

### [!UICONTROL 提供決定]

添加 [建立的提供 [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}，以向使用offer decisioning的客戶提供最佳優惠和體驗。

**注：** 此選項在編輯或建立時可用 [手 [!UICONTROL A/BTest]](/help/main/c-activities/t-test-ab/test-ab.md#types) 或 [[!UICONTROL 體驗目標]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動。 此選項不適用於其他活動類型。

如需詳細資訊，請參閱[使用報價決策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL 影像]

從內容庫選取不同的影像。可用於交換的影像包括上傳至 Experience Cloud 資產資料夾或上傳在 Target 內容庫中的影像。

在初始活動建立期間，顯示的 URL 不是用於傳遞的 URL。在活動同步時，該 URL 會更新為生產 Scene7 URL。

例如，初始 URL 看起來可能如以下範例:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

活動同步之後，傳送 URL 看起來可能如以下範例:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations 在 DIV、SECTION 和 ARTICLE 標記中可支援「取代為」。

**注意:** 交換影像需要 Adobe Scene7 發佈系統帳戶。

### [!UICONTROL HTML 選件]

從[!UICONTROL 「內容資料庫」]選取不同的選件。

**注意:**[!DNL Target] HTML 選件會儲存在 伺服器上。

HTML產品最多可達256 KB。

### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以選件方式使用 Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL 體驗片段]

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL 配置]

可使用下列選項: 

### [!UICONTROL 重新排列]

將元素拖曳到相同上層元素內的另一個位置或 DIV。其他元素會移動位置，為重新排列的元素騰出空間。

**注釋**:按一下跟蹤對重新排列的項目不起作用。

當前，某些VEC操作，如 [!UICONTROL 重新排列] 和 [!UICONTROL 移動]，假定已完全載入源和目標父元素的同級元素。 如果在父DOM元素（源或目標）下發生延遲載入，則這些VEC操作可能導致行為不一致。 我們正在研究一種更可靠的方法，使VEC操作在緩載DOM元素中工作。 作為臨時解決方法，您可以 [!UICONTROL 自定義代碼] 來呈現您的體驗。

### [!UICONTROL 調整大小]

在您的頁面上調整元素的大小。選擇時 [!UICONTROL 調整大小]，在元素的右下角會出現一個手柄，該手柄允許您拖動該角來調整大小。 按住 Shift 鍵來保持相同的外觀比例。

**注意:** 不能對行內元素調整大小。

### [!UICONTROL 移動] {#move}

在頁面上移動元素。與[!UICONTROL 「重新排列」]選項不同，[!UICONTROL 「移動」]選項不會移動其他元素來為已移動的元素騰出空間。使用方向鍵來微調此移動。(計畫的增強：支援確保移動的元素不會隱藏在其他元素後面。)

在某些情況下，例如，當CSS限制要求某個元素保留在其父元素內時，您不能將該元素移到其父元素外。 元素無法移到有下列 CSS 屬性的容器之外: `overflow: hidden`。

請參閱 [!UICONTROL 重新排列] 以獲取有關與 [!UICONTROL 移動] 和 [!UICONTROL 重新排列] 由於DOM元素的緩慢載入而導致的操作。

### [!UICONTROL 隱藏]

隱藏元素。白色空間會保留，但移除內容。

### [!UICONTROL 移除]

移除元素。影像背後的白色空間會移除，而元素所在位置的空間會折疊。

**注意:** 您無法使用此選項移除 &quot;classic&quot; mbox 內的項目 (在 Target Classic 促銷活動內建立的 mbox)。

## [!UICONTROL 展開區段]

除了原始選取的元素以外，請選取上層元素。選取任何上層元素時，系統會自動選取該元素的所有下層。您可以展開選取範圍多次。

## [!UICONTROL 導覽至連結]

開啟連結的目的地。

## [!UICONTROL 撤消]/[!UICONTROL 重做]

在編輯工作階段期間，還原您對活動所進行的變更。您也可以重做先前已還原的變更。

## 考量事項 {#considerations}

* 如果選件包含 HTML 內容，請參閱 [at.js 如何運作](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render)中的「at.js 如何呈現具有 HTML 內容的選件」以取得詳細資訊。

## 自定義元素支援 {#custom}

VEC支援 [Web元件](https://developer.mozilla.org/en-US/docs/Web/Web_Components) 以便您建立和test個性化體驗，並在自定義元素和自定義元素內的元素上提供。 此功能在VEC中可用於所有 [!DNL Target] 活動類型。

>[!NOTE]
>
>中支援對自定義元素的VEC支援 [at.js版本](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) 2.7.0（或更高版本）。 確保您的網站部署了所需版本。 如果使用 [Visual Experience Composer幫助程式擴展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)，還必須部署所需的at.js版本。 上述VEC選項不可見，可用於不支援的at.js版本。
>
>當前不支援對自定義元素的VEC支援 [Adobe Experience PlatformWeb SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。

大多數VEC操作都支援自定義事件和內部自定義事件，但有以下例外：

以下操作在自定義元素上不可用：

* [!UICONTROL 編輯]
   * [!UICONTROL 文字/HTML]
   * [!UICONTROL 連結]
   * [!UICONTROL 編輯源]

* [!UICONTROL 替換內容]

自定義元素中不提供以下操作：

* [!UICONTROL 配置]
   * [!UICONTROL 重新排列]

## 使用 DOM 路徑導覽元素 {#dom-path}

當您按一下頁面上的元素時，VEC 選項功能表隨即顯示。此外，當您按一下元素時，對應的 DOM 路徑會顯示於頁面底部。

![DOM 路徑](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

您可以使用 DOM 路徑快速查看有關已選取元素 (類型、ID 和類別) 的資訊，然後向上或向下移動 DOM 路徑以選取想要的元素。

當您將游標暫留在 DOM 路徑上方時，藍色方塊隨即醒目提示 VEC 中的對應元素。當您按一下元素時，橘色方塊隨即醒目提示元素且 VEC 選項功能表隨即顯示 (如上所述)。

您可以使用 DOM 路徑，輕鬆導覽至 VEC 中的任何父項、同層級項目或子項元素。

設定[點擊追蹤](/help/main/c-activities/r-success-metrics/click-tracking.md)時，也可使用 DOM 路徑功能。
