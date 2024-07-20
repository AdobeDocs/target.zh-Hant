---
keywords: faq;常見問題集;analytics for target;a4T;報表;檢視報表;計數方法;曝光次數;訪客;造訪;預設量度;活動轉換;未指定
description: 尋找使用Analytics for [!DNL Target] (A4T)時經常詢問關於檢視報表問題的回答。 A4T可讓您對 [!DNL Target] 個活動使用Analytics報告。
title: 尋找使用A4T檢視報表的相關問題解答？
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 79ae58377c9eea0faca1ade11f2ab53da56b7bc1
workflow-type: tm+mt
source-wordcount: '2573'
ht-degree: 25%

---

# 檢視報表 - A4T 常見問題集

此主題包含使用[!DNL Adobe Analytics]做為[!DNL Adobe Target] (A4T)的報表來源時，經常詢問關於檢視報表問題的回答。

## 我可以在[!DNL Analysis Workspace]中檢視我的[!DNL Target]活動資料嗎？{#workspace}

+++回答
您可以使用[!DNL Analysis Workspace]來分析您的[!DNL Target]活動和體驗。 [Analytics for Target面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html??lang=zh-Hant)可讓您檢視多達三個成功量度的提升度和可信度。 您也可以使用表格和視覺效果來深入瞭解。

如需詳細資訊和範例，請開啟[!UICONTROL Adobe Experience League]提供的[Analytics &amp; Target： Analysis最佳實務教學課程](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。

+++

## 區段可套用至[!DNL Analysis Workspace]的何處？{#segmentation}

+++回答
區段最常用於區段放置區中面板的頂端。 區段會套用至面板中的所有表格和視覺效果。 這項技術對於檢視測試如何影響一部分人最有用（例如，這項測試對英國人的表現如何）？

區段也可以直接在自由格式表格中分層，但請注意，您必須將其覆蓋在整個表格中，以保留A4T面板中的提升度和信賴度計算。 目前面板中不支援欄級區段。

+++

## 我可以在[!DNL Analysis Workspace]中套用「同一次接觸」Attribution IQ模型嗎？

+++回答
在[!DNL Analysis Workspace]中使用[!DNL Target]活動曝光次數和轉換時，請套用「同一次接觸」Attribution IQ模型至量度，以確保計數準確。 若要套用[非預設歸因模型](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)，請在量度上按一下滑鼠右鍵，以&#x200B;**修改欄設定 > 啟用使用非預設歸因模型 > 選擇相同接觸模型**&#x200B;。&#x200B;若未套用此模型，這些量度就會被誇大。

所有目前的[!DNL Adobe Analytics]套件都可以使用[!UICONTROL Attribution IQ]新增此模型。 如果您沒有[!UICONTROL Attribution IQ]的存取權，請依賴[!UICONTROL Reports & Analytics]中的A4T資料。

+++

## 當我為特定[!DNL Target]活動套用點選區段時，為何會傳回不相關的體驗？ {#activity-segmentation}

+++回答
傳送至[!DNL Analytics]的[!DNL Target]變數有90天的預設期限。 （注意：如有需要，客戶服務可調整此有效期）。 當訪客在此有效期限內瀏覽網站時，他們屬於許多[!DNL Target]活動的一部分，這些活動全都收集在維度中。

當您將活動分段以顯示於點選中時，您將獲得屬於該活動的所有體驗&#x200B;*加上*&#x200B;保留於該點選的任何其他體驗。

+++

## 設定我的[!UICONTROL Goal Metrics]時，為何無法存取[!UICONTROL Advanced Settings]？

+++回答
對於使用[!DNL Analytics]作為報表來源(A4T)的活動，目標量度使用&quot;[!UICONTROL Increment Count & Keep User in Activity]&quot;和&quot;[!UICONTROL On Every Impression]&quot;設定。 這些設定是&#x200B;*不可設定的*。

如需詳細資訊，請參閱「設定目標量度時，為何無法存取進階設定選項？」 在[量度定義中 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)。

+++

## 我是否應該使用訪客、造訪或活動曝光數作為標準化量度（即計數方法）？ {#metrics}

+++回答
在A4T報告中標準化量度有數個選項。 此量度（也稱為計數方法）會成為提升度計算的分母。 也會影響在套用可信度計算前彙總資料的方式。

* ***不重複訪客***&#x200B;在使用者首次符合活動資格時增加一次。
* 使用者（不重複訪客）進入活動後，即使後續造訪中未檢視該活動，每個工作階段也會增加&#x200B;***造訪***。
* 每次提供活動內容時，***活動曝光次數***&#x200B;都會增加。 （由[!DNL Target]測量）。

訪客檢視包含活動的頁面時，系統會為該訪客設定包含活動名稱的變數。如需瞭解每個計數方法如何進行比較，請參閱下列的詳細案例。

考慮以下事項:

* 當使用者符合活動資格，且內容從[!DNL Target]傳回時，上述量度就會觸發。 這不一定表示使用者已經看到選件。若活動體驗位於下半部，且使用者並未向下捲動頁面，則雖然 [!DNL Target] 已提供選件，但使用者並未看到選件。
* [!UICONTROL Activity Impressions] （由[!DNL Target]測量）與[!UICONTROL Instances] （由[!DNL Analytics]測量）相等，除非相同活動的相同頁面上有多個mbox呼叫。 這會導致計算多個[!UICONTROL Activity Impressions]，但只有一個[!UICONTROL Instance]。

如需詳細資訊，請參閱&#x200B;*Adobe TargetTutorials*&#x200B;中的[如何在Analysis Workspace中為自動鎖定目標活動設定A4T報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html)。

+++

## 為什麼[!DNL Analysis Workspace]中的「活動曝光數」和「活動轉換次數」高於[!UICONTROL Reports & Analytics]？{#sametouch}

+++回答
[!DNL Reports & Analytics]將同一次接觸歸因模型套用至「活動曝光數」和「活動轉換」，但[!DNL Analysis Workspace]會顯示原始量度，由於[!DNL Target]維度的持續存在，這些量度可能會膨脹。

若要在[!DNL Analysis Workspace]中評估精確的[!UICONTROL Activity Impressions]和[!UICONTROL Activity Conversions]量度，請確定這兩個量度皆已套用[!UICONTROL Same Touch]歸因模型。 若要套用模型，請按一下欄設定齒輪，啟用[!UICONTROL Non-default attribution models]，然後選取[!UICONTROL Same Touch]。 在&#x200B;*Analytics工具指南*&#x200B;的[屬性IQ概觀](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html)中進一步瞭解歸因。

+++

## 如果行銷人員在活動設定期間挑選[!DNL Analytics]量度，「活動轉換」是什麼意思？ {#section_F3EBACF85AF846E9B366A549AAB64356}

+++回答
如果已選取[!DNL Analytics]量度作為活動的轉換量度，「活動轉換」為空白。

+++

## 為什麼在[!DNL Analytics]報表中看到「未指定」？ 這是什麼意思? {#unspecified}

+++回答
在其他報表中，「未指定」表示資料不符合分類規則，但在A4T中則絕對不應發生這種情況。 如果看到「未指定」，就表示分類服務尚未執行。通常需要 24 到 72 小時，活動資料才會出現在報表中。即使在此之前活動不會顯示在此報表中，但這些活動相關的所有訪客資料皆會擷取並在分類完成時顯示。

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報告套裝。

如果已為該活動完成分類，而您仍然在報表中看到「未指定」列，請確定報表未使用非[!DNL Target]量度來顯示資料。 除非報表使用[!DNL Target]特定量度，否則該「未指定」列包含與[!DNL Target]無關之呼叫的事件。 該列不會包含任何[!DNL Target]相關資訊（例如訪客/造訪/曝光數）。

+++

## 為什麼即便在活動已停用後，[!DNL Target]個量度仍會傳送至[!DNL Analytics]？ {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++回答
傳送至[!DNL Analytics]的[!DNL Target]變數有90天的預設期限。 如有需要，客戶服務可調整此有效期。 此設定是適用於所有活動的全域設定；不過，不應針對一種情況調整此設定。

您可能會看到在到期日之後傳送到[!DNL Analytics]的[!DNL Target]變數，因為到期日為90天，但前提是該使用者從未看到另一個啟用A4T的[!DNL Target]活動。 如果使用者在第 45 天回到網站並看到另一個活動，則整個 A4T eVar 值的計數器會重設為 90 天。這表示從第 1 天開始的第一個行銷活動，現在最多會持續到 45 + 90 = 135 天。如果使用者一直回來，您可能會看到報表中的量度從較舊的活動傳送至[!DNL Analytics]。 當使用者刪除Cookie且沒有返回網站時，該活動中的數字會下降，但您仍可看到它們。

這表示在活動結束後，對於在活動期間成為活動一部分的訪客，活動最多有90天會持續取得頁面檢視、造訪等。 不過，如果您檢視[!UICONTROL Activity Impressions]量度，活動結束之後應該不會看到任何曝光數。

這是正常可預期的情況。A4T 變數的作用如同任何其他與使用者相關聯的 eVar 值，直到期間到期為止 (90 天)。因此，如果活動僅活躍兩週，則至少接下來的90天中，該值仍與使用者相關聯。

最佳作法是只檢視該活動進行那段期間的報表。當您在[!DNL Analytics]中檢視活動時，預設應該正確設定日期，因此除非您已手動延長日期，否則從報表的角度來看，這應該不是問題。

舉例來說，我們假設A4T變數在90天後過期，且測試從1月1日起至1月15日有效。

在 1 月 1 日，使用者來到網站並看到活動 XYZ 一次，之後有五次頁面檢視。在接下來兩週，使用者皆沒有回到網站。對此使用者而言，資料如下:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

使用者在2月1日回訪，檢視了另外五個頁面，不再遇到任何Target活動，且原始活動不再有效。 即使活動已不再進行，仍然會透過 eVar 持續性來追蹤使用者。現在，資料看起來像這樣:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

使用者在 3 月 1 日回來，看到新的活動 ABC。使用者還檢視五個頁面。因為活動XYZ仍透過持續性在追蹤使用者，然後此使用者設定了ABC，您會在報表中看到兩行專案：

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

接著，使用者在 4 月 1 日回來，檢視另外五個頁面並購物。第一個eVar值的90天有效期限會在4月1日重設，因此您會在報表中看到該情況。 使用者看到的所有 Target 活動皆獲得轉換的點數，但轉換總數已去除重複性。

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 | 訂單 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 總計 | 2 | 20 | 3 | 1 | 1 |

因為兩個體驗都在轉換前看過，所以它們都會獲得訂單的「評分」。 但系統中僅會有一個訂單生效，並透過總計反映出來。對於[!DNL Target]報告，因為您不是針對其他活動放入[!DNL Target]活動以檢視哪些活動更成功，所以使用者看到的所有活動獲得點數並不重要。 您正在比較單一活動中兩個專案的結果。 使用者不可能在同一個活動中看到不同的體驗，因此您不必擔心訂購點數的交叉汙染。

如需詳細資訊，請參閱&#x200B;*Analytics管理指南*&#x200B;中的[轉換變數(eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html))。

+++

## 在我的活動停用後，要如何持續看到更多曝光？ {#deactivated}

+++回答
A4T活動停用後的報表曝光來源可以是QA模式流量。 Target通常不會記錄已停用活動的事件，但Analytics無法得知曝光來自QA模式。 從Analytics擷取Target活動報表時，會顯示這些曝光數。 這是依照設計運作，因為即使活動未使用QA模式啟用，客戶也需要檢查A4T報表的方法。

+++

## 為什麼[!DNL Analytics]和[!UICONTROL Analytics for Adobe Target] (A4T)計算[!UICONTROL Unique Visitors]量度的數字不同？ {#section_0C3B648AB54041F9A2AA839D51791883}

+++回答
當您執行A/B測試(使用[Welch的t測試](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} （信賴度量度）來選擇測試的獲勝者時，其中一個假設是有固定的時間範圍。 除非您檢視固定的樣本大小，否則測試在統計上無效。

[!UICONTROL Unique Visitors]量度在[!DNL Analytics]和[!DNL Target]中不同，但前提是您所檢視的期間比實際測試短。 如果您尚未達到樣本大小，測試就不那麼可靠。 如需詳細資訊，請參閱 [Evan Miller 網站](https://www.evanmiller.org/index.html)上的 [如何不執行 A/B 測試](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

[!UICONTROL Unique Visitors]量度會顯示特定時段內曾接觸到測試並造訪過網站的人數。 這些人是測試的一部分，應該被計入。 如果只想看一週內接觸到的人數，您可以建立已有活動曝光的訪客區段，並套用至報表。

您可以縮短[!DNL Target]變數持續存在至工作階段的時間長度；不過，對於轉換事件不太可能在相同工作階段發生的測試而言，這會造成問題。

+++

## 為什麼在[!DNL Analytics]中，同一個訪客有時會被計入多個體驗？{#section_1397E972D31C4207A142E4D2D6D794A2}

+++回答
下列清單說明在[!DNL Analytics]中可在多個體驗中計算相同訪客的原因：

* [!DNL Target]設定檔已過期，但[!DNL Analytics] Cookie仍然存在。 在此情況下，[!DNL Target]會重新評估使用者，但[!DNL Analytics]會將訪客視為同一個人。
* 如果訪客使用`mbox3rdPartyId`，當匿名訪客與第三方ID設定檔合併時，[!DNL Target]可能會將訪客安排到不同的體驗，以符合第三方ID。 如需詳細資訊，請參閱 [mbox3rdPartyID 的即時設定檔同步](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics]可能會以與[!DNL Target]不同的方式追蹤作為相同訪客的不同裝置，以追蹤這些裝置： [!DNL Target]中的第三方ID設定與Analytics中的設定不同。

+++

## A4T 是否支援虛擬報表套裝? {#virtual}

+++回答
雖然虛擬報告套裝未包含在[!UICONTROL Report Suite]清單中，但與連結至[!DNL Analytics]中虛擬報告套裝的報告套裝共用的任何A4T資料都可以存取該資料。 請注意，任何從虛擬報表套裝建立的對象都不能分享回[!DNL Target]。

+++

## 是否可以在使用 A4T 的活動啟用後變更該活動中的流量分配百分比?

+++回答
在活動啟用後變更該活動中的流量分配百分比，可能會導致[!DNL Analytics]中的報表不一致，因為此變更只會影響新訪客。 再度訪問的訪客不會受到影響。

您應採用的最佳實務是，停止現有活動，然後建立新活動，而不是在啟用後變更百分比。新活動的報表會從新訪客開始，而來自再度訪問的訪客的資料不會導致不一致的報表。

+++

## 使用A4T的[!UICONTROL Auto-Target]活動中的造訪次數如何計入[!DNL Analytics]以及轉換點數如何分配？

+++回答
當訪客符合A4T活動的資格、檢視內容或轉換時，[!DNL Target]會將事件資料傳送至[!DNL Analytics]。 此事件資料允許[!DNL Analytics]將頁面上發生的轉換事件和其他點按資料流事件歸因於相關的[!DNL Target]活動和體驗。

檢視[!DNL Analytics]報告時請謹記以下幾點：

* 一般來說，最佳實務是報告期間應從活動的開始日期開始。
* 如果轉換發生在報表的視窗之外，則轉換不會顯示在[!DNL Analytics]中。
* 當在[!UICONTROL Auto-Target]活動之「已鎖定目標」流量的部分時，訪客可能會在不同工作階段中看到不同的體驗。 例如，如果他們的設定檔或內容已變更，[!DNL Target]的機器學習演演算法決定他們更可能在新體驗上轉換。 當訪客從體驗移至體驗時，每個已檢視體驗的造訪計數都會增加。 這不同於一般A/B測試活動，這些活動中的體驗會跨造訪對訪客產生粘性。
* 如果訪客在跨造訪中看到多個體驗，則任何轉換都會一律歸因於訪客看到的最後一個體驗。 如前所述，造訪計數會隨著訪客所看到的每個體驗而增加。 在[!DNL Adobe Analytics]個報表中檢視&quot;[!UICONTROL Targeted]&quot;維度下的體驗時，這可能會人為地降低每個體驗的轉換率。

+++

## 使用[!UICONTROL Analytics for Target] (A4T)時如何在[!DNL Analysis Workspace]中追蹤活動曝光數？ {#activity-impressions}

+++回答

若要在[!DNL Analysis Workspace]中檢視活動曝光數：

1. 在[!DNL Target] UI中，按一下&#x200B;**[!UICONTROL View in Analytics]**。
1. 將&#x200B;**[!UICONTROL Activity Impressions]**&#x200B;欄新增至[[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html){target=_blank}報表。
1. 在&#x200B;**[!UICONTROL Activity Impressions]**&#x200B;欄上，按一下[!UICONTROL Gear]圖示。
1. 按一下 **[!UICONTROL Use non-default attribution model]**。
1. 選取&#x200B;**[!UICONTROL Same Touch Model]** > **[!UICONTROL Apply]**。

+++