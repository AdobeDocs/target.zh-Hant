---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;reporting source
description: 如果您使用較舊版本的 at.js 或 mbox.js，您必須針對使用 Analytics for Target (A4T) 的活動指定分析追蹤伺服器。
title: 使用 Analytics 追蹤伺服器
feature: null
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 53%

---


# 使用 Analytics 追蹤伺服器{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). mbox.js 或 at.js 資料庫會自動傳送追蹤伺服器值至 [!DNL Target]。在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Cloud Debugger] to determine the correct tracking server for your activity.

您應該在將傳送活動的頁面上檢視偵錯程式，以確保選取正確的追蹤伺服器。您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. From the page on which you are creating your activity, open the [!DNL Adobe Experience Cloud Debugger].

   如果您尚未安裝除錯程式，請參 [閱安裝Experience Cloud除錯程式](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html)。

   ![](assets/Screen_DebuggerTrackServ.png)

   The analytics tracking server is found in the [!UICONTROL SiteCatalyst Image] section of the debugger. 根據實施情況，欄位會稱為&#x200B;*第一方 Cookie*&#x200B;或&#x200B;*第三方 Cookie*，而 追蹤伺服器值將採用這些格式中的其中一個:[!DNL Analytics]

   * (適用於 CNAME 實施)
   * (適用於非 RDC 實作)
   * (適用於 RDC 實施)

   *Company*[!DNL Analytics] 代表 公司名稱，*metrics* 為 CNAME 值的範例，以及 *d1* 為 資料中心的範例。[!DNL Analytics]
1. 複製欄位的整個內容。
1. 在您的活動[!UICONTROL 「目標與設定」][!UICONTROL 畫面的]「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

