---
description: Target 可讓您追蹤任何元素上的點擊做為成功量度。
keywords: 點擊追蹤; 追蹤點擊; 點擊; AppMeasurement
seo-description: Target 可讓您追蹤任何元素上的點擊做為成功量度。
seo-title: 點擊追蹤
solution: Target
subtopic: 快速入門
title: 點擊追蹤
topic: Standard
uuid: 4a8fbb23-93d8-49f3-aca3-dbbdd6da0178
translation-type: tm+mt
source-git-commit: 4af5c367d292524d508eae6e535dd0925b2f9013

---


# 點擊追蹤{#click-tracking}

Target 可讓您追蹤任何元素上的點擊做為成功量度。

>[!NOTE]
>
>Target 全域 mbox 作為表單式活動的地點時，不支援追蹤點擊。

## 設定點擊追蹤 {#section_5540C5A533114E57BAE022A600B02E72}

1. 在活動的[!UICONTROL 「目標與設定」]頁面上設定您的目標時，請選取**[!UICONTROL 「轉換」]成功量度。**
1. 針對動作，選取**[!UICONTROL 「點擊元素」]**，然後按一下**[!UICONTROL 「選取元素」]**。

   您的頁面隨即在[!UICONTROL 可視化體驗撰寫器] (VEC) 中開啟。

1. 選取您要追蹤的任何元素。

   請參閱以下的「考量事項」區段，以取得選取元素的相關提示。

1. 按一下畫面上方的核取記號來儲存您的選擇項目。

當活動加入者點擊選取的元素時，該點擊會被計為轉換。

## 考量事項 {#considerations}

選取元素時，有數個項目要考慮:

* 設定點按追蹤時，可使用DOM路徑功能。當您按一下頁面上的元素時，會顯示「CMS選項」功能表。此外，對應的DOM路徑會顯示在頁面底部。您可以使用DOM路徑快速查看所選元素(類型、ID和類別)的相關資訊，並向上或向下移動DOM路徑以選取所需元素。

   ![DOM路徑插圖](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   就像在活動建立工作流程中的步驟中建立體驗時，頁面底部的DOM路徑選擇器可讓您選擇元素。在從DOM路徑選取元素時，CMS中的對應元素會顯示為「選取」。若要取消選取選取的元素，您可以再次按一下DOM路徑選擇器中的元素，或按一下CMS中的「選取的」方塊。

   如需詳細資訊，請參閱 [「視覺體驗撰寫器選項」](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) 中 *使用DOM路徑導覽元素*。

* 您可以瀏覽至不同頁面，以追蹤您可能不會變更內容之頁面上的點擊。必須在活動中包括這個不同的頁面，使用[多頁功能](../../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)，並且必須已在其上實施 [!DNL at.js] 或 [!DNL mbox.js]。
* 如果您選取多個元素，當加入者點擊所選取元素的任何一個時，即會計入該點擊。若要個別計算每個項目，請為每個元素設定個別的成功量度。
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
   | [ ] | 方括弧 |

* 如果您使用 [!DNL at.js] 點擊追蹤，並且也使用 Analytics AppMeasurement，[!DNL at.js] 點擊追蹤會取消所有其他的點擊事件處理常式。因此，AppMeasurement 點擊事件處理常式永遠不會執行。

   當基礎元素為 [!DNL at.js] (連結) 標記或`A` 標記時，`FORM` 對於點擊追蹤有特殊的處理方式。

   當點擊追蹤事件附加至 [!DNL at.js] (連結) 標記或 `A` 標記時，下列步驟是由 `FORM` 執行:

   1. 叫用 `event.preventDefault()`。

   1. 觸發 Target 要求。

   1. 在 Target 要求 success 或 error 回呼時，執行預設行為:

      * `A` (連結) 標記: 預設行為是導覽至 HREF 屬性定義的 URL。
      * `FORM` 標記: 預設行為是提交表單。
   此預設行為可能會干擾 Analytics 點擊追蹤。如果您使用 Analytics，針對點擊追蹤，您應該仰賴於 Analytics 而非 Target。

* 頁面和活動URL屬於不同屬性的頁面上不會記錄點擊追蹤。企業使用者權限是Target Premium功能。如需詳細資訊，請參閱 [企業使用者權限](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

## 訓練影片 {#section_36607204DAE146E3B8E2C609D244EDB1}

此影片包括關於建立點擊追蹤成功量度的資訊。

* 瞭解「目標」量度
* 瞭解和建置轉換、收入和參與量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)