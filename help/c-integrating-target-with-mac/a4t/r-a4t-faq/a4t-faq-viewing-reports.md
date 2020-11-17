---
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
description: 此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於檢視報表問題的回答。
title: 檢視報表 - A4T 常見問題集
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 7ad57c6f3814140df0826f57d8052f6db3fda301
workflow-type: tm+mt
source-wordcount: '2196'
ht-degree: 57%

---


# 檢視報表 - A4T 常見問題集

This topic contains answers to questions that are frequently asked about viewing reports when using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## 是否可以在 Analysis Workspace 中檢視我的 Target 活動資料? {#workspace}

您可用來 [!DNL Analysis Workspace] 分析您的活 [!DNL Target] 動和體驗。 「 [Analytics for Target」面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) ，可讓您檢視最多3個成功度量的提升度與可信度。 您也可以使用表格和視覺化來深入挖掘。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## 分析工作區中可套用區段的位置？ {#segmentation}

區段最常套用至區段拖放區域中的面板頂端。 區段會套用至面板中的所有表格和視覺化。 此技巧對於查看測試如何影響一部分人最有用（例如，此測試對英國人的表現如何）?

## 當我套用特定Target活動的點擊區段時，為什麼會看到傳回的不相關體驗？ {#activity-segmentation}

傳送至 [!DNL Target] 的 [!DNL Analytics] 變數有 90 天的預設期限。(注意：客戶服務可視需要調整此有效期間)。 當訪客在此有效期期間瀏覽網站時，他們是許多活動的一部 [!DNL Target] 分，所有活動都會收集在維度中。

因此，當您分段某個活動以呈現在點擊中時，您將會獲得該活動的所有體驗，再加上該點擊上持續存在的 ** 任何其他體驗。

## 我是否應將訪客、瀏覽或活動曝光次數用作我的標準化量度（即計算方法）? {#metrics}

A4T報表中有數個用於標準化量度的選項。 此量度也稱為計算方法，會成為提升度計算的分母。 也會影響在套用可信度計算前彙總資料的方式。

* 使用者首次符合活動資格時，***獨特訪客***&#x200B;會增加一次。
* 一旦使用者 (獨特訪客) 進入活動，即使未在後續的造訪檢視該活動，***造訪***&#x200B;也會在每個工作階段增加一次。
* 每次提供活動內容時，***活動曝光次數***&#x200B;都會增加。(測量方 [!DNL Target]式)。

訪客檢視包含活動的頁面時，系統會為該訪客設定包含活動名稱的變數。如需瞭解每個計數方法如何進行比較，請參閱下列的詳細案例。

考慮以下事項:

* All of the above metrics trigger when a user qualifies for an activity and content is returned from [!DNL [!DNL Target]]. 這不一定表示使用者已經看到選件。若活動體驗位於下半部，且使用者並未向下捲動頁面，則雖然 [!DNL Target] 已提供選件，但使用者並未看到選件。
* [!UICONTROL 活動曝光次數] (由 [!DNL Target] 測量) 和[!UICONTROL 例項] (由 [!DNL Analytics] 測量) 相等，除非相同活動的相同頁面上有多個 mbox 呼叫。這會導致系統計算多個[!UICONTROL 活動曝光次數]，但僅有單一[!UICONTROL 例項]。

## 為什麼「分析工作區」中的「活動印象」和「活動轉換」比「報告與分析」高？ {#sametouch}

[!DNL Reports & Analytics] 套用相同的觸控歸因模型至「活動印象」和「活動轉換」，而 [!DNL Analysis Workspace] 顯示原始量度，因為維度的持續性可能會造成誇大 [!DNL Target] 量度。

To evaluate accurate [!UICONTROL Activity Impressions] and [!UICONTROL Activity Conversions] metrics in [!DNL Analysis Workspace], ensure that both metrics have [!UICONTROL Same Touch] attribution models applied. 若要套用模型，請按一下欄設定齒輪圖示，啟用[!UICONTROL 非預設歸因模型]，然後選取[!UICONTROL 相同接觸點]。進一步瞭解 [Analytics工具指南中的屬性](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) IQ概觀 *，以*&#x200B;瞭解歸因。

## 如果市場行銷人員在活動設定期間挑選 Analytics 量度，「活動轉換」是什麼意思? {#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Activity conversions&quot; will be empty if an [!DNL Analytics] metric was selected as the conversion metric for the activity.

## 我在 Analytics 報表中為何看到「未指定」? 這是什麼意思? {#unspecified}

在其他報表中，「未指定」表示資料不符合分類規則，但這在 A4T 中絕對不會發生。如果看到「未指定」，就表示分類服務尚未執行。通常需要 24 到 72 小時，活動資料才會出現在報表中。即使在此之前活動不會出現在報表中，但這些活動相關的所有訪客資料皆會記錄下來，當分類完成時即會出現。

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報表套裝。

## 為什麼即便在活動已停用後，仍會將 Target 量度傳送到 Analytics? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

傳送至 [!DNL Target] 的 [!DNL Analytics] 變數有 90 天的預設期限。如有需要，客戶服務可以調整此有效期。 不過，此設定全域適用所有活動，因此不應針對一個案例進行調整。

You might see [!DNL Target] variables sent to [!DNL Analytics] after the expiration period because the expiration is 90 days, but only if that user never sees another A4T-enabled [!DNL Target] activity. 如果使用者在第 45 天回到網站並看到另一個活動，則整個 A4T eVar 值的計數器會重設為 90 天。這表示從第 1 天開始的第一個行銷活動，現在最多會持續到 45 + 90 = 135 天。If the user keeps coming back, you might get to the point where you see metrics sent to [!DNL Analytics] in your reporting from much older activities. 當使用者刪除 Cookie 且沒有回到網站時，該活動中的數字會下降，但您仍然會看到。

這表示對於在活動進行期間參與的訪客，當活動結束後，活動會持續收集頁面檢視和造訪等，最多 90 天。不過，如果您查看[!UICONTROL 活動曝光次數]量度，應該不會看到活動結束後的任何曝光次數。

這是正常可預期的情況。A4T 變數的作用如同任何其他與使用者相關聯的 eVar 值，直到期間到期為止 (90 天)。因此，如果活動只進行兩週，則至少接下來 90 天，值仍然會與使用者相關聯。

最佳作法是只檢視該活動進行那段期間的報表。The dates should be set correctly by default when you view the activity in [!DNL Analytics], so unless you have manually extended the date this shouldn’t be an issue from a reporting standpoint.

舉例來說，假設 A4T 變數在 90 天後到期，而我們的測試從 1 月 1 日進行到 1 月 15 日。

在 1 月 1 日，使用者來到網站並看到活動 XYZ 一次，之後有五次頁面檢視。在接下來兩週，使用者皆沒有回到網站。對此使用者而言，資料如下:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

使用者在 2 月 1 日回來並檢視其他五個頁面，且沒有遇到更多的 Target 活動，而原始活動已非使用中。即使活動已不再進行，仍然會透過 eVar 持續性來追蹤使用者。現在，資料看起來像這樣:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

使用者在 3 月 1 日回來，看到新的活動 ABC。使用者還檢視五個頁面。因為活動 XYZ 仍透過持續性在追蹤使用者，接著使用者就遇到 ABC，我們在報表中會看到兩行項目:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

接著，使用者在 4 月 1 日回來，檢視另外五個頁面並購物。這第一個 eVar 值的 90 天期限在 4 月 1 日重設，所以我們會在報表中看見。使用者看到的所有 Target 活動皆獲得轉換的點數，但轉換總數已去除重複性。

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 | 訂單 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 總計 | 2 | 20 | 3 | 1 | 1 |

因為兩個體驗皆在轉換之前被看到，所以皆獲得訂單的「點數」。但系統中僅會有一個訂單生效，並透過總計反映出來。For [!DNL Target] reporting, because you aren’t putting a [!DNL Target] activity against another activity to see which is more successful, it doesn’t matter that all activities the user saw got credit. 您是在比較單一活動內兩個項目的結果，而使用者不可能在相同個活動中看到不同的體驗，所以不必擔心訂單點數交叉污染。

For more information, see [Conversion Variables (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## 為什麼 Analytics 和 Analytics for Target (A4T) 計算的獨特訪客量度數字不同? {#section_0C3B648AB54041F9A2AA839D51791883}

執行 A/B 測試時 (採用 Student t 檢定 (可信度量度) 來選擇測試的獲勝者)，其中一項假設是固定時間範圍。除非查看固定樣本大小，否則此測試在統計學上無效。

The [!UICONTROL Unique Visitors] metric is different in [!DNL Analytics] and [!DNL Target] only when you are looking at a period of time that is shorter than the actual test. 如果尚未達到您的樣本大小，測試就不太可靠。如需詳細資訊，請參閱 [Evan Miller 網站](https://www.evanmiller.org/index.html)上的 [如何不執行 A/B 測試](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

The [!UICONTROL Unique Visitors] metric displays the number of people who have been exposed to the test who have visited the site during the specified time period. 這些人仍然為測試的一部分，應該計算在內。如果只想看一週內接觸到的人數，您可以建立已有活動曝光的訪客區段，並套用至報表。

You can shorten the amount of time the [!DNL Target] variable persists down to a session; however, that is usually problematic for tests where the conversion event isn’t as likely to happen within the same session.

## Analytics 中為何有時會在多個體驗中統計相同位訪客? {#section_1397E972D31C4207A142E4D2D6D794A2}

The following list explains reasons why the same visitor could be counted in multiple experiences in [!DNL Analytics]:

* The [!DNL Target] profile expired but the [!DNL Analytics] cookie is still there. In this situation, [!DNL Target] re-evaluates the user but [!DNL Analytics] considers the visitor to be the same person.
* 如果訪客使用 `mbox3rdPartyId`，當匿名訪客與其第三方 ID 設定檔合併時， 會將訪客安排到不同的體驗，以符合第三方 ID。[!DNL Target]如需詳細資訊，請參閱 [mbox3rdPartyID 的即時設定檔同步](/help/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics] 可能是以不同的方式，跟蹤不同的裝置，與追蹤這些 [!DNL Target] 裝置不同：協力廠商ID的設定與 [!DNL Target] Analytics中的不同。

## A4T 是否支援虛擬報表套裝?

報表套裝清單中&#x200B;*不*&#x200B;包含虛擬報表套裝，且 A4T 報表不支援虛擬報表套裝中的對象。

## 是否可以在使用 A4T 的活動啟用後變更該活動中的流量分配百分比?

Changing the traffic allocation percentage in an activity after activation can cause inconsistent reporting in [!DNL Analytics] because the change impacts only new visitors. 再度訪問的訪客不會受到影響。

您應採用的最佳實務是，停止現有活動，然後建立新活動，而不是在啟用後變更百分比。新活動的報表會從新訪客開始，而來自再度訪問的訪客的資料不會導致不一致的報表。

## 在使用A4T的Auto-Target活動中，如何在Analytics中計算瀏覽次數和轉換評價？

當訪客符合A4T活動的資格、檢視內容或轉換時，會將事件資料傳送至 [!DNL Target] , [!DNL Analytics]以便將頁面上發生的轉換事件和其他點按流事件歸因於相關活動 [!DNL Analytics][!DNL Target] 和體驗。

以下是檢視報表時應注意的幾 [!DNL Analytics] 點：

* 一般而言，您的報告視窗應一律從活動的開始日期開始。
* 如果轉換發生在報表視窗之外，轉換將不會顯示在中 [!DNL Analytics]。
* 當訪客在 [!UICONTROL Auto-Target][!DNL Target]活動流量的「目標」部分看到不同的體驗時，例如，他們的個人檔案或內容已變更，而機器學習演算法決定他們更可能根據新體驗進行轉換。 這與一般A/B測試活動不同，這些活動會在瀏覽期間吸引訪客體驗。
* 如果訪客在瀏覽間看到多個體驗，則任何轉換一律會歸因於訪客上次看見的體驗；但是，訪客所看見的每個體驗的瀏覽計數都會增加。 這可能會人為降低在報表中「已定位」維度下檢視體驗時的[!UICONTROL 每次體驗轉][!DNL Adobe Analytics] 換率。
