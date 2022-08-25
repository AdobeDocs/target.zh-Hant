---
keywords: 分析跟蹤伺服器；A4T;Adobe Experience Cloud調試器；Adobe Experience Platform調試器；報告源；開發人員工具
description: '瞭解如何為使用Analytics進行分析的活動指定分析跟蹤伺服器 [!DNL Target] (A4T)，如果您使用的是at.js的舊版本。 '
title: 如何使用分析跟蹤伺服器？
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 34ff1a79c8e0988df410a45b8b9b20dda057d099
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 22%

---

# 使用 [!DNL Analytics] 跟蹤伺服器

如果使用的是at.js的較舊版本，則必須指定 [!DNL Analytics] 跟蹤伺服器，用於活動 [!DNL Adobe Analytics] 為 [!DNL Adobe Target] (A4T)。

>[!NOTE]
>
>如果您使用 at.js 0.9.1 版 (或更新版本)，您在活動建立期間就不需要指定追蹤伺服器。 at.js 程式庫會自動傳送追蹤伺服器值給 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL 目標與設定]頁面上的[!UICONTROL 追蹤伺服器]欄位保留空白。
>
>的 [!DNL Target] 團隊支援at.js 1。*x* 與 at.js 2.*x* 之間的對應。升級到at.js的任一主版本的最新更新，以確保您正在運行受支援的版本。 有關詳細資訊，請參見 [at.js版本詳細資訊](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}。

確保資料來自 [!DNL Target] 轉到中的正確位置 [!DNL Analytics], A4T需要 [!DNL Analytics] 跟蹤伺服器，以從所有呼叫發送到Modstats [!DNL Target]。 對於使用多個跟蹤伺服器的實現，使用 [!DNL Adobe Experience Platform Debugger] 或瀏覽器的「開發人員工具」，以確定活動的正確跟蹤伺服器。

## 獲取 [!DNL Analytics] 跟蹤伺服器使用 [!DNL Adobe Experience Platform Debugger]

應在交付活動的頁面上查看調試器，以確保選擇正確的跟蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 在建立活動的頁面中，開啟 [!DNL Adobe Experience Platform Debugger]。

   如果尚未安裝調試器，請參見 [Adobe Experience Platform調試器概述](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html)。

1. 按一下 **[!UICONTROL 分析]** 的子菜單。

   ![](assets/Screen_DebuggerTrackServ.png)

   的 [!DNL Analytics] 在 [!UICONTROL 主機名] 的子菜單。

   * **第一方跟蹤伺服器**:如果請求的主機名與您所在的域匹配，則它是第一方跟蹤伺服器。 例如，如果 `adobe.com`。 `adobe.com` 是第一方跟蹤伺服器。
   * **第三方跟蹤伺服器**:第三方跟蹤伺服器通常 `[company].sc.omtrdc.net` 公司是您公司的名稱，但總是以 `sc.omtrdc.net`。
   * **CNAME實現**: `sstats.adobe.com` 是CNAME第一方跟蹤伺服器用於https（安全）請求的示例。 `stats.adobe.com` 是http（非安全）頁的CNAME第一方請求的示例。

1. 複製欄位的整個內容。

1. 在您的活動&#x200B;**[!UICONTROL 「目標與設定」]****[!UICONTROL 畫面的]**「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >選擇 [!UICONTROL 分析作為報告源] 為您的活動 [!UICONTROL 跟蹤伺服器] 的子菜單。

## 獲取 [!DNL Analytics] 使用瀏覽器的開發人員工具跟蹤伺服器

應在交付活動的頁面上查看開發人員工具，以確保您選擇正確的跟蹤伺服器。 您也可以為每個帳戶指定預設的追蹤伺服器。請連絡客戶服務來指定或修改預設值。

1. 在建立活動的頁面上，開啟瀏覽器的開發人員工具(在GoogleChrome中，按一下右上角的三個垂直橢圓>更多工具>開發人員工具)。

   ![鉻顯影工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 按一下 **[!UICONTROL 網路]** 頁籤。

1. 篩選 `/ss,` 顯示 [!DNL Analytics] 請求。

   ![使用/ss搜索的Chrome開發工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   跟蹤伺服器是請求的主機名。

   * **第一方跟蹤伺服器**:如果請求的主機名與您所在的域匹配，則它是第一方跟蹤伺服器。 例如，如果 `adobe.com`。 `adobe.com` 是第一方跟蹤伺服器。
   * **第三方跟蹤伺服器**:第三方跟蹤伺服器通常 `[company].sc.omtrdc.net` 公司是您公司的名稱，但總是以 `sc.omtrdc.net`。
   * **CNAME實現**: `sstats.adobe.com` 是CNAME第一方跟蹤伺服器用於https（安全）請求的示例。 `stats.adobe.com` 是http（非安全）頁的CNAME第一方請求的示例。

1. 複製欄位的整個內容。

1. 在您的活動&#x200B;**[!UICONTROL 「目標與設定」]****[!UICONTROL 畫面的]**「報表設定」**[!UICONTROL 區段中，於「追蹤伺服器」]**&#x200B;欄位中貼上追蹤伺服器資訊。

   >[!NOTE]
   >
   >選擇 [!UICONTROL 分析作為報告源] 為您的活動 [!UICONTROL 跟蹤伺服器] 的子菜單。
