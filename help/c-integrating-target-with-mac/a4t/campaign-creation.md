---
description: 您可以在 Target Standard/Premium 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
seo-description: 您可以在 Target Standard/Premium 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。
seo-title: 活動建立
solution: Target
title: 活動建立
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 活動建立{#activity-creation}

您可以在 Target Standard/Premium 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。

設定使用 Analytics 做為報表來源的活動之前，請建立活動的目標，例如改善每位訪客帶來的收入 (RPV) 或增加購物車的點擊次數。選擇活動的最終成功量度。儘管您隨時可以在 Analytics 中選取其他的量度，您仍必須指定預期此測試產生作用的特定量度。

建立使用 Analytics 作為報表來源的 Target Standard 活動與設定一般的 Target Standard 活動類似，但有一些差異。例如，在建立活動時您無法選取報表的區段，因為檢視報表時可以套用 Analytics 中可用的所有區段。

1. 按一下 **[!UICONTROL 「建立活動」]**。

   >[!NOTE]
   >
   >如果使用 Analytics 作為報表來源，活動名稱不能包含「%」字元。

1. 選取活動類型並開始設定活動。
1. 進入活動建立流程的 **[!UICONTROL 「設定」]** 部分時，請選擇 **[!UICONTROL 「Adobe Analytics」]** 並指定您的公司。
1. 選擇一個報表套裝。

   您可以選擇 Adobe Analytics 中可供您使用的任何報表套裝。報表套裝會定義所收集的資料將可供使用的位置。報表套裝清單中未包括虛擬報表套裝。

   選取報表套裝時，您可能遇到兩個可能的錯誤:

   * 您遇到沒有可用的報表套裝的錯誤，但您的帳戶已正確設定。
   您可能需要洽詢您的 Analytics 公司。如果您的 Experience Cloud 帳戶已綁定至多個 Analytics 公司，請從 Target 登出，並在適當的公司上登入 Analytics。然後回到 Target，接著報表套裝將會載入。

   * 您並未看到所預期的報表套裝。
   只有佈建為連接至 Adobe Target 的報表套裝才可供選取。如果沒看到您要找的報表套裝，請先登出再登入 Adobe Experience Cloud，然後再試一次。

   如果報表套裝仍未出現在清單中，請[請聯絡客戶服務](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
1. 指定您的追蹤伺服器。

   請參閱[使用 Analytics 追蹤伺服器](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定義體驗。
1. 指定活動目標。

   您需要選取要用作每個測試目標的成功量度。您的活動目標為代表成功活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。您可以在 Analytics 量度選取器中選擇任何可用的 Analytics 量度。

   >[!NOTE]
   >
   >您可以傳送自訂 Target 型量度至 Analytics，而非仰賴於 Analytics 資料。例如，您可以監控頁面上的點擊，Analytics 一般不會追蹤這個部分。此自訂量度會自動從 Target 伺服器傳送至 Analytics，並在 Analytics 量度選取器中顯示為「Target 轉換」量度。如果您選擇使用 Analytics 量度，則 Target 轉換量度會為空白。

   設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對活動改善之項目的提示。

   在訪客達到目標之後會保持在活動中。訪客會繼續看見活動內容，但不會被計為新活動項目。

   >[!NOTE]
   >
   >在設定 Analytics 作為您的報表來源之後設定活動時，沒有選項可用來設定報表對象。在 Target 活動報表可以取得 Analytics 區段。

1. 按一下 **[!UICONTROL 「儲存」]**。

