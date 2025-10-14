---
keywords: 視覺化體驗撰寫器選項；體驗撰寫器選項；體驗選項；編輯文字；編輯html；編輯文字/html；編輯背景顏色；背景顏色；插入元素；編輯連結；連結；視覺化體驗撰寫器連結；編輯css類別；CSS類別；交換選件；選件交換；交換影像；影像交換；移除專案；專案移除；隱藏專案；重新排列；移動元素；元素移動；調整元素大小；元素大小；展開選取範圍；導覽至此連結；導覽連結；導覽；連結；復原；還原/重做；自訂事件；網頁元件；選件決定；選件決策
description: 探索 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中可用的選項。
title: 如何使用[!UICONTROL Visual Experience Composer] (VEC)選項？
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '2667'
ht-degree: 56%

---

# 可視化體驗撰寫器選項

當您在[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中按一下頁面元素時，功能表會顯示該元素型別可用的選項。 此外，DOM 路徑會顯示在頁面底部，讓您輕鬆導覽頁面結構。

各種[!UICONTROL Visual Experience Composer] (VEC)動作會分組到適當的功能表選項中，讓您的工作更快更有效率：

![VEC 選項功能表](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>可用的選項取決於您建立或編輯的活動型別。

## [!UICONTROL Edit]

可使用下列選項: 

### [!UICONTROL Text/HTML] {#edit-text-html}

變更元素的 HTML 程式碼，例如文字區域、按鈕或連結的文字。

除了 HTML 程式碼，您可以編輯和插入自訂 JavaScript。

針對[!UICONTROL A/B]和[!UICONTROL Experience Targeting]活動編輯文字和HTML時，有數個RTF格式選項可供使用。 您可選擇字型、選取字型樣式、變更文字對齊方式，以及其他標準文字格式化選項。修改 HTML 時，您可在 HTML 的程式碼檢視和 RTF 編輯之間切換。

以下是可巢狀的 HTML5 標記:

| 標記 | 允許的巢狀標記 |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

### [!UICONTROL Background Color]

使用檢色器來選取或設定背景顏色。您可以選取一個色票，然後使用 RGB 值或色彩十六進位代碼調整它。檢色器中的紅色 x 可讓背景透明化。

**注意:** 此選項無法供設定了背景影像的元素使用。

### [!UICONTROL Styles] {#styles}

使用[!UICONTROL Styles]面板檢視或編輯所選元素的現有樣式的值。 您也可以新增其他樣式。

若要存取[!UICONTROL Styles]面板，請按一下VEC中的頁面元素，然後按一下&#x200B;**[!UICONTROL Edit]** > **[!UICONTROL Styles]**。

[!UICONTROL Styles]面板會顯示在VEC的右側。 此面板包含可讓您編輯或新增至所選元素的樣式清單。如果您習慣使用階層式樣式表 (CSS) 或如果您收到來自開發人員的程式碼，即時 CSS 編輯器可讓您檢視變更及新增樣式。

![樣式面板](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

當您套用不同的樣式時，在您變更任何區段後，只要按一下顯示於[!UICONTROL Revert]面板右上角的[!UICONTROL Styles]圖示，即可隨時回覆變更。 按一下[!UICONTROL Revert]圖示會還原目前區段面板上的所有變更。

展開每個區段以編輯或新增樣式 (如下所述)。若要儲存變更，請按一下面板頂端的[!UICONTROL Back]圖示以返回面板的主要顯示，然後按一下&#x200B;**[!UICONTROL Save]**。

主面板上以及各個區段面板上每個選項旁的藍點表示，您已變更對應的樣式。 此視覺指示器可讓您在按一下[!UICONTROL Save]前輕鬆檢閱變更。

>[!NOTE]
>
>版面變更、背景顏色、調整大小和移動的快速動作在 VEC 功能表中也有個別的動作可供使用。這些選項可作為個別動作使用，您也可以使用「樣式」選單，如以下所述。

* **[!UICONTROL Background]**

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

* **[!UICONTROL Typography]**

  變更元素的印刷樣式。印刷樣式編輯既快速又簡單。

  雖然RTF編輯器(編輯文字/HTML)可供進行微調使用，仍可透過此選項使用變更整個元素的快速動作。 如果您只要將印刷樣式變更套用至局部文字 (而非全部文字)，請使用 [RTF 編輯器](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)。

  您可以編輯下列印刷樣式:

   * [!UICONTROL Font size]
   * [!UICONTROL Font weight]
   * [!UICONTROL Font style]
   * [!UICONTROL Color] （指定色彩代碼或使用檢色器）
   * [!UICONTROL Word spacing]
   * [!UICONTROL Line height]
   * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  變更所選元素的邊界。您可以變更上、下、左、右邊界。

  按一下每個邊界的下拉式圖示，以從下列選項中選擇:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （拖曳滑桿以設定邊界，或指定每個邊界的畫素數量）

  邊界支援正值和負值。

  Target也支援其他大小單位，例如rem、pc、em。 如需這些單位的詳細資訊，請參閱[網頁樣式表CSS提示與秘訣](https://www.w3.org/Style/Examples/007/units.en.html)。

* **[!UICONTROL Padding]**

  變更所選元素的邊框間距。您可以變更上、下、左、右邊框間距。

  拖曳滑桿以設定邊框間距，或為邊框間距指定像素數量。

  邊框間距支援 0 以上的寬度刻度。

  Target也支援[其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em。

* **[!UICONTROL Border]**

  按一下面板頂端的邊框圖示，以變更所選元素的邊界。

  您可以編輯每個邊框的以下樣式 (上、下、左和右):

   * [!UICONTROL Border style] （無、隱藏、點狀、虛線、實線或雙線）
   * [!UICONTROL Border color] （指定色彩代碼或使用檢色器）
   * [!UICONTROL Border width] （拖曳滑桿以選取邊框寬度，或以畫素指定寬度）

  邊框支援 0 以上的寬度刻度。

  Target也支援[其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em。

* **[!UICONTROL Position]**

  從所選元素的目前位置移動該元素。您可以變更專案的上、下、左、右和[Z索引](https://www.w3schools.com/cssref/pr_pos_z-index.asp)位置。

  按一下[!UICONTROL Static]下拉式清單，以從下列位置選項中選擇：

   * [!UICONTROL Static]
   * [!UICONTROL Relative]
   * [!UICONTROL Absolute]
   * [!UICONTROL Sticky]
   * [!UICONTROL Fixed]

  按一下每個位置的下拉式圖示，以從下列選項中選擇:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （拖曳滑桿以定位元素，或指定您要移動元素的畫素數量）

  位置支援正值和負值。

  Target也支援[其他大小單位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em。

* **[!UICONTROL Size]**

  變更所選元素的寬度和高度。

  按一下[!UICONTROL Width]和[!UICONTROL Height]旁的下拉式圖示，以從下列選項中選擇：

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （拖曳滑桿以調整元素大小，或指定每個維度的畫素數量）

* **[!UICONTROL Filter]**

  拖曳每個篩選器選項的滑桿，或指定想要的百分比:

   * [!UICONTROL Sepia]
   * [!UICONTROL Contrast]
   * [!UICONTROL Brightness]
   * [!UICONTROL GrayScale]
   * [!UICONTROL Blur]
   * [!UICONTROL Opacity]
   * [!UICONTROL Invert]
*[!UICONTROL &#x200B; Hue-rotate]
   * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  如果您習慣使用階層式樣式表 (CSS) 或如果您收到來自開發人員的程式碼，即時 CSS 編輯器可讓您檢視變更及新增樣式。

  CSS 編輯器會在樣式面板中顯示您所做的任何變更。如下圖所示，已變更字型大小、上邊框和影像大小:

  ![含有變更的 CSS 編輯器](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  請注意上圖中[!UICONTROL Typography]、[!UICONTROL Border]和[!UICONTROL Size]選項旁的藍點。 這些點代表您已變更這些區段。 如果您開啟這些區段面板，藍點會顯示在您已變更的特定選項旁邊。

  如果[!UICONTROL Styles]中預設沒有您想要的樣式，您可以輸入自己的程式碼。

  CSS編輯器只會顯示目前工作階段的詳細資料。 如果您儲存變更然後重新開啟編輯器，即使您再次選取相同的元素，先前變更的相關詳細資料也不會顯示在編輯器中。

  >[!IMPORTANT]
  >
  >您可以使用 CSS 編輯器套用背景影像，但可能會導致忽隱忽現的情形。請在部署前測試您的變更。

### [!UICONTROL CSS Class]

指定用於元素的預先定義 CSS 類別。如果選取超過一個元素，請將多個 CSS 類別以空格分隔。

可用於[!UICONTROL A/B]、[!UICONTROL Automated Personalization]和[!UICONTROL Multivariate Test]活動。

### [!UICONTROL Link]

變更連結中的 URL。

使用「編輯連結」來更新選取器以指向相同的影像元素。不過，不支援連結至不同的影像元素。若要連結至不同的影像元素，請從程式碼編輯器中刪除原始動作，並使用[!UICONTROL Visual Experience Composer]將動作套用至其他影像元素。

## [!UICONTROL Insert Before]

可使用下列選項: 

### [!UICONTROL Offer Decision]

新增在[&#x200B; [!DNL Adobe Journey Optimizer]中建立的](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=zh-Hant){target=_blank}優惠方案，以使用Offer Decisioning向客戶呈現最佳優惠方案和體驗。

**注意：**&#x200B;此選項僅在編輯或建立[手動[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)或[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動時可用。 此選項不適用於其他活動型別。

如需詳細資訊，請參閱[使用優惠決定](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL Image]、[!UICONTROL HTML]和[!UICONTROL Text]

除了修改現有內容以外，新增任何類型的元素至您的頁面。新增文字、代碼、清單和更多內容來建立完全不同的體驗進行測試。

在頁面上選取元素，然後按一下「[!UICONTROL Insert Before]」並選擇您要插入影像、HTML或文字。 插入的元素會出現在選取的元素之前。

所插入元素的行為取決於頁面、CSS 和其他頁面組態選項的結構。需要 HTML 才能讓您的頁面正確出現。在插入項目之後，請一律測試您的頁面，以確定它能如預期般顯示。

[!UICONTROL Recommendations]支援[!UICONTROL Insert Before] DIV、SECTION和ARTICLE標籤的內容。

**注意:** 插入影像需要啟用 [!DNL Adobe Scene7 Publishing System] 發佈系統，這樣您才會具備影像資料庫的存取權。

### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以產品建議方式使用推薦](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL Experience Fragment]

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL Insert After]

可使用下列選項: 

### [!UICONTROL Offer Decision]

新增在[&#x200B; [!DNL Adobe Journey Optimizer]中建立的](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=zh-Hant){target=_blank}優惠方案，以使用Offer Decisioning向客戶呈現最佳優惠方案和體驗。

**注意：**&#x200B;此選項僅在編輯或建立[手動[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)或[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動時可用。 此選項不適用於其他活動型別。

如需詳細資訊，請參閱[使用優惠決定](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL Image]、[!UICONTROL HTML]和[!UICONTROL Text]

除了修改現有內容以外，新增任何類型的元素至您的頁面。新增文字、代碼、清單和更多內容來建立完全不同的體驗進行測試。

在頁面上選取元素，然後按一下「[!UICONTROL Insert After]」並選擇您要插入影像、HTML或文字。 插入的元素會出現在選取的元素之後。

所插入元素的行為取決於頁面、CSS 和其他頁面組態選項的結構。需要 HTML 才能讓您的頁面正確出現。在插入項目之後，請一律測試您的頁面，以確定它能如預期般顯示。

[!UICONTROL Recommendations]支援[!UICONTROL Insert After] DIV、SECTION和ARTICLE標籤的內容。

**注意:** 插入影像需要啟用 [!DNL Adobe Scene7 Publishing System] 發佈系統，這樣您才會具備影像資料庫的存取權。

### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以產品建議方式使用推薦](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL Experience Fragment]

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL Replace Content]

可使用下列選項: 

### [!UICONTROL Offer Decision]

新增在[&#x200B; [!DNL Adobe Journey Optimizer]中建立的](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=zh-Hant){target=_blank}優惠方案，以使用Offer Decisioning向客戶呈現最佳優惠方案和體驗。

**注意：**&#x200B;此選項僅在編輯或建立[手動[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)或[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動時可用。 此選項不適用於其他活動型別。

如需詳細資訊，請參閱[使用優惠決定](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL Image]

從內容庫選取不同的影像。可用於交換的影像包括上傳至 Experience Cloud 資產資料夾或上傳在 Target 內容庫中的影像。

在初始活動建立期間，顯示的 URL 不是用於傳遞的 URL。在活動同步時，該 URL 會更新為生產 Scene7 URL。

例如，初始 URL 看起來可能如以下範例:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

活動同步之後，傳送 URL 看起來可能如以下範例:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

推薦在 DIV、SECTION 和 ARTICLE 標記中可支援「取代為」。

**注意:** 交換影像需要 Adobe Scene7 發佈系統帳戶。

### [!UICONTROL HTML Offer]

從[!UICONTROL Content Library]中選取其他選件。

**注意:**&#x200B;[!DNL Target] HTML 產品建議會儲存在 伺服器上。

HTML選件最高可達256 KB。

### 建議

包括 A/B 測試 (含自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動內的建議。如需詳細資訊，請參閱[以產品建議方式使用推薦](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL Experience Fragment]

在 [!DNL Target] 活動中插入在 [!DNL Adobe Experience Manager] (AEM) 中建立的體驗片段，以輔助最佳化或個人化。如需詳細資訊，請參閱 [AEM Experience 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL Layout]

可使用下列選項: 

### [!UICONTROL Rearrange]

將元素拖曳到相同上層元素內的另一個位置或 DIV。其他元素會移動位置，為重新排列的元素騰出空間。

**注意**：點選追蹤對重新排列的專案沒有作用。

目前，某些VEC動作（例如[!UICONTROL Rearrange]和[!UICONTROL Move]）假設來源和目的地父元素的同層級元素已完全載入。 如果在父DOM元素（來源或目的地）底下發生延遲載入，這些VEC動作可能會造成不一致的行為。 我們正在研究更可靠的方法，讓VEC動作在延遲載入的DOM元素中運作。 作為臨時因應措施，您可以在這些案例中使用[!UICONTROL Custom Code]來呈現您的體驗。

### [!UICONTROL Resize]

在您的頁面上調整元素的大小。選取[!UICONTROL Resize]時，元素右下角會出現控制代碼，可讓您拖曳該角調整大小。 按住 Shift 鍵來保持相同的外觀比例。

**注意:** 不能對行內元素調整大小。

### [!UICONTROL Move] {#move}

在頁面上移動元素。與[!UICONTROL Rearrange]選項不同，[!UICONTROL Move]不會移動其他元素來騰出空間給要移動的元素。 使用方向鍵來微調此移動。（規劃的增強功能：支援確保移動的元素不會隱藏在其他元素後面。）

在某些情況下，例如當CSS限制需要元素保留在其上層元素內時，您無法將元素移出其上層之外。 元素無法移到有下列 CSS 屬性的容器之外: `overflow: hidden`。

請參閱上述[!UICONTROL Rearrange]，以取得由於延遲載入DOM元素而導致[!UICONTROL Move]和[!UICONTROL Rearrange]動作不一致之行為的詳細資訊。

### [!UICONTROL Hide]

隱藏元素。白色空間會保留，但移除內容。

### [!UICONTROL Remove]

移除元素。影像背後的白色空間會移除，而元素所在位置的空間會折疊。

**注意:** 您無法使用此選項移除 &quot;classic&quot; mbox 內的項目 (在 Target Classic 促銷活動內建立的 mbox)。

## [!UICONTROL Expand Section]

除了原始選取的元素以外，請選取上層元素。選取任何上層元素時，系統會自動選取該元素的所有下層。您可以展開選取範圍多次。

## [!UICONTROL Navigate to Link]

開啟連結的目的地。

## [!UICONTROL Undo]/[!UICONTROL Redo]

在編輯工作階段期間，還原您對活動所進行的變更。您也可以重做先前已還原的變更。

## 考量事項 {#considerations}

* 如果產品建議包含 HTML 內容，請參閱 [at.js 如何運作](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=zh-Hant){target=_blank}中的「at.js 如何呈現具有 HTML 內容的產品建議」以取得詳細資訊。

## 自訂元素支援 {#custom}

VEC支援[Web元件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)，可讓您在自訂元素以及自訂元素內部的元素上建立和測試個人化體驗和選件。 此功能適用於所有[!DNL Target]活動型別。

>[!NOTE]
>
>[at.js版本](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} 2.7.0 （或更新版本）{target=_blank}支援自訂元素的VEC支援。 確保您的網站已部署所需版本。 如果您正在使用[視覺化體驗撰寫器Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)，它也必須部署必要的at.js版本。 上述VEC選項無法看見，且無法搭配不支援的at.js版本使用。
>
>[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}目前不支援自訂元素的VEC支援。

大部分的VEC動作都可在自訂事件和內部自訂事件上支援，但下列例外情況除外：

下列動作不適用於自訂元素：

* [!UICONTROL Edit]
   * [!UICONTROL Text/HTML]
   * [!UICONTROL Link]
   * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

下列動作在自訂元素中無法使用：

* [!UICONTROL Layout]
   * [!UICONTROL Rearrange]

## 使用DOM路徑導覽元素 {#dom-path}

當您按一下頁面上的元素時，VEC 選項功能表隨即顯示。此外，當您按一下元素時，對應的 DOM 路徑會顯示於頁面底部。

![DOM 路徑](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

您可以使用 DOM 路徑快速查看有關已選取元素 (類型、ID 和類別) 的資訊，然後向上或向下移動 DOM 路徑以選取想要的元素。

當您將游標暫留在 DOM 路徑上方時，藍色方塊隨即醒目提示 VEC 中的對應元素。當您按一下元素時，橘色方塊隨即醒目提示元素且 VEC 選項功能表隨即顯示 (如上所述)。

您可以使用 DOM 路徑，輕鬆導覽至 VEC 中的任何父項、同層級項目或子項元素。

設定[點擊追蹤](/help/main/c-activities/r-success-metrics/click-tracking.md)時，也可使用 DOM 路徑功能。
