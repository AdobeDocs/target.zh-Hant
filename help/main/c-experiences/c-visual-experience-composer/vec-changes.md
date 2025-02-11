---
keywords: 視覺化體驗撰寫器； VEC； WYSIWYG
description: 瞭解Adobe Target 25.2.1版（2025年2月11日）中視覺化體驗撰寫器(VEC)中匯入的變更。
title: 新的視覺化體驗撰寫器(VEC)引進了哪些變更？
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 75f44b7ea4c3aff0e33cc2ee54bc39a705deaf2a
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer]個變更

[!DNL Adobe Target Standard/Premium] 25.2.1版（2015年2月11日）推出更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文說明VEC舊版與更新版之間的差異。

當您建立或編輯現有活動時，VEC隨即顯示。

![可視化體驗撰寫器 (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## 重大變更

以下幾節將說明更新VEC與舊版相比的主要變更。

### [!UICONTROL Experiences]面板

和舊版一樣，[!UICONTROL Experiences]面板仍保留在VEC的左側。 無法摺疊[!UICONTROL Experiences]面板。

![體驗面板](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

您可以使用[!UICONTROL Experiences]面板來建立、重新命名或移除體驗。 按一下&#x200B;**[!UICONTROL Add]**&#x200B;圖示（ ![新增圖示](/help/main/assets/icons/Add.svg) ）以新增體驗。 按一下[!UICONTROL More Actions]圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ）以複製、刪除或重新導向體驗。

### [!UICONTROL Components]面板（新）

您可以使用新的[!UICONTROL Components]面板，新增許多元件至網頁並編輯所需元件。

![元件面板](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

若要新增元件，請在編輯畫布中將您要插入的元件拖曳至現有頁面元素上方。 然後選擇將元件插入在所選元素的前面。

和舊版VEC相比，您無法用元件取代選取的元素。

### [!UICONTROL Modifications]面板

若要開啟[!UICONTROL Modifications]面板，請按一下[!UICONTROL Components]面板中的[!UICONTROL Show Modifications]圖示（ ![顯示修改面板](/help/main/assets/icons/History.svg) ）。 [!UICONTROL Modifications]面板從編輯畫布的右側變更為左側。

![「修改」面板](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

[!UICONTROL Modifications]面板會顯示在[!UICONTROL Visual Experience Composer] (VEC)中對您的頁面所做的所有變更，並可讓您進行其他變更（例如CSS選取器、Mbox和自訂程式碼）。

按一下[!UICONTROL More Options]圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ）以新增修改、刪除所有修改或刪除所有無效修改。 按一下[!UICONTROL Select]以執行大量作業： [!UICONTROL Apply to All Pages]或[!UICONTROL Delete]。

### [!UICONTROL Properties]面板（新）

新的[!UICONTROL Properties]面板可讓您變更頁面上所選元素的屬性，無論這些元素是HTML元素或專屬於[!DNL Target]的物件，例如建議或選件。

![屬性面板](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

按一下面板頂端的圖示以編輯HTML程式碼或刪除、複製或隱藏元素。 變更會顯示在[!UICONTROL Modifications]面板中。

[!UICONTROL Properties]面板可在右側邊欄中摺疊。 按一下面板右側的[!UICONTROL Show/Hide Properties]圖示（ ![屬性圖示](/help/main/assets/icons/Propertie.svg) ）以摺疊或顯示[!UICONTROL Properties]面板。

### 活動設定/設定

按一下設計畫布上方顯示的[!UICONTROL Configure]圖示（![設定圖示](/help/main/assets/icons/Setting.svg)）以顯示活動屬性功能表。

![活動設定選項](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

不同的選項可讓您啟用或停用多頁或多個對象活動、指派屬性（[[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)功能）或編輯頁面傳送規則。

位置和功能與舊版VEC UI類似。

### [!UICONTROL Design]/[!UICONTROL Browse]模式

使用設計畫布上方顯示的[!UICONTROL Design]/[!UICONTROL Browse]切換功能，在設計模式和瀏覽模式之間切換。

![設計和瀏覽切換](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

使用[!UICONTROL Browse]模式瀏覽您的網站，並挑選您要更新的檢視或頁面。 切換回[!UICONTROL Design]模式以新增或編輯您的變更。

### [!UICONTROL Undo]/[!UICONTROL Redo]

您可以按一下[!UICONTROL Undo]圖示（ ![復原圖示](/help/main/assets/icons/Undo.svg) ）來復原所做的變更。

VEC中的![復原圖示](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

若要重做動作，請展開復原/[!UICONTROL Redo]按鈕群組並選擇[!UICONTROL Redo]。

### [!UICONTROL Design]畫布

[!UICONTROL Design]畫布可讓您選取檢視區，包括符合熒幕大小、[!UICONTROL Desktop]、[!UICONTROL Tablet]、[!UICONTROL Mobile Landscape]和[!UICONTROL Mobile Portrait]。 依預設，畫布會將頁面與[管理](/help/main/administrating-target/visual-experience-composer-set-up.md)區段中定義的檢視區一起調整到熒幕。

![檢視區選項](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

更新的VEC也可讓您按一下適當的圖示（ ![放大圖示](/help/main/assets/icons/ZoomIn.svg)或![縮小圖示](/help/main/assets/icons/ZoomOut.svg) ）來放大或縮小。

## 顯示UI變更的視覺化插圖

下圖顯示更新VEC後的高階UI變更。 圖的上方顯示更新的VEC UI，下方則顯示先前的UI。 箭頭會顯示各種元素已移動的位置。

![VEC比較 — 與先前的UI比較](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png)