---
description: Adobe Target會自動收集並使用各種資料，在自動個人化(AP)和自動Target(AT)活動中建立個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。
keywords: 環境資料；作業資料；地理資料；地理資料；裝置資料；行動資料；屬性；描述檔屬性
seo-description: Adobe Target會自動收集並使用各種資料，在自動個人化(AP)和自動Target(AT)活動中建立個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。
seo-title: Adobe Target個人化演算法的資料收集
solution: Target
title: Target 個人化演算法的資料收集
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 156587a0375fe2dbf8c461e310b2eae04b491b57

---


# ![PREMIUM](/help/assets/premium.png) Target 個人化演算法的資料收集{#data-collection-for-the-target-personalization-algorithms}

Target 會自動收集和使用各種資料，在自動個人化 (AP) and 自動鎖定目標 (AT) 活動中建置其個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。

若要進一步瞭解關於 Target 個人化演算法，請參閱[隨機森林演算法](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA)。

The following table shows the data collected by Automated Personalization and Auto-Target by default, without the marketer having to do anything, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). 您可以隨時擴大輸入的資料。若要進一步瞭解如何上傳其他資料，請參閱[上傳用於 Target 個人化演算法的資料](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)。

| 資料類型 | 說明 | 資料類型命名慣例 | 範例屬性 |
| --- | --- | --- | --- |
| [裝置與行動資料](#device-mobile) | 裝置和行動特定資訊。<br>請參閱下方的「裝置和行動資料」。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Mobile Device OS<br>Mobile Screen Size |
| [環境資料](#env) | 有關訪客作業系統的資訊，以及訪客存取活動的方式和時機。 | `Browser - / Operating System] - [Attribute Name]` | 瀏覽器 - 類型 |
| Experience Cloud部分 | 在Audience Manager或Analytics中建立的觀眾，並共用在Experience Cloud中 | `Custom - Experience Cloud Audience - [Audience Name]` | 自訂資料 |
| [地理資料](#geo) | 有關訪客所在位置的資訊。<br>請參閱下方的「地理資料」。 | `Geo - [geo attribute]` | City<br>Country<br>Region/State<br>Zip Code<br>Latitude<br>Longitude<br>ISP or Mobile Carrier |
| 設定檔屬性 | 透過Update API直接上傳至Target描述檔的描述檔指令碼或屬性 | `Custom - Visitor Profile - [attribute name]` | 自訂資料 |
| 反向連結URL參數 | 一般來說，反向連結 URL 為參考起始 mbox 呼叫的特定頁面的 URL。<br>請注意，此變數可能受到您的網站上使用者的活動以及網站的技術實作影響。 | `Custom - [Referring URL Parameter] - [Parameter value]` | 自訂資料 |
| 報告區段 | 在活動設定中設定的任何區段。 | `Reporting Segment -[Segment Name]` | 自訂資料 |
| [工作階段資料](#session) | 存取活動時訪客行為的相關資訊。 | `Visitor Profile - [Attribute Name]` | 訪客設定檔 - 開始最近一次瀏覽 |
| URL 參數 | Target 會檢查 URL 來擷取 URL 參數。 | `Custom - URL Parameter - [URL Parameter]` | 自訂資料 |

以下章節包含各種資料類型的詳細資訊，包括屬性名稱、說明和範例值。

## Device and Mobile data {#device-mobile}

| 屬性名稱 | 屬性描述 | 範例值 |
| --- | --- | --- |
| 行動-裝置-品牌 | 訪客用來存取活動的行動裝置品牌。 | Apple |
| 行動-裝置-電子書閱讀器 | 指定裝置是否為eReader。 | 0為False，1為True |
| 行動-裝置-遊戲主控台 | 指定裝置是否為遊戲主控台。 | 0為False，1為True |
| 行動-裝置-媒體播放器 | 指定裝置是否為媒體播放器。 | 0為False，1為True |
| 行動-裝置-行動電話 | 指定裝置是否為行動電話。 | 0為False，1為True |
| 行動-裝置-模型名稱 | 訪客用來存取活動的行動裝置模型名稱。 | iPhone XS |
| 裝置-機上盒 | 指定裝置是否為機上盒。 | 0為False，1為True |
| 行動-裝置-平板電腦 | 指定裝置是否為平板電腦。 | 0為False，1為True |
| 行動-像素密度(ppi) | 訪客用來存取活動的行動裝置像素密度。 | 1、2、等 |
| 行動- OS- OSX(Android、Windows等) | 指定使用者是否使用OSX(或Android、Windows等)裝置存取活動。 | 0為False，1為True |
| 行動-螢幕高度(px) | 用來存取活動的行動裝置的螢幕高度(以像素為單位)。 | 1、2、等 |
| 行動-螢幕寬度(px) | 用來存取活動的行動裝置螢幕寬度(以像素為單位)。 | 1、2、等 |

## Environmental data {#env}

| 屬性名稱 | 屬性描述 | 範例值 |
| --- | --- | --- |
| 瀏覽器 - 每週特定日期 | 訪客存取活動的一周中的某天。 | 到6。<br>(日為星期日) |
| 瀏覽器-每日時數 | 訪客存取活動的日期。 | 0 to 23<br>(0 is midnight) |
| 瀏覽器-星期 | 訪客存取活動的一周中的某小時。 | 0 to 168<br>(Sunday midnight is 0) |
| 瀏覽器 - 語言設定 | 訪客瀏覽器中用來存取活動的語言。 | English<br>German |
| 瀏覽器-螢幕高度(px) | 用來存取活動的裝置瀏覽器螢幕高度(以像素為單位)。 | 1、2、等 |
| 瀏覽器-每日時間 | 瀏覽器在訪客存取活動時的時間。 | 0, 6, 12, 18<br>(0 is night, 6 is morning,<br>12 is afternoon, 18 is evening) |
| 瀏覽器 - 時區 | 訪客存取活動時的時區。 | Pacific Time<br>Eastern Time<br>GMT |
| 瀏覽器 - 類型 | 訪客存取活動時使用的瀏覽器類型。 | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| 瀏覽器-工作日/週末 | 訪客存取活動(週末、工作日或工作日免費)時的工作狀態。 | Saturday and Sunday is weekend<br>Monday-Friday 0900 to 1800 is work time<br>Monday-Friday after 1800 until 0900 is weekday free time |
| 瀏覽器-視窗高度(px) | 用來存取活動的瀏覽器的視窗高度(以像素為單位)。 | 1、2、等 |
| 瀏覽器-視窗寬度(px) | 用來存取活動的瀏覽器的視窗寬度(以像素為單位)。 | 1、2、等 |
| 裝置-螢幕高度 | 訪客用來存取活動的裝置螢幕高度。 | 1、2、等 |
| 裝置-螢幕寬度 | 訪客用來存取活動的裝置螢幕寬度。 | 1、2、等 |
| 作業系統  | 訪客裝置上用來存取活動的作業系統。 | Mac OS<br>Windows<br>Linux<br>Search Bot<br>Unknown OS |
| 作業系統-版本 | 訪客用來存取活動的作業系統版本。 | Windows 10<br>Mac OS 10 |
| 流量來源-反向連結著陸頁面URL | 訪客存取您的網站時所看到的第一個頁面。 | `https://www.adobe.com/ecloud.html` |

## Geographical data {#geo}

| 屬性名稱 | 屬性描述 | 範例值 |
| --- | --- | --- |
| 地理-城市 | 訪客存取活動的城市。 | San Francisco |
| 地域-國家 | 訪客存取活動的所在國家。 | 德國 |
| 地理- DMA | 訪客存取活動的指定行銷區域(DMA)。 | Charlottesville |
| 地理-緯度 | 訪客存取活動的緯度。 | 47.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| 地理-發行者 | 訪客存取活動的發行者。 | -122.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| 地域-州/地區 | 訪客存取活動的州或地區。 | Utah<br>New South Wales |
| 地理-郵遞區號 | 訪客存取活動的郵遞區號。 | 84004 |
| 行動-電信業者 | 訪客存取活動時使用的行動電信業者。 | Vodafone<br>T-Mobile |
| 網路-連線速度 | 訪客存取活動時的裝置網路連線速度。 | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| 網路-網域名稱 | 訪客存取活動的網路網域名稱。 | `nnt.net` |
| 網路- ISP | 訪客存取活動的網路。 | nt munications Corporation |

## Session data {#session}

| 屬性名稱 | 屬性描述 | 範例值 |
| --- | --- | --- |
| 訪客資料-活動期限順序值 | 指定所有瀏覽/作業對特定活動之所有瀏覽/作業的總和。 | 雙倍 |
| 訪客資料-網站上的活動期限時間 | 指定訪客在網站逗留時間(排除目前作業)，並在作業過期時更新。 | 雙重，毫秒 |
| 訪客資料-活動期間每次瀏覽的平均頁面檢視次數 | 指定每個工作階段中，排除目前作業的平均頁面檢視次數。 | 雙倍 |
| 訪客設定檔 - 每次瀏覽的平均時間 | 指定每次瀏覽/作業的平均逗留時間。這不包含目前的作業。 | 雙重，毫秒 |
| 訪客資料-首次瀏覽 | 指定使用者與Target互動的第一次瀏覽時間。 | 雙重，毫秒 |
| 訪客資料-自從上次瀏覽以來的時數 | 指定自上次瀏覽至此特定活動後的時間。 | 雙重(僅整數整數)1、2、等。 |
| 訪客資料-位置/內容曝光 | 指定特定活動中特定位置/內容組合的曝光次數。 | 雙重(僅整數整數)1、2、等。 |
| 訪客資料-上次定位的互動 | 指定上次與Target互動的時間。每次mbox請求都會發生互動，因為Target的目前實作會更新每個請求上的描述檔。 | 雙重，毫秒 |
| 訪客資料-活動之前所檢視的頁面 | 指定頁面檢視總數(印象)的數目，包括目前瀏覽/作業，直到訪客進入活動為止。 | 雙重(僅整數整數)1、2、等。 |
| 訪客資料-目前瀏覽中的頁面檢視 | 指定目前瀏覽/作業中的頁面檢視次數，直到訪客進入活動為止。更精確的印象數。這些印象不是實際頁面檢視，而是請求到達Target的次數。Target無法識別使用者未收到或檢視內容的逾時或任何其他原因。 | 雙重(僅整數整數) |
| 訪客資料-目前瀏覽開始 | 指定當Target開始時，目前瀏覽/作業的時間。您可以起始Target的瀏覽，而不需進入活動。只需要呼叫任何mbox。訪客可能需要花費一段時間才進入活動，然後才會擷取快照。 | 雙重，毫秒 |
| 訪客設定檔 - 開始最近一次瀏覽 | 指定上次瀏覽/工作階段與Target開始時的時間。此屬性會在作業過期時更新。<br>如果這是訪客的第一個作業，則會產生 `LAST_SESSION_START = 0.` | 雙重，毫秒 |
| 訪客資料-自首次輸入活動後最近瀏覽的時間 | 指定上一個作業和使用者進入活動時的時間長度，並執行快照。 | 雙重，毫秒 |
| 訪客資料-進入活動前的瀏覽時間 | 指定上次與Target互動和目前瀏覽開始之間的差異。此屬性可視為造訪/作業期間，直到使用者進入活動並執行快照為止。<br>負值會在作業開始和上次更新時間由相同的mbox呼叫觸發時發生。負值值應視為(零)。 | 雙重，毫秒 |
| 訪客設定檔 - 瀏覽總數 | 指定瀏覽/作業的總數。不包含目前的瀏覽/作業。 | 雙重(僅整數整數)1、2、等。 |
| 訪客資料-活動總數 | 指定特定活動的瀏覽次數。如果沒有前一次瀏覽，則傳回(零)。 | 雙重(僅整數整數)1、2、等。 |
| 訪客資料-具有轉換的活動總數 | 指定瀏覽期間至少有一個轉換的瀏覽/作業次數。 | 雙倍 |
| 訪客資料-沒有轉換的活動瀏覽 | 瀏覽次數/作業次數，不會轉換為特定活動。此值會在轉換後重設為零，如果轉換從未發生，則將其重設。 | 雙重(僅整數整數)1、2、等。 |
