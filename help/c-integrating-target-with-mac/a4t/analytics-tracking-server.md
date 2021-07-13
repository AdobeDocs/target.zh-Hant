---
keywords: Analytics追蹤伺服器；A4T;Adobe Experience Cloud Debugger;Adobe Experience Platform Debugger；報表來源；開發人員工具
description: '了解如何為使用Analytics for [!DNL Target] (A4T)的活動指定Analytics追蹤伺服器（若您使用的是舊版at.js）。 '
title: 如何使用Analytics追蹤伺服器？
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 19%

---

# 使用 Analytics 追蹤伺服器

如果您使用的是舊版at.js，則必須為[!DNL Adobe Analytics] for [!DNL Adobe Target](A4T)的活動指定Analytics追蹤伺服器。

>[!NOTE]
>
>如果您使用at.js版本0.9.1（或更新版本），則無需在活動建立期間指定追蹤伺服器。 at.js程式庫會自動傳送追蹤伺服器值至[!DNL Target]。 在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。
>
>[!DNL Target]團隊同時支援at.js 1.*x* 與 at.js 2.*x* 之間的對應。請升級至任一主要版本的at.js最新更新，以確保您執行的是支援的版本。 如需詳細資訊，請參閱[ at.js 版本詳細資訊](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

為確保[!DNL Target]中的資料前往[!DNL Analytics]中的正確位置，A4T要求在從[!DNL Target]對Modstats的所有呼叫中傳送Analytics追蹤伺服器。 若是使用多個追蹤伺服器的實作，請使用[!DNL Adobe Experience Platform Debugger]或瀏覽器的開發人員工具，判斷活動的正確追蹤伺服器。

## 使用Adobe Experience Platform Debugger取得Analytics追蹤伺服器

應該在傳送活動的頁面上檢視除錯程式，以確保您選取正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 從建立活動的頁面，開啟[!DNL Adobe Experience Platform Debugger]。

   如果您尚未安裝除錯程式，請參閱[Adobe Experience Platform除錯程式簡介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)。

   ![](assets/Screen_DebuggerTrackServ.png)

1. 按一下左側導覽功能表中的&#x200B;**[!UICONTROL Analytics]**。

   在偵錯工具的[!UICONTROL Hostname]區段中找到Analytics追蹤伺服器。

   * **第一方追蹤伺服器**:如果要求的主機名稱符合您所在的網域，則是第一方追蹤伺服器。例如，若您位於`adobe.com`,`adobe.com`為第一方追蹤伺服器。
   * **第三方追蹤伺服器**:協力廠商追蹤伺服器通 `[company].sc.omtrdc.net` 常是公司名稱，但結尾一律為 `sc.omtrdc.net`。
   * **CNAME實作**: `sstats.adobe.com` 是適用於https（安全）要求的CNAME第一方追蹤伺服器的範例。`stats.adobe.com` 是CNAME第一方要求http（非安全）頁面的範例。

1. 複製欄位的整個內容。

1. 在您的活動&#x200B;**[!UICONTROL 「目標與設定」]****[!UICONTROL 畫面的]**「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >選取[!UICONTROL Analytics作為報表來源]，讓您的活動[!UICONTROL 追蹤伺服器]欄位可用。

## 使用瀏覽器的開發人員工具取得Analytics追蹤伺服器

應在傳送活動的頁面上檢視開發人員工具，以確保您選取正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 從您建立活動的頁面，開啟瀏覽器的開發人員工具（在Google Chrome中，按一下右上角的三個垂直的點>更多工具>開發人員工具）。

   ![Chrome開發人員工具](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 按一下&#x200B;**[!UICONTROL Network]**&#x200B;頁簽。

1. 篩選`/ss,`以顯示Analytics請求。

   ![具有/ss搜尋的Chrome開發人員工具](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   追蹤伺服器是要求的主機名稱。

   * **第一方追蹤伺服器**:如果要求的主機名稱符合您所在的網域，則是第一方追蹤伺服器。例如，若您位於`adobe.com`,`adobe.com`為第一方追蹤伺服器。
   * **第三方追蹤伺服器**:協力廠商追蹤伺服器通 `[company].sc.omtrdc.net` 常是公司名稱，但結尾一律為 `sc.omtrdc.net`。
   * **CNAME實作**: `sstats.adobe.com` 是適用於https（安全）要求的CNAME第一方追蹤伺服器的範例。`stats.adobe.com` 是CNAME第一方要求http（非安全）頁面的範例。

1. 複製欄位的整個內容。

1. 在您的活動&#x200B;**[!UICONTROL 「目標與設定」]****[!UICONTROL 畫面的]**「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >選取[!UICONTROL Analytics作為報表來源]，讓您的活動[!UICONTROL 追蹤伺服器]欄位可用。
