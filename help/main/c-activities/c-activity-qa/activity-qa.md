---
keywords: qa;qa模式活動qa;qa url;qa urls；預覽url；預覽url;
description: 瞭解如何使用Adobe [!DNL Target] QA URL可執行簡單的端到端活動QA，其中預覽連結永不更改，可選的受眾目標，以及與即時活動資料保持分段的QA報告。
title: 如何進行QA活動？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1829'
ht-degree: 38%

---

# 活動 QA

在中使用QA URL [!DNL Adobe Target] 通過預覽連結執行輕鬆的端到端活動QA，這些連結永遠不會更改，可選的受眾目標，以及保留與即時活動資料分段的QA報告。

[!UICONTROL 活動QA] 讓您完全test [!DNL Target] 在啟動前進行活動。 的 [!UICONTROL 活動QA] 功能包括：

* 與團隊成員分享的連結，無論體驗或活動如何更新，這些連結皆不可能變更或需要重新產生. 此功能允許您在整個用戶行程中完全test活動。
* 可選擇是否考量對象狀況，這讓市場行銷人員測試鎖定目標條件或忽略鎖定目標條件，以 QA 體驗的外觀，而不必配合對象狀況。
* 擷取 QA 報表，讓市場行銷人員可以確認量度如預期增加，且 QA 報表資料和生產報表 (適用於非 A4T 報表) 分開。
* 能夠單獨預覽體驗或與滿足交付標準（頁面/目標請求/受眾）的其他即時活動一起預覽體驗。
* 能夠 QA 整個使用者旅程。您可以利用 QA 連結來存取一次您的網站，然後在活動 QA 期間瀏覽整個網站。您會停留在活動 QA 中直到結束工作階段，或直到您使用 [QA目標書籤](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 逼自己離開 [!UICONTROL 活動QA]。 如果活動跨越多個網頁，則此功能非常有用。

   >[!NOTE]
   >
   >對於版本2的at.js實現，此功能正確。*x* 或稍後。 為at.js 1。*x* 實現時，僅當訪問者的瀏覽器不阻止第三方cookie時，此功能才為真。

## 存取和共用 QA URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. 從活動 [!UICONTROL 概述] 的 **[!UICONTROL 活動QA]** 的子菜單。

   ![活動 QA 連結](assets/qa_link.png)

1. 完成下列設定:

   ![QA 連結設定選項](assets/qa_link_config.png)

   * **[!UICONTROL 匹配受眾規則以查看體驗]:** 有時，您想確認您的受眾匹配是否有效。 其它時候，您需要檢查活動的外觀和感覺。 如果此設定切換到「開啟」位置，測試者必須符合鎖定目標需求，才有資格看到體驗。對於「體驗鎖定目標 (XT)」活動，只會提供單一活動 URL。您看到的體驗取決於您是否符合其中一個鎖定目標規則。

      如果此設定切換到「關閉」位置，則按一下連結所顯示的體驗不在乎您是否符合資格。執行 QA 時，您可以在是否需要顧及對象鎖定目標之間來回切換。

   * **顯示所有其他活動的預設內容：** 如果此選項被切換到「開啟」位置，則顯示所有其他活動的預設內容。 例如，預覽是單獨顯示的，不考慮同一頁/[!DNL Target] 請求。

      如果此設定切換為「關閉」，請考量下列事項:

      * 如果您測試的活動與其他已上線的活動之間有衝突，則會套用[標準優先順序規則](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)。由於衝突，您可能看不到您打算進行QA的活動。
      * 已檢視的活動會增加量度，但僅限於 QA 報表環境中。

1. 按一下 **[!UICONTROL 「完成」]**&#x200B;以儲存變更。
1. 與組織成員共用活動連結URL以進行測試。

   活動連結永遠不會過期，如果有人更改了活動或體驗，則無需重新發送連結。 但是，如果您應用的受眾與 [!UICONTROL 受眾庫]，而不是簡單地編輯活動，將生成一個必須重新共用的新連結。

   每個活動連結URL（用於體驗A、體驗B等）允許您從相應的體驗開始用戶旅程。 按一下為體驗生成的URL，然後繼續正常的網站瀏覽以查看多頁上的體驗（如果存在多頁）。 即使體驗橫跨多個頁面 (範本測試或多頁測試)，每個體驗也只會產生一個 URL。

   您可以導航站點以查看其他頁，因為 [!UICONTROL 活動QA] 模式是粘滯的。 對於版本2的at.js實現，這種情況是正確的。*x* 或稍後。 為at.js 1。*x* 實現時，僅當訪問者的瀏覽器不阻止第三方cookie時，此情況才成立。

1. 要查看從活動連結URL生成的報告，請按一下活動的 **[!UICONTROL 報告]** 的 **[!UICONTROL 設定]** 表徵圖。  ![](assets/icon_gear.png) )，然後選擇 **[!UICONTROL QA模式通信]** 從 **[!UICONTROL 環境]** 的子菜單。

## 考量事項 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* 的 [!UICONTROL 活動QA] 連結顯示在 [!UICONTROL 概述] 所有活動類型的頁面，但 [!UICONTROL 自動目標] 和 [!UICONTROL Automated Personalization] （美聯社）
* [!UICONTROL 如果帳戶中有太多已儲存的活動，已儲存活動的活動 QA 預覽連結可能會無法載入。]重試預覽連結應該有效。 為防止此情況繼續發生，請存檔已保存且不再被主動使用的活動。
* [!UICONTROL 以 Analytics 作為報表來源 (A4T) 的活動皆有活動 QA URL。]使用執行QA時生成的命中數 [!UICONTROL 活動QA] 即使活動生效後，也會流到活動資料流所在的報告套件。
* [!UICONTROL 針對已封存的活動或超過結束日期的活動，活動 QA 不會顯示內容。]如果停用已結束的活動，則必須再次保存該活動 [!UICONTROL 活動QA] 工作。
* 導入到 [!DNL Target Standard/Premium] 從 [!DNL Target Classic]例如)不支援QA URL。
* 在 [!UICONTROL 自動分配] 和 [!UICONTROL Recommendations] 活動，模型不受中捕獲的訪問的影響 [!UICONTROL 活動QA]。
* [!UICONTROL 活動QA] 很粘。 瀏覽網站後 [!UICONTROL 活動QA]您 [!DNL Target] 會話必須過期，或者您必須 [!DNL Target] 釋放您 [!UICONTROL 活動QA] 才能像一個普通訪問者一樣查看您的站點。 使用 [目標QA書籤](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 逼自己離開 [!UICONTROL 活動QA]。

   您也可以在網站上以帶有空白值的 `at_preview_token` 參數 (例如，`https://www.mysite.com/?at_preview_token=`) 來載入頁面，以手動強迫自己離開。

* 如果在建立活動時指定了「URL is」 [基於表單的作曲家的改進](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) 或 [Visual Experience Composer中的頁面交付選項)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81),QA URL無效，因為 [!UICONTROL 活動QA] 附加URL參數。 若要解決此問題，請按一下 QA URL 前往您的網站，從 URL 中移除附加的參數，然後載入新的 URL。
* 如果你有at.js1 *x*。 [!UICONTROL 活動QA] 如果使用Safari或其他阻止第三方cookie的瀏覽器，則模式不會粘滯。 在這些情況下，必須將預覽參數添加到導航到的每個URL。 如果您已實施 [名稱](https://developer.adobe.com/target/before-implement/implement-cname-support-in-target/){target=_blank}。
* 如果活動使用多個體驗受眾（例如，同一活動中包含的美國和英國網站），則不會為四個組合（體驗A/US網站、體驗A/UK網站、體驗B/US網站、體驗B/UK網站）生成QA連結。 只會建立兩個 QA 連結 (體驗 A 和體驗 B)，使用者必須屬於適當的對象，才能看到頁面。英國QA人員無法查看美國網站。
* 所有 `at_preview` 參數和值皆已完成 URL 編碼。大多數時候，一切都按預期運行。 但是，有些客戶必須載入平衡器或Web伺服器，這些伺服器會嘗試重新編碼查詢字串參數。

   因為這種雙重編碼，當 [!DNL Target] 試圖破譯 `at_preview_token`。 [!DNL Target] 無法提取正確的標籤值，導致預覽無法工作。

   Adobe建議您與IT團隊進行交談，以確保允許列出所有預覽參數，以便不以任何方式轉換這些值。

   下表列出了可在域中列出的參數：

   | 參數 | 類型 | 值 | 說明 |
   |--- |--- |--- |--- |
   | `at_preview_token` | 加密的字串 | 強制；無預設值 | 包含可在QA模式下執行的市場活動ID清單的加密實體。 |
   | `at_preview_index` | 字串 | 空白 | 參數格式為 `<campaignIndex>` 或 `<campaignIndex>_< experienceIndex>`<br>兩個索引的開頭皆為 1。 |
   | `at_preview_listed_activities_only` | 布林值 (true/false) | 預設值: false | 若設為「true」，則 `at_preview_index` 參數中指定的所有促銷活動都會經過處理。<br>若設為「false」，即使預覽 Token 中未指定促銷活動，頁面的所有促銷活動都會經過處理。 |
   | `at_preview_evaluate_as_true_audience_ids` | 字串 | 空白 | 應始終（在目標和報告級別）在segmentId-s的範圍中以「true」計算的下划線分隔(&quot;_&quot;)清單 [!DNL Target] 請求。 |
   | `_AT_Debug` | 字串 | 視窗或主控台 | 主控台記錄或新視窗。 |
   | `adobe_mc_ref` |  |  | 將預設頁面的轉介 URL 傳給新頁面。與 `AppMeasurement.js` 2.1 版 (或更新版) 一起使用時，[!DNL Adobe Analytics] 會在新頁面上將此參數值當作轉介 URL。 |
   | `adobe_mc_sdid` |  |  | 通過 [!DNL Supplemental Data Id] (SDID)和 [!DNL Experience Cloud Org Id] 從預設頁面到新頁面。 通過這些ID允許 [!UICONTROL 目標分析] (A4T)將「縫合」 [!DNL Target] 在預設頁面上的請求 [!DNL Analytics] 請求。 |

* 的 [!UICONTROL 目標QA模式] UI僅顯示多頁活動中體驗的第一個URL。 假設您正在建立行程test，並從URL1移動到URL2。 不過，若要單獨前往 URL2，請複製根據 URL1 提供的所有 URL 參數，並在放置 &quot;?&quot; 後將其套用至 URL2，  就像您在 URL1 中看到的一樣。
* 如果帳戶中有太多已儲存的活動，已儲存活動的活動 QA 預覽連結可能會無法載入。重試預覽連結。封存已儲存的活動，這些活動不再主動用於防止此問題持續發生。

## Target JavaScript 程式庫 [!UICONTROL QA 模式]相容性 {#compatibility}

[!DNL Target] 支援以下JavaScript庫：

* [at.js 1.x](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)
* [at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)
* [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)

下表列出了各種活動類型，並指示 [!UICONTROL 活動QA] 每個庫支援模式：

| 活動類型 | at.js 1.x | at.js 2.x | 平台Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B 測試] | 是 | 是 | 是 |
| [!UICONTROL 自動分配] | 是 | 是 | 是 |
| [!UICONTROL 自動鎖定目標] | 無 | 無 | 無 |
| [!UICONTROL Automated Personalization] (AP) | 無 | 無 | 無 |
| [!UICONTROL 體驗鎖定] (XT) | 是 | 是 | 是 |
| [!UICONTROL 多變數測試] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |

## 預覽 URL {#preview}

可為所有用戶生成體驗預覽URL [!DNL Target] 活動類型。 預覽URL使您可以在活動開始前直接在站點上查看體驗內容，以便進行預覽和QA。 體驗預覽URL繞過目標以強制查看特定體驗。

有關預覽URL如何與 [!UICONTROL Automated Personalization] (AP)活動，請參閱 [使用體驗預覽URL預覽Automated Personalization活動](/help/main/c-activities/t-automated-personalization/experience-preview.md)。

訪問和共用活動的預覽URL **[!UICONTROL 概述]** 的 **[!UICONTROL 活動QA]** 的子菜單。

>[!NOTE]
>
>的 [!UICONTROL 活動QA] 連結和預覽URL對於除 [!DNL Target] AP活動。

下表列出了各種活動類型，並指示每個庫或API是否支援預覽URL功能：

| 活動類型 | at.js 1.x | at.js 2.x | 平台Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B 測試] | 是 | 是 | 是 |
| [!UICONTROL 自動分配] | 是 | 是 | 是 |
| [!UICONTROL 自動鎖定目標] | 是 | 是 | 是 |
| [!UICONTROL Automated Personalization] （美聯社） | 是 | 是 | 是 |
| [!UICONTROL 體驗鎖定] (XT) | 是 | 是 | 是 |
| [!UICONTROL 多變數測試] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |

