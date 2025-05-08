---
keywords: 視覺化體驗撰寫器； VEC； WYSIWYG
description: 瞭解Adobe Target 25.2.1版（2025年2月17日）中視覺化體驗撰寫器(VEC)所推出的變更。
title: 新的視覺化體驗撰寫器(VEC)引進了哪些變更？
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: f9f914c11dbff64d902a3fd8d6bf96237d1f4aae
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer]個變更

[!DNL Adobe Target Standard/Premium] 25.2.1版（2015年2月17日）推出更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文說明VEC舊版與更新版之間的差異。

>[!IMPORTANT]
>
>更新的[!UICONTROL Visual Editing Composer]需要[!DNL Chrome Web Store]中可用的[!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper]延伸模組](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

當您建立或編輯現有活動時，VEC隨即顯示。

![可視化體驗撰寫器 (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## VEC的重大變更

以下幾節將說明更新VEC與舊版相比的主要變更。

### [!UICONTROL Experiences]邊欄

和舊版一樣，[!UICONTROL Experiences]邊欄仍保留在VEC的左側。 無法收合[!UICONTROL Experiences]邊欄。

![體驗邊欄](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

您可以使用[!UICONTROL Experiences]邊欄來建立、重新命名或移除體驗。 按一下&#x200B;**[!UICONTROL Add]**&#x200B;圖示（ ![新增圖示](/help/main/assets/icons/Add.svg) ）以新增體驗。 按一下[!UICONTROL More Actions]圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ）以複製、刪除或重新導向體驗。

### [!UICONTROL Components]邊欄（新）

您可以使用新的[!UICONTROL Components]邊欄，在網頁中新增許多元件，並視需要加以編輯。

![元件邊欄](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

若要新增元件，請從您要插入的[!UICONTROL Components]邊欄拖曳元件，將其置於[!UICONTROL Design]畫布中的現有頁面元素上。 然後選擇將元件插入在所選元素的前面。

和舊版VEC相比，您無法用元件取代選取的元素。

### [!UICONTROL Modifications]邊欄

若要開啟[!UICONTROL Modifications]邊欄，請按一下[!UICONTROL Components]邊欄中的[!UICONTROL Show Modifications]圖示（ ![顯示修改邊欄](/help/main/assets/icons/History.svg) ）。 [!UICONTROL Modifications]邊欄從編輯畫布的右側變更為左側。

![修改邊欄](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

[!UICONTROL Modifications]邊欄會顯示在VEC中對您的頁面所做的所有變更，並可讓您進行其他變更（例如CSS選取器、Mbox和自訂程式碼）。

按一下[!UICONTROL More Options]圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ）以新增修改、刪除所有修改或刪除所有無效修改。 按一下[!UICONTROL Select]以執行大量作業： [!UICONTROL Apply to All Pages]或[!UICONTROL Delete]。

若要再次顯示[!UICONTROL Modifications]邊欄，請按一下[!UICONTROL Modifications]邊欄中的[!UICONTROL Hide Modifications]圖示（ ![顯示修改邊欄](/help/main/assets/icons/History.svg) ）。

### [!UICONTROL Properties]邊欄（新）

[!UICONTROL Properties]邊欄可讓您變更頁面上所選元素的屬性，不論這些元素是HTML元素或專屬於[!DNL Target]的物件，例如建議或選件。

![屬性邊欄](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

按一下邊欄頂端的圖示，即可編輯HTML程式碼或刪除、複製或隱藏元素。 變更會顯示在[!UICONTROL Modifications]邊欄中。

![屬性圖示](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

[!UICONTROL Properties]邊欄可在右側邊欄中摺疊。 按一下邊欄右側的[!UICONTROL Show/Hide Properties]圖示（ ![屬性圖示](/help/main/assets/icons/Propertie.svg) ）以收合或顯示[!UICONTROL Properties]邊欄。

### 活動設定/設定

按一下設計畫布上方顯示的[!UICONTROL Configure]圖示（![設定圖示](/help/main/assets/icons/Setting.svg)）以顯示活動屬性功能表。

![活動設定選項](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

不同的選項可讓您指派屬性、編輯頁面傳送規則、指定網站偏好設定、新增其他頁面，以及啟用或停用多頁面或多個對象活動。 指派[!UICONTROL Properties]是[[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)功能。

位置和功能與舊版VEC UI類似。

### [!UICONTROL Design]/[!UICONTROL Browse]模式

使用[!UICONTROL Properties]邊欄頂端顯示的[!UICONTROL Design]/[!UICONTROL Browse]切換功能，在設計模式和瀏覽模式之間切換。

![設計和瀏覽切換](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

使用[!UICONTROL Browse]模式瀏覽您的網站，並挑選您要更新的檢視或頁面。 切換回[!UICONTROL Design]模式以新增或編輯您的變更。

### [!UICONTROL Undo]/[!UICONTROL Redo]

您可以按一下[!UICONTROL Undo]圖示（ ![復原圖示](/help/main/assets/icons/Undo.svg) ）來復原所做的變更。

VEC中的![復原圖示](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

若要重做動作，請展開復原/[!UICONTROL Redo]按鈕群組並選擇[!UICONTROL Redo]。

### [!UICONTROL Design]畫布

[!UICONTROL Design]畫布可讓您選取檢視區，包括符合熒幕大小、[!UICONTROL Desktop]、[!UICONTROL Tablet]、[!UICONTROL Mobile Landscape]和[!UICONTROL Mobile Portrait]。

![檢視區選項](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

更新的VEC也可讓您按一下適當的圖示（ ![放大圖示](/help/main/assets/icons/ZoomIn.svg)或![縮小圖示](/help/main/assets/icons/ZoomOut.svg) ）來放大或縮小。

## 顯示UI變更的視覺化插圖

下圖顯示更新VEC後的高階UI變更。 圖的上方顯示更新的VEC UI，下方則顯示先前的UI。 箭頭會顯示各種元素已移動的位置。

（按一下影像可將其展開至瀏覽器的完整寬度。）

![VEC比較 — 與先前的UI比較](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}
