---
keywords: 點擊追蹤; 追蹤點擊; 點擊; AppMeasurement
description: 瞭解如何 [!DNL Adobe Target] 可讓您追蹤任何元素上的點選做為成功量度。
title: 什麼是點選追蹤？
feature: Success Metrics
exl-id: 9181424b-179e-49fc-b760-b764a0c3458a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 67%

---

# 點擊追蹤

[!DNL Adobe Target] 可讓您追蹤任何元素上的點選做為成功量度。

>[!NOTE]
>
>全域不支援追蹤點按 [!DNL Target] 請求（當其用作表單式活動中的位置時）。

## 設定點選追蹤 {#section_5540C5A533114E57BAE022A600B02E72}

1. 在活動的[!UICONTROL 「目標與設定」]頁面上設定您的目標時，請選取&#x200B;**[!UICONTROL 「轉換」]**&#x200B;成功量度。
1. 針對動作，選取&#x200B;**[!UICONTROL 「點擊元素」]**，然後按一下&#x200B;**[!UICONTROL 「選取元素」]**。

   您的頁面隨即在[!UICONTROL 可視化體驗撰寫器] (VEC) 中開啟。

1. 選取您要追蹤的任何元素。

   請參閱以下的&#x200B;*「考量事項」*&#x200B;區段，以取得選取元素的相關提示。

1. 按一下 **[!UICONTROL 儲存]** ，儲存您的選取專案。

當活動加入者點擊選取的元素時，該點擊會被計為轉換。

## 所選元素面板 {#selected-elements}

對象 [!UICONTROL A/B測試]， [!UICONTROL 體驗鎖定] (XT)， [!UICONTROL Automated Personalization] (AP)，和 [!UICONTROL 多變數測試] (MVT)活動、a [!UICONTROL 選取的元素] 面板會在右側列出點選追蹤的所選元素。

![所選元素面板](/help/main/c-activities/r-success-metrics/assets/selected-elements.png)

當您將游標停留在中的元素上時，有一些可套用的動作 [!UICONTROL 選取的元素] 面板。 下表說明可在元素上執行的各個動作:

| 動作 | 說明 |
| --- | --- |
| 資訊 | 顯示元素類型和選取器的完整 DOM 路徑。 |
| 編輯   | 可讓您編輯 CSS 選取器。 |
| 刪除 | 刪除元素。 |

### 新增元素

如果您已知道選取器的DOM路徑，可以按一下面板頂端的加號圖示手動新增。

![新增元素圖示](/help/main/c-activities/r-success-metrics/assets/add-element.png)

### 選取的元素快顯視窗

為點擊追蹤選取多個元素後，您可以在活動的[!UICONTROL 目標與設定]步驟上按一下[!UICONTROL 所選元素]連結，查看針對點擊追蹤所選之元素的完整清單。此清單包含元素的完整 DOM 路徑，可協助您驗證要用於點擊追蹤的所選元素。

![所選元素連結](/help/main/c-activities/r-success-metrics/assets/elements-selected-link.png)

## 考量事項 {#considerations}

選取元素時，有數個項目要考慮:

* 設定點擊追蹤時，可使用 DOM 路徑功能。當您按一下頁面上的元素時，VEC 選項功能表隨即顯示。此外，對應的 DOM 路徑會顯示於頁面底部。您可以使用 DOM 路徑快速查看有關已選取元素 (類型、ID 和類別) 的資訊，然後向上或向下移動 DOM 路徑以選取想要的元素。

   ![DOM 路徑圖](/help/main/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   就像在活動建立工作流程的步驟1建立體驗時一樣，頁面底部的DOM路徑選取器可讓您選擇元素。 在從 DOM 路徑選取元素時，VEC 中的對應元素會顯示為「已選取」。若要取消選取選取的元素，您可以在DOM路徑選取器中再次按一下該元素，或按一下VEC中的「已選取」方塊。

   如需詳細資訊，請參閱&#x200B;*可視化體驗撰寫器選項*&#x200B;中的[使用 DOM 路徑導覽元素](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)。

* 您可以瀏覽至不同頁面，以追蹤您可能不會變更內容之頁面上的點擊。必須在活動中包括這個不同的頁面，使用 [多頁功能](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) 和 [!DNL at.js] 必須在其中實作。
* 如果您選取多個元素，當加入者點擊所選取元素的任何一個時，即會計入該點擊。若要個別計算每個項目，請為每個元素設定個別的成功量度。若要藉由按一下頁面上的數個元素來計算一個專案，請編輯CSS元素選取器以比對多個元素。
* 確定選取您要追蹤的元素層級。例如，在指定按鈕時，請確定您選取連結而非按鈕文字。
* 點擊事件會傳送到與點擊相同的頁面上的 [!DNL Target]。
* 如果點選追蹤量度是的目標量度 [!UICONTROL 目標分析] (A4T)活動，訪客必須在頁面載入後60秒內按一下此元素，才會追蹤量度。
* 點擊追蹤對於其選取器中包括逸出字元的元素無法運作，包括下列:

   | 字元 | 說明 |
   |---|---|
   | # | 數字符號或雜湊 |
   | : | 冒號 |
   | 。 | 時段 |
   | $ | 貨幣符號 |
   | `[ ]` | 方括弧 |

* 如果您使用 [!DNL at.js][!DNL Analytics] 點擊追蹤，並且也使用 AppMeasurement，[!DNL at.js] 點擊追蹤會取消所有其他的點擊事件處理常式。因此，AppMeasurement 點擊事件處理常式永遠不會執行。

   當基礎元素為 [!DNL at.js] (連結) 標記或`A` 標記時，`FORM` 對於點擊追蹤有特殊的處理方式。

   當點擊追蹤事件附加至 [!DNL at.js] (連結) 標記或 `A` 標記時，下列步驟是由 `FORM` 執行:

   1. 叫用 `event.preventDefault()`。

   1. 引發 [!DNL Target] 要求。

   1. 開啟 [!DNL Target] 要求成功或錯誤回撥，執行預設行為：

      * `A` (連結) 標記: 預設行為是導覽至 HREF 屬性定義的 URL。
      * `FORM` 標記: 預設行為是提交表單。

   此預設行為可能干擾 [!DNL Analytics] 點選追蹤。 如果您使用 [!DNL Analytics]，您應依賴 [!DNL Analytics] 以追蹤點選，而非 [!DNL Target].

* 如果頁面上的頁面和活動 URL 屬於不同屬性，系統則不會記錄點擊追蹤。企業使用者許可權是 [!DNL Target Premium] 功能。 如需詳細資訊，請參閱[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

* 點擊追蹤量度未連結至活動中的任何特定體驗。

* 如果有必要限制點擊追蹤量度的範圍，請使用受眾。

* 多個活動可以為同一個選擇器定義一個點擊追蹤量度。 若是如此，當訪客符合其中一項活動的資格並點擊該選擇器時，訪客符合資格的所有相關活動的點擊追蹤量度都會增加。

## 訓練影片 {#section_36607204DAE146E3B8E2C609D244EDB1}

此影片包括關於建立點擊追蹤成功量度的資訊。

* 瞭解「目標」量度
* 瞭解並建置 [!UICONTROL 轉換]， [!UICONTROL 收入]、和 [!UICONTROL 參與] 量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)
