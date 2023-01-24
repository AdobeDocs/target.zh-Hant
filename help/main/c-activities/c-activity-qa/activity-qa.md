---
keywords: qa;qa模式；活動qa;qa url;qa url；預覽url；預覽url
description: 了解如何使用Adobe [!DNL Target] QA URL以執行簡易的端對端活動QA，具有永不變更的預覽連結、可選對象鎖定目標，以及與即時活動資料保持分段的QA報表。
title: 如何QA活動？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 33d85fcbfc971c188f4154cca5b4d21103b4dbb7
workflow-type: tm+mt
source-wordcount: '1881'
ht-degree: 36%

---

# 活動 QA

在中使用QA URL [!DNL Adobe Target] 執行簡易的端對端活動QA，具有永不變更的預覽連結、可選對象鎖定目標，以及與即時活動資料保持分段的QA報表。

[!UICONTROL 活動QA] 可讓您完全測試 [!DNL Target] 活動之後，再啟動它們為「使用中」。 此 [!UICONTROL 活動QA] 功能包括：

* 與團隊成員分享的連結，無論體驗或活動如何更新，這些連結皆不可能變更或需要重新產生. 此功能可讓您完整測試整個使用者歷程中的活動。
* 可選擇是否考量對象狀況，這讓市場行銷人員測試鎖定目標條件或忽略鎖定目標條件，以 QA 體驗的外觀，而不必配合對象狀況。
* 擷取 QA 報表，讓市場行銷人員可以確認量度如預期增加，且 QA 報表資料和生產報表 (適用於非 A4T 報表) 分開。
* 能夠單獨預覽體驗，或預覽符合傳送條件的其他已上線活動(頁面/[!DNL Target] 要求/對象)。
* 能夠 QA 整個使用者旅程。您可以利用 QA 連結來存取一次您的網站，然後在活動 QA 期間瀏覽整個網站。您會停留在活動 QA 中直到結束工作階段，或直到您使用 [QA Target書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 強迫自己離開 [!UICONTROL 活動QA]. 如果您的活動橫跨多個網頁，此功能就十分實用。

   >[!NOTE]
   >
   >若是使用第2版的at.js實作，則此功能即為正確。*x* 或更新版本。 針對at.js 1.*x* 實作中，只有在訪客的瀏覽器未封鎖第三方cookie時，此功能才成立。

## 存取和共用 QA URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. 從活動的 [!UICONTROL 概述] 頁面，按一下 **[!UICONTROL 活動QA]**.

   ![活動 QA 連結](assets/qa_link.png)

1. 完成下列設定:

   ![QA 連結設定選項](assets/qa_link_config.png)

   * **[!UICONTROL 比對對象規則以查看體驗]:** 有時候您會想要確認您的對象比對有效果。 其他時候，您想要檢查活動的外觀和風格。 如果此設定切換到「開啟」位置，測試者必須符合鎖定目標需求，才有資格看到體驗。對於「體驗鎖定目標 (XT)」活動，只會提供單一活動 URL。您看到的體驗取決於您是否符合其中一個鎖定目標規則。

      如果此設定切換到「關閉」位置，則按一下連結所顯示的體驗不在乎您是否符合資格。執行 QA 時，您可以在是否需要顧及對象鎖定目標之間來回切換。

   * **顯示所有其他活動的預設內容：** 如果此選項切換至「開啟」位置，則會顯示所有其他活動的預設內容。 例如，預覽會單獨顯示，而不考慮相同頁面/上的所有其他已上線活動[!DNL Target] 請求。

      如果此設定切換為「關閉」，請考量下列事項:

      * 如果您測試的活動與其他已上線的活動之間有衝突，則會套用[標準優先順序規則](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)。由於衝突，您可能看不到您打算QA的活動。
      * 已檢視的活動會增加量度，但僅限於 QA 報表環境中。

1. 按一下 **[!UICONTROL 「完成」]**&#x200B;以儲存變更。
1. 與組織成員共用活動連結URL以進行測試。

   活動連結永不過期，如果有人變更活動或體驗，您不需要重新傳送連結。 不過，如果您套用 [!UICONTROL 對象庫]，而非僅編輯活動，會產生您必須再次共用的新連結。

   每個活動連結URL（體驗A、體驗B等）都可讓您從對應的體驗開始使用者歷程。 按一下為體驗產生的URL，然後繼續一般的網站瀏覽，以查看多個頁面上的體驗（如果有多個頁面）。 即使體驗橫跨多個頁面 (範本測試或多頁測試)，每個體驗也只會產生一個 URL。

   您可以導覽網站以查看其他頁面，因為 [!UICONTROL 活動QA] 模式有黏性。 若是使用2版的at.js實作，即會發生此情況。*x* 或更新版本。 針對at.js 1.*x* 實作時，只有在訪客的瀏覽器未封鎖第三方cookie時，才會發生此情況。

1. 若要查看從活動連結URL產生的報表，請按一下活動的 **[!UICONTROL 報表]** 頁面，按一下 **[!UICONTROL 設定]** 圖示(  ![icon_gear影像](assets/icon_gear.png) )，然後選取 **[!UICONTROL QA模式流量]** 從 **[!UICONTROL 環境]** 下拉式清單。

## 考量事項 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* 此 [!UICONTROL 活動QA] 連結會顯示在 [!UICONTROL 概述] 除外的所有活動類型頁面 [!UICONTROL Automated Personalization] （美聯社）。

   >[!NOTE]
   >
   >[活動QA](/help/main/c-activities/c-activity-qa/activity-qa.md) AP活動目前可供測試版方案中的特定客戶使用。 在初始測試階段後，所有客戶都能使用此功能。

* [!UICONTROL 如果帳戶中有太多已儲存的活動，已儲存活動的活動 QA 預覽連結可能會無法載入。]重試預覽連結應可運作。 為避免此情況繼續發生，請封存已不再使用的已儲存活動。
* [!UICONTROL 活動QA] URL可搭配活動使用 [Analytics作為報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。 執行QA時產生的點擊，使用 [!UICONTROL 活動QA] 即使活動上線後，活動資料仍會流向相同的報表套裝。
* [!UICONTROL 針對已封存的活動或超過結束日期的活動，活動 QA 不會顯示內容。]如果您停用已結束的活動，則必須再次儲存活動 [!UICONTROL 活動QA] 工作。
* 匯入至的活動 [!DNL Target Standard/Premium] 從 [!DNL Target Classic]，例如)不支援QA URL。
* 在 [!UICONTROL 自動分配] 和 [!UICONTROL Recommendations] 活動，模型不會受中擷取的造訪影響 [!UICONTROL 活動QA].
* [!UICONTROL 活動QA] 有黏性。 在您瀏覽 [!UICONTROL 活動QA]，您的 [!DNL Target] 工作階段必須過期，否則您必須 [!DNL Target] 從 [!UICONTROL 活動QA] 才能像一般訪客一樣檢視您的網站。 使用 [Target QA書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 強迫自己離開 [!UICONTROL 活動QA].

   您也可以在網站上以帶有空白值的 `at_preview_token` 參數 (例如，`https://www.mysite.com/?at_preview_token=`) 來載入頁面，以手動強迫自己離開。

* 如果您在建立活動時指定「URL是」 [表單式撰寫器中的細分](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) 或 [可視化體驗撰寫器中的頁面傳送選項)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81),QA URL無法運作，因為 [!UICONTROL 活動QA] 附加URL參數。 若要解決此問題，請按一下 QA URL 前往您的網站，從 URL 中移除附加的參數，然後載入新的 URL。
* 如果您有at.js 1.*x*, [!UICONTROL 活動QA] 如果您使用Safari或其他封鎖第三方Cookie的瀏覽器，模式就不會有黏性。 在這些情況下，您必須將預覽參數新增至導覽至的每個URL。 如果您已實作，則情況相同 [CNAME](https://developer.adobe.com/target/before-implement/implement-cname-support-in-target/){target=_blank}.
* 如果活動使用多個體驗對象（例如，相同活動中包含的美國和英國網站），則這四個組合（體驗A/US網站、體驗A/UK網站、體驗B/US網站、體驗B/UK網站）不會產生QA連結。 只會建立兩個 QA 連結 (體驗 A 和體驗 B)，使用者必須屬於適當的對象，才能看到頁面。英國QA人員看不到美國網站。
* 所有 `at_preview` 參數和值皆已完成 URL 編碼。大多數時候，一切都如預期般運作。 不過，有些客戶必須執行負載平衡器或Web伺服器，才會嘗試將查詢字串參數重新編碼。

   因為編碼兩次， [!DNL Target] 試圖解碼 `at_preview_token`, [!DNL Target] 無法擷取正確的代號值，導致預覽無法運作。

   [!DNL Adobe] 建議您洽詢IT團隊，確定所有預覽參數皆允許列出，這樣這些值就不會以任何方式轉換。

   下表列出可在您的網域中允許列出的參數：

   | 參數 | 類型 | 值 | 說明 |
   |--- |--- |--- |--- |
   | `at_preview_token` | 加密的字串 | 強制；無預設值 | 加密實體，包含可在QA模式中執行的促銷活動ID清單。 |
   | `at_preview_index` | 字串 | 空白 | 參數格式為 `<campaignIndex>` 或 `<campaignIndex>_< experienceIndex>`<br>兩個索引的開頭皆為 1。 |
   | `at_preview_listed_activities_only` | 布林值 (true/false) | 預設值: false | 若設為「true」，則 `at_preview_index` 參數中指定的所有促銷活動都會經過處理。<br>若設為「false」，即使預覽 Token 中未指定促銷活動，頁面的所有促銷活動都會經過處理。 |
   | `at_preview_evaluate_as_true_audience_ids` | 字串 | 空白 | 區段ID的底線分隔(&quot;_&quot;)清單，在 [!DNL Target] 請求。 |
   | `_AT_Debug` | 字串 | 視窗或主控台 | 主控台記錄或新視窗。 |
   | `adobe_mc_ref` |  |  | 將預設頁面的轉介 URL 傳給新頁面。與 `AppMeasurement.js` 2.1 版 (或更新版) 一起使用時，[!DNL Adobe Analytics] 會在新頁面上將此參數值當作轉介 URL。 |
   | `adobe_mc_sdid` |  |  | 傳遞 [!DNL Supplemental Data Id] (SDID)及 [!DNL Experience Cloud Org Id] 從預設頁面移至新頁面。 允許傳遞這些ID [!UICONTROL Analytics for Target] (A4T)將 [!DNL Target] 在預設頁面上的請求 [!DNL Analytics] 請求。 |

* 此 [!UICONTROL 目標QA模式] UI只會顯示多頁活動中體驗的第一個URL。 假設您正在建立歷程測試，且從URL1移至URL2。 不過，若要單獨前往 URL2，請複製根據 URL1 提供的所有 URL 參數，並在放置 &quot;?&quot; 後將其套用至 URL2，  就像您在 URL1 中看到的一樣。
* 如果帳戶中有太多已儲存的活動，已儲存活動的活動 QA 預覽連結可能會無法載入。重試預覽連結。封存已儲存的活動，這些活動不再主動用於防止此問題持續發生。

## Target JavaScript 程式庫 [!UICONTROL QA 模式]相容性 {#compatibility}

[!DNL Target] 支援下列JavaScript程式庫：

* [at.js 1.x](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)
* [at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)
* [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)

下表列出各種活動類型，並指出 [!UICONTROL 活動QA] 每個程式庫皆支援模式：

| 活動類型 | at.js 1.x | at.js 2.x | 平台Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B 測試] | 是 | 是 | 是 |
| [!UICONTROL 自動分配] | 是 | 是 | 是 |
| [!UICONTROL 自動鎖定目標] | 無 | 無 | 無 |
| [!UICONTROL Automated Personalization] (AP) | 無 | 無 | 無 |
| [!UICONTROL 體驗鎖定] (XT) | 是 | 是 | 是 |
| [!UICONTROL 多變數測試] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |

>[!NOTE]
>
>[活動QA](/help/main/c-activities/c-activity-qa/activity-qa.md) AP活動目前可供測試版方案中的特定客戶使用。 在初始測試階段後，所有客戶都能使用此功能。

## 預覽 URL {#preview}

可針對所有項目產生體驗預覽URL [!DNL Target] 活動類型。 預覽URL可讓您在活動上線之前，直接在網站上查看體驗內容，以供預覽和QA之用。 體驗預覽URL會略過鎖定目標以強制檢視特定體驗。

如需預覽URL如何搭配運作的相關資訊 [!UICONTROL Automated Personalization] (AP)活動，請參閱 [使用體驗預覽URL預覽Automated Personalization活動](/help/main/c-activities/t-automated-personalization/experience-preview.md).

若要存取和共用預覽URL，請從活動的 **[!UICONTROL 概述]** 頁面，按一下 **[!UICONTROL 活動QA]** 連結。

>[!NOTE]
>
>此 [!UICONTROL 活動QA] 連結和預覽URL對於除了 [!DNL Target] AP活動。

下表列出各種活動類型，並指出每個程式庫或API是否支援預覽URL功能：

| 活動類型 | at.js 1.x | at.js 2.x | 平台Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B 測試] | 是 | 是 | 是 |
| [!UICONTROL 自動分配] | 是 | 是 | 是 |
| [!UICONTROL 自動鎖定目標] | 是 | 是 | 是 |
| [!UICONTROL Automated Personalization] (AP) | 是 | 是 | 是 |
| [!UICONTROL 體驗鎖定] (XT) | 是 | 是 | 是 |
| [!UICONTROL 多變數測試] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |

