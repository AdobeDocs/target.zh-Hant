---
keywords: 視覺化體驗撰寫器； VEC； WYSIWYG
description: 瞭解在Adobe Target中使用視覺化體驗撰寫器(VEC)的基本知識。 VEC是WYSIWYG編輯器，可讓您輕鬆建立個人化體驗。
title: 如何使用視覺化體驗撰寫器(VEC)？
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
source-git-commit: 4abd24f63dd65e65a1d8b07647630eeb640e7a1d
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 73%

---

# 可視化體驗撰寫器 (VEC)

有關在[!DNL Adobe Target]中使用[!UICONTROL Visual Experience Composer] (VEC)的資訊。

VEC是WYSIWYG使用者介面，可讓您輕鬆建立及測試網站內容中的個人化體驗和選件。 您可以拖放、切換及修改網頁 (或選件) 或行動網頁的版面與內容，藉此建立 Target 活動的體驗和選件。

VEC 是 [!DNL Adobe Target] 的其中一項主要功能。VEC 可讓行銷人員和設計人員使用視覺化介面來建立和變更內容。您可以進行許多設計選擇，而不需直接編輯程式碼。您也可以使用撰寫器中提供的編輯選項來編輯 HTML 和 JavaScript。

在目標&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**&#x200B;標籤上，您可以輸入預設視覺化體驗撰寫器URL。

![預設 VEC URL 設定](/help/main/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

此 URL 決定您開啟 VEC 時的開始位置。如果不輸入預設值，則開啟編輯器時會從空白頁開始，到時可以指定 URL。

>[!NOTE]
>
>如果頁面包含混合內容 (例如，安全網站中的不安全頁面)，某些瀏覽器 (例如 Firefox) 會阻擋此頁面在 VEC 中顯示。如果您的頁面未顯示，請在瀏覽器網址列按一下URL旁的圖示，然後按一下&#x200B;**[!UICONTROL Disable protection on this page]**。 此問題不影響向網站訪客顯示您的頁面。

頁面上位於 iframe 內的內容無法在 VEC 中修改。若要編輯 iframe 內的內容，請確定 iframe 文件已啟用 Target 功能，然後在 VEC 中載入該 iframe URL。

您可以使用橫跨頁面頂端的下拉式功能表，以不同對象的角度或以不同體驗來檢視您的頁面。您可以在第二個下拉式清單中提供每一個體驗的名稱。例如，假設您在導覽列中測試首頁連結的位置，您可能將最先出現首頁連結的體驗命名為像是「首頁連結」，以輕鬆地辨別清單中的體驗。

>[!NOTE]
>
>如果變更頁面結構而影響該頁面上建立的活動中所使用的位置，可能會在編輯體驗時造成問題。如果在 VEC 之外變更位置，Target 可能找不到已變更內容的位置。

當您在頁面上四處移動滑鼠時，即時線上方塊會緊跟著游標，並醒目提示頁面上的元素。

![醒目提示 VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

按一下&#x200B;**[!UICONTROL Overlays]**&#x200B;圖示以變更醒目提示的顯示方式。 例如，您可以選擇僅醒目提示影像、連結、區域 mbox、修改或 JavaScript。您可以變更醒目提示的顏色。您也可以指定用於醒目提示不同元素類型的醒目提示顏色和填色類型。

![變更覆蓋設定](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

按一下醒目提示的元素，以顯示該元素型別可用的選項功能表。例如，您可以按一下影像，然後選取&#x200B;**[!UICONTROL Edit > Text/HTML]**&#x200B;來變更文字，或按一下按鈕並變更背景顏色。 您可以使用頁面左上方的按鈕來開啟或關閉覆蓋。

您也可以按一下&#x200B;**[!UICONTROL Browse]**，然後導覽至主要頁面所提供的頁面，例如出貨頁面或購物車，然後在該頁面上測試變更。 您也可以存取暫留時可用的頁面元素，例如飛出功能表和迷你購物車。完成瀏覽至頁面時，請按一下&#x200B;**[!UICONTROL Compose]**&#x200B;編輯體驗。 例如，您可能需要變更購物車下拉式清單或影像輪播的設計。

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

當頁面載入時（或無法載入後），[!UICONTROL Experiences]面板、[!UICONTROL Modifications]面板和體驗頂端的設定（覆蓋、修改、設定等）全部皆可存取。

下圖顯示您可以在頁面仍在載入時插入自訂程式碼或執行其他動作:

![頁面載入中](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## 在VEC內取消載入頁面 {#cancel-loading}

您可以在 VEC 內取消頁面載入，以解除鎖定活動編輯，而不需要等候頁面載入。此功能可節省時間並協助您更有效率地進行簡單的編輯或插入自訂程式碼，而不需要等候 VEC 內的頁面載入。

您可能想要取消 VEC 內的頁面載入的幾項原因包括:

* 想要對現有修改進行微幅編輯
* 想要刪除一或多個現有修改
* 想要插入或編輯自訂程式碼
* 您錯誤地輸入了錯誤的頁面 URL
* 想要在 VEC 內的頁面載入前啟用或停用 JavaScript
* 想要將更多範本測試規則新增至頁面傳送條件
* 想要在透過 EEC 或僅限 iframe 載入頁面時覆寫全域增強體驗撰寫器 (EEC) 切換，可能依頁面而有所不同

取消在 VEC 內載入頁面後，您可以在活動中的體驗之間切換，而不需要等候頁面載入。若要再次在VEC內檢視頁面，您必須按一下&#x200B;**[!UICONTROL Reload]**&#x200B;按鈕。

>[!IMPORTANT]
>
>請注意，進行自訂程式碼或任何修改時，若選擇取消在 VEC 內載入，您則必須確保程式碼或變更已正確執行。請務必執行適當的 QA，確保自訂程式碼和任何其他修改如預期般提供。

若要取消在VEC內載入頁面，請在頁面載入時按一下&#x200B;**[!UICONTROL Cancel Loading]**&#x200B;按鈕。 在目前編輯工作階段期間，頁面將不會在此活動的 VEC 中載入。

![取消載入按鈕](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

若要繼續管理目前活動中的體驗或新增新的修改，您必須按一下&#x200B;**[!UICONTROL Reload]**&#x200B;按鈕。

![重新載入按鈕](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

## 培訓影片

以下影片含有本文章探討之概念的詳細資訊。

### 視覺化體驗撰寫器(1/2) (7:17) ![教學課程徽章](/help/main/assets/tutorial.png)

* 變更頁面的內容
* 變更頁面的配置

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### 視覺化體驗撰寫器(2/2) (7:29) ![教學課程徽章](/help/main/assets/tutorial.png)

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### 營業時間：視覺化體驗撰寫器![教學課程徽章](/help/main/assets/tutorial.png)

這支影片記錄了「[營業時間](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」，這是一項 Adobe 客戶服務團隊主導的計劃。

* VEC 運作原理
* 如何避免 VEC 的常見問題
* 透過一系列練習，日後可應用於 VEC

>[!VIDEO](https://video.tv.adobe.com/v/20784/)
