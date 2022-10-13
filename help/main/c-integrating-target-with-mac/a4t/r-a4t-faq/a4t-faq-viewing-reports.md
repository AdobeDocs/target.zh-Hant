---
keywords: faq;常見問題集;analytics for target;a4T;報表;檢視報表;計數方法;曝光次數;訪客;造訪;預設量度;活動轉換;未指定
description: 針對使用Analytics時經常詢問關於檢視報表問題的回答 [!DNL Target] (A4T)。 A4T可讓您對 [!DNL Target] 活動。
title: 尋找有關使用A4T檢視報表的問題解答？
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 34461e3fb6022a0d241cba2e6e31c3113006ee94
workflow-type: tm+mt
source-wordcount: '2638'
ht-degree: 31%

---

# 檢視報表 - A4T 常見問題集

此主題包含使用 [!DNL Adobe Analytics] 作為的報表來源 [!DNL Adobe Target] (A4T)。

## 我可以檢視 [!DNL Target] 活動資料 [!DNL Analysis Workspace]? {#workspace}

您可以使用 [!DNL Analysis Workspace] 分析 [!DNL Target] 活動和體驗。 此 [Analytics for Target面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html??lang=zh-Hant) 可讓您查看最多三個成功量度的提升度和可信度。 您也可以使用表格和視覺效果，更進一步了解詳情。

如需詳細資訊和範例，請開啟 [Analytics與Target:Analysis最佳實務教學課程](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)，提供者 [!UICONTROL Adobe Experience League].

## 其中可套用區段 [!DNL Analysis Workspace]? {#segmentation}

區段最常用於區段放置區中的面板頂端。 區段會套用至面板中的所有表格和視覺效果。 此技巧對於查看測試如何影響人員子集（例如，此測試對英國人員的效能如何）非常有用？

區段也可直接在自由表格中分層，但請注意，您必須將區段覆蓋整個表格，以保留A4T面板內的提升度和可信度計算。 面板中目前不支援欄層級區段。

## 我可以在 [!DNL Analysis Workspace]?

使用時 [!DNL Target] 活動曝光次數和轉換次數 [!DNL Analysis Workspace]，將「同一次接觸」Attribution IQ模型套用至量度，以確保計數準確。 若要套用[非預設歸因模型](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)，請在量度上按一下滑鼠右鍵，以&#x200B;**修改欄設定 > 啟用使用非預設歸因模型 > 選擇相同接觸模型**&#x200B;。&#x200B;若未套用此模型，這些量度就會被誇大。

所有當前 [!DNL Adobe Analytics] 包可以使用 [!UICONTROL Attribution IQ]. 如果您沒有 [!UICONTROL Attribution IQ]，請依賴中的A4T資料 [!UICONTROL Reports &amp; Analytics].

## 為特定 [!DNL Target] 活動，為何傳回不相關的體驗？ {#activity-segmentation}

傳送至 [!DNL Target] 的 [!DNL Analytics] 變數有 90 天的預設期限。(注意：客戶服務可視需要調整此到期日)。 當訪客在此有效期內導覽網站時，他們是許多 [!DNL Target] 活動，所有活動都會收集在維度中。

當您劃分要存在於點擊中的活動時，您會獲得屬於該活動的所有體驗 *plus* 持續存在於該點擊上的任何其他體驗。

## 設定我的 [!UICONTROL 目標量度]，為何無法存取 [!UICONTROL 進階設定]?

針對使用 [!DNL Analytics] 作為報表來源(A4T)，目標量度會使用[!UICONTROL 增加計數並讓使用者留在活動中]&quot;和&quot;[!UICONTROL 在每次曝光時]」設定。 這些設定包括 *not* 可設定。

如需詳細資訊，請參閱「設定目標量度時，為何無法存取進階設定選項？」 in [量度定義 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## 我是否應將訪客、造訪或活動曝光數作為標準化量度（即計數方法）? {#metrics}

在A4T報表中，有數個標準化量度的選項。 此量度（也稱為計數方法）會成為提升度計算的分母。 也會影響在套用可信度計算前彙總資料的方式。

* 使用者首次符合活動資格時，***獨特訪客***&#x200B;會增加一次。
* 一旦使用者 (獨特訪客) 進入活動，即使未在後續的造訪檢視該活動，***造訪***&#x200B;也會在每個工作階段增加一次。
* 每次提供活動內容時，***活動曝光次數***&#x200B;都會增加。(測量方式： [!DNL Target])。

訪客檢視包含活動的頁面時，系統會為該訪客設定包含活動名稱的變數。如需瞭解每個計數方法如何進行比較，請參閱下列的詳細案例。

考慮以下事項:

* 使用者符合活動資格，且內容從 [!DNL Target]. 這不一定表示使用者已經看到選件。若活動體驗位於下半部，且使用者並未向下捲動頁面，則雖然 [!DNL Target] 已提供選件，但使用者並未看到選件。
* [!UICONTROL 活動曝光次數] (由 [!DNL Target] 測量) 和[!UICONTROL 例項] (由 [!DNL Analytics] 測量) 相等，除非相同活動的相同頁面上有多個 mbox 呼叫。這會導致系統計算多個[!UICONTROL 活動曝光次數]，但僅有單一[!UICONTROL 例項]。

如需詳細資訊，請參閱 [如何在Analysis Workspace中設定A4T報表以用於自動鎖定目標活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe TargetTutorials*.

## 「活動曝光次數」和「活動轉換」在 [!DNL Analysis Workspace] 大於 [!UICONTROL Reports &amp; Analytics]? {#sametouch}

[!DNL Reports & Analytics] 將同一接觸歸因模型套用至「活動曝光次數」和「活動轉換」，但 [!DNL Analysis Workspace] 顯示原始量度，這些量度可能會因 [!DNL Target] 維度。

評估準確性 [!UICONTROL 活動曝光數] 和 [!UICONTROL 活動轉換] 量度 [!DNL Analysis Workspace]，請確定兩個量度皆已 [!UICONTROL 同一次接觸] 套用歸因模型。 若要套用模型，請按一下欄設定齒輪圖示，啟用[!UICONTROL 非預設歸因模型]，然後選取[!UICONTROL 相同接觸點]。進一步了解歸因，位於 [屬性IQ概觀](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) 在 *Analytics工具指南*.

## 如果行銷人員挑選 [!DNL Analytics] 量度（在活動設定期間）? {#section_F3EBACF85AF846E9B366A549AAB64356}

如果 [!DNL Analytics] 已選取量度作為活動的轉換量度。

## 為什麼會在 [!DNL Analytics] 報表？ 這是什麼意思? {#unspecified}

在其他報表中，「未指定」表示資料不符合分類規則，但這在 A4T 中絕對不會發生。如果看到「未指定」，就表示分類服務尚未執行。通常需要 24 到 72 小時，活動資料才會出現在報表中。即使在此之前活動不會出現在此報表中，但系結至這些活動的所有訪客資料都會擷取，並在分類完成時顯示。

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報表套裝。

如果已對該活動執行分類，而您仍在報表中看到「未指定」列，請確定報表未使用非[!DNL Target] 量度來顯示資料。 除非報表使用 [!DNL Target] — 特定量度中，「未指定」列包含未關聯之呼叫的事件 [!DNL Target]. 該行不包含任何 [!DNL Target] — 相關資訊（例如訪客/造訪/曝光數）。

## 為什麼 [!DNL Target] 傳送至的量度 [!DNL Analytics] 即使在活動已停用後？ {#section_38AA8380A4D54A18972F1EF3E73E22EF}

傳送至 [!DNL Target] 的 [!DNL Analytics] 變數有 90 天的預設期限。客戶服務可視需要調整此到期日。 此設定對所有活動都是全域的；但是，不應針對一個案例加以調整。

你可能會看到 [!DNL Target] 傳送至的變數 [!DNL Analytics] 過期，因為過期時間是90天，但僅限於該使用者從未看到已啟用另一個A4T的情況 [!DNL Target] 活動。 如果使用者在第 45 天回到網站並看到另一個活動，則整個 A4T eVar 值的計數器會重設為 90 天。這表示從第 1 天開始的第一個行銷活動，現在最多會持續到 45 + 90 = 135 天。如果使用者不斷回訪，您可能會看到量度傳送至 [!DNL Analytics] 從較舊的活動填入報表。 當使用者刪除Cookie且未返回網站時，該活動中的數字會下降，但您仍可以看到。

這表示活動在活動結束後，如果訪客在活動期間成為活動的一部分，則活動會持續取得頁面檢視、瀏覽等最多90天。 不過，如果您查看[!UICONTROL 活動曝光次數]量度，應該不會看到活動結束後的任何曝光次數。

這是正常可預期的情況。A4T 變數的作用如同任何其他與使用者相關聯的 eVar 值，直到期間到期為止 (90 天)。因此，如果活動僅作用兩週，該值至少在接下來90天內仍與使用者相關聯。

最佳作法是只檢視該活動進行那段期間的報表。在中檢視活動時，預設應正確設定日期 [!DNL Analytics]，因此，除非您手動延長日期，從報表的角度來看，這不會是問題。

例如，假設A4T變數在90天後過期，而測試在1月1日到1月15日期間生效。

在 1 月 1 日，使用者來到網站並看到活動 XYZ 一次，之後有五次頁面檢視。在接下來兩週，使用者皆沒有回到網站。對此使用者而言，資料如下:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

使用者在2月1日返回，又檢視了5個頁面，且沒有再遇到任何Target活動，且原始活動不再作用中。 即使活動已不再進行，仍然會透過 eVar 持續性來追蹤使用者。現在，資料看起來像這樣:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

使用者在 3 月 1 日回來，看到新的活動 ABC。使用者還檢視五個頁面。由於活動XYZ仍透過持續性追蹤使用者，而此使用者接著已設定ABC，因此您會在報表中看到兩行項目：

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

接著，使用者在 4 月 1 日回來，檢視另外五個頁面並購物。第一個eVar值的90天過期將在4月1日重設，因此您在報表中會看到這點。 使用者看到的所有 Target 活動皆獲得轉換的點數，但轉換總數已去除重複性。

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 | 訂單 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 總計 | 2 | 20 | 3 | 1 | 1 |

因為兩個體驗在轉換前皆已顯示，因此兩者都獲得訂單的「評分」。 但系統中僅會有一個訂單生效，並透過總計反映出來。針對 [!DNL Target] 報告，因為 [!DNL Target] 針對其他活動的活動來查看哪個活動比較成功，則使用者看到的所有活動都獲得評分並不重要。 您正在比較單一活動中兩個項目的結果。使用者無法在相同活動中看到不同的體驗，因此您不必擔心訂單信用的交叉污染。

如需詳細資訊，請參閱 [轉換變數(eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) *Analytics管理指南*.

## 在我的活動停用後，要如何持續看到更多曝光？ {#deactivated}

停用後，A4T活動報表的曝光來源可以是QA模式流量。 Target通常不會記錄已停用活動的事件，但Analytics無法知道曝光次數來自QA模式。 從Analytics擷取Target活動報表時，會顯示這些曝光數。 這可如預期運作，因為即使活動未使用QA模式作用中，客戶仍需要檢查A4T報表的方式。

## 為什麼 [!DNL Analytics] 和 [!UICONTROL Analytics for Adobe Target] (A4T)計算 [!UICONTROL 不重複訪客] 量度不同？ {#section_0C3B648AB54041F9A2AA839D51791883}

執行A/B測試時，會使用 [韋爾奇的T型](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}（信賴度量）若要選擇測試的獲勝者，其中一個假設是有固定的時間範圍。 除非您查看的是固定的樣本大小，否則測試在統計上無效。

此 [!UICONTROL 不重複訪客] 量度在 [!DNL Analytics] 和 [!DNL Target] 只有當您查看的期間比實際測試短時。 如果您未達到樣本大小，則測試不會那麼可靠。 如需詳細資訊，請參閱 [Evan Miller 網站](https://www.evanmiller.org/index.html)上的 [如何不執行 A/B 測試](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

此 [!UICONTROL 不重複訪客] 量度會顯示在指定時段內曾造訪過網站之測試的訪客人數。 這些人是測試的一部分，應該被計算。 如果只想看一週內接觸到的人數，您可以建立已有活動曝光的訪客區段，並套用至報表。

您可以縮短 [!DNL Target] 變數會持續存在至工作階段；不過，若測試中的轉換事件不太可能發生在相同的工作階段中，則這會有問題。

## 為何有時會在 [!DNL Analytics]? {#section_1397E972D31C4207A142E4D2D6D794A2}

下列清單說明在中，同一位訪客可被計入多個體驗的原因 [!DNL Analytics]:

* 此 [!DNL Target] 設定檔已過期，但 [!DNL Analytics] cookie仍然存在。 在這種情況下， [!DNL Target] 重新評估使用者，但 [!DNL Analytics] 將訪客視為同一人。
* 如果訪客使用 `mbox3rdPartyId`，當匿名訪客與第三方ID設定檔合併時， [!DNL Target] 可將訪客放入不同的體驗，以符合第三方ID。 如需詳細資訊，請參閱 [mbox3rdPartyID 的即時設定檔同步](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics] 可能是以不同的方式，以相同訪客身分來追蹤不同的裝置 [!DNL Target] 追蹤這些裝置：第三方ID設定於 [!DNL Target] 與Analytics中不同。

## A4T 是否支援虛擬報表套裝? {#virtual}

雖然虛擬報表套裝未包含在 [!UICONTROL 報表套裝] 清單，任何與報表套裝共用、且連結至 [!DNL Analytics] 有權存取該資料。 請注意，從虛擬報表套裝建立的任何對象都無法共用回 [!DNL Target].

## 是否可以在使用 A4T 的活動啟用後變更該活動中的流量分配百分比?

在啟動後變更活動中的流量分配百分比，可能會在 [!DNL Analytics] 因為此變更只會影響新訪客。 再度訪問的訪客不會受到影響。

您應採用的最佳實務是，停止現有活動，然後建立新活動，而不是在啟用後變更百分比。新活動的報表會從新訪客開始，而來自再度訪問的訪客的資料不會導致不一致的報表。

## 如何計入造訪 [!DNL Analytics] 及轉換評分 [!UICONTROL 自動鎖定目標] 使用A4T的活動？

當訪客符合A4T活動中的、檢視內容或轉換資格時， [!DNL Target] 將事件資料傳送至 [!DNL Analytics]. 此事件資料允許 [!DNL Analytics] 將頁面上發生的轉換事件和其他點按資料流事件歸因於相關的 [!DNL Target] 活動和體驗。

檢視時請謹記以下幾點 [!DNL Analytics] 報表：

* 一般而言，您的報表視窗應從活動的開始日期開始，這是最佳作法。
* 如果轉換發生在報表視窗之外，則轉換不會顯示在 [!DNL Analytics].
* 當位於 [!UICONTROL 自動鎖定目標] 活動中，訪客可能會在不同工作階段之間看見不同的體驗。 例如，如果其設定檔或內容已變更，且 [!DNL Target]機器學習演算法決定它們更可能根據新體驗轉換。 當訪客在不同體驗間移動時，每個體驗的瀏覽計數都會隨之增加。 這不同於一般A/B測試活動，其中體驗會在各次造訪間黏著訪客。
* 如果訪客在瀏覽間看到多個體驗，則任何轉換一律會歸因於訪客上次看到的體驗。 如前所述，瀏覽計數會隨著訪客所看到的每個體驗而增加。 這可能會在下方檢視體驗時，人為地降低每個體驗的轉換率。[!UICONTROL 已鎖定]「維」 [!DNL Adobe Analytics] 報表。
