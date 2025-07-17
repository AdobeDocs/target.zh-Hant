---
keywords: 鎖定目標；成功；轉換量度；頁面分數量度；頁面檢視量度；收入量度；網站逗留時間量度；預估值；進階設定；成功量度；進階設定；相依性；相依性；增加計數並保留活動中的使用者；增加計數、釋出使用者，以及允許重新進入；增加計數、釋出使用者，並禁止重新進入
description: 瞭解可協助您判斷活動是否成功的成功量度。 成功量度包括轉換、收入、頁面檢視、自訂評分和網站逗留時間。
title: 什麼是成功量度？
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: ad26684d40ccb5239a345da73adfa924a04189ef
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 22%

---

# [!UICONTROL Success metrics]

[!DNL Adobe Target]中的成功量度是協助測量活動效能的關鍵指標。 這些量度會擷取重要的業務結果，例如轉換、每位訪客帶來的收入和客戶參與度，讓您能夠評估特定體驗或選件的影響。

例如，您可以追蹤新的促銷活動是否會增加每位訪客帶來的收入，或是否會導致更多專案新增至購物車。 成功量度還有助於識別使用者流程中的問題，例如註冊、結帳或購買程式，同時提供整體訪客行為的深入分析。

## 概觀

在[!DNL Target]中，成功量度已預先設定建議的設定，以確保準確的報告和有效追蹤。

依預設，轉換事件使用設定&#x200B;**[!UICONTROL Increment count & keep user in activity]。**&#x200B;此設定表示每個訪客僅計算為轉換一次。 不計算重複轉換。 這些訪客會在整個工作階段中持續看到活動內容。

對於使用相同設定的收入量度，只有訪客的第一個訂單會記錄訂單詳細資料。 雖然後續訂單會增加轉換計數，但不會貢獻收入型量度，例如[!UICONTROL Revenue per Visitor (RPV)]、[!UICONTROL Average Order Value (AOV)]或[!DNL Total Sales]。 這些額外的訂單也會從[!UICONTROL Order Details]報表中排除。

>[!NOTE]
>
>對於使用[Analytics作為報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活動，目標量度一律使用&quot;[!UICONTROL Increment Count & Keep User in Activity]&quot;和&quot;[!UICONTROL On Every Impression]&quot;設定。 這些設定是&#x200B;*不可設定的*。

可在[!UICONTROL Reporting Settings]上的[!UICONTROL Activity Settings page]區段中，於[!UICONTROL Goals & Settings]步驟下設定下列成功量度：

| 成功量度 | 測量方式 | 定義 |
|--- |--- |--- |
| [!UICONTROL Con]版本 | 轉換型 | 轉換是指訪客在您定義的網站上執行動作時，例如 <ul><li>已檢視頁面</li><li>已檢視 mbox</li><li>按一下元素</li></ul>每個訪客或每次訪客完成轉換時，可計算一次轉換。 |
| [!UICONTROL Revenue] | 轉換型 | 造訪產生的收入。您只能選擇一個收入量度：<ul><li>已檢視 mbox</li></ul>如需有關更新的[!DNL Target] UI中有關收入成功量度相關變更的詳細資訊，請參閱下方的[與成功量度相關的UI變更](#changes)。 |
| [!UICONTROL Engagement] | 參與型 | 造訪產生的參與度。 您可以從下列參與量度中選擇：<UL><li>頁面檢視：每次不重複造訪均會計為轉換。</li><li>[!UICONTROL Custom Scoring]：從訪客第一眼看到此活動的第一個顯示[!DNL Target]要求開始，根據網站上已造訪頁面所指派的值彙總分數。</li>[!DNL Time on Site]：瀏覽所花的時間（以秒為單位），從訪客看到活動的第一個顯示[!DNL Target]要求開始，一直到載入工作階段中有要求的最後一頁為止。</UL> |

針對參與型量度（不同於轉換型和收入型量度），訪客必須重新符合每次造訪的活動資格，才能遞增該工作階段的計數。 相關量度會在重新取得資格後開始增加計數，並在各訪客的工作階段結束後停止。閒置 30 分鐘後，工作階段就會結束。因此，在測試期間不會立即看到結果；不過，該工作階段的所有結果在工作階段結束後的幾分鐘內即可使用。

## 自訂成功量度

您也可以建立自訂成功量度。

選取成功量度之後，請選取訪客為了達成目標採取的動作。例如，選擇一個[!UICONTROL Conversion]量度，將其設為每位訪客計算一次，然後設定當訪客檢視特定頁面（或一組頁面）、檢視特定[!DNL Target]請求或按一下特定連結時是否成功。

如果已啟用，[!UICONTROL Estimated Value of one conversion]欄位（[!UICONTROL Page Score]量度無法使用）可提供目標的值，但不適用其他量度。 此值可讓 [!DNL Target] 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。對於所有收入量度（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales]和[!UICONTROL Orders]），預估會使用[!UICONTROL Revenue per Visitor]。 資料類型為貨幣。請參閱[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。

檢視活動報表時，您為活動選擇的成功量度會顯示在報表設定中。

某些量度（例如[!UICONTROL Custom Scoring]和[!UICONTROL Revenue Per Visitor]）需要傳遞資訊（例如訂單總計和訂單ID）的自訂實作。

## 進階設定 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

使用進階設定來管理測量成功的方式。選項包括新增相依性、選擇讓使用者留在活動還是移除活動，以及是否對每個加入者或每次曝光都計算一次量度。

若要存取[!UICONTROL Advanced Settings]選項，請按一下&#x200B;**[!UICONTROL More Actions]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallListVert.svg) ），然後按一下&#x200B;**[!UICONTROL Advanced Settings]**。

![進階設定功能表](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

如需[!UICONTROL Advanced Settings]選項（&quot;[!UICONTROL What will happen after a user encounters this goal]&quot;和&quot;[!UICONTROL How will the count be incremented]&quot;）的詳細資訊，請參閱[使用者遇到此目標量度後會發生什麼事](#what-happens)？

>[!NOTE]
>
>如果您使用 [!DNL Adobe Analytics] 作為您的報表來源，則設定是由 [!DNL Analytics] 伺服器管理。[!UICONTROL Advanced Settings]選項無法使用。 如需詳細資訊，請參閱[Adobe Analytics作為Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的報告來源。

### 新增相依性

您可以使用進階設定來建立相依成功量度，只有在訪客先達到另一個量度時才遞增一個量度。

例如，測試轉換可能只有在轉換之前訪客點擊了產品建議，或是達到特定頁面時才有效。

相依性功能&#x200B;*不支援下列專案*：

* [!UICONTROL Recommendations]個活動。 所有其他活動類型均支援此功能。
* 如果您使用[Analytics作為您的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。
* 「已檢視頁面」量度型別。
* 視覺化體驗撰寫器(VEC)活動的「已點按元素」量度型別。

相依成功量度在下列情況下不會轉換：

* 如果您建立循環相依性，其中的 metric1 相依於 metric2，而 metric2 相依於 metric1，則這兩個量度都不會轉換。
* 達到轉換量度時，[!UICONTROL Automated Personalization]個活動會釋出使用者並重新啟動活動，因此相依於轉換量度的任何量度都不會轉換。

### 使用者達到此目標量度後會發生什麼事? {#what-happens}

使用進階設定來判斷使用者達到目標量度之後要執行的動作。下表顯示可用的選項：

| 使用者達到此目標量度之後 | 選項 |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | 指定計數的遞增方式:<ul><li>每次進入則計數加一 (預設)</li><li>在每次曝光時，排除頁面重新整理</li><li>在每次曝光時</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | 選取訪客重新進入活動時看到的體驗：<ul><li>相同體驗 (預設)</li><li>隨機體驗</li><li>未見的體驗</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | 決定使用者看見的內容而非活動內容:<ul><li>相同體驗，無追蹤 (預設)</li><li>預設內容，或其他活動內容</li></ul> |

>[!NOTE]
>
>如果您將量度設定為[!UICONTROL Increment Count]個選項（如上所述）的其中之一，則量度計數只會以訪客層級的每個加入者正確遞增一次。 在造訪層級，每個新工作階段的量度計數在每次造訪中增加一次。

### 計數如何增加：

選擇所要的行為：

* 每個加入者一次
* 在每次曝光時（排除頁面重新整理）
* 在每次曝光時

## 已知問題

* 將進階選項「計數將如何增加」設為「在每次曝光時」或「在每次曝光時 (不含頁面重新整理)」的成功量度，無法當作另一個量度所相依的成功量度使用。

  當成功量度設為每次曝光遞增時，[!DNL Target]會在每次訪客造訪此成功量度時再次計入訪客。 [!DNL Target]然後將成功量度「成員資格」重設為0，以便在下次曝光時再次計入。 因此，如果另一個量度要求先看到此量度，[!DNL Target]永遠不會將該使用者識別為已看到第一個量度。

## 已更新Target UI變更

[[!DNL Target Standard/Premium] 25.2.1版本](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)於2015年2月17日推出，推出更新的[!DNL Target]和[!UICONTROL Visual Experience Composer] (VEC) UI。 本節概述舊版和更新版UI之間的主要差異，尤其是有關設定和管理成功量度的差異。

### 與[!UICONTROL Revenue]個成功量度相關的UI變更 {#changes}

在更新的[!DNL Target]介面中，[!UICONTROL Default View for Reporting]下拉式清單已移除。 此欄位是多餘的，因為它先前在舊版UI中儲存了[!DNL Overview] > [!UICONTROL Reports]下的預設報告檢視。

透過更新的UI，預設報告量度現在一律設為[!UICONTROL Revenue per Visitor (RPV)]。 您仍然可以自訂[!UICONTROL Reports]區段中的檢視，以顯示與您的分析最相關的量度。

此變更不會影響傳遞量度。 此變更只會影響報表檢視中顯示的預設篩選器。 由於RPV是客戶中最常使用的量度，因此選取此預設值以簡化報告工作流程。 您可以隨時在[!UICONTROL Reports]區段內切換至其他量度。