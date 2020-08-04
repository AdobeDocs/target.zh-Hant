---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics;advanced settings
description: 在Adobe Target中，成功度量是用來測量活動成功的參數。 成功量度包含重要的商務測量，可讓您判斷 Target 活動中指定體驗或選件的成功程度。
title: Adobe Target中的成功度量
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: 4fd2de5600060d58759ffa54a771a45b263f115b
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 52%

---


# 成功量度{#success-metrics}

In [!DNL Adobe Target] success metrics are parameters used to measure the success of an activity. Success metrics include key business measures that enable you to determine the success of a given experience or offer in a [!DNL Target] activity.

例如，您可以判斷新選件是否會提高每位訪客帶來的收入，或將項目新增至購物車的機會。成功量度非常適合用於探索關於註冊、訂購或購買漏斗的問題，但也適合探索關於訪客或客戶參與度的問題。

## 概述

在中， [!DNL Target]成功度量已預先設定了用於報告和追蹤目的的最佳選項。

依預設，轉換事件會設為「增[!UICONTROL 量計數並讓使用者留在活動]」。 轉換只會計算一次，不會計算重複的轉換，而訪客總是會看到活動內容。

Revenue metrics that are set to &quot;[!UICONTROL Increment count &amp; keep user in activity]&quot; log order details only for the first order made by the same visitor. All subsequent orders increase conversion count, but will not add revenue to RPV/AOV/Sales, and will not be included in the [!UICONTROL Order Details] report.

>[!NOTE]
>
>使用 [Analytics作為報告來源](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活動的預設行為為「增量計數並保留使用者參與活動[!UICONTROL 」，並且「每個參加者]一次」。

下列為可使用的成功量度:

| 成功量度 | 測量方式 | 定義 |
|--- |--- |--- |
| 轉換 | 轉換型 | 轉換是指訪客在您定義的網站上執行動作，例如 <ul><li>按一下按鈕</li><li>已檢視頁面</li><li>完成調查</li><li>購買</li></ul>每個訪客或任何訪客每次完成轉換時，都可計算一次轉換。 |
| 收入 | 轉換型 | 造訪產生的收入。您可以從以下收入量度中選擇: <ul><li>每位訪客帶來的收入 (RPV)</li><li>平均訂購值 (AOV)</li><li>銷售總額</li><li>訂單</li></ul> |
| 頁面檢視 | 參與型 | 每個不重複訪客都會被計為轉換。 |
| 自訂得分 | 參與型 | Aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the activity&#39;s first display [!DNL Target] request. |
| 網站逗留時間 | 參與型 | Time spent in the visit (in seconds) from the point the visitor sees the activity&#39;s first display [!DNL Target] request to the load of the final page with a request in the session. |

若為參與型量度 (非以轉換和收入為基礎的量度)，訪客每次瀏覽均須重新取得活動資格，以增加該工作階段計數。相關量度會在重新取得資格後開始增加計數，並在各訪客的工作階段結束後停止。閒置 30 分鐘後，工作階段就會結束。因此，測試時不會立即看到結果； 不過，該作業的所有結果都可在作業結束後的幾分鐘內取得。

## 自訂成功度量

您也可以建立自訂成功量度。

選取成功量度之後，請選取訪客為了達成目標採取的動作。For example, choose a [!UICONTROL Conversion] metric, set it to be counted once per visitor, then set whether success is achieved when a visitor views a certain page (or set of pages), views a specific [!DNL Target] request, or clicks a specific link.

If enabled, the [!UICONTROL Estimated Value of one conversion] field (not available for the [!UICONTROL Page Score] metrics) provides a value for your goal, but not for other metrics. 此值可讓 [!DNL Target] 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。For all revenue metrics ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], and [!UICONTROL Orders]), the estimate uses [!UICONTROL Revenue per Visitor]. 資料類型為貨幣。請參閱[預估收入中的提升度](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。

為您的活動選擇的成功量度可在您檢視活動的報表時，於報表設定中取得。

Some metrics, such as [!UICONTROL Custom Scoring] and [!UICONTROL Revenue Per Visitor], require a customized implementation that passes in information such as order totals and order IDs.

## 進階設定 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

使用進階設定來管理測量成功的方式。選項包括計算每個曝光次數的量度或每位訪客一次，以及選擇是否在活動中保留使用者或是加以移除。

若要存取「進 [!UICONTROL 階設定] 」選項，請按一 **[!UICONTROL 下垂直橢圓]** > **[!UICONTROL 進階設定]**。

![進階設定功能表](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>如果您使用 [!DNL Adobe Analytics] 作為您的報表來源，則設定是由 [!DNL Analytics] 伺服器管理。The [!UICONTROL Advanced Settings] option will not be available. For more information, see [Adobe Analytics as the reporting source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).

您也可以使用進階設定來建立相依成功量度，只有在訪客先達到另一個量度時才遞增一個量度。

![新增相依性](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

例如，測試轉換可能只有在轉換之前訪客點擊了選件，或是達到特定頁面時才有效。

A/B 測試、自動個人化、體驗鎖定目標和多變數測試活動中支援相依成功量度。Recommendations 活動目前不支援相依成功量度。

>[!NOTE]
>
>相依成功量度在下列情況下不會轉換:
>
>* 如果您建立循環相依性，其中的 metric1 相依於 metric2，而 metric2 相依於 metric1，則這兩個量度都不會轉換。
>* 自動個人化活動會在達到轉換量度時釋出使用者並重新開始活動，因此相依於轉換量度的任何量度永遠不會轉換。


使用進階設定來判斷使用者達到目標量度之後要執行的動作。下表顯示了可用選項：

| 使用者達到此目標量度之後 | 選項 |
|--- |--- |
| [!UICONTROL 增加計數以及讓使用者留在活動中] | 指定計數的遞增方式:<ul><li>每次進入則計數加一 (預設)</li><li>在每次曝光時，排除頁面重新整理</li><li>在每次曝光時</li></ul> |
| [!UICONTROL 增量計數、釋放用戶和允許再入] | 選取訪客重新進入活動時會看見的體驗:<ul><li>相同體驗 (預設)</li><li>隨機體驗</li><li>未見的體驗</li></ul> |
| [!UICONTROL 再入時增加計數、釋放用戶和欄] | 決定使用者看見的內容而非活動內容:<ul><li>相同體驗，無追蹤 (預設)</li><li>預設內容，或其他活動內容</li></ul> |

>[!NOTE]
>
>如果您將量度設定為其中一個「 [!UICONTROL 增量計數] 」選項（上述），則量度計數只會在訪客層級每位進入者正確遞增一次。 在瀏覽層級，每次瀏覽一次新作業的度量計數都會遞增一次。

## 訓練影片: 活動量度

這部影片說明活動量度使用方式。

* 瞭解「目標」量度
* 瞭解和建置轉換、收入和參與量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)