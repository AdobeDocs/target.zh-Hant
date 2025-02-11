---
keywords: 視覺化體驗撰寫器選項；體驗撰寫器選項；體驗選項；編輯文字；編輯html；編輯文字/html；編輯背景顏色；背景顏色；插入元素；編輯連結；連結；視覺化體驗撰寫器連結；編輯css類別；CSS類別；交換選件；選件交換；交換影像；影像交換；移除專案；專案移除；隱藏專案；重新排列；移動元素；元素移動；調整元素大小；元素大小；展開選取範圍；導覽至此連結；導覽連結；導覽；連結；復原；還原/重做；自訂事件；網頁元件；選件決定；offer decisioning
description: 探索 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中可用的選項。
title: 如何使用[!UICONTROL Visual Experience Composer] (VEC)選項？
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: 457b02cb3cbaeee8ad9b56844891dd7e9f6f2d86
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 14%

---

# 可視化體驗撰寫器選項

當您在[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中按一下頁面元素時，功能表會顯示該元素型別可用的選項。 此外，DOM路徑會顯示在頁面底部，讓您輕鬆導覽頁面結構

>[!NOTE]
>
>[!DNL Target Standard/Premium] 25.2.1 （2025年2月11日）發行版本包含VEC的更新版本。 如需有關更新的VEC與舊版有何差異的資訊，請參閱[視覺化體驗撰寫器變更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)。


各種[!UICONTROL Visual Experience Composer] (VEC)動作會分組到適當的功能表選項中，讓您的工作更快更有效率：

![VEC 選項功能表](/help/main/c-experiences/c-visual-experience-composer/assets/vec-options.png)

>[!NOTE]
>
>可用的選項取決於您建立或編輯的活動型別和元素。 下列章節包含影像和文字各種選項的相關資訊。

## 影像選項

如果您按一下[!UICONTROL A/B Test]活動中的影像，VEC看起來會類似於下圖：

已選取影像的![VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-image.png)

從左側的「元件」框架中選取元件以插入下列元素：

* 基本(分隔線、HTML、影像)。
* 文字（標題、段落、連結）。
* 動態([建議](/help/main/c-recommendations/recommendations-as-an-offer.md)，[體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)，HTML選件)。

影像頂端的功能表可讓您進行下列工作：

* 插入連結（ ![插入連結圖示](/help/main/assets/icons/Link.svg) ）。
* 變更影像（ ![選擇影像圖示](/help/main/assets/icons/Images.svg) ）。
* 新增個人化(![新增Personalization圖示](/help/main/assets/icons/PersonalizationField.svg) )。
* 刪除影像（ ![刪除圖示](/help/main/assets/icons/Delete.svg) ）。

右側的框架可進一步設定影像的屬性。

框架頂端的圖示可讓您執行下列動作：

* 編輯HTML( ![插入HTML圖示](/help/main/assets/icons/Code.svg) )。 如需詳細資訊，請參閱下方的[編輯HTML](#html)。
* 複製影像（ ![復製圖示](/help/main/assets/icons/Code.svg) ）。
* 刪除影像（ ![刪除圖示](/help/main/assets/icons/Delete.svg) ）。
* 隱藏影像（ ![隱藏圖示](/help/main/assets/icons/VisibilityOff.svg) ）。

右側框架中的選項可讓您進行下列操作：

* 編輯CSS類別。
* 設定影像的屬性（來源、標題、替代文字）。
* 編輯連結URL
* 設定影像的大小（高度和寬度）。 按一下[!UICONTROL Show Advanced Options]以設定影像的最小和最大大小、寬度、高度、溢位和物件大小。
* 設定影像在頁面上的位置（絕對、固定、相對、靜態或粘著）。
* 設定元素的間距，包括邊界和邊距。
* 設定元素的效果（不透明度）。 按一下[!UICONTROL Show Advanced Options]設定影像的棕褐色、灰階、對比、亮度和模糊值。 您也可以反轉或旋轉影像。
* 設定影像的內嵌樣式。

## 文字選項

如果您在[!UICONTROL A/B Test]活動中按一下文字，VEC看起來會類似於下圖：

已選取文字的![VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-text.png)

從左側的[!UICONTROL Components]框架中選取元件以插入下列元素：

* 基本(分隔線、HTML、影像)。
* 文字（標題、段落、連結）。
* 動態([建議](/help/main/c-recommendations/recommendations-as-an-offer.md)，[體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)，HTML選件)。

按一下「[!UICONTROL Show Modifications]」圖示（![顯示修改圖示](/help/main/assets/icons/History.svg)）以顯示體驗的修改。

文字元素頂端的功能表可讓您進行下列工作：

* 設定文字的屬性（標題層級、段落、區塊引號或等寬）
* 選取文字的顏色（ ![文字顏色圖示](/help/main/assets/icons/TextColor.svg) ）
* 設定文字的屬性（粗體、斜體、底線或刪除線） （ ![選擇文字屬性圖示](/help/main/assets/icons/Text.svg) ）。
* 設定文字的對齊方式（靠左、置中、靠右、左右對齊） （![文字對齊方式圖示](/help/main/assets/icons/TextAlignCenter.svg) ）。
* 插入連結（ ![插入連結圖示](/help/main/assets/icons/Link.svg) ）。
* 以HTML選件、[體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)或[建議]/help/main/c-recommendations/recommendations-as-an-offer.md)取代內容。
* 編輯HTML( ![插入HTML圖示](/help/main/assets/icons/Code.svg) )。
* 新增個人化(![新增Personalization圖示](/help/main/assets/icons/PersonalizationField.svg) )。
* 刪除影像（ ![刪除圖示](/help/main/assets/icons/Delete.svg) ）。

右側的框架可進一步設定文字的屬性。

框架頂端的圖示可讓您執行下列動作：

* 編輯HTML( ![插入HTML圖示](/help/main/assets/icons/Code.svg) )。 如需詳細資訊，請參閱下方的[編輯HTML](#html)。
* 複製文字（ ![復製圖示](/help/main/assets/icons/Code.svg) ）。
* 刪除文字（ ![刪除圖示](/help/main/assets/icons/Delete.svg) ）。
* 隱藏文字（ ![隱藏圖示](/help/main/assets/icons/VisibilityOff.svg) ）。

右側框架中的選項可讓您進行下列操作：

* 編輯CSS類別。
* 設定文字的背景顏色和影像。
* 設定文字的印刷樣式(標題樣式、字型大小、字型粗細、行高、對齊、文字色彩、文字樣式（粗體、斜體、底線或刪除線）)。
* 設定清單，包括專案符號、編號或A、B、C。
* 選擇邊框顏色。
* 設定文字方塊的大小（高度和寬度）。 按一下[!UICONTROL Show Advanced Options]以設定文字方塊的最小和最大大小、寬度、高度、溢位和物件大小。
* 設定文字方塊在頁面上的位置（絕對、固定、相對、靜態或粘著），並設定從上、右、下和左的畫素數量。
* 設定元素的間距，包括邊界和邊距。
* 設定元素的效果（不透明度）。 按一下[!UICONTROL Show Advanced Options]設定影像的棕褐色、灰階、對比、亮度和模糊值。 您也可以反轉或旋轉文字。
* 設定內嵌樣式。

## 編輯HTML {#html}

除了 HTML 程式碼，您可以編輯和插入自訂 JavaScript。

編輯[!UICONTROL A/B]和[!UICONTROL Experience Targeting]活動的文字和HTML時，有數個RTF格式選項可供使用。 您可選擇字型、選取字型樣式、變更文字對齊方式，以及其他標準文字格式化選項。修改HTML時，您可以在程式碼檢視和HTML的豐富編輯檢視之間切換。

以下是可巢狀的 HTML5 標記:

| 標記 | 允許的巢狀標記 |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

## 使用DOM路徑導覽元素 {#dom-path}

當您按一下頁面上的元素時，VEC 選項功能表隨即顯示。此外，當您按一下元素時，對應的 DOM 路徑會顯示於頁面底部。

![DOM 路徑](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path-refresh.png)

如果沒有看見DOM路徑，請按一下[!UICONTROL Show DOM]圖示（ ![顯示DOM圖示](/help/main/assets/icons/LayersBringToFront.svg) ）。

您可以使用 DOM 路徑快速查看有關已選取元素 (類型、ID 和類別) 的資訊，然後向上或向下移動 DOM 路徑以選取想要的元素。

<!--When you hover over the DOM path, a blue box highlights the corresponding element in the VEC. When you click the element, an orange box highlights the element and the VEC options menu displays, as explained above.-->

您可以使用 DOM 路徑，輕鬆導覽至 VEC 中的任何父項、同層級項目或子項元素。

設定[點擊追蹤](/help/main/c-activities/r-success-metrics/click-tracking.md)時，也可使用 DOM 路徑功能。

<!--## [!UICONTROL Edit]

The following options are available:

### [!UICONTROL Text/HTML] {#edit-text-html}

Change the HTML code for the element, such as the text for a text area, button, or link.

In addition to HTML code, you can edit and inject custom JavaScript.

Several rich text formatting options are available when editing text and HTML for [!UICONTROL A/B] and [!UICONTROL Experience Targeting] activities. You can choose a font, select a font style, change text alignment, and other standard text formatting options. When modifying HTML, you can toggle between the code view and rich-editing view of the HTML.

The following HTML5 tags can be nested:

|Tag|Allowed Nested Tags|
| --- | --- |
|`<a>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>`|
|`<ins>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`|
|`<del>`|`<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>`|
|`<label>`|`<p>`|

### [!UICONTROL Background Color]

Use the color picker to select or configure a background color. You can select a color swatch, and adjust it using RGB values or color hex codes. The red x in the color picker makes the background transparent.

**Note:** This option is not available for an element where a background image is set. 

### [!UICONTROL Styles] {#styles}

Use the [!UICONTROL Styles] panel to view or edit the value of existing styles for the selected element. You can also add additional styling.

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

The [!UICONTROL Styles] panel displays on the right side of the VEC. The panel contains a list of styles that lets you edit or add to the selected element. A real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

![Styles panel](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

As you apply different styles, you can always revert your changes by clicking the [!UICONTROL Revert] icon that displays at the top-right corner of the [!UICONTROL Styles] panel after you change any section. Clicking the [!UICONTROL Revert] icon reverts all changes on the current section's panel.

Expand each section to edit or add styles, as explained below. To save your changes, click the [!UICONTROL Back] icon at the top of the panel to return to the panel's main display, then click **[!UICONTROL Save]**. 

Blue dots on the main panel and next to each option on the various section panels indicate that you have changed the corresponding styles. This visual indicator makes it easy for you to review your changes before clicking [!UICONTROL Save].

>[!NOTE]
>
>Quick actions for layout changes, background color, resizing, and move are also available as separate actions in the VEC menu. These options can be used as separate actions or you can use the Styles menu, as explained here.

* **[!UICONTROL Background]**

  Change the background color and image.

  * Color (specify the color code or use the color picker)
  * Image (select an image from the image picker)
  * Image source (specify an external URL)
  * Attachment
    * Click the top drop-down list to select scroll, fixed, or local
    * Click the bottom drop-down list to select repeat, repeat-x, repeat-y, no-repeat, space, or round
  * Clip
    * Click the top drop-down list to select border-box, padding-box, content-box, or text
    * Click the bottom drop-down list to select auto audio or audio

* **[!UICONTROL Typography]**

  Change the typography of an element. Typography edits are quick and easy. 

  Although the rich text editor (Edit Text/HTML) is available for fine tuning, quick actions to change the entire element is available via this option. If you want to apply typography changes to only a part of the text (not to the full text), use the [rich text editor](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md). 

  You can edit the following typography styles:

  * [!UICONTROL Font size]
  * [!UICONTROL Font weight]
  * [!UICONTROL Font style]
  * [!UICONTROL Color] (specify the color code or use the color picker)
  * [!UICONTROL Word spacing]
  * [!UICONTROL Line height]
  * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Change the margin for the selected element. You can change the left, right, bottom, and top margins.

  Click the drop-down icon for each margin to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to set the margin or specify the number of pixels for each margin)

  Margin supports positive and negative values.

  Target also supports other size units, such as rem, pc, em. For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Change the padding for the selected element. You can change the left, right, bottom, and top padding.

  Drag the slider to set the padding or specify the number of pixels for padding.

  Padding supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Border]**

  Click the border icons at the top of the panel to change the selected element's border.

  You can edit the following styles for each border (top, right, bottom, and left):

  * [!UICONTROL Border style] (none, hidden, dotted, dashed, solid, or double)
  * [!UICONTROL Border color] (specify the color code or use the color picker)
  * [!UICONTROL Border width] (drag the slider to select a border width or specify the width in pixels)

  Border supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Position]**

  Move the selected element from its current position. You can change the element's top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

  Click the [!UICONTROL Static] drop-down list to choose from the following position options:

  * [!UICONTROL Static]
  * [!UICONTROL Relative]
  * [!UICONTROL Absolute]
  * [!UICONTROL Sticky]
  * [!UICONTROL Fixed]

  Click the drop-down icon for each position to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to position the element or specify the number of pixels you want to move the element)

  Position supports positive and negative values.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Size]**

  Change the selected element's width and height.

  Click the drop-down icon next to [!UICONTROL Width] and [!UICONTROL Height] to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to size the element or specify the number of pixels for each dimension)

* **[!UICONTROL Filter]**

  Drag the slider for each filter option or specify the desired percentage:

  * [!UICONTROL Sepia]
  * [!UICONTROL Contrast]
  * [!UICONTROL Brightness]
  * [!UICONTROL GrayScale]
  * [!UICONTROL Blur]
  * [!UICONTROL Opacity]
  * [!UICONTROL Invert]
  *[!UICONTROL  Hue-rotate]
  * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  The real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

  The CSS Editor displays any changes that you make in the Styles panel. As shown in the illustration below, the font size, top border, and image size have been changed:

  ![CSS editor with changes](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Notice the blue dots next to the [!UICONTROL Typography], [!UICONTROL Border], and [!UICONTROL Size] options in the preceding illustration. These dots indicate that you have changed these sections. If you open these section panels, blue dots display next to the specific options that you changed.

  You can type your own code if your desired style is not available by default in the [!UICONTROL Styles].

  The CSS Editor shows details for the current session only. If you save changes and then reopen the editor, details about your previous change do not display in the editor, even if you select the same element again.

  >[!IMPORTANT]
  >
  >You can apply a background image using the CSS Editor, but it might cause flicker. Test your changes before deployment.

### [!UICONTROL CSS Class]

Specify the predefined CSS class used for the element. If more than one element is selected, separate multiple CSS classes with a space.

Available for [!UICONTROL A/B], [!UICONTROL Automated Personalization], and [!UICONTROL Multivariate Test] activities.

### [!UICONTROL Link]

Change the URL in the link.

Use Edit Link to update the selector to point to the same image element. However, linking to a different image element is not supported. To link to a different image element, delete the original action from the code editor and use the [!UICONTROL Visual Experience Composer] to apply the action on the other image element.

## [!UICONTROL Insert Before]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert Before] and choose whether you want to insert an image, HTML, or text. The inserted element appears before the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert Before] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert After] and choose whether you want to insert an image, HTML, or text. The inserted element appears after the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert After] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Select a different image from the Content Library. The images available for swapping include the images uploaded to the Experience Cloud assets folder or uploaded in the Content Library in Target.

During initial activity creation, the URL displayed is not the URL used for delivery. Upon activity synching, that URL is updated to a production Scene7 URL.

For example, the initial URL might look like the following example:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

After activity syncing, the delivery URL might look like the following example:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations supports Replace With in DIV, SECTION, and ARTICLE tags.

**Note:** Swapping images requires an Adobe Scene7 Publishing System Account.

### [!UICONTROL HTML Offer]

Select a different offer from the [!UICONTROL Content Library].

**Note:** HTML Offers are stored on [!DNL Target] servers.

An HTML offer can be up to 256 KB.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

The following options are available:

### [!UICONTROL Rearrange]

Drag the element to another location inside the same parent element or DIV. Other elements shift location to make space for the rearranged element.

**Note**: Click-tracking does not work on rearranged items.

Currently, certain VEC actions, such as [!UICONTROL Rearrange] and [!UICONTROL Move], assume that the sibling elements of the source and destination parent elements are completely loaded. If lazy loading occurs under the parent DOM elements (source or destination), these VEC actions can cause inconsistent behavior. We are working on a more reliable approach to make VEC actions work in lazy-loaded DOM elements. As a temporary workaround, you can use [!UICONTROL Custom Code] in these scenarios to render your experiences.

### [!UICONTROL Resize]

Resize an element on your page. When you select [!UICONTROL Resize], a handle appears in the bottom-right corner of the element that lets you drag that corner to resize. Hold the Shift key to retain the same aspect ratio.

**Note:** Inline elements cannot be resized.

### [!UICONTROL Move] {#move}

Move elements on your page. Unlike the [!UICONTROL Rearrange] option, [!UICONTROL Move] does not shift other elements to make room for the element being moved. Use the arrow keys to fine tune the move. (Planned enhancement: support to ensure moved elements are not hidden behind other elements.)

In certain situations, such as when a CSS restriction requires an element to remain inside its parent element, you cannot move the element outside its parent. An element cannot be moved outside of a container that has following CSS property: `overflow: hidden`.

See [!UICONTROL Rearrange] above for more information about inconsistent behavior with the [!UICONTROL Move] and [!UICONTROL Rearrange] actions due to lazy loading of DOM elements.

### [!UICONTROL Hide]

Hide the element. The white space remains, but the content is removed.

### [!UICONTROL Remove]

Remove the element. The white space behind the image is removed and the space where the element was is collapsed.

**Note:** Items within a "classic" mbox (an mbox created within a Target Classic campaign) cannot be removed using this option.

## [!UICONTROL Expand Section]

Select the parent element in addition to the originally selected element. When you select any parent element, all children of that element are automatically selected. You can expand the selection multiple times.

## [!UICONTROL Navigate to Link]

Open the destination of the link.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Undo changes you make to your activities during an editing session. You can also redo changes that have been previously undone.

## Considerations {#considerations}

* If an offer contains HTML content, see "How at.js renders offers with HTML content" in [How at.js works](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} for more information.

## Custom element support {#custom}

The VEC supports [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) to let you create and test personalized experiences and offers on custom elements and on elements inside custom elements. This functionality is available in the VEC for all [!DNL Target] activity types.

>[!NOTE]
>
>VEC support for custom elements is supported in [at.js version](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} 2.7.0 (or later){target=_blank}. Ensure that your website has the required version deployed. If you are using the [Visual Experience Composer helper extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), it must also have the required version of at.js deployed. The VEC options described above are not visible and available for use with non-supported versions of at.js.
>
>VEC support for custom elements is currently not supported with the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

Most VEC actions are supported on custom events and inside custom events, with the following exceptions: 

The following actions are not available on custom elements:

* [!UICONTROL Edit]
  * [!UICONTROL Text/HTML]
  * [!UICONTROL Link]
  * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

The following action is not available inside custom elements:

* [!UICONTROL Layout]
  * [!UICONTROL Rearrange]-->
