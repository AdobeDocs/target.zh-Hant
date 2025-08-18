---
keywords: 鎖定目標；成功；轉換量度；頁面分數量度；頁面檢視量度；收入量度；網站逗留時間量度；預估值；進階設定；成功量度；進階設定；相依性；相依性；增加計數並保留活動中的使用者；增加計數、釋出使用者，以及允許重新進入；增加計數、釋出使用者，並禁止重新進入
description: 瞭解Adobe [!DNL Target] 中的成功量度，協助您判斷活動是否成功。 成功量度包括轉換、收入、頁面檢視、自訂評分和網站逗留時間。
title: 什麼是成功量度？
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 43%

---

# 成功量度

在[!DNL Adobe Target]個成功量度中，是用來測量活動成功的引數。 成功量度包含重要的商務測量，可讓您判斷[!DNL Target]活動中特定體驗或選件的成功程度。

例如，您可以判斷新產品建議是否會提高每位訪客帶來的收入，或將項目新增至購物車的機會。成功量度非常適合用於探索關於註冊、訂購或購買漏斗的問題，但也適合探索關於訪客或客戶參與度的問題。

## 概觀

在[!DNL Target]中，成功量度已預先設定用於報表和追蹤用途的最佳選項。

依預設，轉換事件會設為&quot;[!UICONTROL Increment count & keep user in activity]&quot;。 轉換只會計算一次，不計算重複轉換，且訪客一律會看到活動內容。

針對相同訪客下第一個訂單，將收入量度設為&quot;[!UICONTROL Increment count & keep user in activity]&quot;記錄訂單詳細資料。 所有後續訂單都會增加轉換計數，但不會將收入新增至RPV/AOV/銷售，且不會包含在[!UICONTROL Order Details]報表中。

>[!NOTE]
>
>對於使用[Analytics作為報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活動，目標量度將一律使用&quot;[!UICONTROL Increment Count & Keep User in Activity]&quot;和&quot;[!UICONTROL On Every Impression]&quot;設定。 這是&#x200B;*無法設定的*。

下列為可使用的成功量度:

| 成功量度 | 測量方式 | 定義 |
|--- |--- |--- |
| 轉換 | 轉換型 | 轉換是指訪客在您定義的網站上執行動作時，例如 <ul><li>按一下按鈕</li><li>已檢視頁面</li><li>完成一項調查</li><li>進行了購買</li></ul>每個訪客或每次訪客完成轉換時，可計算一次轉換。 |
| 收入 | 轉換型 | 造訪產生的收入。您可以從以下收入量度中選擇: <ul><li>每位訪客帶來的收入 (RPV)</li><li>平均訂購值 (AOV)</li><li>銷售總額</li><li>訂單</li></ul> |
| 頁面檢視 | 參與型 | 每個不重複訪客都會被計為轉換。 |
| 自訂得分 | 參與型 | 彙總分數是根據指派給網站上造訪頁面的值，從訪客第一眼看到此活動的第一個顯示[!DNL Target]請求開始計算。 |
| 網站逗留時間 | 參與型 | 從訪客看到活動的第一個顯示[!DNL Target]要求開始到載入工作階段中有要求的最後一頁為止的造訪逗留時間（以秒為單位）。 |

若為參與型量度 (非以轉換和收入為基礎的量度)，訪客每次瀏覽均須重新取得活動資格，以增加該工作階段計數。相關量度會在重新取得資格後開始增加計數，並在各訪客的工作階段結束後停止。閒置 30 分鐘後，工作階段就會結束。因此，在測試期間不會立即看到結果；但是，該工作階段的所有結果在工作階段結束後的幾分鐘內即可使用。

## 自訂成功量度

您也可以建立自訂成功量度。

選取成功量度之後，請選取訪客為了達成目標採取的動作。例如，選擇一個[!UICONTROL Conversion]量度，將其設為每位訪客計算一次，然後設定當訪客檢視特定頁面（或一組頁面）、檢視特定[!DNL Target]請求或按一下特定連結時是否成功。

如果已啟用，[!UICONTROL Estimated Value of one conversion]欄位（[!UICONTROL Page Score]量度無法使用）可提供目標的值，但不適用其他量度。 此值可讓 [!DNL Target] 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。對於所有收入量度（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales]和[!UICONTROL Orders]），預估會使用[!UICONTROL Revenue per Visitor]。 資料類型為貨幣。請參閱[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。

為您的活動選擇的成功量度可在您檢視活動的報表時，於報表設定中取得。

有些量度（例如[!UICONTROL Custom Scoring]和[!UICONTROL Revenue Per Visitor]）需要自訂的實作，以傳遞訂單總計和訂單ID等資訊。

## 進階設定 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

使用進階設定來管理測量成功的方式。選項包括新增相依性、選擇讓使用者留在活動還是移除活動，以及是否對每個加入者或每次曝光都計算一次量度。

若要存取[!UICONTROL Advanced Settings]選項，請按一下&#x200B;**[!UICONTROL vertical ellipses]** > **[!UICONTROL Advanced Settings]**。

![進階設定功能表](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>如果您使用 [!DNL Adobe Analytics] 作為您的報表來源，則設定是由 [!DNL Analytics] 伺服器管理。[!UICONTROL Advanced Settings]選項將無法使用。 如需詳細資訊，請參閱[Adobe Analytics作為Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的報告來源。

### 新增相依性

您可以使用進階設定來建立相依成功量度，只有在訪客先達到另一個量度時才遞增一個量度。

![新增相依性](/help/main/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

例如，測試轉換可能只有在轉換之前訪客點擊了產品建議，或是達到特定頁面時才有效。

相依性功能&#x200B;*不支援下列專案*：

* [!UICONTROL Recommendations]個活動。 所有其他活動類型均支援此功能。
* 如果您使用[Analytics作為您的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。
* 「已檢視頁面」量度型別。
* 視覺化體驗撰寫器(VEC)活動的「已點按元素」量度型別。

相依成功量度在下列情況下不會轉換:

* 如果您建立循環相依性，其中的 metric1 相依於 metric2，而 metric2 相依於 metric1，則這兩個量度都不會轉換。
* 自動個人化活動會在達到轉換量度時釋出使用者並重新開始活動，因此相依於轉換量度的任何量度永遠不會轉換。

### 使用者達到此目標量度後會發生什麼事?

使用進階設定來判斷使用者達到目標量度之後要執行的動作。下表顯示可用的選項：

| 使用者達到此目標量度之後 | 選項 |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | 指定計數的遞增方式:<ul><li>每次進入則計數加一 (預設)</li><li>在每次曝光時，排除頁面重新整理</li><li>在每次曝光時</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | 選取訪客重新進入活動時會看見的體驗:<ul><li>相同體驗 (預設)</li><li>隨機體驗</li><li>未見的體驗</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | 決定使用者看見的內容而非活動內容:<ul><li>相同體驗，無追蹤 (預設)</li><li>預設內容，或其他活動內容</li></ul> |

>[!NOTE]
>
>如果您將量度設定為[!UICONTROL Increment Count]個選項（如上所述）的其中之一，則量度計數只會以訪客層級的每個加入者正確遞增一次。 在造訪層級，每個新工作階段的量度計數在每次造訪中增加一次。

### 計數將如何增加：

選擇所要的行為：

* 每個加入者一次
* 在每次曝光時（排除頁面重新整理）
* 在每次曝光時

## 已知問題

* 將進階選項「計數將如何增加」設為「在每次曝光時」或「在每次曝光時 (不含頁面重新整理)」的成功量度，無法當作另一個量度所相依的成功量度使用。

當成功量度設為每次曝光遞增時，[!DNL Target]會在每次訪客造訪此成功量度時再次計入訪客。 [!DNL Target]然後將成功量度「成員資格」重設為0，以便在下次曝光時再次計入。 因此，如果另一個量度要求先看到此量度，[!DNL Target]永遠不會將該使用者識別為已看到第一個量度。

## 訓練影片: 活動量度

這部影片說明活動量度使用方式。

* 瞭解「目標」量度
* 瞭解和建置轉換、收入和參與量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)
