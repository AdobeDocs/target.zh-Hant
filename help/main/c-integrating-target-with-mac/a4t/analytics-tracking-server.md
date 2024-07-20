---
keywords: analytics追蹤伺服器；A4T；Adobe Experience Cloud debugger；Adobe Experience Platform debugger；報表來源；開發人員工具
description: 如果您使用舊版的at.js，瞭解如何為使用Analytics for [!DNL Target] (A4T)的活動指定Analytics追蹤伺服器。
title: 如何使用Analytics追蹤伺服器？
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 14%

---

# 使用[!DNL Analytics]追蹤伺服器

如果您使用較舊版本的at.js，您必須針對[!DNL Adobe Target] (A4T)使用[!DNL Adobe Analytics]的活動指定[!DNL Analytics]追蹤伺服器。

>[!NOTE]
>
>如果您使用 at.js 0.9.1 版 (或更新版本)，您在活動建立期間就不需要指定追蹤伺服器。 at.js 程式庫會自動傳送追蹤伺服器值給 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL Goals & Settings]頁面上的[!UICONTROL Tracking Server]欄位保留空白。
>
>[!DNL Target]團隊同時支援at.js 1。*x* 和 at.js 2 中的 Hide Body 和 Show Body 呼叫。*x* 使用供跨網域追蹤功能時。 升級至任一主要版本的at.js最新更新，以確保您執行的是支援的版本。 如需詳細資訊，請參閱[at.js版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}。

為確保來自[!DNL Target]的資料進入[!DNL Analytics]中的正確位置，A4T要求在所有從[!DNL Target]呼叫Modstats時傳送[!DNL Analytics]追蹤伺服器。 針對使用多個追蹤伺服器的實作，請使用[!DNL Adobe Experience Platform Debugger]或瀏覽器的開發人員工具來決定活動的正確追蹤伺服器。

## 使用[!DNL Adobe Experience Platform Debugger]取得[!DNL Analytics]追蹤伺服器

您應在傳送活動的頁面上檢視除錯工具，以確保選取正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 從您正在建立活動的頁面，開啟[!DNL Adobe Experience Platform Debugger]。

   如果您尚未安裝偵錯工具，請參閱[Adobe Experience Platform Debugger概述](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html)。

1. 按一下左側導覽功能表中的&#x200B;**[!UICONTROL Analytics]**。

   ![Screen_DebuggerTrackServ影像](assets/Screen_DebuggerTrackServ.png)

   在Debugger的[!UICONTROL Hostname]區段中找到[!DNL Analytics]追蹤伺服器。

   * **第一方追蹤伺服器**：如果要求的主機名稱符合您所在的網域，則為第一方追蹤伺服器。 例如，如果您在`adobe.com`，則`adobe.com`是第一方追蹤伺服器。
   * **協力廠商追蹤伺服器**：協力廠商追蹤伺服器通常是`[company].sc.omtrdc.net`，其中公司是您公司的名稱，但結尾一律為`sc.omtrdc.net`。
   * **CNAME實作**： `sstats.adobe.com`是https （安全）要求的CNAME第一方追蹤伺服器的範例。 `stats.adobe.com`是http （非安全）頁面的CNAME第一方要求範例。

1. 複製欄位的整個內容。

1. 在活動&#x200B;**[!UICONTROL Goal & Settings]**&#x200B;畫面的&#x200B;**[!UICONTROL Reporting Settings]**&#x200B;區段中，將追蹤伺服器資訊貼到&#x200B;**[!UICONTROL Tracking Server]**&#x200B;欄位中。

   >[!NOTE]
   >
   >針對您的活動選取[!UICONTROL Analytics as the Reporting Source]，讓[!UICONTROL Tracking Server]欄位可供使用。

## 使用瀏覽器的開發人員工具取得[!DNL Analytics]追蹤伺服器

開發人員工具應在傳送活動的頁面上檢視，以確保您選取正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 從建立活動的頁面上，開啟瀏覽器的開發人員工具(在Google Chrome中，按一下右上角的三個垂直的點> 「更多工具>開發人員工具」)。

   ![Chrome開發人員工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 按一下「**[!UICONTROL Network]**」標籤。

1. 篩選`/ss,`以顯示[!DNL Analytics]個請求。

   ![使用/ss search的Chrome開發人員工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   追蹤伺服器是要求的主機名稱。

   * **第一方追蹤伺服器**：如果要求的主機名稱符合您所在的網域，則為第一方追蹤伺服器。 例如，如果您在`adobe.com`，則`adobe.com`是第一方追蹤伺服器。
   * **協力廠商追蹤伺服器**：協力廠商追蹤伺服器通常是`[company].sc.omtrdc.net`，其中公司是您公司的名稱，但結尾一律為`sc.omtrdc.net`。
   * **CNAME實作**： `sstats.adobe.com`是https （安全）要求的CNAME第一方追蹤伺服器的範例。 `stats.adobe.com`是http （非安全）頁面的CNAME第一方要求範例。

1. 複製欄位的整個內容。

1. 在活動&#x200B;**[!UICONTROL Goal & Settings]**&#x200B;畫面的&#x200B;**[!UICONTROL Reporting Settings]**&#x200B;區段中，將追蹤伺服器資訊貼到&#x200B;**[!UICONTROL Tracking Server]**&#x200B;欄位中。

   >[!NOTE]
   >
   >針對您的活動選取[!UICONTROL Analytics as the Reporting Source]，讓[!UICONTROL Tracking Server]欄位可供使用。
