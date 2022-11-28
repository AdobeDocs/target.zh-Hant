---
keywords: 環境資料；工作階段資料；地理資料；地理資料；地理資料；裝置資料；行動資料；屬性；設定檔屬性；個人化演算法；機器學習演算法；機器學習演算法
description: 了解哪些資料Adobe [!DNL Target] 收集並用於建置其機器學習演算法。
title: 收集哪些資料以建立機器學習演算法？
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 3274423523c0dfddef202cc161882ea6d25a1dff
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 48%

---

# ![PREMIUM](/help/main/assets/premium.png) 使用的資料 [!DNL Target] 機器學習算法

[!DNL Adobe Target] 自動收集和使用各種資料，以建立其個人化演算法，於 [!UICONTROL Automated Personalization] （美聯社）和 [!UICONTROL 自動鎖定目標] (AT)活動。 當訪客進入AP或AT活動時，資訊的快照會傳遞至一組「訓練記錄」（個人化演算法將學習的訪客資料）。

若要進一步了解 [!DNL Target] 個人化演算法，請參閱 [隨機森林演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## 預設 [!DNL Adobe Target] 屬性類別

下表顯示 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自動鎖定目標] 活動，預設為不設定 [!DNL Target] 或其他 [!DNL Adobe] 解決方案，以及用於指示 [個人化前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). 您可以隨時擴大輸入的資料。若要進一步瞭解如何上傳其他資料，請參閱 [上傳 [!DNL Target] 個人化演算法](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| 資料類別 | 系統前置詞 | 說明 | 顯示名稱(在 [!UICONTROL 前瞻分析] 報告 |
| --- | --- | --- | --- |
| 環境參數 | ENV | 使用者環境的相關資訊，包括作業系統、瀏覽器，以及一天/一天中的時間。 | 瀏覽器 —  [屬性名稱]<br>作業系統 —  [值] |
| Geography | 地理 | 透過IP查閱取得之使用者地理位置的相關資訊。 | 地理 —  [地理屬性] |
| 行動裝置 | MOB | 使用者行動裝置的相關資訊。 | 裝置 —  [裝置屬性]<br>行動 —  [行動屬性] |
| Target報表區段 | SEG | 在 [!DNL Target] 報告。 | 報表區段 — [區段名稱] |
| 工作階段行為 | SES | 使用者行為的相關資訊，例如檢視的頁數。 | 訪客資料 —  [屬性名稱] |

## 自訂Adobe Target屬性類別

下表顯示由 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自動鎖定目標] 活動。 只有在您提供此資料時，才會收集此資料。 特定屬性名稱和範例值對您的系統配置將是特定的。

| 資料類別 | 系統前置詞 | 說明 | 顯示名稱(在 [!UICONTROL 前瞻分析] 報告 |
| --- | --- | --- | --- |
| 頁面參數 | 框 | 在對的呼叫中傳遞的自訂頁面參數（「mbox參數」） [!DNL Target]. | 自訂 — Mbox參數 —  [參數名稱] |
| [!DNL Target] 描述檔 | PRO | 直接上傳至的自訂設定檔屬性 [!DNL Target] 設定檔（透過API或頁面參數）和 [!DNL Target] 設定檔指令碼。 | 自訂 — 訪客資料 —  [屬性名稱] |
| 客戶屬性 | CRS | 已上傳至 [!DNL Target] 透過 [Adobe Experience Cloud客戶屬性服務](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}。 | 自訂 — 訪客資料 —  [屬性名稱] |
| URL 參數 | URL | 目前檢視頁面的URL和任何URL參數。 | 自訂 — URL參數 —  [URL參數] |
| 反向連結 URL | 參考 | 轉介URL和轉介URL的任何URL參數。 | 自訂 —  [轉介URL參數] - [參數值] |
| Adobe Experience Cloud共用對象 | AAM | 共用給的所有對象 [!DNL Target] 其他 [!DNL Adobe Experience Cloud] 解決方案(例如 [!DNL Adobe Audience Manager] 和 [!DNL Adobe Analytics]，透過 [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank})。 | 自訂 — Experience Cloud對象 —  [對象名稱] |
| Adobe Experience Platform Real-time CDP觀眾 | UPS | 與共用的AEP Real-time CDP Audiences [!DNL Target] 透過目的地。 |  |
| Adobe Experience Platform Real-time CDP屬性 | AEP | 與共用的AEP Real-time CDP屬性 [!DNL Target] 透過目的地。 此功能目前仍在測試中。 |  |

## 阻止功能 [!DNL Target] 機器學習算法

功能可從 [!DNL Target] 機器學習演算法，防止其用於任何 [!UICONTROL 自動鎖定目標] 或 [!UICONTROL Automated Personalization] 模型或活動。

如需詳細資訊，請參閱 [模型API（封鎖清單）概觀](https://developer-stage.adobe.com/target/before-administer/models-api/){target=_blank}，位於 *Adobe Target開發人員指南*.

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
| 行動 - OS – OSX (Android、Windows 等) | 指定使用者是否已使用 OSX (或 Android、Windows 等)裝置來存取活動。 | 0 為 False，1 為 True | MOB_targeting.mobile.os[作業系統]<br>例如， MOB_targeting.mobile.osOSx、MOB_targeting.mobile.osWindows、MOB_targeting.mobile.osAndroid、MOB_targeting.mobile.osAndroid、MOB_targeting.mobile.osLinux |
| 行動 - 畫面高度 (px) | 訪客用來存取活動的行動裝置畫面高度 (以像素為單位)。 | 1、2、3 等 | MOB_targeting.mobile.displayHeight |
| 行動 - 畫面寬度 (px) | 訪客用來存取活動的行動裝置畫面寬度 (以像素為單位)。 | 1、2、3 等 | MOB_targeting.mobile.displayWidth |

## 環境資料 {#env}

|屬性名稱|屬性說明|示例值|系統名稱| | — | — | — | — | |瀏覽器 — 一週中的某天|訪客存取活動時的每週某天。|0到6。<br>（0是星期日）|ENV_DayOfWeek| |瀏覽器 — 一天中的第幾個小時|訪客存取活動時的一天中的第幾個小時。|0 - 23<br>（0是午夜）|ENV_UserHour| |瀏覽器 — 一週中的某小時|訪客存取活動時的一週中的某小時。|0 - 168<br>（星期日午夜為0）|ENV_WeekHour| |瀏覽器 — 語言設定|訪客瀏覽器中指定用來存取活動的語言。|英語<br>德文|ENV_語言| |瀏覽器 — 每日時間|訪客存取活動時的瀏覽器每日時間。|0、6、12、18<br>(0是晚上，6是早上，<br>12是下午，18是晚上)|ENV_LocalTimePeriod| |瀏覽器 — 時區|存取活動時的訪客時區。|太平洋時間<br>東部時間<br>GMT|ENV_BrowserTimezoneOffsetMinutes| |瀏覽器 — 類型|訪客在存取活動時使用的瀏覽器類型。|Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>其他|ENV_Browser| |瀏覽器 — 工作日/週末|訪客存取活動時的工作狀態（週末、工作時間或工作日自由時間）。|星期六和星期日是週末<br>09:00至18:00是工作時間<br>1800之後的星期一至星期五至0900是平日自由時間|ENV_UserHourType| |瀏覽器 — 視窗高度(px)|訪客用來存取活動的瀏覽器視窗高度（像素）。|1、2、3等|ENV_BrowserHeight| |瀏覽器 — 視窗寬度(px)|訪客用來存取活動的瀏覽器視窗寬度（像素）。|1、2、3等|ENV_BrowserWidth| |裝置 — 螢幕高度(px)|訪客用來存取活動的裝置螢幕高度。|1、2、3等|ENV_ScreenHeight| |裝置 — 螢幕寬度(px)|訪客用來存取活動的裝置螢幕寬度。|1、2、3等|ENV_ScreenWidth| |作業系統|訪客裝置上用來存取活動的作業系統。|Mac OS<br>Windows<br>Linux<br>搜尋機器人<br>未知的OS|ENV_OperatingSystem| |作業系統 — 版本|訪客用來存取活動的作業系統版本。|Windows 10<br>Mac OS 10|ENV_OperatingSystemVersion| |流量來源 — 反向連結著陸頁面URL|訪客在存取您的網站時看到的第一個頁面。|`https://www.adobe.com/ecloud.html`|ENV_Referrer|

## 地理位置資料 {#geo}

| 屬性名稱 | 屬性說明 | 值範例 | 系統名稱 |
| --- | --- | --- | --- |
| 地理 - 城市 | 訪客存取活動時所在的城市。 | San Francisco | 地理_城市 |
| 地理 - 國家/地區 | 訪客存取活動時所在的國家/地區。 | 德國 | 地域_國家 |
| 地理 - DMA | 訪客存取活動時所在的指定市場區域 (DMA)。 | Charlottesville | Geo_DMA |
| 地理 - 緯度 | 訪客存取活動時所在的緯度。 | 47.269<br>四捨五入至小數點後的 3 位數 (大約 100 公尺的準確度) | GEO_Latitude |
| 地理 - 經度 | 訪客存取活動時所在的經度。 | -122.269<br>四捨五入至小數點後的 3 位數 (大約 100 公尺的準確度) | GEO_Longitude |
| 地理 - 州/區域 | 訪客存取活動時所在的州或區域。 | 猶他州<br>新南威爾斯州 | GEO_State<br>GEO_Region |
| 地理 - 郵遞區號 | 訪客存取活動時所在位置的郵遞區號。 | 84004 | GEO_ZipCode |
| 行動 - 電信業者 | 訪客存取活動時使用的行動電信業者。 | Vodafone<br>T-Mobile | GEO_mobileCarrier |
| 網路 - 連線速度 | 訪客存取活動時的裝置網路連線速度。 | 寬頻<br>纜線<br>DSL<br>行動<br>無線<br>衛星 | GEO_ConnectionSpeed |
| 網路 - 網域名稱 | 訪客存取活動時所使用的網路網域名稱。 | `nnt.net` | GEO_DomainName |
| 網路 - ISP | 訪客存取活動時所使用的網路。 | nnt communications corporation | GEO_IspName |

## 工作階段資料 {#session}

| 屬性名稱 | 屬性說明 | 值範例 | 系統名稱 |
| --- | --- | --- | --- |
| 訪客設定檔 - 活動期限訂購值 | 指定某個特定活動的所有造訪/工作階段的所有訂購值的總和。 | 雙倍 | SES_CUMULATIVE_ORDER_VALUE |
| 訪客設定檔 - 活動期限網站逗留時間 | 指定訪客在網站上的總計停留時間，這不包括目前的工作階段，且會在工作階段過期時更新。 | 雙倍，毫秒 | SES_TOTAL_TIME |
| 訪客設定檔 - 活動期間每個造訪的平均頁面檢視數 | 指定每個工作階段的平均頁面檢視數，這不包括目前的工作階段。 | 雙倍 | SES_REQUESTS_PER_SESSION |
| 訪客設定檔 - 每次瀏覽的平均時間 | 指定每個造訪/工作階段停留的平均時間。這不包括目前的工作階段。 | 雙倍，毫秒 | SES_TIME_PER_SESSION |
| 訪客設定檔 - 第一次造訪 | 指定使用者互動的首次造訪時間 [!DNL Target]. | 雙倍，毫秒 | SES_PROFILE_CREATION_TIME |
| 訪客設定檔 - 自上次造訪以來的時數 | 指定自上次造訪此特定活動以來的時數。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_HOURS_SINCE_LAST_VISIT |
| 訪客設定檔 - 位置/內容的曝光次數 | 指定特定活動中特定位置/內容組合的曝光次數。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| 訪客資料 — 最後 [!DNL Target] 互動 | 指定上次與 [!DNL Target]. 互動會發生在每個 [!DNL Target] 請求，因為目前的 [!DNL Target] 會更新每個請求的設定檔。 | 雙倍，毫秒 | SES_PROFILE_UPDATE_TIME |
| 訪客設定檔 - 活動前檢視的頁面 | 指定在訪客進入活動之前的頁面檢視總數 (曝光次數)，包括目前的造訪/工作階段。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_TOTAL_PAGE_VIEWS |
| 訪客設定檔 - 目前造訪中的頁面檢視數 | 指定在訪客進入活動之前，目前造訪/工作階段中的頁面檢視數。更準確地說，也就是曝光次數。這些曝光並不是真正的頁面檢視數，而是要求已到達 Target 的次數。針對逾時或是使用者未收到或檢視內容的任何其他原因，Target 無法將其加以區分。 | 雙倍 (僅限正整數) | SES_SESSION_POSITION |
| 訪客設定檔 - 目前造訪開始時間 | 指定 Target 的目前造訪/工作階段開始的時間。可以初始化 Target 的造訪，而不需要進入活動。只需呼叫任何 [!DNL Target] 請求。 訪客在進入活動並拍攝快照之前可能需要一些時間。 | 雙倍，毫秒 | SES_SESSION_START |
| 訪客設定檔 - 開始最近一次瀏覽 | 指定上次造訪/工作階段的時間，與 [!DNL Target] 已開始。 此屬性會在工作階段過期時更新。<br>如果這是訪客的第一個工作階段，則會產生 `LAST_SESSION_START = 0.` | 雙倍，毫秒 | SES_LAST_SESSION_START |
| 訪客設定檔 - 初次進入活動時自最近一次造訪以來的時間 | 指定上一個工作階段與使用者進入活動且執行快照之間的時間的持續時間。 | 雙倍，毫秒 | SES_RECENCY |
| 訪客設定檔 - 進入活動之前的造訪時間 | 指定上次互動與 [!DNL Target] 和目前造訪開始時。 此屬性可視為在使用者進入活動且執行快照之前的造訪/工作階段持續時間。<br>[!DNL Target]當工作階段開始且同一個 呼叫已觸發上次更新時間時 ，則會出現負值。負值應視為 0 (零)。 | 雙倍，毫秒 | SES_SESSION_TIME |
| 訪客設定檔 - 瀏覽總數 | 指定指定造訪/工作階段總數。不包含目前的造訪/工作階段。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_TOTAL_SESSIONS |
| 訪客設定檔 - 活動的總造訪次數 | 指定特定活動的造訪次數。如果之前沒有任何造訪，則會傳回 0 (零)。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_PREVIOUS_VISIT_COUNT |
| 訪客設定檔 - 包含轉換之活動的總造訪次數 | 指定造訪期間至少有一個轉換時，特定活動的造訪/工作階段數目。 | 雙倍 | SES_CUMULATIVE_SECTURES |
| 訪客設定檔 - 不包含轉換之活動的造訪次數 | 不包含轉換之特定活動的造訪/工作階段數目。此值在轉換後會重設為零，或者若從未發生轉換，則會出現 -1。 | 雙倍 (僅限正整數) 1、2、3 等 | SES_SUCCESS_RECENCY |
