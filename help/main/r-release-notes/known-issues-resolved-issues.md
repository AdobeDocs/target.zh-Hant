---
keywords: 已知問題;已解決問題;發行說明;錯誤;問題;修正
description: 尋找有關 Adobe Target 中已知問題的相關資訊，包括因應措施的資訊。問題解決後會被移到「已解決」區段。
title: 何處可以獲得有關 「已知問題」和「已解決問題」的資訊？
feature: Release Notes
exl-id: 6eb854f7-ed46-4673-afeb-0b44970598cd
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '4520'
ht-degree: 99%

---

# 已知問題和已解決問題

關於 [!DNL Adobe Target] 已知問題的資訊。也包括已解決問題的相關資訊。

>[!NOTE]
>
>括號內的問題編號僅供 Adobe 內部使用。

## 已知問題 {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

以下小節羅列 [!DNL Target] 的已知問題：

### 在使用表單式體驗撰寫器建立的活動中刪除擁有臨時選件的位置 {#ad-hoc}

如果在使用表單式體驗撰寫器建立的活動中有位置使用臨時選件 (在活動內建立的選件)，請避免刪除這些位置。 刪除位置可能會導致活動損毀。 [!DNL Target] 團隊正在努力解決這個問題。 暫行解決方法是從[!UICONTROL 選件資料庫]建立全域選件，並將這些選件用於位置，或是視需要建立新的體驗。 (KB-2014)

### 使用 A4T 自動分配活動的流量分佈 {#aa-a4t}

在某些情況下，使用 [!UICONTROL Analytics for Target] (A4T) 的[!UICONTROL 自動分配]活動的流量分佈，可能不同於根據每個體驗回報的轉換率所應該發生的情況。此問題常發生於回訪訪客流量比例高的活動。受影響的客戶將會收到受影響活動的通知。

在此問題解決之前，請對標準 [!DNL Target] 報告使用[!UICONTROL 自動分配]，或對 [!DNL Analytics] 報告使用標準 A/B 測試，作為[!UICONTROL 自動分配]與 [!DNL Analytics] 報告的替代方案。(TOP-131)

### Analytics for Adobe Target (A4T) 自動分配活動和自動鎖定目標活動的量度

[!DNL Target] UI 可讓使用者選擇不支援的參與和收入量度，作為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動中最佳化的主要目標量度。 支援轉換量度；&#x200B;*不*&#x200B;支援參與和收入量度。如果您選擇參與或收入目標量度，則最佳化模型不會建立。

如需支援和不支援的目標量度清單，請參閱[自動分配和自動鎖定目標活動的 A4T 支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。(TNT-38409)

### 增強體驗撰寫器 (EEC) 不支援 PUT 要求。

EEC 的問題使其目前無法支援 PUT 要求，並產生 504 逾時錯誤。(TGT-41493)

### [!DNL Adobe Experience Platform] 區段名稱不會顯示在[!UICONTROL 重要屬性]報告中。

[!DNL Adobe Experience Platform] 區段名稱不會顯示在 [!UICONTROL Automated Personalization] (AP) 和[!UICONTROL 自動鎖定目標] (AT) 活動的[!UICONTROL 重要屬性]報告中。(TOP-3813)

### 封存[!UICONTROL 自動鎖定目標]活動可能會導致同步問題發生

嘗試封存非作用中的[!UICONTROL 自動鎖定目標]活動可能會導致同步問題。在修正此問題之前，請勿封存[!UICONTROL 自動鎖定目標]活動。請把它們留在[!UICONTROL 非作用中]狀態。(TGT-40885)

### 重新導向選件 {#redirect}

* at.js 實作中的重新導向活動可能會造成預覽 URL 進入迴圈 (重複傳送選件)。您可以使用 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)，而不是執行預覽和 QA。此問題不會影響選件的實際傳送。(TGT-23019)

### 取消在視覺體驗撰寫器 (VEC) 中載入頁面 {#cancel}

* 在包含重新導向 URL 的 VEC 內取消載入 [!UICONTROL A/B 測試]或[!UICONTROL 體驗鎖定] (XT) 活動時，目前存在下列已知問題。

   在其中一個 VEC 引導式工作流程中，當您取消頁面載入時，VEC 中會顯示 [!UICONTROL 修改] 面板，並將重新導向至 URL 範本套用至體驗 (例如「體驗 B」)。當您繼續步驟二或步驟三然後回到步驟一時，會發生下列情況。

   根據預設，在「體驗 B」上，取消的網站載入範本隨即呈現，且可存取[!UICONTROL 修改]面板，但情況不應如此，因為此體驗已套用重新導向至 URL 範本。系統應顯示重新導向至 URL 範本。

   若要在 VEC 中顯示體驗的正確狀態：

   如果您切換至其他體驗，然後切換回「體驗 B」，[!DNL Target] 會顯示此體驗上已套用的重新導向至 URL 範本，且無法存取[!UICONTROL 修改]面板。(TGT-32138)

* 若為單頁應用程式 (SPA) 網站，取消載入不會允許您編輯[!UICONTROL 修改]面板下的動作。

### Recommendations

下列是 [!UICONTROL Recommendations] 活動的已知問題：

* 當 [!DNL Target] 傳回含 getOffer() 的 JSON 選件時，它會傳回 JSON 類型。然而，如果您傳回 JSON Recommendations 設計，則它會傳回 HTML 類型。
* 若 60 天內未經由動態消息或 API 收到更新，實體即會確實過期；不過，實體過期之後並未從編目搜尋索引中移除。(IRI-857)
* 條件與設計的「使用資訊」覆蓋圖無法反映其在 A/B 和體驗鎖定活動中的使用情況 (TGT-34331)
* A/B 和體驗鎖定活動中的 Recommendations 選件不會顯示 Recommendations 系統匣的視覺化預覽 (TGT-33426)
* 透過 API 建立的集合、排除、條件和設計不會顯示在 Target 使用者介面中，而且只能透過 API 編輯。同樣地，如果您在 Target UI 中建立任何這些項目，並稍後透過 API 加以編輯，這些變更不會反映在 Target UI 中。 透過 API 編輯的項目應繼續透過 API 編輯，以避免遺失任何修改。(TGT-35777)
* 透過 API 建立的 Recommendations 活動可在使用者介面中檢視，但只能透過 API 編輯。
* 條件清單 (卡片) 檢視中顯示的自訂條件摘要狀態每隔十分鐘會重新整理一次，但在少數情況下，可能會過時超過十分鐘。自訂條件編輯檢視中顯示的狀態會即時擷取，且隨時保持在最新狀態。(TGT-35896 和 TGT-36173)
* 標準和設計卡片無法顯示正在使用它們的活動的正確數目。 如果 A/B 活動中使用標準或設計，卡片可能會錯誤地顯示未使用設計或標準，即使活動中使用了設計或標準亦然。(TGT-36621 和 TGT-37217)

### 多變數測試 (MVT) 活動

在 MVT 活動中，在檢查量度時，表格和圖形中顯示的成功者不一致。如果用戶從「摘要」切換到「圖形視圖」，然後切換回「摘要視圖」，更改量度，然後切換到「圖形視圖」，就會發生這種情況。發生此問題時，摘要檢視一律會顯示正確的獲勝者。如果使用者從未在摘要檢視間切換圖表檢視，圖表便會檢視顯示正確的獲勝者。

### at.js {#atjs}

下列是 at.js 的已知問題:

* 將頁面載入視覺體驗撰寫器 (VEC) 時，Target 需要判斷全域 mbox 設定已啟用或已停用，以及 entityID 或 categoryID 是否出現在使用者嘗試在 VEC 中套用推薦的位置。條件清單會根據此資訊篩選。預設清單具有篩選演算法，但[相容核取方塊](/help/main/c-recommendations/t-create-recs-activity/algo-select-recs.md)可讓您檢視完整的演算法清單。

   使用 at.js 時，「相容性」核取方塊會隱藏，使您無法看見不相容的演算法。

   只有使用 VEC 的 Recommendations 活動會發生此問題。

   **因應措施**：在[!UICONTROL 「Recommendations > 設定」]中停用[!UICONTROL 「篩選不相容的條件」]選項。停用此設定之後，所有條件 (相容的與不相容的) 將顯示在條件選擇器中。(TGT-25949)

* 升級為 at.js 版本 1.0 之後，由於 at.js 與訪客 API 2.2.0 之間的互動，Microsoft Explorer 11 瀏覽器上不會觸發 mbox。此問題會影響 at.js 版本 0.9.6 和更新版本。(TNT-27600)
* at.js 可能無法與 Cordova/混合式應用程式搭配使用，因為它們目前不支援第一方 Cookie。(TNT-26166)

   **因應措施**：將 at.js 的「x-only」選項設為已啟用，並在呼叫中傳遞 `mboxThirdPartyId` 以管理使用者。

### 成功量度

將進階選項「計數將如何增加」設為「在每次曝光時」或「在每次曝光時 (不含頁面重新整理)」的成功量度，無法當作另一個量度所相依的成功量度使用。

當成功量度設為在每次曝光時遞增時，Target 會在每次訪客造訪此成功量度時便再次計入訪客。然後 Target 會將成功量度「會員資格」重設為 0，使得它可以在下一次曝光時再次計入。因此，如果其他量度要求先看見此量度，Target 永遠不會將該使用者識別為已看見第一個量度。

### Analytics for [!DNL Target] (A4T)

在 Analysis Workspace 中使用 Target 活動曝光和轉換時，請套用「相同接觸」 Attribution IQ 模型至量度，以確保計數準確。若要套用[非預設歸因模型](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)，請在量度上按一下滑鼠右鍵，以&#x200B;**修改欄設定 > 啟用使用非預設歸因模型 > 選擇相同接觸模型**&#x200B;。&#x200B;若未套用此模型，這些量度就會被誇大。

所有目前的 Analytics 套件都可以用 Attribution IQ 加入此模型。如果您沒有 Attribution IQ 存取權，請依賴「Reports &amp; Analytics」中的 A4T 資料。

### Target API

客戶無法透過 Adobe I/O 上的 v3 版本 A/B 活動 API，針對自動分配活動執行 CRUD 作業。

### 報告 - 可下載的 .csv 報告與 [!DNL Target] UI 中顯示的報告之間的資料不一致。 {#csv}

如果活動使用多個量度，則為下載所產生的 .csv 報告會不一致。可下載的報告僅是根據報告設定而產生，並會針對使用的任何其他量度考慮相同的值。

真相來源永遠是在 [!DNL Target] UI 中顯示的報告。

## 已解決問題 {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

上述已知問題解決後，它們會被移至下列章節。如有需要，會新增其他附註。

### at.js

* 如果您使用 at.js 2.1.1 或更舊版本在不進行任何修改的情況下建立體驗 (例如預設體驗)，該體驗可能不會計入報表、Analytics for Target (A4T)、Adobe Analytics 或 Google Analytics 中。此外，ttMeta 外掛程式可能會無法正常運作。

   若要解決此問題，可在體驗內容中使用空白字元。

   at.js 2.2.0 已修正此問題。請升級至 [at.js 最新版本](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)，或僅針對 2.2.0 之前的 at.js 版本使用上述因應措施。(TNT-33366)

* 使用 2.2.0 之前的 at.js 版本，如果頁面元素上沒有 [!DNL Adobe Analytics] 代碼 (例如按鈕)，點按追蹤不會報告 [!UICONTROL Analytics for Target] (A4T) 中的轉換。

   at.js 2.2.0 已針對此問題導入修正程式。如果您發生此問題，[請升級至 at.js 最新版本](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)。

### 地理目標定位

2020年5月10日，Adobe 更新了 GEO 提供者檔案，造成一些不一致。 例如，新增了一些包含逗號的值；不過，現有受眾中的值沒有逗號。並非所有 Adobe 傳送伺服器都受到此項變更的影響。因此，在 2020 年 5 月 10 日至 7 月 22 日之間使用這些值的受眾可能不符合所有正確訪客的資格。

### 複製 [!UICONTROL Recommendations] 活動

複製具有有效促銷活動的 [!UICONTROL Recommendations] 活動時，重複活動中的任何變更目前也會影響原始活動，反之亦然。(TGT-39155)

[!DNL Target Standard/Premium] 21.2.1 版本已修正此問題。

### Recommendations 活動的 QA 模式

如果活動中使用的標準是項目型或類別型，則已知問題會防止預覽。(TNT-37455)

此問題已在 2022 年 1 月中修正。(TNT-37455)

### 頁面傳送 {#page-delivery}

如果您新增範本規則，例如[頁面傳送](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md)的 URL 內含有 (/checkout, /cart)，規則的開頭會加上額外的空格。這些額外的空格是修飾性的，不影響受眾定義的建立與選件傳送。(TGT-35920)

### 顯示「處理」標籤的影像選件

「選件」頁面上的影像選件有時會在影像上傳後數小時內保留「處理」標籤。在大多數情況下，這是僅標籤的問題：影像選件仍可用於活動中並加以傳送。(MCUI-10264、TGT-37458)

此問題已在 Target Standard/Premium 20.10.1 版中修正。

### Analytics for Adobe Target (A4T) 報告

下列與 A4T 相關的問題已解決：

* 對使用 [!DNL Analytics] 目標量度的 A4T 活動造成影響的問題，會造成 A4T 報告顯示未預期的流量分割或人為誇大的轉換。

   此問題會影響下列條件下的 A4T 報告：

   * 活動是在 2020 年 9 月 15 日到 11 月 5 日 (太平洋標準時間上午 4 點) 之間建立或儲存的，並且
   * 活動已選擇 [!DNL Analytics] 量度作為目標量度。

   [!DNL Target] 在此期間正確分割流量。但是，比方說，活動設定中的 50/50 分割可能在 A4T 報告中可能會顯示為 90/10 分割。

   對於受影響的活動，在 11 月 5 日 (太平洋標準時間上午 4 點) 之後首次瀏覽活動的訪客可看到正確的流量分割。在此期間之後建立或儲存的新活動會正確報告流量分割。

* 對使用 [!DNL Target] 目標量度的 A4T 活動造成影響的問題，會造成 A4T 報告顯示低轉換或無轉換。

   >[!NOTE]
   >
   >此問題僅影響 A4T 報告。它不會影響活動傳送。

   此問題會影響下列條件下的 A4T 報告：

   * A4T 活動在 2020 年 9 月 22 日到 11 月 11 日 (太平洋標準時間下午 2 點 30 分) 之間處於運轉狀態，並且
   * 該活動已選擇 [!DNL Target] 量度作為目標量度，並且
   * 當訪客點擊活動的目標事件 (例如[!UICONTROL 按一下元素]) 時，也會有符合轉換事件的低優先順序的非 A4T 活動。如果非 A4T 活動的設定了與 A4T量度活動相同的量度，或是如果設定了「任何 mbox」量度，就有可能發生此情況。

   此問題影響了 2020 年 9 月 22 日到 11 月 11 日 (太平洋標準時間下午 2 點 30 分) 之間的即時 A4T 活動報告。受影響的 A4T 活動的報告會顯示此日期範圍外的正確轉換。非 A4T 活動報告未受影響。

如果您有其他問題，請洽詢客戶成功經理 (CSM) 或 [Adobe 客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。(CSO 20201110016)

### 自動鎖定目標報告 {#at-metrics}

對從 9 月 15 日下午 2:30 開始影響 [!DNL Adobe Target Premium] 使用者的[!UICONTROL 自動鎖定目標]報告的問題已解決。檢視受影響的轉換量度 (使用「[!UICONTROL 已檢視頁面]」或「[!UICONTROL 已點按 mbox]」選項設定) 的報告時，轉換率報告不正確。目前沒有已知的傳送問題。

若要重新同步並更正報告，請執行以下操作：

1. 複製並儲存受影響的[!UICONTROL 自動鎖定目標]活動。
1. 啟動新儲存的活動 (如果受影響的活動是即時的)。
1. 刪除原始 (受影響) 的活動。

(TGT-38522、CSO 20201006007)

### 報表 {#conversions-audiences}

目前，轉換的增加會根據使用的受眾而有所不同。

例如，對於相同的訪客，如果轉換計數設定為「每個參與者增加一次」：

* 受眾：造訪層級轉換的「所有合格訪客」只會增加一次。這是預期行為。
* 受眾：造訪層級轉換的「新訪客」每次都會錯誤地增加一次，而不是只增加一次。這不是預期行為。

如果轉換計數設為「每次曝光」都會增加：

* 受眾：造訪層級轉換的「新訪客」只錯誤地增加一次，而不是每次都增加。這不是預期行為。
* 受眾：造訪層級轉換的「新訪客」每次都增加一次。這是預期行為。

請注意，此問題僅與 [!DNL Target]報告有關。使用 [!UICONTROL Analytics for Target (A4T)] 報告時，這並不是問題。

此問題已解決。

### 使用 Google Chrome 80+ 版時，未在視覺體驗撰寫器 (VEC) 或增強體驗撰寫器 (EEC) 中載入的頁面

此已知問題與 Google 從 Chrome 80 版開始將 Cookie 預設行為變更為不使用 SameSite 屬性的決定相關。在此變更前，Chrome 將不含 SameSite 屬性的所有 Cookie 預設為「SameSite=None」，現在則預設為「SameSite=Lax」，這會變更 Cookie 在 GET 和 POST 請求時的傳送方式。請參閱 [SameSite 更新](https://www.chromium.org/updates/same-site)。

如需詳細資訊和修正，請參閱[排解視覺體驗撰寫器和增強體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)中的「最近宣佈的 Google Chrome SameSite Cookie 實施政策如何影響 VEC 和 EEC？」。

### 使用自訂體驗作為控制時，自動鎖定目標活動的圖表報表無法呈現

如果所有體驗中都沒有資料 (0 次造訪)，自動鎖定目標活動的圖表報表無法在「差別」模式 (平均提升度和每日提升度) 中呈現。如果控制體驗設為自訂，在活動初期期間可能會發生這種情況。此功能在其他模式 (執行中的平均值控制和已鎖定目標、每日控制和已鎖定目標，以及瀏覽次數) 中可正常運作。只要有一些資料 (非零次造訪)，報表就會如預期般呈現。

Target 19.7.1 版本已修正此問題。

### 實作：全域 Mbox 自動建立

在「實作」標籤 ([!UICONTROL 「管理」 > 「實作」]) 上，新佈建的租用戶的「[!UICONTROL 全域 Mbox 自動建立]」欄位預設為「false」。

佈建後第一次下載 at.js 時，所下載的 at.js 檔案和 [!DNL Target] 後端中的「[!UICONTROL 全域 Mbox 自動建立]」欄位會設為 &quot;true&quot;，但它會在 UI 的「[!UICONTROL 實作]」頁面上繼續顯示為 &quot;false&quot;，直到頁面重新整理為止 (重新整理頁面之後，狀態將會是 &quot;true&quot;)。

針對新佈建的租用戶下載的 at.js 將具有 `global_mbox_autocreate = false`。如果先下載了 mbox.js (現已被取代)，global\_mbox\_autocreate 會設為 &quot;true&quot;，而下載的 at.js 也將具有 `global_mbox_autocreate = true`。(TGT-15929)

### [!DNL Target] API 中的企業權限支援 {#api}

如果使用 GET API 提取選件清單，預設工作區中可能會顯示從選件資料庫中的 Target UI 建立的代碼選件。此問題將會在 2019 年 3 月的第一週修正。此修正就緒後，從 API 進行提取時，系統會在適當的工作區中顯示代碼選件。此問題&#x200B;*不會*&#x200B;影響從 API 建立的選件。例如，無論是透過 GET API 或從 Target UI 中擷取，從 API 建立的代碼選件都會顯示在其建立的工作區中。

### 報告與極端訂單

從 2019 年 11 月 25 日到 2020 年 4 月 26 日，一個 Target 伺服器遇到問題，導致極端訂單值計入收入型報告量度 (AOV、RPV)。從 2019 年 12 月 19 日到 2020 年 4 月 23 日，另一台伺服器遇到了相同問題。此問題並未影響所有 Target 伺服器或所有 Target 客戶。

如果符合下列條件，則您&#x200B;*沒有*&#x200B;受到影響：

* 您的 Target 實作使用不同的伺服器。
* 您的報告未排除極端訂單。
* 您使用了轉換量度來測量活動。
* 您的 Target 活動使用 Analytics for Target (A4T)。
* 您位於亞太地區。

若要判斷此問題是否影響 Target 報告，請聯絡 [Client Care](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。

### Recommendations

* 當摘要中的項目與前次執行相同時，Recommendations 摘要索引會顯示「等候索引」。傳送所需的產品擷取不受影響。(RECS-6663)

   Target 19.4.2 版本已修正此問題。

* Recommendations 摘要耗費較預期更長的時間。(COR-2836)

   在 Target 16.10.1 版本中修正。

* Recommendation 摘要 UI 未顯示索引的正確狀態。後端工作運作正確，但 UI 無法擷取和顯示目前的狀態。

   17.10.1 版已修正此問題。

### 重新導向選件

您的頁面上的競爭條件可能造成將原始頁面和重新導向頁面上的頁面檢視計入。計劃對 at.js 實作進行更新，以確保可以避免此競爭條件。

at.js 1.6.3 已修正此問題。

### 排除群組

* 在建立排除群組之後套用自動去除重複時，UI 中活動圖上的計數可能不正確。
* 編輯具有排除群組的現有活動時，手動包含可能不會在 UI 中正確反映。

這些問題已解決。

### Target API

Adobe I/O 上的 v1 版本選件 API 會將所有透過 Target 建立的選件視為在預設工作區中。(TTTEAM-41957)

此問題已解決。

### at.js {#at-js-2}

升級為 at.js 版本 1.0 之後，由於 at.js 與訪客 API 2.2.0 之間的互動，Microsoft Explorer 11 瀏覽器上不會觸發 mbox。此問題會影響 at.js 版本 0.9.6 和更新版本。(TNT-27600)

已在 API 2.3.0 或更新版本中修正。

### 地理定位

目前建立地理定位受眾時，無法搜尋內含特殊字元 (如空格或逗號) 的字串。舉例來說，根據城市、州、國家/地區等建立受眾時，就會發生這個問題。例如，搜尋「new york」時，搜尋不會傳回有效的結果。

已在 2018 年 11 月修正。

### at.js {#at-js-3}

使用 at.js 1.6.0 版時，Analytics for Target (A4T) 會重新導向，但不具活動資格。

已在 at.js 1.6.2 版修正。

### 活動、工作區及刪除活動 API

透過 API 刪除的預設工作區活動，會顯示於 Target UI 中。請改為使用 Target UI 刪除預設工作區的所有活動。(TGT-31315)

已在 2018 年 10 月 25 日修正

### Automated Personalization (AP) 選件層級報表

按一下 Automated Personalization (AP) 活動報表的已鎖定目標體驗，查看選件層級報表時，目前會看到空白結果、錯誤訊息或載入中圖示。(TNT-30695)

已在 2018 年 9 月 27 日修正。

### 代碼編輯器

如果在 Firefox 和 Internet Explorer 使用代碼編輯器時，在三步驟引導式工作流程的步驟 1 重新載入 VEC，「修改」標籤會無法正確顯示，但 VEC 功能不受影響。(TGT-28730)

18.9.1 版已修正此問題。

### 使用「屬性升級」規則的 Recommendations 活動

編輯或複製使用「屬性促銷活動」規則的 Recommendations 活動時，在按一下「儲存」時顯示「有缺少的欄位」錯誤。

在 17.8.1 版本中已獲修正。

### 備份 Recommendations

備用 Recommendations 錯誤地在 Target UI「最近查看的項目」卡上顯示「已啟用」。(TGT-29308)

18.4.1 版已修正此問題，能順利顯示「已停用」。

### 自動鎖定目標活動和報表受眾

當自動鎖定目標活動中使用的報表受眾名稱已變更時，Target 對該活動的進一步更新可能會失敗，並顯示錯誤訊息。

Target 18.5.1 (2018 年 5 月 22 日) 版本已修正此問題。

### at.js {#at-js-4}

用於擷取儲存 Cookie 時應該使用的上層網域的演算法在 at.js 版本 0.9.6 中已變更。因為此變更，無法將 Cookie 儲存至使用 IP 的位址。大部分時候，IP 位址是用於測試用途，但做為解決辦法，您可以使用 DNS 項目調整本機機器上的主機檔案，或是使用 targetGlobalSettings() at.js 函數來插入程式碼片段以支援 IP 位址。

此問題已在 at.js 版本 1.2 中修復。

### [!DNL Target] Premium 的企業使用者權限

隨著企業權限移轉，所有 Target Premium 使用者管理已從 Adobe Target UI 移至 Adobe Admin Console。

移轉後，請注意兩個可能問題：

* 非管理員使用者會收到電子郵件，指出他們現在可存取 Adobe Target。這表示您的組織移轉已完成。可以忽略電子郵件本身。
* 在移轉之後，Adobe Admin Console 中出重新出現一些先前已停用使用者的報表。如果 Adobe Admin Console 中已停用的使用者在移轉之前仍出現在您的 Target 使用者清單，這可能是組織的問題。建議管理員在 Admin Console 中檢閱使用者的清單以驗證存取權。

此問題已在 2017 年 8 月 30 日修正

### 活動建立

17.6.2 版本的問題可能已影響在 2017 年 6 月 22 日與 2017 年 6 月 29 日之間建立和/或更新的活動。具有下列情況的活動會受到影響：

* 在體驗鎖定目標 (XT) 中重新排列的任何體驗會還原為原始的順序
* 活動本機的任何區段規則 (未儲存在受眾內) 會遺失，包括結合的受眾、位置細分和任何規則成功度量。

其他活動未受影響。

**重要**：此問題未自動修正。您必須重新儲存受影響的任何活動，以修正此問題。

此問題已在 2017 年 6 月 29 日修正

### 表單式體驗撰寫器

目前已回報下列使用表單式體驗撰寫器時的已知問題：

* 如果您使用表單式體驗撰寫器搭配自動建立的全域 mbox 以外的 mbox (target-global-mbox)，然後選擇參與量度做為成功量度，則量度只會在活動中使用了該 mbox 的頁面上遞增。做為範例，如果您的 mbox 為 homepage\_mbox，每次造訪帶來的頁面量度為在該造訪期間對 homepage\_mbox 的點擊數。(TGT-22789)
* 當您在程序的步驟 1 期間使用表單式體驗撰寫器時，刪除體驗鎖定目標 (XT) 活動中的體驗，會擲出 JavaScript 例外。(TGT-24366)

第一個問題已在 Target 17.3.1 版本 (2017 年 3 月) 中修正。

第二個問題已在 Target 17.6.1 版本 (2017 年 6 月) 中修正。

### at.js {#at-js-5}

自從 Target 17.4.1 版本 (2017 年 4 月 27日) 以來，使用視覺體驗撰寫器 (VEC) 中的「插入影像」動作會造成使用 at.js 程式庫時無法傳遞選件內容。

已對 2017 年 5 月 22 日發行的 at.js 版本 0.9.7 進行此問題的修正。

### 報表：A/B 和體驗鎖定 (XT) 活動

在 4 月 27 日下午 9:00 PST 與 5 月 5 日上午 6:00 PST 之間，使用「已檢視頁面」轉換動作 (未基於其他度量) 建立或編輯、具有度量的 A/B 和 XT 活動，可能會有不正確記錄的轉換。此問題現在已解決；不過，在影響期間對這些活動「已檢視頁面」轉換動作的相關報表可能不準確，並且不幸地，無法更正。針對這些活動基於「已檢視頁面」轉換動作的任何決策，建議您僅仰賴於影響期間之前或之後記錄的資料。

仍可以使用其他度量的報表資料，因為它們不受影響。

已在 Target 17.4.3 hotfix 中修正。

### 選件：A/B 和體驗鎖定 (XT) 活動

在具有至少兩個體驗並且是使用表單式體驗撰寫器在 4 月 29 日 (太平洋時間下午 9:00) 與 5 月 1 日星期一 (太平洋時間下午 9:15) 之間建立或編輯的 A/B 和 XT 活動中選件的傳遞和預覽受到影響。僅顯示具有預設內容的選件。

已在 Target 17.4.3 hotfix 中修正。

### at.js {#at-js-6}

下列動作造成在使用視覺體驗撰寫器 (VEC) 和 at.js 時未傳遞選件：移動並重新排列。

已對 at.js 版本 0.9.6 進行此問題的修正。

### 報表

包括在 Target 17.3.1 版本 (2017 年 3 月 30 日) 的在報表中檢視多個度量的功能，已由於未預期的行為而移除。此功能將在即將發行的版本中再次提供。

能夠在報表中檢視多個度量的功能過去包括在 Target 17.4.1 版本 (2017 年 4 月 27 日) 中。

### 選件

從「影像選件」資料庫 (「選件 > 影像選件」) 中刪除的影像，仍顯示在 UI 中。在未來版本中，這些已刪除的影像將不再顯示。同時，刪除的影像會顯示在 UI 中，但是會具有已刪除的狀態。(TGT-23793)

在 Target 17.4.1 版本中修正 (2017 年 4 月 27 日)。

### 重新導向選件

針對「最近查看的」條件，如果未在 mbox 要求中傳遞 entity.id 參數，基於動態規則的實體將導致無建議。(RECS-6241)

此問題在 Recommendations 版本 (2018 年 3 月 22 日) 之後已修正。在 Recommendations 版本之後，如果未在 mbox 要求中傳遞 entity.id，Target 會略過實體型動態規則。

### at.js {#at-js-7}

當使用者嘗試在更新 at.js 設定之後從「實作」詳細資料頁面下載 at.js 時，會下載 而非 at.js。(TGT-23069)

在 Target 17.3.1 版本 (2017 年 3 月 30 日) 中修正。

### 全域排除規則

全域排除規則耗費 10-20 分鐘來填入至 Premium Recommendations 的 Edge。(RECS-5270)

在 Recommendations 17.2.2.0 版本 (2017 年 3 月 6 日) 中修正。

### Analytics for Adobe Target (A4T) 報告

切換報表量度時，報表並未更新。 此問題僅影響 UI。對於報表資料收集或傳送沒有影響。(TGT-22970)

在 Target 17.2.2.0 版本 (2017 年 2 月 24 日) 中修正。

### CSV 報表

下載的報表未採用排除極端訂單設定。(TGT-21871)

在 Target 17.2.1.0 版本中修正。
