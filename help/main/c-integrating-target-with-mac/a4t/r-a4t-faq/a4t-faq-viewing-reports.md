---
keywords: faq;常見問題集;analytics for target;a4T;報表;檢視報表;計數方法;曝光次數;訪客;造訪;預設量度;活動轉換;未指定
description: 查找在使用Analytics時查看報告時經常詢問的問題的答案 [!DNL Target] (A4T)。 A4T允許您使用Analytics報告 [!DNL Target] 活動。
title: 查找有關使用A4T查看報告的問題的答案？
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 66c662e367b64ca51c5d9246cb097a12755d9aff
workflow-type: tm+mt
source-wordcount: '2551'
ht-degree: 33%

---

# 檢視報表 - A4T 常見問題集

本主題包含有關使用時查看報告的常見問題的答案 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。

## 我可以查看 [!DNL Target] Analysis Workspace的活動資料？ {#workspace}

您可以使用 [!DNL Analysis Workspace] 分析 [!DNL Target] 活動和經驗。 的 [「目標分析」面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html??lang=zh-Hant) 讓您查看多達三個成功指標的提升和信心。 也可使用表和可視化進行更深入的挖掘。

有關詳細資訊和示例，請開啟 [分析和目標：分析最佳做法教程](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)，由Adobe Experience League提供。

## 區段可套用在 Analysis Workspace 的什麼地方？ {#segmentation}

段最常用於段落區域中面板的頂部。 該段應用於面板中的所有表和可視化。 此技術對於瞭解test如何影響一部分人(例如，此test對英國人的表現如何)最有用？

段也可以直接在自由形式表內分層，但請注意，必須將其覆蓋整個表，以在「A4T面板」中保留提升和置信度計算。 面板中當前不支援列級段。

## 當我為特定對象應用命中段時 [!DNL Target] 活動，為什麼不相關的體驗會返回？ {#activity-segmentation}

傳送至 [!DNL Target] 的 [!DNL Analytics] 變數有 90 天的預設期限。(注：如果需要，可以由「客戶服務」調整此到期期限)。 訪問者在此過期窗口中瀏覽站點時，他們是許多站點的一部分 [!DNL Target] 活動，所有活動都在維中收集。

當您為某個活動分段以便在命中顯示時，您將獲得該活動的一部分的所有體驗 *加* 其他任何堅持在那次襲擊中的經歷。

## 配置我的目標度量時，為什麼無法訪問高級設定？

對於使用 [!DNL Analytics] 作為報告源(A4T)，目標度量使用[!UICONTROL 增量計數和保留活動中的用戶]&quot;和&quot;[!UICONTROL 論每個印象]。 這些設定是 *不* 可配置。

有關詳細資訊，請參閱「配置我的目標度量時，為什麼無法訪問高級設定選項？」 在 [度量定義 — A4T常見問題](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)。

## 我是否應將訪問者、訪問或活動印象作為我的正常指標（即計數方法）? {#metrics}

在A4T報告中，有幾種標準化度量的選項。 這一度量也稱為計數方法，成為升力計算的分母。 也會影響在套用可信度計算前彙總資料的方式。

* 使用者首次符合活動資格時，***獨特訪客***&#x200B;會增加一次。
* 一旦使用者 (獨特訪客) 進入活動，即使未在後續的造訪檢視該活動，***造訪***&#x200B;也會在每個工作階段增加一次。
* 每次提供活動內容時，***活動曝光次數***&#x200B;都會增加。(按 [!DNL Target])。

訪客檢視包含活動的頁面時，系統會為該訪客設定包含活動名稱的變數。如需瞭解每個計數方法如何進行比較，請參閱下列的詳細案例。

考慮以下事項:

* 當用戶符合活動條件並返回內容時，以上度量將觸發 [!DNL Target]。 這不一定表示使用者已經看到選件。若活動體驗位於下半部，且使用者並未向下捲動頁面，則雖然 [!DNL Target] 已提供選件，但使用者並未看到選件。
* [!UICONTROL 活動曝光次數] (由 [!DNL Target] 測量) 和[!UICONTROL 例項] (由 [!DNL Analytics] 測量) 相等，除非相同活動的相同頁面上有多個 mbox 呼叫。這會導致系統計算多個[!UICONTROL 活動曝光次數]，但僅有單一[!UICONTROL 例項]。

有關詳細資訊，請參見 [如何在Analysis Workspace設定A4T報告以進行自動目標活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) 在 *Adobe TargetTutorials*。

## 為什麼Analysis Workspace的「活動印象」和「活動轉換」比報告和分析高？ {#sametouch}

[!DNL Reports & Analytics] 對「活動印象」和「活動轉換」應用同一觸點歸屬模型，而 [!DNL Analysis Workspace] 顯示原始度量，由於持久性 [!DNL Target] 維。

要準確評估 [!UICONTROL 活動印象] 和 [!UICONTROL 活動轉換] 度量 [!DNL Analysis Workspace]，確保兩個指標 [!UICONTROL 同一觸摸] 應用了屬性模型。 若要套用模型，請按一下欄設定齒輪圖示，啟用[!UICONTROL 非預設歸因模型]，然後選取[!UICONTROL 相同接觸點]。瞭解有關屬性的詳細資訊 [屬性IQ概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) 的 *分析工具指南*。

## 如果市場行銷人員在活動設定期間挑選 Analytics 量度，「活動轉換」是什麼意思? {#section_F3EBACF85AF846E9B366A549AAB64356}

「活動轉換」為空 [!DNL Analytics] 度量被選作活動的轉換度量。

## 我在 Analytics 報表中為何看到「未指定」? 這是什麼意思? {#unspecified}

在其他報表中，「未指定」表示資料不符合分類規則，但這在 A4T 中絕對不會發生。如果看到「未指定」，就表示分類服務尚未執行。通常需要 24 到 72 小時，活動資料才會出現在報表中。即使在此之前活動不會顯示在此報告中，但與這些活動關聯的所有訪問者資料都會被捕獲，並在分類完成時顯示。

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報表套裝。

如果已對該活動進行分類，並且您仍在報告中看到「未指定」行，請確保報告未使用非[!DNL Target] 以顯示資料的度量。 除非報告使用 [!DNL Target] — 特定度量，該「未指定」行包含未與關聯的調用的事件 [!DNL Target]。 該行將不包含任何 [!DNL Target] — 關聯資訊（例如訪問者/訪問/印象）。

## 為什麼 [!DNL Target] 是否在活動被停用後將指標發送到分析？ {#section_38AA8380A4D54A18972F1EF3E73E22EF}

傳送至 [!DNL Target] 的 [!DNL Analytics] 變數有 90 天的預設期限。如果需要，可以由客戶服務部調整此到期期限。 不過，此設定全域適用所有活動，因此不應針對一個案例進行調整。

你可能會看到 [!DNL Target] 發送到的變數 [!DNL Analytics] 過期期後，因為過期為90天，但僅當該用戶從未看到啟用了A4T的其他內容時 [!DNL Target] 的子菜單。 如果使用者在第 45 天回到網站並看到另一個活動，則整個 A4T eVar 值的計數器會重設為 90 天。這表示從第 1 天開始的第一個行銷活動，現在最多會持續到 45 + 90 = 135 天。如果用戶不斷返回，您可能會看到發送到的度量 [!DNL Analytics] 在你的報告裡。 當用戶刪除cookie且不返回站點時，該活動中的數字會下降，但您仍然可以看到它們。

這意味著活動在活動結束後將繼續獲得頁面視圖、訪問等，最長為90天，活動在活動期間成為活動一部分的訪問者將繼續獲得此活動。 不過，如果您查看[!UICONTROL 活動曝光次數]量度，應該不會看到活動結束後的任何曝光次數。

這是正常可預期的情況。A4T 變數的作用如同任何其他與使用者相關聯的 eVar 值，直到期間到期為止 (90 天)。因此，如果活動僅處於活動狀態兩週，則該值至少在接下來的90天內仍與用戶關聯。

最佳作法是只檢視該活動進行那段期間的報表。預設情況下，在中查看活動時應正確設定日期 [!DNL Analytics]因此，除非您手動延長了日期，否則從報告的角度來看，這不應是問題。

例如，我們假設A4T變數在90天後過期，而test在1月1日到1月15日之間處於活動狀態。

在 1 月 1 日，使用者來到網站並看到活動 XYZ 一次，之後有五次頁面檢視。在接下來兩週，使用者皆沒有回到網站。對此使用者而言，資料如下:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

用戶在2月1日返回，再查看五頁，並且不再遇到任何「目標」活動，並且原始活動不再處於活動狀態。 即使活動已不再進行，仍然會透過 eVar 持續性來追蹤使用者。現在，資料看起來像這樣:

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

使用者在 3 月 1 日回來，看到新的活動 ABC。使用者還檢視五個頁面。由於活動XYZ仍在通過持久性跟蹤用戶，並且此用戶隨後設定了ABC，因此您將在報告中看到兩個行項：

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

接著，使用者在 4 月 1 日回來，檢視另外五個頁面並購物。第一個eVar值的90天到期時間將在4月1日重置，因此您在報告中可以看到這一點。 使用者看到的所有 Target 活動皆獲得轉換的點數，但轉換總數已去除重複性。

| 活動名稱 | 例項 (曝光次數) | 頁面檢視 | 瀏覽次數 | 獨特訪客 | 訂單 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 總計 | 2 | 20 | 3 | 1 | 1 |

因為兩次都是在轉換前，都得到訂單的&quot;功勞&quot;。 但系統中僅會有一個訂單生效，並透過總計反映出來。對於 [!DNL Target] 報告，因為你不是 [!DNL Target] 針對另一個活動的活動查看哪個活動更成功，用戶看到的所有活動都獲得信用並不重要。 您正在比較單個活動中兩個項目的結果。用戶不可能在同一活動中看到不同的體驗，因此您不必擔心訂單信用的交叉污染。

有關詳細資訊，請參見 [轉換變數(eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) *分析管理指南*。

## 在我的活動停用後，要如何持續看到更多曝光？ {#deactivated}

停用後對A4T活動報告的印象來源可以是QA模式通信。 目標通常不會記錄已停用活動的事件，但分析無法瞭解印象來自QA模式。 從分析中檢索目標活動報告時，會顯示這些印象。 這是按設計運行的，因為客戶需要一種方法來檢查A4T報告，即使活動在使用QA模式時不處於活動狀態。

## 為什麼Adobe Target的分析和分析(A4T)會以不同方式計算「唯一訪問者」指標的數字？ {#section_0C3B648AB54041F9A2AA839D51791883}

運行A/Btest時， [韋爾奇Ttest](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}（置信度量）來選擇test的獲勝者，其中一個假設是存在固定的時間範圍。 test在統計上無效，除非您查看的是該固定樣本大小。

的 [!UICONTROL 獨特訪問者] 度量在 [!DNL Analytics] 和 [!DNL Target] 只有當你看到的時段比實際test短。 如果尚未達到樣本大小，則test不那麼可靠。 如需詳細資訊，請參閱 [Evan Miller 網站](https://www.evanmiller.org/index.html)上的 [如何不執行 A/B 測試](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

的 [!UICONTROL 獨特訪問者] metric顯示在指定時間段內已訪問該站點的test接觸的人數。 這些人是test的一部分，應該被計算在內。 如果只想看一週內接觸到的人數，您可以建立已有活動曝光的訪客區段，並套用至報表。

可以縮短 [!DNL Target] 變數持續到會話；但是，對於在同一會話中發生轉換事件的可能性不大的test，這是有問題的。

## Analytics 中為何有時會在多個體驗中統計相同位訪客? {#section_1397E972D31C4207A142E4D2D6D794A2}

以下清單解釋了為什麼同一訪問者可以計入以下多個體驗 [!DNL Analytics]:

* 的 [!DNL Target] 配置檔案已過期，但 [!DNL Analytics] 餅乾還在。 在這種情況下， [!DNL Target] 重新評估用戶，但 [!DNL Analytics] 認為訪客是同一個人。
* 如果訪問者使用 `mbox3rdPartyId`，當匿名訪問者與第三方ID配置檔案合併時， [!DNL Target] 可以讓訪客體驗不同的體驗，以與第三方身份相匹配。 如需詳細資訊，請參閱 [mbox3rdPartyID 的即時設定檔同步](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics] 跟蹤同一訪問者的不同設備的方式可能不同 [!DNL Target] 跟蹤這些設備：第三方ID設定 [!DNL Target] 與分析學不同。

## A4T 是否支援虛擬報表套裝? {#virtual}

儘管虛擬報告套件未包含在 [!UICONTROL 報表套件] 清單，與連結到中虛擬報表套件的報表套件共用的任何A4T資料 [!DNL Analytics] 有權訪問資料。 請注意，從虛擬報告套件建立的任何受眾都不能共用回 [!DNL Target]。

## 是否可以在使用 A4T 的活動啟用後變更該活動中的流量分配百分比?

在激活後更改活動中的流量分配百分比可能會導致 [!DNL Analytics] 因為變化只影響新訪問者。 再度訪問的訪客不會受到影響。

您應採用的最佳實務是，停止現有活動，然後建立新活動，而不是在啟用後變更百分比。新活動的報告從新訪問者開始，而返回訪問者的資料不會導致報告不一致。

## 在使用A4T的「自動目標」活動中，「分析」和「轉換貸項」中如何計算訪問量？

訪問者在A4T活動中符合條件、查看內容或進行轉換時， [!DNL Target] 發送事件資料 [!DNL Analytics]。 此事件資料允許 [!DNL Analytics] 將頁面上發生的轉換事件和其他點擊流事件屬性為相關 [!DNL Target] 活動和經驗。

在查看時，請注意以下幾點 [!DNL Analytics] 報告：

* 通常，作為最佳做法，報告窗口應從活動的開始日期開始。
* 如果在報表窗口外發生轉換，則在中不顯示該轉換 [!DNL Analytics]。
* 當在「目標」部分中 [!UICONTROL 自動目標] 活動，參觀者可能會看到不同的體驗，從一個會議到下一個會議。 例如，如果其配置檔案或上下文已更改， [!DNL Target]他們的機器學習算法決定，他們更可能根據新體驗進行轉換。 隨著訪問者從體驗到體驗的轉變，每次體驗的訪問次數都會增加。 這與常規的A/B測試活動不同，在這些活動中，訪問者在訪問期間體驗會很難掌握。
* 如果訪問者在訪問期間看到多種體驗，則任何轉換都始終歸因於訪問者看到的最後一次體驗。 如前所述，訪問者所看到的每次體驗的訪問次數都會增加。 這會人為地降低在「 」下查看體驗時的每體驗轉換率[!UICONTROL 目標]&quot;維 [!DNL Adobe Analytics] 報告。
