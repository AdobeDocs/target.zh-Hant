---
description: Target 會自動收集和使用各種資料，在自動個人化 (AP) and 自動鎖定目標 (AT) 活動中建置其個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。
seo-description: Target 會自動收集和使用各種資料，在自動個人化 (AP) and 自動鎖定目標 (AT) 活動中建置其個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。
seo-title: Target 個人化演算法的資料收集
solution: Target
title: Target 個人化演算法的資料收集
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Target 個人化演算法的資料收集{#data-collection-for-the-target-personalization-algorithms}

Target 會自動收集和使用各種資料，在自動個人化 (AP) and 自動鎖定目標 (AT) 活動中建置其個人化演算法。當訪客進入 AP 或 AT 活動時，將會傳送資訊的快照至一組「訓練記錄」(個人化演算法將學習的訪客資料)。

若要進一步瞭解關於 Target 個人化演算法，請參閱[隨機森林演算法](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA)。

下表顯示自動個人化依預設收集的資料 (行銷人員不需要執行任何動作)，以及在[個人化前瞻分析報表](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)中用於指示這些屬性的命名慣例。您可以隨時擴大輸入的資料。若要進一步瞭解如何上傳其他資料，請參閱[上傳用於 Target 個人化演算法的資料](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)。

| 資料類型 | 說明 | 資料類型命名慣例 | 範例屬性 |
|--- |--- |--- |--- |
| URL 參數 | Target 會檢查 URL 來擷取 URL 參數。 | `Custom - URL Parameter - [URL Parameter]` | 自訂資料 |
| 反向連結 URL 參數 | 一般來說，反向連結 URL 為參考起始 mbox 呼叫的特定頁面的 URL。<br>請注意，此變數可能受到您的網站上使用者的活動以及網站的技術實作影響。 | `Custom - [Referring URL Parameter] - [Parameter value]` | 自訂資料 |
| 環境和工作階段資料 | 關於使用者如何與何時存取活動的資訊。 | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | 訪客設定檔 - 最近一次瀏覽開始<br>訪客設定檔 - 瀏覽總數<br>訪客設定檔 - 每次瀏覽的平均時間<br>瀏覽器 - 時區<br>瀏覽器 - 每週特定日期<br>瀏覽器 - 語言設定<br>瀏覽器 - 類型<br>作業系統 - 版本 |
| Geography | 有關訪客所在位置的資訊。 | `Geo - [geo attribute]` | 城市<br>國家/地區<br>區域/州<br>郵遞區號<br>緯度<br>經度<br>ISP 或行動電信業者 |
| 裝置和行動資料 | 裝置和行動特定資訊。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | 行動裝置作業系統<br>行動螢幕大小 |

