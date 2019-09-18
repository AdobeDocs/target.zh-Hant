---
description: 您可以在 Target Standard 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。
keywords: 鎖定目標; Analytics; 追蹤伺服器
seo-description: 您可以在 Target Standard 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。
seo-title: 使用 Analytics 資料
solution: Target
title: 使用 Analytics 資料
uuid: 4ac0c181-030b-4cf5-b138-acf02c7af4f6
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# 使用 Analytics 資料{#using-analytics-data}

您可以在 Target Standard 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。

For detailed information about setting up Analytics as the data source for Target, see [Adobe Analytics as the Reporting Source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

設定使用 Analytics 做為報表來源的活動之前，請建立活動的目標，例如改善每位訪客帶來的收入 (RPV) 或增加購物車的點擊次數。選擇促銷活動的最終成功量度。儘管您隨時可以在 Analytics 中選取其他的量度，您仍必須指定預期此測試產生作用的特定量度。

>[!NOTE]
>
>如果您已將您的 Adobe Experience Cloud 帳戶與 Analytics 和 Target 連結，便可使用 Adobe Analytics 選項，即使您的帳戶尚未設定 Target 和 Analytics 之間的整合。

選取 Analytics 做為 Target 的報表來源時，請選取 Analytics 報表套裝來接收 Target 活動資料。若要這麼做，請先從您帳戶繫結的 Analytics 公司中選擇任一，接著為該活動選取適當的報表套裝。只有佈建為連接至 Adobe Target 的報表套裝才可供選取。如果沒看到您要找的報表套裝，請先登出再登入 Adobe Experience Cloud，然後再試一次。如果報表套裝仍未出現在清單中，請聯絡客戶服務。

Analytics for Target 需要追蹤伺服器才能正確報告結果。「追蹤伺服器」欄位中將出現預設的追蹤伺服器。如果您使用一部以上的追蹤伺服器，您應該檢查以確保您在此欄位中包括了正確的追蹤伺服器。請參閱[使用 Analytics 追蹤伺服器](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)以取得詳細資訊。

>[!NOTE]
>
>如果您使用 Adobe Analytics 做為活動的報表來源，若您使用的是 mbox.js 61 版 (或更新版本) 或 at.js 0.9.1 版 (或更新版本)，則不需在活動建立期間指定追蹤伺服器。mbox.js 或 at.js 資料庫會自動傳送追蹤伺服器值至 [!DNL Target]。在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。

在設定 Analytics 作為您的報表來源之後設定活動時，沒有選項可用來設定報表對象。在 Target 活動報表可以取得 Analytics 區段。

您需要選取要用作每個測試目標的成功量度。您的活動目標為代表成功促銷活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。您可以在 Analytics 量度選取器中選擇任何可用的 Analytics 量度。

設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對測試改善之項目的提示。

訪客完成您的目標之後，該訪客便不再包括在促銷活動中。如果訪客在完成活動之後重新進入您的促銷活動，他或她會被計為新訪客。
