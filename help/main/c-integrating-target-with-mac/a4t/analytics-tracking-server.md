---
keywords: analytics追蹤伺服器；A4T；Adobe Experience Cloud debugger；Adobe Experience Platform debugger；報表來源；開發人員工具
description: 瞭解如何為使用Analytics的活動指定Analytics追蹤伺服器 [!DNL Target] (A4T)。
title: 如何使用Analytics追蹤伺服器？
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 21%

---

# 使用 [!DNL Analytics] 追蹤伺服器

如果您使用舊版at.js，您必須指定 [!DNL Analytics] 使用的活動的追蹤伺服器 [!DNL Adobe Analytics] 的 [!DNL Adobe Target] (A4T)。

>[!NOTE]
>
>如果您使用 at.js 0.9.1 版 (或更新版本)，您在活動建立期間就不需要指定追蹤伺服器。 at.js 程式庫會自動傳送追蹤伺服器值給 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL 目標與設定]頁面上的[!UICONTROL 追蹤伺服器]欄位保留空白。
>
>此 [!DNL Target] 團隊同時支援at.js 1.*x* 與 at.js 2.*x* 之間的對應。升級至任一主要版本at.js的最新更新，以確保您執行的是支援的版本。 如需詳細資訊，請參閱 [at.js版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

若要確保資料來自 [!DNL Target] 前往中的正確位置 [!DNL Analytics]，A4T需要 [!DNL Analytics] 要在所有對Modstats的呼叫中傳送的追蹤伺服器 [!DNL Target]. 針對使用多個追蹤伺服器的實作，請使用 [!DNL Adobe Experience Platform Debugger] 或瀏覽器的開發人員工具來決定活動的正確追蹤伺服器。

## 取得 [!DNL Analytics] 追蹤伺服器使用 [!DNL Adobe Experience Platform Debugger]

您應在傳送活動的頁面上檢視Debugger，以確保選取正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 從建立活動的頁面，開啟 [!DNL Adobe Experience Platform Debugger].

   如果您尚未安裝除錯程式，請參閱 [Adobe Experience Platform Debugger概觀](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html).

1. 按一下 **[!UICONTROL 分析]** ，位於左側導覽功能表中。

   ![Screen_DebuggerTrackServ圖片](assets/Screen_DebuggerTrackServ.png)

   此 [!DNL Analytics] 追蹤伺服器位於 [!UICONTROL 主機名稱] 區段。

   * **第一方追蹤伺服器**：如果請求的主機名稱與您所在的網域相符，則為第一方追蹤伺服器。 例如，如果您在 `adobe.com`， `adobe.com` 是第一方追蹤伺服器。
   * **協力廠商追蹤伺服器**：第三方追蹤伺服器通常會 `[company].sc.omtrdc.net` 其中公司是公司的名稱，但結尾一律為 `sc.omtrdc.net`.
   * **CNAME實施**： `sstats.adobe.com` 是https （安全）請求的CNAME第一方追蹤伺服器範例。 `stats.adobe.com` 是http （非安全）頁面的CNAME第一方要求範例。

1. 複製欄位的整個內容。

1. 在您的活動&#x200B;**[!UICONTROL 「目標與設定」]****[!UICONTROL 畫面的]**「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >選取 [!UICONTROL Analytics作為報表來源] （針對您針對的活動） [!UICONTROL 追蹤伺服器] 欄位可供使用。

## 取得 [!DNL Analytics] 使用瀏覽器的開發人員工具追蹤伺服器

您應在傳送活動的頁面上檢視開發人員工具，以確保您選取正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 從建立活動的頁面上，開啟瀏覽器的開發人員工具(在Google Chrome中，按一下右上角的三個垂直點> 「更多工具>開發人員工具」)。

   ![Chrome開發人員工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 按一下 **[!UICONTROL 網路]** 標籤。

1. 篩選對象 `/ss,` 以顯示 [!DNL Analytics] 要求。

   ![具有/ss搜尋的Chrome開發人員工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   追蹤伺服器是請求的主機名稱。

   * **第一方追蹤伺服器**：如果請求的主機名稱與您所在的網域相符，則為第一方追蹤伺服器。 例如，如果您在 `adobe.com`， `adobe.com` 是第一方追蹤伺服器。
   * **協力廠商追蹤伺服器**：第三方追蹤伺服器通常會 `[company].sc.omtrdc.net` 其中公司是公司的名稱，但結尾一律為 `sc.omtrdc.net`.
   * **CNAME實施**： `sstats.adobe.com` 是https （安全）請求的CNAME第一方追蹤伺服器範例。 `stats.adobe.com` 是http （非安全）頁面的CNAME第一方要求範例。

1. 複製欄位的整個內容。

1. 在您的活動&#x200B;**[!UICONTROL 「目標與設定」]****[!UICONTROL 畫面的]**「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >選取 [!UICONTROL Analytics作為報表來源] （針對您針對的活動） [!UICONTROL 追蹤伺服器] 欄位可供使用。
