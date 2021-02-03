---
keywords: 點擊追蹤; 追蹤點擊; 點擊; AppMeasurement
description: Adobe Target可讓您將任何元素的點按次數作為成功度量進行追蹤。
title: 點按次數追蹤
feature: Success Metrics
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 92%

---


# 點擊追蹤

[!DNL Adobe Target] 可讓您將任何元素上的點按次數作為成功度量進行追蹤。

>[!NOTE]
>
>當全域Target請求用作表單型活動中的位置時，不支援追蹤點按。

## 設定點擊追蹤 {#section_5540C5A533114E57BAE022A600B02E72}

1. 在活動的[!UICONTROL 「目標與設定」]頁面上設定您的目標時，請選取&#x200B;**[!UICONTROL 「轉換」]**&#x200B;成功量度。
1. 針對動作，選取&#x200B;**[!UICONTROL 「點擊元素」]**，然後按一下&#x200B;**[!UICONTROL 「選取元素」]**。

   您的頁面隨即在[!UICONTROL 可視化體驗撰寫器] (VEC) 中開啟。

1. 選取您要追蹤的任何元素。

   請參閱以下的「考量事項」區段，以取得選取元素的相關提示。

1. 按一下畫面上方的核取記號來儲存您的選擇項目。

當活動加入者點擊選取的元素時，該點擊會被計為轉換。

## 所選元素面板{#selected-elements}

若為 A/B 測試、體驗鎖定目標 (XT)、Automated Personalization (AP) 和多變數測試 (MVT) 活動，[!UICONTROL 所選元素]面板會在右側列出點擊追蹤的所有所選元素。

![所選元素面板](/help/c-activities/r-success-metrics/assets/selected-elements.png)

當您將游標移至[!UICONTROL 所選元素]面板中的某個元素上時，有一些可套用的動作。下表說明可在元素上執行的各個動作:

| 動作 | 說明 |
| --- | --- |
| 資訊 | 顯示元素類型和選取器的完整 DOM 路徑。 |
| 編輯   | 可讓您編輯 CSS 選取器。 |
| 刪除 | 刪除元素。 |

### 新增元素

如果您已知道選取器的 DOM 路徑，您可以按一下位於面板頂端的加號圖示手動新增。

![新增元素圖示](/help/c-activities/r-success-metrics/assets/add-element.png)

### 所選元素暫留快顯

為點擊追蹤選取多個元素後，您可以在活動的[!UICONTROL 目標與設定]步驟上按一下[!UICONTROL 所選元素]連結，查看針對點擊追蹤所選之元素的完整清單。此清單包含元素的完整 DOM 路徑，可協助您驗證要用於點擊追蹤的所選元素。

![所選元素連結](/help/c-activities/r-success-metrics/assets/elements-selected-link.png)

## 考量事項 {#considerations}

選取元素時，有數個項目要考慮:

* 設定點擊追蹤時，可使用 DOM 路徑功能。當您按一下頁面上的元素時，VEC 選項功能表隨即顯示。此外，對應的 DOM 路徑會顯示於頁面底部。您可以使用 DOM 路徑快速查看有關已選取元素 (類型、ID 和類別) 的資訊，然後向上或向下移動 DOM 路徑以選取想要的元素。

   ![DOM 路徑圖](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   就像在活動建立工作流程的步驟 1 建立體驗時一樣，頁面底部的 DOM 路徑選取器可讓您選擇元素。在從 DOM 路徑選取元素時，VEC 中的對應元素會顯示為「已選取」。若要取消選取已選取的元素，您可以再次按一下 DOM 路徑選取器中的元素，或按一下 VEC 中的「已選取」方塊。

   如需詳細資訊，請參閱&#x200B;*可視化體驗撰寫器選項*&#x200B;中的[使用 DOM 路徑導覽元素](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)。

* 您可以瀏覽至不同頁面，以追蹤您可能不會變更內容之頁面上的點擊。必須在活動中包括這個不同的頁面，使用[多頁功能](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)，並且必須已在其上實施 [!DNL at.js] 或 [!DNL mbox.js]。
* 如果您選取多個元素，當加入者點擊所選取元素的任何一個時，即會計入該點擊。若要個別計算每個項目，請為每個元素設定個別的成功量度。若要按一下頁面上的數個元素來計算一個項目，請編輯「CSS元素選擇器」以比對多個元素。
* 確定選取您要追蹤的元素層級。例如，在指定按鈕時，請確定您選取連結而非按鈕文字。
* 點擊事件會傳送到與點擊相同的頁面上的 [!DNL Target]。
* 如果點擊追蹤量度為 A4T 活動的目標量度，訪客必須在頁面載入的 60 秒內點擊此元素，量度才能進行追蹤。
* 點擊追蹤對於其選取器中包括逸出字元的元素無法運作，包括下列:

   | 字元 | 說明 |
   |---|---|
   | # | 數字符號或雜湊 |
   | : | 冒號 |
   | 。 | 時段 |
   | $ | 貨幣符號 |
   | `[ ]` | 方括弧 |

* 如果您使用 [!DNL at.js] 點擊追蹤，並且也使用 Analytics AppMeasurement，[!DNL at.js] 點擊追蹤會取消所有其他的點擊事件處理常式。因此，AppMeasurement 點擊事件處理常式永遠不會執行。

   當基礎元素為 [!DNL at.js] (連結) 標記或`A` 標記時，`FORM` 對於點擊追蹤有特殊的處理方式。

   當點擊追蹤事件附加至 [!DNL at.js] (連結) 標記或 `A` 標記時，下列步驟是由 `FORM` 執行:

   1. 叫用 `event.preventDefault()`。

   1. 觸發 Target 要求。

   1. 在 Target 要求 success 或 error 回呼時，執行預設行為:

      * `A` (連結) 標記: 預設行為是導覽至 HREF 屬性定義的 URL。
      * `FORM` 標記: 預設行為是提交表單。

   此預設行為可能會干擾 Analytics 點擊追蹤。如果您使用 Analytics，針對點擊追蹤，您應該仰賴於 Analytics 而非 Target。

* 如果頁面上的頁面和活動 URL 屬於不同屬性，系統則不會記錄點擊追蹤。企業使用者權限為 Target Premium 功能。如需詳細資訊，請參閱[企業使用者權限](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

## 訓練影片 {#section_36607204DAE146E3B8E2C609D244EDB1}

此影片包括關於建立點擊追蹤成功量度的資訊。

* 瞭解「目標」量度
* 瞭解和建置轉換、收入和參與量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)