---
keywords: environmental data;session data;geo data;geographical data;device data;mobile data;attributes;profile attributes
description: Adobe Target 會自動收集和使用各種資料，在 Automated Personalization (AP) 和自動鎖定目標 (AT) 活動中建置其個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。
title: Adobe Target 個人化演算法的資料收集
feature: ap
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1755'
ht-degree: 97%

---


# ![PREMIUM](/help/assets/premium.png) Target 個人化演算法的資料收集{#data-collection-for-the-target-personalization-algorithms}

 Target 會自動收集和使用各種資料，在 Automated Personalization (AP) 和自動鎖定目標 (AT) 活動中建置其個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。

若要進一步瞭解關於 Target 個人化演算法，請參閱[隨機森林演算法](/help/c-activities/t-automated-personalization/algo-random-forest.md)。

下表顯示 Automated Personalization 和自動鎖定目標依預設收集的資料 (行銷人員不需要執行任何動作)，以及在[個人化前瞻分析報表](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)中用於指示這些屬性的命名慣例。您可以隨時擴大輸入的資料。若要進一步瞭解如何上傳其他資料，請參閱[上傳用於 Target 個人化演算法的資料](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

| 資料類型 | 說明 | 資料類型命名慣例 | 範例屬性 |
| --- | --- | --- | --- |
| [裝置和行動資料](#device-mobile) | 裝置和行動特定資訊。<br>請參閱下方的「裝置和行動資料」。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | 行動裝置 OS<br>行動螢幕大小 |
| [環境資料](#env) | 訪客的作業系統以及訪客存取活動之方式和時間的相關資訊。 | `Browser - / Operating System] - [Attribute Name]` | 瀏覽器 - 類型 |
| Experience Cloud 區段 | Audience Manager 或 Analytics 中所建立的受眾且在整個 Experience Cloud 中共用 | `Custom - Experience Cloud Audience - [Audience Name]` | 自訂資料 |
| [地理位置資料](#geo) | 有關訪客所在位置的資訊。<br>請參閱下方的「地理位置資料」。 | `Geo - [geo attribute]` | 城市<br>國家/地區<br>區域/州<br>郵遞區號<br>緯度<br>經度<br>ISP 或行動電信業者 |
| 設定檔屬性 | 透過更新 API 直接上傳至 Target 設定檔的設定檔指令碼或屬性 | `Custom - Visitor Profile - [attribute name]` | 自訂資料 |
| 反向連結 URL 參數 | 一般而言，反向連結URL是指引導Target呼叫的特定頁面的URL。<br>請注意，此變數可能受到您的網站上使用者的活動以及網站的技術實作影響。 | `Custom - [Referring URL Parameter] - [Parameter value]` | 自訂資料 |
| 報表區段 | 活動設定中所設定的任何區段。 | `Reporting Segment -[Segment Name]` | 自訂資料 |
| [工作階段資料](#session) | 存取活動時，訪客在工作階段中的行為的相關資訊。 | `Visitor Profile - [Attribute Name]` | 訪客設定檔 - 開始最近一次瀏覽 |
| URL 參數 | Target 會檢查 URL 來擷取 URL 參數。 | `Custom - URL Parameter - [URL Parameter]` | 自訂資料 |

下列章節包含有關各種資料類型的詳細資訊，包括屬性名稱、說明和值範例。

## 裝置和行動資料 {#device-mobile}

| 屬性名稱 | 屬性說明 | 值範例 |
| --- | --- | --- |
| 行動 - 裝置 - 品牌 | 訪客用來存取活動的行動裝置品牌。 | Apple |
| 行動 - 裝置 - 電子書閱讀器 | 指定裝置是否為電子書閱讀器。 | 0 為 False，1 為 True |
| 行動 - 裝置 - 遊戲機 | 指定裝置是否為遊戲機。 | 0 為 False，1 為 True |
| 行動 - 裝置 - 媒體播放器 | 指定裝置是否為媒體播放器。 | 0 為 False，1 為 True |
| 行動 - 裝置 - 行動電話 | 指定裝置是否為行動電話。 | 0 為 False，1 為 True |
| 行動 - 裝置 - 型號 | 訪客用來存取活動的行動裝置型號。 | iPhone XS |
| 裝置 - 電視盒 | 指定裝置是否為電視盒。 | 0 為 False，1 為 True |
| 行動 - 裝置 - 平板電腦 | 指定裝置是否為平板電腦。 | 0 為 False，1 為 True |
| 行動 - 像素密度 (ppi) | 訪客用來存取活動的行動裝置像素密度。 | 1、2、3 等 |
| 行動 - OS – OSX (Android、Windows 等) | 指定使用者是否已使用 OSX (或 Android、Windows 等)裝置來存取活動。 | 0 為 False，1 為 True |
| 行動 - 畫面高度 (px) | 訪客用來存取活動的行動裝置畫面高度 (以像素為單位)。 | 1、2、3 等 |
| 行動 - 畫面寬度 (px) | 訪客用來存取活動的行動裝置畫面寬度 (以像素為單位)。 | 1、2、3 等 |

## 環境資料 {#env}

| 屬性名稱 | 屬性說明 | 值範例 |
| --- | --- | --- |
| 瀏覽器 - 每週特定日期 | 訪客存取活動時的每週特定日期。 | 0 至 6。<br>(0 是星期日) |
| 瀏覽器 - 一天中的第幾個小時 | 訪客存取活動時的一天中的第幾個小時。 | 0 至 23<br>(0 是凌晨 12 點) |
| 瀏覽器 - 一週中的第幾個小時 | 訪客存取活動時的一週中的第幾個小時。 | 0 至 168<br>(星期日凌晨 12 點是 0) |
| 瀏覽器 - 語言設定 | 用來存取活動的訪客瀏覽器中指定的語言。 | 英文<br>德文 |
| 瀏覽器 - 畫面高度 (px) | 訪客用來存取活動的裝置瀏覽器畫面高度 (以像素為單位)。 | 1、2、3 等 |
| 瀏覽器 - 時段 | 訪客存取活動時的瀏覽器的時段。 | 0、6、12、18<br>(0 是晚上，6 是早上，<br>12 是下午，18 是傍晚) |
| 瀏覽器 - 時區 | 訪客存取活動時的時區。 | 太平洋時間<br>美國東部標準時間<br>GMT |
| 瀏覽器 - 類型 | 訪客存取活動時使用的瀏覽器類型。 | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>其他 |
| 瀏覽器 - 平日/週末 | 訪客存取活動時的工作狀態 (週末、上班時間、平日自由時間)。 | 星期六和星期日是週末<br>星期一至星期五 0900 至 1800 是上班時間<br>星期一至星期五的 1800 後至 0900 是平日自由時間 |
| 瀏覽器 - 視窗高度 (px) | 訪客用來存取活動的瀏覽器視窗高度 (以像素為單位)。 | 1、2、3 等 |
| 瀏覽器 - 視窗寬度 (px) | 訪客用來存取活動的瀏覽器視窗寬度 (以像素為單位)。 | 1、2、3 等 |
| 裝置 - 畫面高度 | 訪客用來存取活動的裝置畫面高度。 | 1、2、3 等 |
| 裝置 - 畫面寬度 | 訪客用來存取活動的裝置畫面寬度。 | 1、2、3 等 |
| 作業系統  | 訪客用來存取活動的裝置上的作業系統。 | Mac OS<br>Windows<br>Linux<br>搜尋機器人<br>未知 OS |
| 作業系統 - 版本 | 訪客用來存取活動的作業系統版本。 | Windows 10<br>Mac OS 10 |
| 流量來源 - 引用登陸頁面 URL | 訪客在存取您的網站時看到的第一個頁面。 | `https://www.adobe.com/ecloud.html` |

## 地理位置資料 {#geo}

| 屬性名稱 | 屬性說明 | 值範例 |
| --- | --- | --- |
| 地理 - 城市 | 訪客存取活動時所在的城市。 | San Francisco |
| 地理 - 國家/地區 | 訪客存取活動時所在的國家/地區。 | 德國 |
| 地理 - DMA | 訪客存取活動時所在的指定市場區域 (DMA)。 | Charlottesville |
| 地理 - 緯度 | 訪客存取活動時所在的緯度。 | 47.269<br>四捨五入至小數點後的 3 位數 (大約 100 公尺的準確度) |
| 地理 - 經度 | 訪客存取活動時所在的經度。 | -122.269<br>四捨五入至小數點後的 3 位數 (大約 100 公尺的準確度) |
| 地理 - 州/區域 | 訪客存取活動時所在的州或區域。 | 猶他州<br>新南威爾斯州 |
| 地理 - 郵遞區號 | 訪客存取活動時所在位置的郵遞區號。 | 84004 |
| 行動 - 電信業者 | 訪客存取活動時使用的行動電信業者。 | Vodafone<br>T-Mobile |
| 網路 - 連線速度 | 訪客存取活動時的裝置網路連線速度。 | 寬頻<br>纜線<br>DSL<br>行動<br>無線<br>衛星 |
| 網路 - 網域名稱 | 訪客存取活動時所使用的網路網域名稱。 | `nnt.net` |
| 網路 - ISP | 訪客存取活動時所使用的網路。 | nnt communications corporation |

## 工作階段資料 {#session}

| 屬性名稱 | 屬性說明 | 值範例 |
| --- | --- | --- |
| 訪客設定檔 - 活動期限訂購值 | 指定某個特定活動的所有造訪/工作階段的所有訂購值的總和。 | 雙倍 |
| 訪客設定檔 - 活動期限網站逗留時間 | 指定訪客在網站上的總計停留時間，這不包括目前的工作階段，且會在工作階段過期時更新。 | 雙倍，毫秒 |
| 訪客設定檔 - 活動期間每個造訪的平均頁面檢視數 | 指定每個工作階段的平均頁面檢視數，這不包括目前的工作階段。 | 雙倍 |
| 訪客設定檔 - 每次瀏覽的平均時間 | 指定每個造訪/工作階段停留的平均時間。這不包括目前的工作階段。 | 雙倍，毫秒 |
| 訪客設定檔 - 第一次造訪 | 指定使用者與 Target 互動時的第一次造訪的時間。 | 雙倍，毫秒 |
| 訪客設定檔 - 自上次造訪以來的時數 | 指定自上次造訪此特定活動以來的時數。 | 雙倍 (僅限正整數) 1、2、3 等 |
| 訪客設定檔 - 位置/內容的曝光次數 | 指定特定活動中特定位置/內容組合的曝光次數。 | 雙倍 (僅限正整數) 1、2、3 等 |
| 訪客設定檔 - 上次 Target 互動 | 指定上次與 Target 互動的時間。Interaction happens on every [!DNL Target] request because the current implementation of [!DNL Target] updates the profile on each request. | 雙倍，毫秒 |
| 訪客設定檔 - 活動前檢視的頁面 | 指定在訪客進入活動之前的頁面檢視總數 (曝光次數)，包括目前的造訪/工作階段。 | 雙倍 (僅限正整數) 1、2、3 等 |
| 訪客設定檔 - 目前造訪中的頁面檢視數 | 指定在訪客進入活動之前，目前造訪/工作階段中的頁面檢視數。更準確地說，也就是曝光次數。這些曝光並不是真正的頁面檢視數，而是要求已到達 Target 的次數。針對逾時或是使用者未收到或檢視內容的任何其他原因，Target 無法將其加以區分。 | 雙倍 (僅限正整數) |
| 訪客設定檔 - 目前造訪開始時間 | 指定 Target 的目前造訪/工作階段開始的時間。可以初始化 Target 的造訪，而不需要進入活動。All that is required is a call to any [!DNL Target] request. 訪客在進入活動並拍攝快照之前可能需要一些時間。 | 雙倍，毫秒 |
| 訪客設定檔 - 開始最近一次瀏覽 | 指定 Target 的上次造訪/工作階段開始的時間。此屬性會在工作階段過期時更新。<br>如果這是訪客的第一個工作階段，則會產生 `LAST_SESSION_START = 0.` | 雙倍，毫秒 |
| 訪客設定檔 - 初次進入活動時自最近一次造訪以來的時間 | 指定上一個工作階段與使用者進入活動且執行快照之間的時間的持續時間。 | 雙倍，毫秒 |
| 訪客設定檔 - 進入活動之前的造訪時間 | 指定上次與 Target 進行互動以及目前造訪開始時間之間的差異。此屬性可視為在使用者進入活動且執行快照之前的造訪/工作階段持續時間。<br>[!DNL Target]當工作階段開始且同一個 呼叫已觸發上次更新時間時 ，則會出現負值。負值應視為 0 (零)。 | 雙倍，毫秒 |
| 訪客設定檔 - 瀏覽總數 | 指定指定造訪/工作階段總數。不包含目前的造訪/工作階段。 | 雙倍 (僅限正整數) 1、2、3 等 |
| 訪客設定檔 - 活動的總造訪次數 | 指定特定活動的造訪次數。如果之前沒有任何造訪，則會傳回 0 (零)。 | 雙倍 (僅限正整數) 1、2、3 等 |
| 訪客設定檔 - 包含轉換之活動的總造訪次數 | 指定造訪期間至少有一個轉換時，特定活動的造訪/工作階段數目。 | 雙倍 |
| 訪客設定檔 - 不包含轉換之活動的造訪次數 | 不包含轉換之特定活動的造訪/工作階段數目。此值在轉換後會重設為零，或者若從未發生轉換，則會出現 -1。 | 雙倍 (僅限正整數) 1、2、3 等 |
