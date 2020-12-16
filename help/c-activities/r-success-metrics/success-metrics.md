---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics;advanced settings;dependency;dependant;Increment Count & Keep User in Activity;Increment Count, Release user, & Allow Reentry;increment Count, Release User, & Bar from Reentry
description: 在Adobe Target中，成功度量是用來測量活動成功的參數。 成功量度包含重要的商務測量，可讓您判斷 Target 活動中指定體驗或選件的成功程度。
title: Adobe Target中的成功度量
feature: success metrics
translation-type: tm+mt
source-git-commit: a12eea60aa3e66cdb54ab284fa3f942be4d56178
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 47%

---


# 成功量度

在[!DNL Adobe Target]成功度量中，是用來測量活動成功的參數。 成功度量包括關鍵業務度量，可讓您判斷在[!DNL Target]活動中特定體驗或選件是否成功。

例如，您可以判斷新選件是否會提高每位訪客帶來的收入，或將項目新增至購物車的機會。成功量度非常適合用於探索關於註冊、訂購或購買漏斗的問題，但也適合探索關於訪客或客戶參與度的問題。

## 概述

在[!DNL Target]中，成功度量已預先設定最佳選項，以用於報告和追蹤目的。

依預設，轉換事件會設為&quot;[!UICONTROL 增量計數並保留活動中的使用者]&quot;。 轉換只會計算一次，不會計算重複的轉換，而訪客總是會看到活動內容。

設為「[!UICONTROL 增量計數並保留活動中的使用者」的收入量度，僅針對相同訪客所做的第一筆訂單記錄順序詳細資料。 ]所有後續訂單都會增加轉換計數，但不會將收入新增至RPV/AOV/Sales，也不會納入[!UICONTROL 訂單詳細資料]報表。

>[!NOTE]
>
>對於使用[Analytics作為報告來源](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)的活動，目標量度一律會使用「[!UICONTROL 增量計數與保留活動中的使用者」和「[!UICONTROL 每次曝光]」設定。 ]這是&#x200B;*not*&#x200B;可配置的。

下列為可使用的成功量度:

| 成功量度 | 測量方式 | 定義 |
|--- |--- |--- |
| 轉換 | 轉換型 | 轉換是指訪客在您定義的網站上執行動作，例如 <ul><li>按一下按鈕</li><li>已檢視頁面</li><li>完成調查</li><li>購買</li></ul>每個訪客或任何訪客每次完成轉換時，都可計算一次轉換。 |
| 收入 | 轉換型 | 造訪產生的收入。您可以從以下收入量度中選擇: <ul><li>每位訪客帶來的收入 (RPV)</li><li>平均訂購值 (AOV)</li><li>銷售總額</li><li>訂單</li></ul> |
| 頁面檢視 | 參與型 | 每個不重複訪客都會被計為轉換。 |
| 自訂得分 | 參與型 | 根據指派給網站上瀏覽之頁面的值，從訪客首次看到活動的首次顯示[!DNL Target]請求開始，匯總分數。 |
| 網站逗留時間 | 參與型 | 從訪客看到活動的首次顯示[!DNL Target]請求到載入作業中包含請求的最終頁面，瀏覽逗留時間（以秒為單位）。 |

若為參與型量度 (非以轉換和收入為基礎的量度)，訪客每次瀏覽均須重新取得活動資格，以增加該工作階段計數。相關量度會在重新取得資格後開始增加計數，並在各訪客的工作階段結束後停止。閒置 30 分鐘後，工作階段就會結束。因此，測試時不會立即看到結果；不過，該作業的所有結果都可在作業結束後的幾分鐘內取得。

## 自訂成功度量

您也可以建立自訂成功量度。

選取成功量度之後，請選取訪客為了達成目標採取的動作。例如，選擇[!UICONTROL 轉換]量度，將其設為每位訪客計算一次，然後設定當訪客檢視特定頁面（或一組頁面）、檢視特定[!DNL Target]請求或按一下特定連結時是否成功。

如果啟用，一個轉換]的[!UICONTROL 估計值欄位（[!UICONTROL 頁面分數]量度不適用）會提供目標值，但不適用於其他量度。 此值可讓 [!DNL Target] 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。對於所有收入量度（[!UICONTROL 每位訪客收入]、[!UICONTROL 平均訂單值]、[!UICONTROL 銷售總額]和[!UICONTROL 訂購量]），估計使用[!UICONTROL 每位訪客收入]。 資料類型為貨幣。請參閱[預估收入中的提升度](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。

為您的活動選擇的成功量度可在您檢視活動的報表時，於報表設定中取得。

有些量度（例如[!UICONTROL 自訂計分]和[!UICONTROL 每位訪客收入]）需要自訂實作，並傳遞訂單總計和訂單ID等資訊。

## 進階設定 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

使用進階設定來管理測量成功的方式。選項包括新增相依性、選擇是否讓使用者留在活動中或移除它們，以及是否對每個參與者或每個曝光計算一次量度。

要訪問「[!UICONTROL 高級設定]」選項，請按一下「**[!UICONTROL 垂直橢圓]** > **[!UICONTROL 高級設定]**」。

![進階設定功能表](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>如果您使用 [!DNL Adobe Analytics] 作為您的報表來源，則設定是由 [!DNL Analytics] 伺服器管理。[!UICONTROL 進階設定]選項將不可用。 如需詳細資訊，請參閱[Adobe Analytics作為Adobe Target(A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md)的報表來源。

### 添加相依性

您可以使用進階設定來建立相依的成功度量，只有當訪客先到達另一個度量時，才會遞增一個度量。

![新增相依性](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

例如，測試轉換可能只有在轉換之前訪客點擊了選件，或是達到特定頁面時才有效。

下列項目支援相依性功能&#x200B;*not*:

* [!UICONTROL Recommendations 活動。]所有其他活動類型均支援此功能。
* 如果您使用[Analytics做為報表來源](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)。
* 「已檢視頁面」度量類型。
* 可視化體驗撰寫器 (VEC) 活動的「按一下元素」度量類型。

相依成功量度在下列情況下不會轉換:

* 如果您建立循環相依性，其中的 metric1 相依於 metric2，而 metric2 相依於 metric1，則這兩個量度都不會轉換。
* 自動個人化活動會在達到轉換量度時釋出使用者並重新開始活動，因此相依於轉換量度的任何量度永遠不會轉換。

### 使用者達到此目標量度後會發生什麼事?

使用進階設定來判斷使用者達到目標量度之後要執行的動作。下表顯示了可用選項：

| 使用者達到此目標量度之後 | 選項 |
|--- |--- |
| [!UICONTROL 增加計數以及讓使用者留在活動中] | 指定計數的遞增方式:<ul><li>每次進入則計數加一 (預設)</li><li>在每次曝光時，排除頁面重新整理</li><li>在每次曝光時</li></ul> |
| [!UICONTROL 增量計數、釋放用戶和允許再入] | 選取訪客重新進入活動時會看見的體驗:<ul><li>相同體驗 (預設)</li><li>隨機體驗</li><li>未見的體驗</li></ul> |
| [!UICONTROL 再入時增加計數、釋放用戶和欄] | 決定使用者看見的內容而非活動內容:<ul><li>相同體驗，無追蹤 (預設)</li><li>預設內容，或其他活動內容</li></ul> |

>[!NOTE]
>
>如果您將量度設定為[!UICONTROL 增量計數]選項之一（如上所述），則量度計數只會在訪客層級針對每個進入者正確遞增一次。 在瀏覽層級，每次瀏覽一次新作業的度量計數都會遞增一次。

### 計數將如何增加:

選擇所要的行為：

* 每個參加者一次
* 每次曝光（排除頁面重新整理）
* 在每次曝光時

## 訓練影片: 活動量度

這部影片說明活動量度使用方式。

* 瞭解「目標」量度
* 瞭解和建置轉換、收入和參與量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)