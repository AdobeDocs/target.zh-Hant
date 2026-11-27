---
keywords: 體驗鎖定目標; 登陸頁面測試
description: 元素選取器是可識別一或多個元素的CSS運算式。 瞭解如何在Adobe [!DNL Target]視覺化體驗撰寫器(VEC)中使用元素選取器。
title: 我可以在視覺化體驗撰寫器(VEC)中使用元素選取器嗎？
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
TQID: 'https://experienceleague.adobe.com/sqvUyLFddt7HPHH62jwpOZmwTIMSg-hyLIUr8w-x7vg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 4%
---
# 在[!UICONTROL 視覺化體驗撰寫器]中使用的元素選取器 {#vec-selectors}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解專案選取器在[!UICONTROL 視覺化體驗撰寫器] (VEC)中的運作方式、如何選擇使用的選取器，以及[!DNL Target]如何產生專案的選取器。

>[!ENDSHADEBOX]

元素選取器是可識別一或多個元素的CSS運算式。 有關CSS選取器的基本資訊可在&#x200B;*[!DNL Mozilla Developer Network]* (MDN)上的[選取器](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)檔案中取得。

是否使用元素類別或元素ID是在帳戶偏好設定中設定。 按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 視覺化體驗撰寫器]**，然後選擇偏好的CSS選取器：

* **[!UICONTROL 使用元素ID]**：如果多個元素使用相同的ID，或如果頁面載入時元素ID可能會變更，則停用。
* **[!UICONTROL 使用專案類別]**：如果頁面上的專案類別可能變更，則停用。
* **[!UICONTROL 使用偏好的選取器]**：啟用以在VEC中使用唯一的選取器來識別網站的關鍵區域。

>[!NOTE]
>
>元素類別可在&#x200B;**[!UICONTROL A/B測試]**、**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 多變數測試]**&#x200B;活動中作為選取器使用。

如需何時使用CSS選取器以及何時使用唯一ID的相關資訊，請參閱[視覺化體驗撰寫器最佳作法和限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#vec-best-practices)。

## [!DNL Target]如何產生專案的選取器 {#generate-selector}

[!DNL Target]使用簡單的演演算法來建立選取器。 產生邏輯如下：

1. 如果專案具有ID （例如`id="container"`），則專案的選取器是`#container`。

   例如：

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

1. 如果專案包含類別屬性，[!DNL Target]會嘗試使用專案上任何類別的第一類別。

   [!DNL Target]會嘗試剖析父元素，直到找到`<HTML>`元素或具有ID的元素為止。 每當元素包含ID且選取器在其子繫上計算時，此元素的ID即會貢獻給選取器。

   例如：

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

   在此範例中，選取器是`#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` （「>」表示直屬子項）。

   `eq`提供具有「tagName=UL」和第一個類別`navigation`的專案的索引。 因此，`index` 為 0。 如需詳細資訊，請參閱 MDN 中的[選取器](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)文章。

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

   選取器是`#container` > `ul.navigation:eq(0)` > `li:nth-of-type(4)`。

在此程式中：

* 只要能唯一識別DOM中的元素，可使用任何CSS選取器。
* 以上方法是[!DNL Target]使用的方法。 [!DNL Target]未強制採用此方法。 只要選取器可唯一識別元素，即可新增選取器。
* 選擇器中可使用任何屬性。 本文僅使用類別名稱作為範例。
