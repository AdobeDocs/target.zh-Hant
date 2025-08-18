---
keywords: 視覺化體驗撰寫器； VEC； WYSIWYG
description: 瞭解在Adobe Target中使用視覺化體驗撰寫器(VEC)的基本知識。 VEC是WYSIWYG編輯器，可讓您輕鬆建立個人化體驗。
title: 如何使用視覺化體驗撰寫器(VEC)？
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
source-git-commit: 3f5b198ad08d85caa9c859171e78b710083e44fb
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 43%

---

# [!UICONTROL Visual Experience Composer] (VEC)

[!UICONTROL Visual Experience Composer]中的[!DNL Adobe Target] (VEC)是WYSIWYG編輯器，可讓客戶直接在其網站或行動網頁上建立和測試個人化體驗，而無需編輯程式碼。

>[!NOTE]
>
>[!DNL Target Standard/Premium] 25.2.1 （2025年2月17日）發行版本包含VEC的更新版本。 如需有關更新的VEC與舊版有何差異的資訊，請參閱[視覺化體驗撰寫器變更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)。 如需更新VEC中各種選項的概觀，請參閱[視覺化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

VEC可讓您輕鬆建立及測試網站內容中的個人化體驗和選件。 您可以拖放、交換及修改網頁（或選件）或行動網頁的版面與內容，藉此建立[!DNL Target]活動的體驗和選件。

VEC 是 [!DNL Target] 的其中一項主要功能。VEC 可讓行銷人員和設計人員使用視覺化介面來建立和變更內容。您可以進行許多設計選擇，而不需直接編輯程式碼。您也可以使用撰寫器中提供的編輯選項來編輯 HTML 和 JavaScript。

在[!DNL Target] **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**&#x200B;標籤上，您可以輸入預設的[!UICONTROL Visual Experience Composer] URL。

此 URL 決定您開啟 VEC 時的開始位置。如果您未輸入預設URL，當您開啟編輯器時，會從空白頁面開始，然後您可以指定URL。

![醒目提示 VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

>[!NOTE]
>
>如果頁面包含混合內容（例如，安全網站中的不安全頁面），某些瀏覽器（例如[!DNL Firefox]）可能會阻擋此頁面在VEC中顯示。 如果您的頁面未顯示，請在瀏覽器網址列按一下URL旁的圖示，然後按一下&#x200B;**[!UICONTROL Disable protection on this page]**。 此問題不影響向網站訪客顯示您的頁面。

頁面上位於 iframe 內的內容無法在 VEC 中修改。若要編輯iframe內的內容，請確定iframe檔案已啟用[!DNL Target]，然後在VEC中載入該iframe URL。

您可以使用[!UICONTROL Experiences]邊欄中的索引標籤來檢視您的頁面，使其對不同對象或不同體驗的顯示方式。 您可以為每個體驗命名。 例如，如果您在導覽列中測試「首頁」連結的位置，您可以命名首先顯示「首頁」連結的體驗。 例如，「首頁連結」可讓您更輕鬆地識別清單中的體驗。

>[!NOTE]
>
>如果變更頁面結構而影響該頁面上建立的活動中所使用的位置，可能會在編輯體驗時造成問題。 如果在VEC之外變更位置，[!DNL Target]可能無法找到內容已變更的位置。

當您在頁面上四處移動滑鼠時，即時線上方塊會緊跟著游標，並醒目提示頁面上的元素。

<!--Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)-->

按一下醒目提示的元素，以顯示該元素型別可用的選項功能表。 例如，您可以按一下影像，然後選取&#x200B;**[!UICONTROL Change Image]**&#x200B;以將影像變更為其他影像。 或者，按一下按鈕並變更文字顏色。

您也可以按一下&#x200B;**[!UICONTROL Browse]**，然後導覽至主要頁面所提供的頁面，例如出貨頁面或購物車，然後在該頁面上測試變更。 您也可以存取暫留時可用的頁面元素，例如飛出功能表和迷你購物車。完成瀏覽至頁面時，請按一下&#x200B;**[!UICONTROL Design]**&#x200B;編輯體驗。 例如，您可能需要變更購物車下拉式清單或影像輪播的設計。

>[!NOTE]
>
>如果暫留狀態依賴JavaScript，請確定未選取&#x200B;**[!UICONTROL Disable JavaScript]**。 JavaScript 必須啟用才能編輯 JavaScript 元素。

如需 VEC 中可用選項的相關資訊，請參閱[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)。

您可以在頁面載入時 (或頁面無法載入後) 在頁面上執行一些修改，或者也可以在 VEC 中取消頁面載入。如需詳細資訊，請參閱:

* [在頁面載入時或頁面無法載入後編輯頁面](#loading)
* [在VEC內取消載入頁面](#cancel-loading)

## 在頁面載入時或頁面無法載入後編輯頁面 {#loading}

您可以在 VEC 中的頁面載入前，或甚至頁面完全無法載入時 (例如自訂程式碼無法繼續正常運作) 執行許多動作。

您可能想要在頁面於 VEC 內載入時或無法載入後存取或編輯頁面的一些原因包括:

* 您想要對頁面進行簡單的修改，例如新增自訂程式碼或變更體驗的名稱
* 您想要從無法再存取的頁面中複製現有的自訂程式碼
* 您知道頁面將不會在 VEC 內載入，但您仍想要進行簡單的編輯

當頁面載入時（或無法載入後），[!UICONTROL Experiences]邊欄、[!UICONTROL Components]邊欄和[!UICONTROL Configure]選項可供存取。

## 在VEC內取消載入頁面 {#cancel-loading}

您可以在 VEC 內取消頁面載入，以解除鎖定活動編輯，而不需要等候頁面載入。此功能可節省時間並協助您更有效率地進行簡單的編輯或插入自訂程式碼，而不需要等候 VEC 內的頁面載入。

您可能想要取消 VEC 內的頁面載入的幾項原因包括:

* 想要對現有修改進行微幅編輯
* 想要刪除一或多個現有修改
* 想要插入或編輯自訂程式碼
* 您錯誤地輸入了錯誤的頁面 URL
* 想要在 VEC 內的頁面載入前啟用或停用 JavaScript
* 您想要將更多範本測試規則新增到[!UICONTROL Page Delivery]條件
* 透過EEC或僅限iframe載入頁面時，您想要覆寫全域[!UICONTROL Enhanced Experience Composer] (EEC)切換按鈕

如果您取消在VEC中載入頁面，則可以在活動中的體驗之間切換，而不需要等候頁面載入。 若要再次在VEC內檢視頁面，您必須按一下&#x200B;**[!UICONTROL Reload]**&#x200B;按鈕。

>[!IMPORTANT]
>
>請注意，進行自訂程式碼或任何修改時，若選擇取消在 VEC 內載入，您則必須確保程式碼或變更已正確執行。請務必執行適當的 QA，確保自訂程式碼和任何其他修改如預期般提供。

若要取消在VEC內載入頁面，請在頁面載入時按一下&#x200B;**[!UICONTROL Cancel Loading]**&#x200B;按鈕。 在目前編輯工作階段期間，頁面將不會在此活動的 VEC 中載入。

若要繼續管理目前活動中的體驗或新增新的修改，您必須按一下&#x200B;**[!UICONTROL Reload]**&#x200B;按鈕。
