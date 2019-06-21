---
description: 如果您使用較舊版本的 at.js 或 mbox.js，您必須針對使用 Analytics for Target (A4T) 的活動指定分析追蹤伺服器。
keywords: analytics 追蹤伺服器;A4T, Adobe Experience Cloud Debugger;報表來源
seo-description: 如果您使用較舊版本的 at.js 或 mbox.js，您必須針對使用 Analytics for Target (A4T) 的活動指定分析追蹤伺服器。
seo-title: 使用 Analytics 追蹤伺服器
title: 使用 Analytics 追蹤伺服器
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 使用 Analytics 追蹤伺服器{#use-an-analytics-tracking-server}

如果您使用較舊版本的 at.js 或 mbox.js，您必須針對使用 Analytics for Target (A4T) 的活動指定分析追蹤伺服器。

>[!NOTE]
>
>如果您使用 Adobe Analytics 做為活動的報表來源，若您使用的是 mbox.js 61 版 (或更新版本) 或 at.js 0.9.1 版 (或更新版本)，則不需在活動建立期間指定追蹤伺服器。mbox.js 或 at.js 資料庫會自動傳送追蹤伺服器值至 [!DNL Target]。在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。

若要確保來自 Target 的資料會進入 Analytics 中的正確位置，A4T 要求在從 Target 對 Modstats 的所有呼叫中傳送分析追蹤伺服器。針對使用多個追蹤伺服器的實施，您可以使用 Adobe Experience Cloud Debugger 來決定您的活動的正確追蹤伺服器。

您應該在將傳送活動的頁面上檢視偵錯程式，以確保選取正確的追蹤伺服器。您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 從建立您的活動所在的頁面，開啟 Adobe Experience Cloud Debugger。

   如果您尚未安裝除錯程式，請依照 [Adobe Debugger 安裝說明](https://marketing.adobe.com/resources/help/zh_TW/sc/implement/debugger_install.html)操作。

   ![](assets/Screen_DebuggerTrackServ.png)

   您可以在偵錯程式的 SiteCatalyst 影像區段中找到分析追蹤伺服器。根據實施情況，欄位會稱為*第一方 Cookie*或*第三方 Cookie*，而 Analytics 追蹤伺服器值將採用這些格式中的其中一個:

   * (適用於 CNAME 實施)
   * (適用於非 RDC 實作)
   * (適用於 RDC 實施)
   *Company* 代表 Analytics 公司名稱，*metrics* 為 CNAME 值的範例，以及 *d1* 為 Analytics 資料中心的範例。
1. 複製欄位的整個內容。
1. 在您的活動[!UICONTROL 「目標與設定」][!UICONTROL 畫面的]「報表設定」**區段中，於[!UICONTROL 「追蹤伺服器」]** 欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >您您活動的「報表來源」必須選取「Adobe Analytics」，「追蹤伺服器」欄位才能使用。

