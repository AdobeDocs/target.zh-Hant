---
description: 提供可視化體驗撰寫器 (VEC) 的使用資訊。
seo-description: 提供在 Adobe Target 中使用可視化體驗撰寫器 (VEC) 的資訊。
seo-title: Adobe Target 可視化體驗撰寫器 (VEC)
title: 可視化體驗撰寫器 (VEC)
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
translation-type: tm+mt
source-git-commit: f59e96cd5afcae9d27d730aecead9eb360f04026

---


# 可視化體驗撰寫器 (VEC){#visual-experience-composer-vec}

提供可視化體驗撰寫器 (VEC) 的使用資訊。

CMS是主要的功能 [!DNL Adobe Target]之一。CMS是一種編輯器，可讓行銷人員和設計人員使用視覺化介面來建立和變更內容。您可以進行許多設計選擇，而不需直接編輯程式碼。您也可以使用撰寫器中提供的編輯選項來編輯 HTML 和 JavaScript。

在 Target **[!UICONTROL 「設定]** &gt; **[!UICONTROL 偏好設定]**」標籤上，您可以輸入預設可視化體驗撰寫器 URL。

![預設CMS URL設定](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

此URL會決定您開啓CMS時的開始位置。如果不輸入預設值，則開啟編輯器時會從空白頁開始，到時可以指定 URL。

>[!NOTE]
>
>有些瀏覽器(例如Firefox)可能會阻止頁面在頁面包含混合內容(例如安全網站中的非安全頁面)時顯示頁面。如果您的頁面未顯示，請按一下瀏覽器位址列中URL旁的圖示，然後按一下 **[!UICONTROL 此頁面上的「停用保護]**」。此問題不影響向網站訪客顯示您的頁面。

頁面上iframe內部的內容無法在CMS中修改。若要編輯iframe內的內容，請確定iframe文件已啓用Target，然後在CMS中載入該iframe URL。

您可以使用橫跨頁面頂端的下拉式功能表，以不同對象的角度或以不同體驗來檢視您的頁面。您可以在第二個下拉式清單中提供每一個體驗的名稱。例如，假設您在導覽列中測試首頁連結的位置，您可能將最先出現首頁連結的體驗命名為像是「首頁連結」，以輕鬆地辨別清單中的體驗。

>[!NOTE]
>
>如果變更頁面結構而影響該頁面上建立的活動中所使用的位置，可能會在編輯體驗時造成問題。如果位置已變更為CMS以外的位置，Target可能無法找到內容變更的位置。

當您在頁面上四處移動滑鼠時，即時線上方塊會緊跟著游標，並醒目提示頁面上的元素。

![CMS反白標示](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

按一下 **[!UICONTROL 「覆蓋]** 」圖示，變更反白顯示顯示的方式。例如，您可以選擇只強調影像、連結、區域mbox、修改或JavaScript。您可以變更反白顯示的顏色。您也可以指定用於醒目提示不同元素類型的醒目提示顏色和填色類型。

![變更覆蓋設定](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

按一下反白顯示的元素，以取得該元素類型可用的選項，例如，您可以按一下影像並選取 **[!UICONTROL 「編輯&gt;文字/HTML]** 」來變更文字，或按一下按鈕並變更背景顏色。您可以使用頁面左上方的按鈕來開啟或關閉覆蓋。

您也可以按一下**[!UICONTROL 「瀏覽」]**，然後導覽至主要頁面所提供的頁面，例如出貨頁面或購物車，然後在該頁面上測試變更。您也可以存取暫留時可用的頁面元素，例如飛出功能表和迷你購物車。完成瀏覽至頁面時，按一下**[!UICONTROL 「撰寫」]來編輯體驗。**例如，您可能需要變更購物車下拉式清單或影像輪播的設計。

>[!NOTE]
>
>如果暫留狀態依賴 JavaScript，請確定未選取**[!UICONTROL 「停用 JavaScript」]**。JavaScript 必須啟用才能編輯 JavaScript 元素。

如需CMS可用選項的詳細資訊，請參閱 [Visual Experience Composer選項](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)。

您可以在載入頁面時對頁面執行一些修改(或在頁面載入失敗後)，也可以取消CMS中的頁面載入。如需詳細資訊，請參閱:

* [頁面載入時編輯頁面，或在頁面無法載入後編輯頁面](#loading)
* [取消在CMS內載入頁面](#cancel-loading)

## 頁面載入時編輯頁面，或在頁面無法載入後編輯頁面 {#loading}

您可以在 VEC 中的頁面載入前，或甚至頁面完全無法載入時 (例如自訂程式碼無法繼續正常運作) 執行許多動作。

有些原因會在載入頁面時或在無法載入後，對頁面進行存取或編輯：

* 您想要對頁面進行簡單修改，例如新增自訂代碼或變更體驗的名稱
* 您想要從不再存取的頁面複製現有的自訂代碼
* 您知道某個頁面不會在CMS內載入，但您想要進行簡單編輯

頁面載入(或載入失敗後)、 [!UICONTROL 「修改」][!UICONTROL ] 面板、體驗頂端的設定(覆蓋、修改、設定等)都可以存取。

下圖顯示您可以插入自訂代碼，或在頁面仍在載入時執行其他動作：

![頁面載入](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## 取消在CMS內載入頁面 {#cancel-loading}

您可以取消CMS中的頁面載入，以解除鎖定活動的編輯，而無需等待頁面載入。此功能可節省時間，並可協助您更有效率地進行簡單編輯或插入自訂代碼，而無需等待頁面載入。

您可能想要取消CMS中頁面載入的一些原因包括：

* 您想要對現有修改進行小幅編輯
* 您想要刪除一或多個現有修改
* 您想要插入或編輯自訂代碼
* 您錯誤輸入錯誤的頁面URL
* 在載入CMS中的頁面之前，您想要啓用或停用JavaScript
* 您想要新增更多範本測試規則至「頁面傳送」標準
* 您想要覆寫全域增強Experience Composer(EEC)切換頁面時，透過EEC或iframe-only的頁面載入頁面可能會有所不同頁面

在CMS中取消頁面載入後，您就可以在活動中切換體驗，而無需等待頁面載入。若要再次檢視CMS內的頁面，您必須按一下 **[!UICONTOL 「重新載入]** 」按鈕。

>[!IMPORTANT]
>
>請注意，當自訂代碼或進行任何修改時，只要選擇取消CMS中的載入，您就必須確定您的編碼或變更已正確完成。確保您執行適當的QA，以確保您的自訂代碼及任何其他修改都如預期般傳遞。

若要取消在CMS內載入頁面，請在載入頁面時按一下 **[!UICONTROL 「取消載入]** 」按鈕。在目前的編輯工作階段期間，頁面不會載入此活動的CMS。

![取消載入按鈕](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

若要繼續管理目前活動中的體驗或新增修改，您必須按一下 **[!UICONTROL 「重新載入]** 」按鈕。

![重新載入按鈕](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>此功能目前已知的問題會在下一版中修正。如需詳細資訊，請參閱 [「CMS內的取消載入頁面中的頁面」問題和已解決問題](/help/r-release-notes/known-issues-resolved-issues.md#cancel) 頁面。

## 訓練影片

以下影片含有本文章探討之概念的詳細資訊。

### 可視化體驗撰寫器 (7:17)

這部影片提供關於使用可視化體驗撰寫器選項的資訊。

* 變更頁面的內容
* 變更頁面的配置

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### 可視化體驗撰寫器 (1/2) (上午 07:17)

* 變更頁面的內容
* 變更頁面的配置

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### 可視化體驗撰寫器 (2/2) (上午 07:29)

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### 營業時間: 可視化體驗撰寫器

這支影片記錄了「[營業時間](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」，這是一項 Adobe 客戶服務團隊主導的計劃。

* VEC 運作原理
* 如何避免 VEC 的常見問題
* 透過一系列練習，日後可應用於 VEC

>[!VIDEO](https://video.tv.adobe.com/v/20784/)