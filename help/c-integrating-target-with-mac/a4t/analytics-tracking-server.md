---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Platform debugger;reporting source;developer tools
description: 如果您使用較舊版本的 at.js 或 mbox.js，您必須針對使用 Analytics for Target (A4T) 的活動指定分析追蹤伺服器。
title: 使用 Analytics 追蹤伺服器
feature: a4t general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 27%

---


# 使用 Analytics 追蹤伺服器

If you are using an older version of at.js or mbox.js, you must specify an Analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). mbox.js 或 at.js 資料庫會自動傳送追蹤伺服器值至 [!DNL Target]。在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。
>
>團 [!DNL Target] 隊支援at.js 1。*x* 與 at.js 2.*x* 之間的對應。請升級至任一主要版本的最新更新at.js，以確保您執行的是支援的版本。 For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an Analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Platform Debugger] or your browser&#39;s Developer Tools to determine the correct tracking server for your activity.

## 使用Adobe Experience Platform Debugger取得Analytics追蹤伺服器

您應該在將傳送活動的頁面上檢視偵錯程式，以確保選取正確的追蹤伺服器。您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. From the page on which you are creating your activity, open the [!DNL Adobe Experience Platform Debugger].

   如果您尚未安裝除錯程式，請參 [閱Adobe Experience Platform除錯程式簡介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)。

   ![](assets/Screen_DebuggerTrackServ.png)

1. 按一 **[!UICONTROL 下左側導覽功]** 能表中的「分析」。

   The Analytics tracking server is found in the [!UICONTROL Hostname] section of the debugger.

   * **第一方追蹤伺服器**:如果請求的主機名稱符合您所在的網域，則會是第一方追蹤伺服器。 例如，如果您在， `adobe.com`則 `adobe.com` 是第一方追蹤伺服器。
   * **協力廠商追蹤伺服器**:協力廠商追蹤伺服器通 `[company].sc.omtrdc.net` 常是公司名稱所在的位置，但一律以結尾 `sc.omtrdc.net`。
   * **CNAME實作**: `sstats.adobe.com` 是CNAME第一方追蹤伺服器針對https（安全）要求的範例。 `stats.adobe.com` 是CNAME第一方要求http（非安全）頁面的範例。

1. 複製欄位的整個內容。

1. 在您的活動&#x200B;**[!UICONTROL 「目標與設定」]****[!UICONTROL 畫面的]**「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

## 使用您瀏覽器的「開發人員工具」取得Analytics追蹤伺服器

應在傳送活動的頁面上檢視「開發人員工具」，以確保您選擇正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 從您要建立活動的頁面，開啟瀏覽器的「開發人員工具」（在Google Chrome中，按一下右上角的三個垂直橢圓形>更多工具>開發人員工具）。

   ![Chrome開發人員工具](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Click the **[!UICONTROL Network]** tab.

1. 篩選以 `/ss,` 顯示Analytics請求。

   ![含/ss搜尋的Chrome開發人員工具](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   追蹤伺服器是請求的主機名稱。

   * **第一方追蹤伺服器**:如果請求的主機名稱符合您所在的網域，則會是第一方追蹤伺服器。 例如，如果您在， `adobe.com`則 `adobe.com` 是第一方追蹤伺服器。
   * **協力廠商追蹤伺服器**:協力廠商追蹤伺服器通常 `[company].sc.omtrdc.net` 是公司名稱所在的位置，但一律以結尾 `sc.omtrdc.net`。
   * **CNAME實作**: `sstats.adobe.com` 是CNAME第一方追蹤伺服器針對https（安全）要求的範例。 `stats.adobe.com` 是CNAME第一方要求http（非安全）頁面的範例。

1. 複製欄位的整個內容。

1. 在您的活動&#x200B;**[!UICONTROL 「目標與設定」]****[!UICONTROL 畫面的]**「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

