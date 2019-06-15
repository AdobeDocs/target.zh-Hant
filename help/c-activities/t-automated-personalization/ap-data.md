---
description: Target 會自動收集和使用各種資料，在自動個人化 (AP) and 自動鎖定目標 (AT) 活動中建置其個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。
seo-description: Adobe Target會自動收集並使用各種資料，在自動個人化(AP)和自動Target(AT)活動中建立個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。
seo-title: Adobe Target個人化演算法的資料收集
solution: Target
title: Target 個人化演算法的資料收集
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 1662c5e83a3712626536a659e5001cd537343883

---


# ![PREMIUM](/help/assets/premium.png) Target 個人化演算法的資料收集{#data-collection-for-the-target-personalization-algorithms}

Target 會自動收集和使用各種資料，在自動個人化 (AP) and 自動鎖定目標 (AT) 活動中建置其個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。

若要進一步瞭解關於 Target 個人化演算法，請參閱[隨機森林演算法](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA)。

下表顯示自動個人化依預設收集的資料 (行銷人員不需要執行任何動作)，以及在[個人化前瞻分析報表](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)中用於指示這些屬性的命名慣例。您可以隨時擴大輸入的資料。若要進一步瞭解如何上傳其他資料，請參閱[上傳用於 Target 個人化演算法的資料](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)。

| 資料類型 | 說明 | 資料類型命名慣例 | 範例屬性 |
| --- | --- | --- | --- |
| URL 參數 | Target 會檢查 URL 來擷取 URL 參數。 | `Custom - URL Parameter - [URL Parameter]` | 自訂資料 |
| 反向連結 URL 參數 | 一般來說，反向連結 URL 為參考起始 mbox 呼叫的特定頁面的 URL。<br>請注意，此變數可能受到您的網站上使用者的活動以及網站的技術實作影響。 | `Custom - [Referring URL Parameter] - [Parameter value]` | 自訂資料 |
| 環境和工作階段資料 | 關於使用者如何與何時存取活動的資訊。<br>請參閱下方的「環境與工作階段資料」。 | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | 訪客設定檔 - 最近一次瀏覽開始<br>訪客設定檔 - 瀏覽總數<br>訪客設定檔 - 每次瀏覽的平均時間<br>瀏覽器 - 時區<br>瀏覽器 - 每週特定日期<br>瀏覽器 - 語言設定<br>瀏覽器 - 類型<br>作業系統 - 版本 |
| 地理位置 | 有關訪客所在位置的資訊。<br>請參閱下方的「地理資料」。 | `Geo - [geo attribute]` | CityCountry<br><br>/StateZip<br>CODelatitDelongDelongituDeISP<br><br><br>或Mobile電信業者 |
| 裝置和行動資料 | 裝置和行動特定資訊。<br>請參閱下方的「裝置和行動資料」。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | 行動裝置OmMobile<br>螢幕大小 |

以下章節包含各種資料類型的詳細資訊，包括屬性名稱、說明和範例值。

>[!NOTE]
>
>下列表格中的部分值已四捨五入至最接近的整數或小時。

## 環境與工作階段資料

| 屬性名稱 | 屬性描述 | 範例值 |
| --- | --- | --- |
| 瀏覽器 - 每週特定日期 | 訪客存取活動的一周中的某天。 | 到6。<br>(日為星期日) |
| 瀏覽器-每日時數 | 訪客存取活動的日期。 | 到23<br>(0是午夜) |
| 瀏覽器-星期 | 訪客存取活動的一周中的某小時。 | 到168<br>(周日午夜為0) |
| 瀏覽器 - 語言設定 | 訪客瀏覽器中用來存取活動的語言。 | EngLisherman<br> |
| 瀏覽器-螢幕高度(px) | 用來存取活動的裝置瀏覽器螢幕高度(以像素為單位)。 | 1、2、等 |
| 瀏覽器-每日時間 | 瀏覽器在訪客存取活動時的時間。 | 0、6、12、18<br>(0是晚上、6是早上、12是下午，18是晚上) |
| 瀏覽器 - 時區 | 訪客存取活動時的時區。 | 太平洋時間東部<br>時間GMT<br> |
| 瀏覽器 - 類型 | 訪客存取活動時使用的瀏覽器類型。 | ChromeFirexInternet<br><br>Explexation Safariother<br><br> |
| 瀏覽器-工作日/週末 | 訪客存取活動(週末、工作日或工作日免費)時的工作狀態。 | 星期六和周日是週末星期一<br>到星期五0900到1800之間的工作時間<br>到1800之後，直到0900到0900工作日免費時間 |
| 瀏覽器-視窗高度(px) | 用來存取活動的瀏覽器的視窗高度(以像素為單位)。 | 1、2、等 |
| 瀏覽器-視窗寬度(px) | 用來存取活動的瀏覽器的視窗寬度(以像素為單位)。 | 1、2、等 |
| 裝置-螢幕高度 | 訪客用來存取活動的裝置螢幕高度。 | 1、2、等 |
| 裝置-螢幕寬度 | 訪客用來存取活動的裝置螢幕寬度。 | 1、2、等 |
| 行動&gt;像素密度(ppi) | 訪客用來存取活動的行動裝置像素密度。 | 1、2、等 |
| 作業系統  | 訪客裝置上用來存取活動的作業系統。 | Mac OsWindowsLinuxSearch<br><br><br>BotTunknown<br>OS |
| 作業系統-版本 | 訪客用來存取活動的作業系統版本。 | Windows10<br>Mac OS10 |
| 流量來源-反向連結著陸頁面URL | 訪客存取您的網站時所看到的第一個頁面。 | `https://www.adobe.com/ecloud.html` |

## 地理資料

| 屬性名稱 | 屬性描述 | 範例值 |
| --- | --- | --- |
| 地理-城市 | 訪客存取活動的城市。 | San Francisco |
| 地域-國家 | 訪客存取活動的所在國家。 | 德國 |
| 地理- DMA | 訪客存取活動的指定行銷區域(DMA)。 | Charlottesville |
| 地理-緯度 | 訪客存取活動的緯度。 | 47.269<br>四捨五入至小數點(大約100公尺準確度) |
| 地理-發行者 | 訪客存取活動的發行者。 | -122.269<br>四捨五入至小數點(大約100公尺準確度) |
| 地域-州/地區 | 訪客存取活動的州或地區。 | UtahNew<br>South Wales |
| 地理-郵遞區號 | 訪客存取活動的郵遞區號。 | 84004 |
| 行動-電信業者 | 訪客存取活動時使用的行動電信業者。 | Vodafone<br>T-Mobile |
| 網路-連線速度 | 訪客存取活動時的裝置網路連線速度。 | BroadbandcabedsLMobileWireessMicrosite<br><br><br><br><br> |
| 網路-網域名稱 | 訪客存取活動的網路網域名稱。 | `nnt.net` |
| 網路- ISP | 訪客存取活動的網路。 | nt munications Corporation |

## 裝置與行動資料

| 屬性名稱 | 屬性描述 | 範例值 |
| --- | --- | --- |
| 行動-裝置-品牌 | 訪客用來存取活動的行動裝置品牌。 | Apple |
| 行動-裝置-模型名稱 | 訪客用來存取活動的行動裝置模型名稱。 | iPhone XS |
| 行動- OS- OSX | 指定使用者是否使用OSX裝置存取活動。 | 0為False，1為True |
| 行動-螢幕高度(px) | 用來存取活動的行動裝置的螢幕高度(以像素為單位)。 | 1、2、等 |
| 行動-螢幕寬度(px) | 用來存取活動的行動裝置螢幕寬度(以像素為單位)。 | 1、2、等 |