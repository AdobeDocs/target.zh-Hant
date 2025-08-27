---
keywords: 體驗鎖定目標; 登陸頁面測試
description: 元素選取器是可識別一或多個元素的CSS運算式。 瞭解如何在Adobe [!DNL Target] 視覺化體驗撰寫器(VEC)中使用元素選取器。
title: 我可以在視覺化體驗撰寫器(VEC)中使用元素選取器嗎？
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
source-git-commit: 51e484d54f4d318ea59fdfdb16d1ed7014abdfdb
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 31%

---

# 在可視化體驗撰寫器中使用的元素選取器

元素選取器是可識別一或多個元素的CSS運算式。

您可以在[ (MDN)上的](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)選取器&#x200B;*[!DNL Mozilla Developer Network]*&#x200B;檔案中找到有關CSS選取器的基本資訊。

您可以在帳戶偏好設定中設定使用元素類別還是元素 ID。按一下&#x200B;**[!UICONTROL Administration > Visual Experience Composer]**，然後選擇您偏好的CSS選取器。

* **使用元素ID**：如果相同的ID用於多個元素，或元素ID在頁面載入時可能變更，則停用。
* **使用專案類別**：如果頁面上的專案類別可能變更，則停用。
* **使用偏好的選取器**：若要在VEC中使用唯一的選取器來識別您網站的關鍵區域，請啟用此選項。

>[!NOTE]
>
>元素類別可在[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]和[!UICONTROL &#x200B; Multivariate Test]活動中作為選取器使用。

如需 CSS 選取器及不重複 ID 之使用時機的相關資訊，請參閱[可視化體驗撰寫器最佳作法與限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6)。

## [!DNL Target]如何產生專案的選取器 {#section_D89D954BCBFB486CA081BE183776A475}

[!DNL Target]使用簡單的演演算法來建立選取器。 以下是產生邏輯的簡短說明：

1. 如果專案具有ID （例如`id="container"`），則專案的選取器是`#container`。

   例如:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- Selector is computed for this element -->
       <ul class="navigation">
         <li class="item active"> Home </li>
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

1. 如果元素包含類別屬性，[!DNL Target]會嘗試利用元素上任何類別的第一類別。

   [!DNL Target]會嘗試剖析父元素，直到找到`<HTML>`元素或具有ID的元素為止。 每當元素包含ID且選取器在其子繫上計算時，此元素的ID即會貢獻給選取器。

   例如:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li class="item active"> Home </li> <!-- Selector is computed for this element -->
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

   在此範例中，

   選取器: `#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` (「>」表示直屬子項。)

   `eq` 會向索引表示一個元素有 &quot;tagName=UL&quot;，第一個類別是 `navigation`。因此，`index` 為 0。如需詳細資訊，請參閱 MDN 中的[選取器](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)文章。

1. 如果專案不含類別，[!DNL Target]會針對專案使用`tagName`，並往父專案周遊，直到找到`<HTML>`專案或具有ID的專案為止。

   例如:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li> Home </li>
         <li> Men </li>
         <li class="active"> Women </li>
         <li> Kids </li><!-- Selector is computed for this element -->
       </ul>
     </div>
   </div>
   ```

   選取器: `#container` > `ul.navigation(0)` > `li:nth-of-type(4)`

在上述程序中:

* 只要能夠在 DOM 中唯一地識別元素，您可以使用任何 CSS 選取器。
* 以上方法是[!DNL Target]使用的方法。 [!DNL Target]並未強制您使用此方法。 只要符合第一項重點，您可以新增任何選取器。
* 您可以在選取器中使用任何屬性。本檔案僅使用類別名稱作為範例。
