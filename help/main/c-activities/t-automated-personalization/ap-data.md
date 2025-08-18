---
keywords: 環境資料；工作階段資料；地理資料；地理位置資料；裝置資料；行動資料；屬性；設定檔屬性；個人化演演算法；機器學習演演算法；機器學習演演算法
description: 瞭解 [!DNL Adobe Target] 收集和使用哪些資料來建置其機器學習演演算法。
title: 系統會收集哪些資料來建置機器學習演演算法？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: fe6a7addd3854c430798fc339741c9ae6a4efc7d
workflow-type: tm+mt
source-wordcount: '1958'
ht-degree: 51%

---

# [!DNL Target]個機器學習演演算法使用的資料

[!DNL Adobe Target]會自動收集並使用各種資料，在[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target] (AT)活動中建置其個人化演演算法。 當訪客進入[!UICONTROL Automated Personalization]或[!UICONTROL Auto-Target]活動時，資訊的快照會傳遞至一組「訓練記錄」（個人化演演算法學習的訪客資料）。

若要深入瞭解[!DNL Target]個人化演演算法，請參閱[隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。

## 預設[!DNL Target]屬性類別

下表顯示[!UICONTROL Automated Personalization]與[!UICONTROL Auto-Target]活動依預設收集的資料，而不含任何[!DNL Target]或其他[!DNL Adobe]解決方案的組態。 此表格也包含在[Personalization前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)中用於指示這些屬性的命名慣例。 您可以隨時擴大輸入的資料。若要進一步瞭解如何上傳其他資料，請參閱[上傳 [!DNL Target] 個人化演演算法的資料](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

| 資料類別 | 系統前置詞 | 說明 | 在[!UICONTROL Insights]個報告中顯示名稱 |
| --- | --- | --- | --- |
| 環境引數 | 環境 | 使用者環境的相關資訊，包括作業系統、瀏覽器、一天中的時間/星期幾。 | 瀏覽器 — [屬性名稱]<br>作業系統 — [值] |
| Geography | 地理 | 透過IP查詢取得的使用者地理位置資訊。 | 地理 — [地理屬性] |
| 行動裝置 | MOB | 有關使用者行動裝置的資訊。 | 裝置 — [裝置屬性]<br>行動 — [行動屬性] |
| [!DNL Target]個報表區段 | SEG | 已在[!DNL Target]個報表中設定報表區段。 | 報告區段 — [區段名稱] |
| 工作階段行為 | SES | 有關使用者行為的資訊，例如檢視的頁面數量。 | 訪客設定檔 — [屬性名稱] |

## 自訂[!DNL Target]屬性類別

下表顯示[!UICONTROL Automated Personalization]與[!UICONTROL Auto-Target]活動所收集之客戶提供的資料。 只有在您提供此資料時，才會收集此資料。 特定屬性名稱和範例值是您的系統組態所特有的。

| 資料類別 | 系統前置詞 | 說明 | 在[!UICONTROL Insights]個報告中顯示名稱 |
| --- | --- | --- | --- |
| 頁面參數 | 方塊 | 在呼叫[!DNL Target]中傳遞的自訂頁面引數（「mbox引數」）。 | 自訂 — Mbox引數 — [引數名稱] |
| [!DNL Target]設定檔 | PRO | 自訂設定檔屬性會透過API或頁面引數及[!DNL Target]設定檔指令碼直接上傳至[!DNL Target]設定檔。 | 自訂 — 訪客設定檔 — [屬性名稱] |
| 客戶屬性 | CRS | 透過[!DNL Target][[!DNL Adobe Experience Cloud Customer Attributes Service]上傳至](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=zh-Hant){target=_blank}設定檔的客戶屬性。 | 自訂 — 訪客設定檔 — [屬性名稱] |
| URL 參數 | URL | 目前檢視頁面的URL和任何URL引數。 | 自訂 — URL引數 — [URL引數] |
| 反向連結 URL | 參照 | 反向連結URL和反向連結URL的任何URL引數。 | 自訂 — [反向連結URL引數] - [引數值] |
| [!DNL Adobe Experience Cloud]個共用對象 | AAM | 從其他[!DNL Target]解決方案（例如，[!DNL Adobe Experience Cloud]和[!DNL Adobe Audience Manager]，透過[!DNL Adobe Analytics][[!DNL Experience Cloud Audience Library]）與](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh-Hant){target=_blank}共用所有對象。 | 自訂 — Experience Cloud對象 — [對象名稱] |
| [!DNL Adobe Experience Platform Real-time CDP]個對象 | UPS | 透過[!DNL Target]與[!UICONTROL Destinations]共用的Platform Real-time CDP對象。 |  |


## 正在封鎖[!DNL Target]機器學習演演算法的功能

可以從[!DNL Target]機器學習演演算法中封鎖功能，防止在任何[!UICONTROL Automated Personalization]或[!UICONTROL Auto-Target]模型或活動中使用這些功能。

如需詳細資訊，請參閱[開發人員指南](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html?lang=zh-Hant){target=_blank}中的&#x200B;*[!DNL Adobe Target]模型API （封鎖清單）概觀*。

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
| 行動 - 像素密度 (ppi) | 訪客用來存取活動的行動裝置像素密度。 | 1、2、3等。 | MOB_targeting.mobile.displayPpi |
| 行動 — OS - OS X （[!DNL Android]、[!DNL Windows]等） | 指定使用者是否使用OSX （或[!DNL Android]、[!DNL Windows]等）裝置來存取活動。 | 0 為 False，1 為 True | MOB_targeting.mobile.os[OS]<br>例如，MOB_targeting.mobile.osOSx、MOB_targeting.mobile.osWindows、MOB_targeting.mobile.osAndroid、MOB_targeting.mobile.osLinux |
| 行動 - 畫面高度 (px) | 訪客用來存取活動的行動裝置畫面高度 (以像素為單位)。 | 1、2、3等。 | MOB_targeting.mobile.displayHeight |
| 行動 - 畫面寬度 (px) | 訪客用來存取活動的行動裝置畫面寬度 (以像素為單位)。 | 1、2、3等。 | MOB_targeting.mobile.displayWidth |

## 環境資料 {#env}

| 屬性名稱 | 屬性說明 | 值範例 | 系統名稱 |
| --- | --- | --- | -- |
| 瀏覽器 - 每週特定日期 | 訪客存取活動時的每週特定日期。 | 0 - 6。<br>(0 是星期日) | ENV_DayOfWeek |
| 瀏覽器 - 一天中的第幾個小時 | 訪客存取活動時的一天中的第幾個小時。 | 0 - 23<br>（0是午夜） | ENV_UserHour |
| 瀏覽器 - 一週中的第幾個小時 | 訪客存取活動時的一週中的第幾個小時。 | 0 - 168<br>（星期日午夜為0） | ENV_WeekHour |
| 瀏覽器 - 語言設定 | 用來存取活動的訪客瀏覽器中指定的語言。 | 英文<br>德文 | 環境語言(_L) |
| 瀏覽器 - 時段 | 訪客存取活動時的瀏覽器的時段。 | 0、6、12、18<br>(0 是晚上，6 是早上，<br>12 是下午，18 是傍晚) | ENV_LocalTimePeriod |
| 瀏覽器 - 時區 | 訪客存取活動時的時區。 | 太平洋時間<br>美國東部標準時間<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| 瀏覽器 - 類型 | 訪客存取活動時使用的瀏覽器類型。 | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>其他 | 環境瀏覽器 |
| 瀏覽器 - 平日/週末 | 訪客存取活動時的工作狀態 (週末、上班時間、平日自由時間)。 | 星期六和星期日是週末<br>星期一至星期五0900 - 1800是上班時間<br>星期一至星期五的1800後至0900是平日自由時間 | ENV_UserHourType |
| 瀏覽器 - 視窗高度 (px) | 訪客用來存取活動的瀏覽器視窗高度 (以像素為單位)。 | 1、2、3等， | 環境瀏覽器高度 |
| 瀏覽器 - 視窗寬度 (px) | 訪客用來存取活動的瀏覽器視窗寬度 (以像素為單位)。 | 1、2、3等， | ENV_BrowserWidth |
| 裝置 — 畫面高度(px) | 訪客用來存取活動的裝置畫面高度。 | 1、2、3等， | ENV_ScreenHeight |
| 裝置 — 畫面寬度(px) | 訪客用來存取活動的裝置畫面寬度。 | 1、2、3等， | ENV_Screenwidth |
| 作業系統  | 訪客用來存取活動的裝置上的作業系統。 | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>搜尋機器人<br>未知的作業系統 | ENV_OperatingSystem |
| 作業系統 - 版本 | 訪客用來存取活動的作業系統版本。 | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| 流量來源 - 引用登陸頁面 URL | 訪客在存取您的網站時看到的第一個頁面。 | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## 地理位置資料 {#geo}

| 屬性名稱 | 屬性說明 | 值範例 | 系統名稱 |
| --- | --- | --- | --- |
| 地理 - 城市 | 訪客存取活動時所在的城市。 | San Francisco | Geo_City |
| 地理 - 國家/地區 | 訪客存取活動時所在的國家/地區。 | 德國 | 地理國家/地區 |
| 地理 - DMA | 訪客存取活動時所在的指定市場區域 (DMA)。 | Charlottesville | Geo_DMA |
| 地理 - 緯度 | 訪客存取活動時所在的緯度。 | 47.269<br>四捨五入至小數點後的3位數（大約100米的準確度） | 地理緯度 |
| 地理 - 經度 | 訪客存取活動時所在的經度。 | -122.269<br>四捨五入至小數點後的3位數（大約100米的準確度） | GEO_Longitude |
| 地理 - 州/區域 | 訪客存取活動時所在的州或區域。 | 猶他州<br>新南威爾斯州 | GEO_State<br>GEO_Region |
| 地理 - 郵遞區號 | 訪客存取活動時所在位置的郵遞區號。 | 84004 | GEO_ZipCode |
| 行動 - 電信業者 | 訪客存取活動時使用的行動電信業者。 | [!DNL Vodafone]<br>[!DNL T-Mobile] | GEO_mobileCarrier |
| 網路 - 連線速度 | 訪客存取活動時的裝置網路連線速度。 | 寬頻<br>纜線<br>DSL<br>行動<br>無線<br>衛星 | GEO_ConnectionSpeed |
| 網路 - 網域名稱 | 訪客存取活動時所使用的網路網域名稱。 | `nnt.net` | GEO_DomainName |
| 網路 - ISP | 訪客存取活動時所使用的網路。 | nnt communications corporation | GEO_IspName |

## 工作階段資料 {#session}

| 屬性名稱 | 屬性說明 | 值範例 | 系統名稱 |
| --- | --- | --- | --- |
| 訪客輪廓 - 活動期限訂購值 | 指定某個特定活動的所有造訪/工作階段的所有訂購值的總和。 | 雙倍 | SES_CUMULATIVE_ORDER_VALUE |
| 訪客輪廓 - 活動期限網站逗留時間 | 指定訪客在網站上的總計停留時間，這不包括目前的工作階段，且會在工作階段過期時更新。 | 雙倍，毫秒 | SES_TOTAL_TIME |
| 訪客輪廓 - 活動期間每個造訪的平均頁面檢視數 | 指定每個工作階段的平均頁面檢視數，這不包括目前的工作階段。 | 雙倍 | SES_REQUESTS_PER_SESSION |
| 訪客輪廓 - 每次瀏覽的平均時間 | 指定每個造訪/工作階段停留的平均時間。這不包括目前的工作階段。 | 雙倍，毫秒 | SES_TIME_PER_SESSION |
| 訪客輪廓 - 第一次造訪 | 指定使用者與[!DNL Target]互動的首次造訪時間。 | 雙倍，毫秒 | ses_PROFILE_CREATION_TIME |
| 訪客輪廓 - 自上次造訪以來的時數 | 指定自上次造訪此特定活動以來的時數。 | 雙倍（僅限正整數） 1、2、3等。 | SES_HOURS_SINCE_LAST_VISIT |
| 訪客輪廓 - 位置/內容的曝光次數 | 指定特定活動中特定位置/內容組合的曝光次數。 | 雙倍（僅限正整數） 1、2、3等。 | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| 訪客設定檔 — 最後[!DNL Target]次互動 | 指定上次與[!DNL Target]互動的時間。 互動會在每個[!DNL Target]要求上發生，因為目前的[!DNL Target]實作會更新每個要求上的設定檔。 | 雙倍，毫秒 | SES_PROFILE_UPDATE_TIME |
| 訪客輪廓 - 活動前檢視的頁面 | 指定在訪客進入活動之前的頁面檢視總數（曝光數），包括目前的造訪/工作階段。 | 雙倍（僅限正整數） 1、2、3等。 | SES_TOTAL_PAGE_VIEWS |
| 訪客輪廓 - 目前造訪中的頁面檢視數 | 指定在訪客進入活動之前，目前造訪/工作階段中的頁面檢視次數。 更準確地說，也就是曝光次數。這些曝光不是實際的頁面檢視次數，而是要求達到[!DNL Target]的次數。 [!DNL Target]無法區分逾時或是使用者未收到或檢視內容的任何其他原因。 | 雙倍 (僅限正整數) | SES_SESSION_POSITION |
| 訪客輪廓 - 目前造訪開始時間 | 指定目前與[!DNL Target]的造訪/工作階段開始的時間。 可以初始化[!DNL Target]的造訪，而不需要進入活動。 只需要呼叫任何[!DNL Target]請求即可。 訪客在進入活動並拍攝快照之前可能需要一些時間。 | 雙倍，毫秒 | SES_SESSION_START |
| 訪客輪廓 - 開始最近一次瀏覽 | 指定與[!DNL Target]的上次造訪/工作階段開始的時間。 此屬性會在工作階段過期時更新。<br>如果這是訪客的第一個工作階段，則會產生`LAST_SESSION_START = 0.` | 雙倍，毫秒 | SES_LAST_SESSION_START |
| 訪客輪廓 - 初次進入活動時自最近一次造訪以來的時間 | 指定上一個工作階段與使用者進入活動且執行快照之間的時間的持續時間。 | 雙倍，毫秒 | SES_RECENCY |
| 訪客輪廓 - 進入活動之前的造訪時間 | 指定上次與[!DNL Target]的互動與目前造訪開始時間之間的差異。 此屬性可視為在使用者進入活動且執行快照之前的造訪/工作階段持續時間。<br>當工作階段開始且同一個[!DNL Target]呼叫已觸發上次更新時間時，會發生負值。 負值應視為 0 (零)。 | 雙倍，毫秒 | SES_SESSION_TIME |
| 訪客輪廓 - 瀏覽總數 | 指定指定造訪/工作階段總數。不包含目前的造訪/工作階段。 | 雙倍（僅限正整數） 1、2、3等。 | SES_TOTAL_SESSIONS |
| 訪客輪廓 - 活動的總造訪次數 | 指定特定活動的造訪次數。如果之前沒有任何造訪，則會傳回 0 (零)。 | 雙倍（僅限正整數） 1、2、3等。 | SES_PREVIOUS_VISIT_COUNT |
| 訪客輪廓 - 包含轉換之活動的總造訪次數 | 指定造訪期間至少有一個轉換時，特定活動的造訪/工作階段數目。 | 雙倍 | SES_CUMULATIVE_SUCCESSNS |
| 訪客輪廓 - 不包含轉換之活動的造訪次數 | 不包含轉換之特定活動的造訪/工作階段數目。此值在轉換後會重設為零，或者若從未發生轉換，則會出現 -1。 | 雙倍（僅限正整數） 1、2、3等。 | SES_SUCCESS_RECENCY |
