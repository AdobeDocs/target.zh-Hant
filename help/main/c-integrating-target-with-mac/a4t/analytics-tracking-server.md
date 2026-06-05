---
keywords: analytics追蹤伺服器；A4T；Adobe Experience Cloud Debugger；Adobe Experience Platform Debugger；報表來源；開發人員工具
description: 如果您使用舊版的at.js，瞭解如何為使用Analytics for [!DNL Target] (A4T)的活動指定Analytics追蹤伺服器。
title: 如何使用Analytics追蹤伺服器？
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
TQID: https://experienceleague.adobe.com/mJM5kZPQfnWodzwQ3qDKxu1e1Oq2Y53fA2LpSB4SVSc
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 708
ht-degree: 17%

---

# 使用[!DNL Analytics]追蹤伺服器

如果您使用較舊版本的at.js，您必須針對[!DNL Adobe Target] (A4T)使用[!DNL Adobe Analytics]的活動指定[!DNL Analytics]追蹤伺服器。

>[!NOTE]
>
>如果您使用 at.js 0.9.1 版 (或更新版本)，您在活動建立期間就不需要指定追蹤伺服器。 at.js 程式庫會自動傳送追蹤伺服器值給 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。
>
>[!DNL Target]團隊同時支援at.js 1.*x*&#x200B;和at.js 2.*x*。 升級至任一主要版本的at.js最新更新，以確保您執行的是支援的版本。 如需詳細資訊，請參閱[&#x200B; at.js 版本詳細資訊](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}。

為確保來自[!DNL Target]的資料進入[!DNL Analytics]中的正確位置，A4T要求在所有從[!DNL Target]呼叫Modstats時傳送[!DNL Analytics]追蹤伺服器。 針對使用多個追蹤伺服器的實作，請使用[!DNL Adobe Experience Platform Debugger]或瀏覽器的開發人員工具來決定活動的正確追蹤伺服器。

## 使用[!DNL Adobe Experience Platform Debugger]取得[!DNL Analytics]追蹤伺服器

您應在傳送活動的頁面上檢視除錯工具，以確保選取正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。 請連絡客戶服務來指定或修改預設值。

1. 從您正在建立活動的頁面，開啟[!DNL Adobe Experience Platform Debugger]。

   如果您尚未安裝除錯程式，請參閱[Adobe Experience Platform Debugger概觀](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html?lang=zh-Hant)。

1. 按一下左側導覽功能表中的&#x200B;**[!UICONTROL Analytics]**。

   ![Screen_DebuggerTrackServ影像](assets/Screen_DebuggerTrackServ.png)

   在Debugger的[!UICONTROL 主機名稱]區段中找到[!DNL Analytics]追蹤伺服器。

   * **第一方追蹤伺服器**：如果要求的主機名稱符合您所在的網域，則為第一方追蹤伺服器。 例如，如果您在`adobe.com`，則`adobe.com`是第一方追蹤伺服器。
   * **協力廠商追蹤伺服器**：協力廠商追蹤伺服器通常是`[company].sc.omtrdc.net`，其中公司是您公司的名稱，但結尾一律為`sc.omtrdc.net`。
   * **CNAME實作**： `sstats.adobe.com`是https （安全）要求的CNAME第一方追蹤伺服器的範例。 `stats.adobe.com`是http （非安全）頁面的CNAME第一方要求範例。

1. 複製欄位的整個內容。

1. 在活動的&#x200B;**[!UICONTROL 目標與設定]**&#x200B;畫面的&#x200B;**[!UICONTROL 報告設定]**&#x200B;區段中，將追蹤伺服器資訊貼到&#x200B;**[!UICONTROL 追蹤伺服器]**&#x200B;欄位中。

   >[!NOTE]
   >
   >選取[!UICONTROL Analytics作為您的活動的報表Source]，以使[!UICONTROL 追蹤伺服器]欄位可用。

## 使用瀏覽器的開發人員工具取得[!DNL Analytics]追蹤伺服器

開發人員工具應在傳送活動的頁面上檢視，以確保您選取正確的追蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。 請連絡客戶服務來指定或修改預設值。

1. 從建立活動的頁面上，開啟瀏覽器的開發人員工具（在Google Chrome中，按一下右上角的三個垂直的點> 「更多工具>開發人員工具」）。

   ![Chrome開發人員工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 按一下「**[!UICONTROL 網路]**」標籤。

1. 篩選`/ss,`以顯示[!DNL Analytics]個請求。

   ![使用/ss search的Chrome開發人員工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   追蹤伺服器是要求的主機名稱。

   * **第一方追蹤伺服器**：如果要求的主機名稱符合您所在的網域，則為第一方追蹤伺服器。 例如，如果您在`adobe.com`，則`adobe.com`是第一方追蹤伺服器。
   * **協力廠商追蹤伺服器**：協力廠商追蹤伺服器通常是`[company].sc.omtrdc.net`，其中公司是您公司的名稱，但結尾一律為`sc.omtrdc.net`。
   * **CNAME實作**： `sstats.adobe.com`是https （安全）要求的CNAME第一方追蹤伺服器的範例。 `stats.adobe.com`是http （非安全）頁面的CNAME第一方要求範例。

1. 複製欄位的整個內容。

1. 在活動的&#x200B;**[!UICONTROL 目標與設定]**&#x200B;畫面的&#x200B;**[!UICONTROL 報告設定]**&#x200B;區段中，將追蹤伺服器資訊貼到&#x200B;**[!UICONTROL 追蹤伺服器]**&#x200B;欄位中。

   >[!NOTE]
   >
   >選取[!UICONTROL Analytics作為您的活動的報表Source]，以使[!UICONTROL 追蹤伺服器]欄位可用。
