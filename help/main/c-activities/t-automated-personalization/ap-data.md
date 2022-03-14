---
keywords: 環境資料；會話資料；地理資料；地理資料；設備資料；移動資料；屬性；配置檔案屬性；個性化算法；機器學習算法；機器學習算法
description: 瞭解哪些資料Adobe [!DNL Target] 收集並用於構建其機器學習算法。
title: 收集哪些資料來構建機器學習算法？
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2062'
ht-degree: 48%

---

# ![高級](/help/main/assets/premium.png) 資料使用者 [!DNL Target] 機器學習算法

[!DNL Adobe Target] 自動收集並使用各種資料構建其個性化算法 [!UICONTROL Automated Personalization] （美聯社） [!UICONTROL 自動目標] (AT)活動。 當訪問者進入AP或AT活動時，資訊的快照會傳遞給一組「培訓記錄」（個性化算法將學習的訪問者資料）。

瞭解有關 [!DNL Target] 個性化算法，請參閱 [隨機森林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。

## 預設 [!DNL Adobe Target] 屬性類別

下表顯示了由 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自動目標] 預設情況下的活動，不配置任何 [!DNL Target] 或 [!DNL Adobe] 解決方案，以及用於在 [個性化透視報告](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)。 您可以隨時擴大輸入的資料。若要進一步瞭解如何上傳其他資料，請參閱 [正在上載 [!DNL Target] 個性化算法](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

| 資料類別 | 系統前置詞 | 說明 | 顯示名稱 [!UICONTROL 洞察力] 報告 |
| --- | --- | --- | --- |
| 環境參數 | 環境 | 有關用戶環境的資訊，包括作業系統、瀏覽器和星期中的某天/某天。 | 瀏覽器 —  [屬性名稱]<br>作業系統 —  [值] |
| Geography | 地理 | 通過IP查找獲得的有關用戶地理位置的資訊。 | 地理 —  [geo屬性] |
| 移動裝置 | MOB | 有關用戶移動設備的資訊。 | 設備 —  [設備屬性]<br>移動 —  [移動屬性] |
| 目標報告段 | 塞格 | 在中配置的報告段 [!DNL Target] 報告。 | 報告分部 — [段名稱] |
| 會話行為 | SES | 有關用戶行為的資訊，如查看的頁數。 | 訪問者簡介 —  [屬性名稱] |

## 自定義Adobe Target屬性類別

下表顯示由 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自動目標] 活動。 只有提供此資料時，才會收集此資料。 特定的屬性名稱和示例值將特定於您的系統配置。

| 資料類別 | 系統前置詞 | 說明 | 顯示名稱 [!UICONTROL 洞察力] 報告 |
| --- | --- | --- | --- |
| 頁面參數 | 框 | 在調用中傳遞的自定義頁面參數（「mbox參數」） [!DNL Target]。 | 自定義 — Mbox參數 —  [參數名稱] |
| [!DNL Target] 描述檔 | 專業 | 自定義配置檔案屬性直接上載到 [!DNL Target] 通過API或頁面參數和 [!DNL Target] 配置檔案指令碼。 | 自定義 — 訪問者配置檔案 —  [屬性名稱] |
| 客戶屬性 | CRS | 上載到的客戶屬性 [!DNL Target] 通過 [Adobe Experience Cloud客戶屬性服務](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}。 | 自定義 — 訪問者配置檔案 —  [屬性名稱] |
| URL 參數 | URL | 當前查看頁面的URL和任何URL參數。 | 自定義 — URL參數 —  [URL參數] |
| 反向連結 URL | 參考 | 引用URL和引用URL的任何URL參數。 | 自定義 —  [引用URL參數] - [參數值] |
| Adobe Experience Cloud共用觀眾 | AAM | 與共用的所有受眾 [!DNL Target] 其他 [!DNL Adobe Experience Cloud] 解決方案(例如， [!DNL Adobe Audience Manager] 和 [!DNL Adobe Analytics]，通過 [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank})。 | 自定義 — Experience Cloud受眾 —  [受眾名稱] |
| Adobe Experience PlatformRTCDP觀眾 | UPS | AEP RTCDP訪問群體與 [!DNL Target] 通過目標。 |  |

## 阻止來自 [!DNL Target] 機器學習算法

功能可以阻止 [!DNL Target] 機器學習算法，防止它們被用於任何 [!UICONTROL 自動目標] 或 [!UICONTROL Automated Personalization] 模型或活動。

阻止功能類別 [!DNL Target] 機器學習算法，聯繫 [Adobe客戶關懷](/help/main/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) 並使用上面提供的「系統前置詞」指定要阻止的功能類別。

阻止一個或多個特定功能 [!DNL Target] 機器學習算法，聯繫 [Adobe客戶關懷](/help/main/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) 並使用以下提供的系統名稱指定應阻止的特定功能名稱。 下列章節包含有關各種資料類型的詳細資訊，包括屬性名稱、說明和值範例。

## 裝置和行動資料 {#device-mobile}

| 屬性名稱 | 屬性說明 | 值範例 | 系統名稱 |
| --- | --- | --- | --- |
| 行動 - 裝置 - 品牌 | 訪客用來存取活動的行動裝置品牌。 | Apple | MOB_targeting.mobile.vendor |
| 行動 - 裝置 - 電子書閱讀器 | 指定裝置是否為電子書閱讀器。 | 0 為 False，1 為 True | MOB_targeting.mobile.ereader |
| 行動 - 裝置 - 遊戲機 | 指定裝置是否為遊戲機。 | 0 為 False，1 為 True | MOB_targeting.mobile.gamesConsole |
| 行動 - 裝置 - 媒體播放器 | 指定裝置是否為媒體播放器。 | 0 為 False，1 為 True | MOB_targeting.mobile.mediaPlayer |
| 行動 - 裝置 - 行動電話 | 指定裝置是否為行動電話。 | 0 為 False，1 為 True | MOB_targeting.mobile.mobilePhone |
| 行動 - 裝置 - 型號 | 訪客用來存取活動的行動裝置型號。 | iPhone XS | MOB_targeting.mobile.model |
| 裝置 - 電視盒 | 指定裝置是否為電視盒。 | 0 為 False，1 為 True | MOB_targeting.mobile.setTopBox |
| 行動 - 裝置 - 平板電腦 | 指定裝置是否為平板電腦。 | 0 為 False，1 為 True | MOB_targeting.mobile.tablet |
| 行動 - 像素密度 (ppi) | 訪客用來存取活動的行動裝置像素密度。 | 1、2、3 等 | MOB_targeting.mobile.displayPpi |
| 行動 - OS – OSX (Android、Windows 等) | 指定使用者是否已使用 OSX (或 Android、Windows 等)裝置來存取活動。 | 0 為 False，1 為 True | MOB_targeting.mobile.os[作業系統]<br>例如，MOB_targeting.mobile.osOSx、MOB_targeting.mobile.osWindows、MOB_targeting.mobile.osAndroid、MOB_targeting.mobile.osLinux |
| 行動 - 畫面高度 (px) | 訪客用來存取活動的行動裝置畫面高度 (以像素為單位)。 | 1、2、3 等 | MOB_targeting.mobile.displayHeight |
| 行動 - 畫面寬度 (px) | 訪客用來存取活動的行動裝置畫面寬度 (以像素為單位)。 | 1、2、3 等 | MOB_targeting.mobile.displayWidth |

## 環境資料 {#env}

|屬性名稱|屬性說明|示例值|系統名稱| | - | - | - | - | |瀏覽器 — 週日|訪問者訪問活動的週日。|0到6。<br>（0是星期日）|ENV_DayOfWeek| |瀏覽器 — 一天中的小時|訪問者訪問活動的一天中的小時。|0到23<br>（0為午夜）|ENV_UserHour| |瀏覽器 — 周小時|訪問者訪問活動時的周小時。|0到168<br>（星期日午夜為0）|ENV_WeekHour| |Browser — 語言設定|訪問者瀏覽器中指定的用於訪問活動的語言。|英語<br>德語|ENV_語言| |Browser - Time of Day|訪問者訪問活動時瀏覽器的一天時間。|0、6、12、18<br>(0是夜，6是早，<br>12是下午，18是晚上)|ENV_LocalTimePeriod| |瀏覽器 — 時區|訪問活動時訪問者的時區。|太平洋時間<br>東部時間<br>GMT|ENV_BrowserTimezoneOffsetMinutes| |Browser — 類型|訪問活動時訪問者使用的瀏覽器類型。|Chrome<br>火狐<br>Internet Explorer<br>薩法里<br>其他|ENV_Browser| |瀏覽器 — 工作日/週末|訪問者訪問活動時的工作狀態（週末、工作時間或工作日空閒時間）。|星期六和星期日是週末<br>0900至1800是工作時間<br>1800至0900之後的星期一至星期五是工作日空閒時間|ENV_UserHourType| |Browser — 窗口高度(px)|瀏覽器的窗口高度（以像素為單位），訪問者用於訪問活動。|1、2、3等。|ENV_BrowserHeight| |瀏覽器 — 窗口寬度(px)|瀏覽器窗口寬度（以像素為單位），訪問者用於訪問活動。|1、2、3等。|ENV_BrowserWidth| |設備 — 螢幕高度(px)|訪問者用於訪問活動的設備螢幕高度。|1、2、3等。|ENV_ScreenHeight| |設備 — 螢幕寬度(px)|訪問者用於訪問活動的設備螢幕寬度。|1、2、3等。|ENV_ScreenWidth| |作業系統|訪問者設備上用於訪問活動的作業系統。|Mac作業系統<br>窗口<br>Linux<br>搜索Bot<br>未知的OS|ENV_OperatingSystem| |作業系統 — 版本|訪問者用於訪問活動的作業系統版本。|Windows 10<br>MacOS 10|ENV_OperatingSystemVersion| |流量源 — 引用登錄頁URL|訪問您的網站時訪問者看到的第一頁。|`https://www.adobe.com/ecloud.html`|ENV_引用者|

## 地理位置資料 {#geo}

| 屬性名稱 | 屬性說明 | 值範例 | 系統名稱 |
| --- | --- | --- | --- |
| 地理 - 城市 | 訪客存取活動時所在的城市。 | San Francisco | 地理（城市） |
| 地理 - 國家/地區 | 訪客存取活動時所在的國家/地區。 | 德國 | 地區(_C) |
| 地理 - DMA | 訪客存取活動時所在的指定市場區域 (DMA)。 | Charlottesville | 地理位置(_DMA) |
| 地理 - 緯度 | 訪客存取活動時所在的緯度。 | 47.269<br>四捨五入至小數點後的 3 位數 (大約 100 公尺的準確度) | GEO_Latitude |
| 地理 - 經度 | 訪客存取活動時所在的經度。 | -122.269<br>四捨五入至小數點後的 3 位數 (大約 100 公尺的準確度) | GEO_經度 |
| 地理 - 州/區域 | 訪客存取活動時所在的州或區域。 | 猶他州<br>新南威爾斯州 | GEO狀態<br>GEO區域 |
| 地理 - 郵遞區號 | 訪客存取活動時所在位置的郵遞區號。 | 84004 | GEO_ZipCode |
| 行動 - 電信業者 | 訪客存取活動時使用的行動電信業者。 | Vodafone<br>T-Mobile | GEO_mobileCarrier |
| 網路 - 連線速度 | 訪客存取活動時的裝置網路連線速度。 | 寬頻<br>纜線<br>DSL<br>行動<br>無線<br>衛星 | GEO_ConnectionSpeed |
| 網路 - 網域名稱 | 訪客存取活動時所使用的網路網域名稱。 | `nnt.net` | GEO_域名 |
| 網路 - ISP | 訪客存取活動時所使用的網路。 | nnt communications corporation | GEO_IspName |

## 工作階段資料 {#session}

| 屬性名稱 | 屬性說明 | 值範例 | 系統名稱 |
| --- | --- | --- | --- |
| 訪客設定檔 - 活動期限訂購值 | 指定某個特定活動的所有造訪/工作階段的所有訂購值的總和。 | 雙倍 | SES_CUMULATIVE_ORDER_VALUE |
| 訪客設定檔 - 活動期限網站逗留時間 | 指定訪客在網站上的總計停留時間，這不包括目前的工作階段，且會在工作階段過期時更新。 | 雙倍，毫秒 | SES_TOTAL_TIME |
| 訪客設定檔 - 活動期間每個造訪的平均頁面檢視數 | 指定每個工作階段的平均頁面檢視數，這不包括目前的工作階段。 | 雙倍 | SES_REQUESTS_PER_SESSION |
| 訪客設定檔 - 每次瀏覽的平均時間 | 指定每個造訪/工作階段停留的平均時間。這不包括目前的工作階段。 | 雙倍，毫秒 | SES_TIME_PER_SESSION |
| 訪客設定檔 - 第一次造訪 | 指定用戶與之交互的首次訪問的時間 [!DNL Target]。 | 雙倍，毫秒 | SES_PROFILE_CREATION_TIME |
| 訪客設定檔 - 自上次造訪以來的時數 | 指定自上次造訪此特定活動以來的時數。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_HOURS_SCINE_LAST_VISIT |
| 訪客設定檔 - 位置/內容的曝光次數 | 指定特定活動中特定位置/內容組合的曝光次數。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_CUMULATIVE_ACTION_[位置ID]_[內容ID] |
| 訪問者配置檔案 — 最後 [!DNL Target] 交互 | 指定上次與 [!DNL Target]。 每個 [!DNL Target] 請求，因為 [!DNL Target] 更新每個請求的配置檔案。 | 雙倍，毫秒 | SES_PROFILE_UPDATE_TIME |
| 訪客設定檔 - 活動前檢視的頁面 | 指定在訪客進入活動之前的頁面檢視總數 (曝光次數)，包括目前的造訪/工作階段。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_TOTAL_PAGE_VIEWS |
| 訪客設定檔 - 目前造訪中的頁面檢視數 | 指定在訪客進入活動之前，目前造訪/工作階段中的頁面檢視數。更準確地說，也就是曝光次數。這些曝光並不是真正的頁面檢視數，而是要求已到達 Target 的次數。針對逾時或是使用者未收到或檢視內容的任何其他原因，Target 無法將其加以區分。 | 雙倍 (僅限正整數) | SES_SESSION_POSITION |
| 訪客設定檔 - 目前造訪開始時間 | 指定 Target 的目前造訪/工作階段開始的時間。可以初始化 Target 的造訪，而不需要進入活動。只需呼叫任何 [!DNL Target] 請求。 訪客在進入活動並拍攝快照之前可能需要一些時間。 | 雙倍，毫秒 | SES_SESSION_START |
| 訪客設定檔 - 開始最近一次瀏覽 | 指定上次訪問/會話的時間 [!DNL Target] 。 此屬性會在工作階段過期時更新。<br>如果這是訪客的第一個工作階段，則會產生 `LAST_SESSION_START = 0.` | 雙倍，毫秒 | SES_LAST_SESSION_START |
| 訪客設定檔 - 初次進入活動時自最近一次造訪以來的時間 | 指定上一個工作階段與使用者進入活動且執行快照之間的時間的持續時間。 | 雙倍，毫秒 | SES_RECENCY |
| 訪客設定檔 - 進入活動之前的造訪時間 | 指定上次與 [!DNL Target] 以及這次訪問的開始時間。 此屬性可視為在使用者進入活動且執行快照之前的造訪/工作階段持續時間。<br>[!DNL Target]當工作階段開始且同一個 呼叫已觸發上次更新時間時 ，則會出現負值。負值應視為 0 (零)。 | 雙倍，毫秒 | SES_SESSION_TIME |
| 訪客設定檔 - 瀏覽總數 | 指定指定造訪/工作階段總數。不包含目前的造訪/工作階段。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_TOTAL_SESSIONS |
| 訪客設定檔 - 活動的總造訪次數 | 指定特定活動的造訪次數。如果之前沒有任何造訪，則會傳回 0 (零)。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_PREVIOUS_VISIT_COUNT |
| 訪客設定檔 - 包含轉換之活動的總造訪次數 | 指定造訪期間至少有一個轉換時，特定活動的造訪/工作階段數目。 | 雙倍 | SES_CEMULATIVE_SUCCESS |
| 訪客設定檔 - 不包含轉換之活動的造訪次數 | 不包含轉換之特定活動的造訪/工作階段數目。此值在轉換後會重設為零，或者若從未發生轉換，則會出現 -1。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_SUCCESS_RECENCY |
