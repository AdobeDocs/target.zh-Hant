---
keywords: faq;常見問題集;analytics for target;a4T;報表;檢視報表;計數方法;曝光次數;訪客;造訪;預設量度;活動轉換;未指定
description: 尋找使用Analytics時經常詢問關於檢視報表問題的回答 [!DNL Target] (A4T)。 A4T可讓您將Analytics報表用於 [!DNL Target] 活動。
title: 尋找使用A4T檢視報表的相關問題解答？
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 79ae58377c9eea0faca1ade11f2ab53da56b7bc1
workflow-type: tm+mt
source-wordcount: '2714'
ht-degree: 29%

---

# 檢視報表 - A4T 常見問題集

此主題包含使用時經常詢問關於檢視報表問題的回答 [!DNL Adobe Analytics] 作為的報表來源 [!DNL Adobe Target] (A4T)。

## 我可以檢視我的 [!DNL Target] 中的活動資料 [!DNL Analysis Workspace]？ {#workspace}

+++回答：您可以使用 [!DNL Analysis Workspace] 分析 [!DNL Target] 活動和體驗。 此 [Analytics for Target面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html??lang=zh-Hant) 可讓您檢視最多三個成功量度的提升度和可信度。 您也可以使用表格和視覺效果來深入瞭解。

如需詳細資訊和範例，請開啟 [Analytics與Target：分析最佳做法教學課程](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)，提供者 [!UICONTROL Adobe Experience League].

+++

## 區段可套用至何處 [!DNL Analysis Workspace]？ {#segmentation}

+++答案區段最常用於區段放置區中面板的頂端。 區段會套用至面板中的所有表格和視覺效果。 此技巧對於檢視測試如何影響一部分人最有用（例如，此測試對英國人的表現如何）？

區段也可以直接在自由表格中分層，但請注意，您必須在整個表格中覆蓋區段，以保留A4T面板中的提升度和可信度計算。 目前不支援面板中的欄層級區段。

+++

## 我可以將「同一次接觸」Attribution IQ模型套用在 [!DNL Analysis Workspace]？

+++使用時回答 [!DNL Target] 中的活動曝光次數和轉換 [!DNL Analysis Workspace]，將「同一次接觸」Attribution IQ模型套用至量度，以確保計數準確。 若要套用[非預設歸因模型](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)，請在量度上按一下滑鼠右鍵，以&#x200B;**修改欄設定 > 啟用使用非預設歸因模型 > 選擇相同接觸模型**&#x200B;。&#x200B;若未套用此模型，這些量度就會被誇大。

所有目前專案 [!DNL Adobe Analytics] 套件可新增此模型，但需搭配以下設定： [!UICONTROL Attribution IQ]. 如果您無權存取 [!UICONTROL Attribution IQ]，請仰賴A4T資料 [!UICONTROL Reports &amp; Analytics].

+++

## 當我為特定套用點選區段時 [!DNL Target] 活動，為何傳回不相關的體驗？ {#activity-segmentation}

+++回答 [!DNL Target] 變數傳送至 [!DNL Analytics] 有90天的預設有效期。 （注意：如有需要，客戶服務可調整此有效期）。 當訪客在此有效期內瀏覽網站時，他們屬於許多訪客 [!DNL Target] 活動，所有活動都會收集在維度中。

當您針對要出現在點選中的活動建立區段時，您會獲得屬於該活動的所有體驗 *加* 持續存在該點選上的任何其他體驗。

+++

## 設定我的時 [!UICONTROL 目標量度]，為何無法存取 [!UICONTROL 進階設定]？

+++使用以下專案回答活動： [!DNL Analytics] 作為報表來源(A4T)，目標量度會使用&quot;[!UICONTROL 增加計數並讓使用者留在活動中]「和」[!UICONTROL 每次曝光時]」設定。 這些設定為 *not* 可設定。

如需詳細資訊，請參閱「設定目標量度時，為何無法存取進階設定選項？」 在 [量度定義 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## 我是否應該使用訪客、造訪或活動曝光次數作為標準化量度（即計數方法）？ {#metrics}

+++答案在A4T報告中標準化量度有幾個選項。 此量度（也稱為計數方法）會成為提升度計算的分母。 也會影響在套用可信度計算前彙總資料的方式。

* 使用者首次符合活動資格時，***獨特訪客***&#x200B;會增加一次。
* 一旦使用者 (獨特訪客) 進入活動，即使未在後續的造訪檢視該活動，***造訪***&#x200B;也會在每個工作階段增加一次。
* 每次提供活動內容時，***活動曝光次數***&#x200B;都會增加。(測量方式： [!DNL Target])。

訪客檢視包含活動的頁面時，系統會為該訪客設定包含活動名稱的變數。如需瞭解每個計數方法如何進行比較，請參閱下列的詳細案例。

考慮以下事項:

* 當使用者符合活動資格，且內容已從傳回時，上述量度就會觸發 [!DNL Target]. 這不一定表示使用者已經看到選件。若活動體驗位於下半部，且使用者並未向下捲動頁面，則雖然 [!DNL Target] 已提供選件，但使用者並未看到選件。
* [!UICONTROL 活動曝光次數] (由 [!DNL Target] 測量) 和[!UICONTROL 例項] (由 [!DNL Analytics] 測量) 相等，除非相同活動的相同頁面上有多個 mbox 呼叫。這會導致系統計算多個[!UICONTROL 活動曝光次數]，但僅有單一[!UICONTROL 例項]。

如需詳細資訊，請參閱 [如何在Analysis Workspace中為自動鎖定目標活動設定A4T報表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) 在 *Adobe TargetTutorials*.

+++

## 為什麼「活動曝光次數」和「活動轉換次數」在中較高 [!DNL Analysis Workspace] than [!UICONTROL Reports &amp; Analytics]？ {#sametouch}

+++回答
[!DNL Reports & Analytics] 將同一次接觸歸因模型套用至「活動曝光數」和「活動轉換」，而 [!DNL Analysis Workspace] 顯示原始量度，由於持續存在，原始量度可能會膨脹 [!DNL Target] 維度。

若要評估精確度 [!UICONTROL 活動曝光次數] 和 [!UICONTROL 活動轉換] 中的量度 [!DNL Analysis Workspace]，確認兩個量度皆具備 [!UICONTROL 同一次接觸] 已套用歸因模型。 若要套用模型，請按一下欄設定齒輪圖示，啟用[!UICONTROL 非預設歸因模型]，然後選取[!UICONTROL 相同接觸點]。進一步瞭解歸因，請參閱 [Attributes IQ概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) 在 *Analytics工具指南*.

+++

## 如果行銷人員挑選「 」，則「活動轉換」是什麼意思 [!DNL Analytics] 活動設定期間的量度？ {#section_F3EBACF85AF846E9B366A549AAB64356}

+++如果符合下列條件，則回答「活動轉換」為空白 [!DNL Analytics] 量度已選取為活動的轉換量度。

+++

## 為什麼我會在中看到「未指定」 [!DNL Analytics] 報告？ 這是什麼意思? {#unspecified}

+++回答在其他報表中，「未指定」表示資料不符合分類規則，但在A4T中不應發生這種情況。 如果看到「未指定」，就表示分類服務尚未執行。通常需要 24 到 72 小時，活動資料才會出現在報表中。即使在此之前活動不會顯示在此報表中，但這些活動相關的所有訪客資料都會被擷取，並在分類完成時顯示。

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報表套裝。

如果已為該活動完成分類，而您仍然在報告中看到「未指定」列，請確定報告未使用非[!DNL Target] 量度以顯示資料。 除非報表使用 [!DNL Target]-specific metric，&quot;Unspecified&quot;列包含未關聯之呼叫的事件 [!DNL Target]. 該列將不包含任何 [!DNL Target] — 相關資訊（例如，訪客/造訪/曝光數）。

+++

## 為什麼 [!DNL Target] 量度傳送至 [!DNL Analytics] 即便在活動已停用後？ {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++回答 [!DNL Target] 變數傳送至 [!DNL Analytics] 有90天的預設有效期。 如有需要，客戶服務可調整此有效期。 此設定是所有活動的全域設定；但是，不應針對一種情況調整此設定。

您可能會看到 [!DNL Target] 變數傳送至 [!DNL Analytics] 到期之後到期，因為到期日為90天，但前提是該使用者從未看到其他已啟用A4T [!DNL Target] 活動。 如果使用者在第 45 天回到網站並看到另一個活動，則整個 A4T eVar 值的計數器會重設為 90 天。這表示從第 1 天開始的第一個行銷活動，現在最多會持續到 45 + 90 = 135 天。如果使用者不斷回訪，您可能會看到量度傳送至 [!DNL Analytics] 從更舊的活動建立報表中。 當使用者刪除Cookie且未返回網站時，該活動中的數字會下降，但您仍然可以看到它們。

這表示在活動結束後，對於在活動期間成為活動一部分的訪客，活動最多可維持90天內的頁面檢視、造訪次數等狀況。 不過，如果您查看[!UICONTROL 活動曝光次數]量度，應該不會看到活動結束後的任何曝光次數。

這是正常可預期的情況。A4T 變數的作用如同任何其他與使用者相關聯的 eVar 值，直到期間到期為止 (90 天)。因此，如果活動僅活躍兩週，則至少接下來90天內，該值仍與使用者相關聯。

最佳作法是只檢視該活動進行那段期間的報表。當您在中檢視活動時，日期應依預設正確設定 [!DNL Analytics]，因此除非您手動延長日期，否則從報表的角度來看，這應該不成問題。

例如，假設A4T變數在90天後過期，且測試從1月1日到1月15日作用中。

在 1 月 1 日，使用者來到網站並看到活動 XYZ 一次，之後有五次頁面檢視。在接下來兩週，使用者皆沒有回到網站。對此使用者而言，資料如下:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

使用者在2月1日回訪，又檢視了5個頁面，沒有再遇到任何Target活動，且原始活動不再有效。 即使活動已不再進行，仍然會透過 eVar 持續性來追蹤使用者。現在，資料看起來像這樣:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

使用者在 3 月 1 日回來，看到新的活動 ABC。使用者還檢視五個頁面。由於活動XYZ仍透過持續性來追蹤使用者，且此使用者已設定ABC，因此您會在報表中看到兩個明細專案：

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

接著，使用者在 4 月 1 日回來，檢視另外五個頁面並購物。第一個eVar值的90天到期日將在4月1日重設，因此您會在報表中看到該情況。 使用者看到的所有 Target 活動皆獲得轉換的點數，但轉換總數已去除重複性。

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 | 訂單 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 總計 | 2 | 20 | 3 | 1 | 1 |

由於兩個體驗都在轉換前被看見，因此它們都會獲得訂單的「評分」。 但系統中僅會有一個訂單生效，並透過總計反映出來。對象 [!DNL Target] 報告，因為您未將 [!DNL Target] 針對其他活動的活動以檢視哪個活動更成功，使用者看到的所有活動獲得點數並不重要。 您正在比較單一活動中兩個專案的結果。使用者不可能在同一個活動中看到不同的體驗，因此您不必擔心訂購點數的交叉汙染。

如需詳細資訊，請參閱 [轉換變數(eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html))中 *Analytics管理指南*.

+++

## 在我的活動停用後，要如何持續看到更多曝光？ {#deactivated}

+++回答A4T活動停用後的報表曝光率來源可以是QA模式流量。 Target通常不會記錄已停用活動的事件，但Analytics無法得知曝光來自QA模式。 從Analytics擷取Target活動報表時，會顯示這些曝光數。 這是如預期般運作，因為即使活動未使用QA模式啟用，客戶也需要檢查A4T報表的方法。

+++

## 為什麼 [!DNL Analytics] 和 [!UICONTROL Analytics for Adobe Target] (A4T)計算 [!UICONTROL 不重複訪客] 量度有何不同？ {#section_0C3B648AB54041F9A2AA839D51791883}

+++回答您執行A/B測試時，此測試會使用 [韋爾奇的t檢定](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} （信賴度量度）若要選擇測試的獲勝者，其中一個假設是有固定的時間範圍。 除非您檢視的是固定的樣本大小，否則測試在統計上無效。

此 [!UICONTROL 不重複訪客] 中的量度不同 [!DNL Analytics] 和 [!DNL Target] 僅當檢視的期間短於實際測試時。 如果您尚未達到樣本大小，測試就不那麼可靠。 如需詳細資訊，請參閱 [Evan Miller 網站](https://www.evanmiller.org/index.html)上的 [如何不執行 A/B 測試](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

此 [!UICONTROL 不重複訪客] 量度會顯示特定時段內造訪過網站且接觸到測試的人數。 這些人員是測試的一部分，應該被計入。 如果只想看一週內接觸到的人數，您可以建立已有活動曝光的訪客區段，並套用至報表。

您可以縮短 [!DNL Target] 變數會持續存在到工作階段；不過，對於轉換事件不太可能發生在相同工作階段的測試而言，這是有問題的。

+++

## 為什麼有時會在多個體驗中統計相同訪客 [!DNL Analytics]？ {#section_1397E972D31C4207A142E4D2D6D794A2}

+++答案下列清單說明為何同一個訪客可在的多個體驗中計算 [!DNL Analytics]：

* 此 [!DNL Target] 設定檔已過期，但 [!DNL Analytics] Cookie仍然存在。 在此情況下， [!DNL Target] 重新評估使用者，但 [!DNL Analytics] 會將訪客視為同一個人。
* 如果訪客使用 `mbox3rdPartyId`，當匿名訪客與第三方ID設定檔合併時， [!DNL Target] 可能會將訪客帶入不同的體驗，以符合第三方ID。 如需詳細資訊，請參閱 [mbox3rdPartyID 的即時設定檔同步](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics] 可能會以不同的方式將不同的裝置視為相同的訪客來追蹤 [!DNL Target] 追蹤這些裝置：中的第三方ID設定 [!DNL Target] 與Analytics中的不同。

+++

## A4T 是否支援虛擬報表套裝? {#virtual}

+++回答：雖然虛擬報告套裝未包含在 [!UICONTROL 報表套裝] 清單、與報告套裝共用的任何A4T資料（連結至中的虛擬報告套裝） [!DNL Analytics] 有權存取該資料。 請注意，任何從虛擬報表套裝建立的對象都不能分享回 [!DNL Target].

+++

## 是否可以在使用 A4T 的活動啟用後變更該活動中的流量分配百分比?

+++答案在活動啟動後變更其中的流量分配百分比，可能會在中導致不一致的報表 [!DNL Analytics] 因為此變更只會影響新訪客。 再度訪問的訪客不會受到影響。

您應採用的最佳實務是，停止現有活動，然後建立新活動，而不是在啟用後變更百分比。新活動的報表會從新訪客開始，而來自回訪訪客的資料不會導致不一致的報表。

+++

## 造訪次數如何計入 [!DNL Analytics] 和轉換點數配置於 [!UICONTROL 自動鎖定目標] 使用A4T的活動？

+++回答當訪客符合A4T活動的資格、檢視內容或轉換時， [!DNL Target] 傳送事件資料至 [!DNL Analytics]. 此事件資料允許 [!DNL Analytics] 將頁面上發生的轉換事件和其他點按資料流事件歸因於相關 [!DNL Target] 活動和體驗。

檢視時請謹記以下幾點 [!DNL Analytics] 報告：

* 一般來說，最佳實務是您的報告期間應從活動的開始日期開始。
* 如果轉換發生在報表的視窗之外，則轉換不會顯示在 [!DNL Analytics].
* 當處於以下專案的「目標」流量部分時： [!UICONTROL 自動鎖定目標] 活動，訪客在不同工作階段中可能會看到不同的體驗。 例如，如果其設定檔或內容已變更，而且 [!DNL Target]的機器學習演演算法決定，他們更有可能根據新體驗進行轉換。 當訪客從體驗移至體驗時，所看到的每個體驗的造訪計數都會增加。 這有別於一般A/B測試活動，這些活動中的體驗會跨造訪對訪客產生粘性。
* 如果訪客在多次造訪中看到多個體驗，則任何轉換都一律會歸因於訪客看到的最後一個體驗。 如前所述，訪客看到的每個體驗的造訪計數都會增加。 在「 」下檢視體驗時，這可能會人為降低每個體驗的轉換率[!UICONTROL 已定位]中的「維度」 [!DNL Adobe Analytics] 報表。

+++

## 使用 [!UICONTROL Analytics for Target] (A4T) 時，如何在 [!DNL Analysis Workspace] 中追蹤活動曝光次數？ {#activity-impressions}

+++回答

若要在中檢視活動曝光次數 [!DNL Analysis Workspace]：

1. 在 [!DNL Target] UI，按一下 **[!UICONTROL 在Analytics中檢視]**.
1. 新增 **[!UICONTROL 活動曝光次數]** 欄至 [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html){target=_blank} 報告。
1. 於 **[!UICONTROL 活動曝光次數]** 欄中，按一下 [!UICONTROL 齒輪] 圖示。
1. 按一下 **[!UICONTROL 使用非預設歸因模型]**.
1. 選取 **[!UICONTROL 同一次接觸模型]** > **[!UICONTROL 套用]**.

+++