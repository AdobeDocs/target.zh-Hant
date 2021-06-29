---
keywords: qa;qa模式；活動qa;qa url;qa url；預覽url；預覽url
description: 了解如何使用Adobe [!DNL Target] QA URL來執行簡易的端對端活動QA，同時具有永不變更的預覽連結、可選對象鎖定目標，以及與即時活動資料保持分段的QA報表。
title: 如何QA活動？
feature: 活動
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: ceb98a1f940bb4253aa75639b67f2277f25acbbd
workflow-type: tm+mt
source-wordcount: '1760'
ht-degree: 36%

---

# 活動 QA

在[!DNL Adobe Target]中使用QA URL，來執行簡易的端對端活動QA，同時具有永不變更的預覽連結、可選對象鎖定目標，以及與即時活動資料保持分段的QA報表。

[!UICONTROL 活動] QA可讓您在將活動上線啟動 [!DNL Target] 之前，完全測試活動。[!UICONTROL 活動QA]功能包括：

* 與團隊成員分享的連結，無論體驗或活動如何更新，這些連結皆不可能變更或需要重新產生. 此功能可讓您完整測試整個使用者歷程中的活動。
* 可選擇是否考量對象狀況，這讓市場行銷人員測試鎖定目標條件或忽略鎖定目標條件，以 QA 體驗的外觀，而不必配合對象狀況。
* 擷取 QA 報表，讓市場行銷人員可以確認量度如預期增加，且 QA 報表資料和生產報表 (適用於非 A4T 報表) 分開。
* 能夠單獨預覽體驗，或預覽其他滿足傳送條件（頁面/Target請求/對象）的已上線活動。
* 能夠 QA 整個使用者旅程。您可以利用 QA 連結來存取一次您的網站，然後在活動 QA 期間瀏覽整個網站。您會停留在活動 QA 中直到結束工作階段，或直到您使用  [QA Target書](/help/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 簽小程式強迫自己離開 [!UICONTROL 活動QA]。如果您的活動橫跨多個網頁，此功能就十分實用。

   >[!NOTE]
   >
   >若是使用第2版的at.js實作，則此功能即為正確。** x或更新版本。針對at.js 1.** ximplementations中，只有在訪客的瀏覽器未封鎖第三方Cookie時，此功能才成立。

## 存取和共用 QA URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. 從活動的[!UICONTROL 概述]頁面，按一下&#x200B;**[!UICONTROL 活動QA]**&#x200B;連結。

   ![活動 QA 連結](assets/qa_link.png)

1. 完成下列設定:

   ![QA 連結設定選項](assets/qa_link_config.png)

   * **[!UICONTROL 比對對象規則以查看體驗]:** 您有時需要確認對象比對有效果。其他時候，您想要檢查活動的外觀和風格。 如果此設定切換到「開啟」位置，測試者必須符合鎖定目標需求，才有資格看到體驗。對於「體驗鎖定目標 (XT)」活動，只會提供單一活動 URL。您看到的體驗取決於您是否符合其中一個鎖定目標規則。

      如果此設定切換到「關閉」位置，則按一下連結所顯示的體驗不在乎您是否符合資格。執行 QA 時，您可以在是否需要顧及對象鎖定目標之間來回切換。

   * **顯示所有其他活動的預設內容：** 如果此選項切換至「開啟」位置，則所有其他活動的預設內容都會顯示。例如，預覽會單獨顯示，而不考慮相同頁面/[!DNL Target]請求上的所有其他已上線活動。

      如果此設定切換為「關閉」，請考量下列事項:

      * 如果您測試的活動與其他已上線的活動之間有衝突，則會套用[標準優先順序規則](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)。由於衝突，您可能看不到您打算QA的活動。
      * 已檢視的活動會增加量度，但僅限於 QA 報表環境中。

1. 按一下 **[!UICONTROL 「完成」]**&#x200B;以儲存變更。
1. 與組織成員共用活動連結URL以進行測試。

   活動連結永不過期，如果有人變更活動或體驗，您不需要重新傳送連結。 不過，如果您套用與[!UICONTROL 對象庫]不同的對象，而非僅編輯活動，則會產生您必須重新共用的新連結。

   每個活動連結URL（體驗A、體驗B等）都可讓您從對應的體驗開始使用者歷程。 按一下為體驗產生的URL，然後繼續一般的網站瀏覽，以查看多個頁面上的體驗（如果有多個頁面）。 即使體驗橫跨多個頁面 (範本測試或多頁測試)，每個體驗也只會產生一個 URL。

   您可以導覽網站以查看其他頁面，因為[!UICONTROL 活動QA]模式有黏性。 若是使用2版的at.js實作，即會發生此情況。** x或更新版本。針對at.js 1.** ximplementations中，只有在訪客的瀏覽器未封鎖第三方Cookie時，才會出現此情況。

1. 若要查看從活動連結URL產生的報表，請按一下活動的&#x200B;**[!UICONTROL 報表]**&#x200B;頁面，按一下&#x200B;**[!UICONTROL 設定]**&#x200B;圖示(![](assets/icon_gear.png))，然後從&#x200B;**[!UICONTROL 環境]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL QA模式流量]**。

## 考量事項 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* [!UICONTROL 活動QA]連結顯示在除[!UICONTROL 自動鎖定目標]和[!UICONTROL Automated Personalization](AP)之外所有活動類型的[!UICONTROL 概述]頁面上。
* [!UICONTROL 如果帳戶中有太多已儲存的活動，已儲存活動的活動 QA 預覽連結可能會無法載入。]重試預覽連結應可運作。 為避免此情況繼續發生，請封存已不再使用的已儲存活動。
* [!UICONTROL 以 Analytics 作為報表來源 (A4T) 的活動皆有活動 QA URL。]使用[!UICONTROL 活動QA]執行QA時產生的點擊會流向相同的報表套裝，即使活動上線後，活動的資料也會在該報表套裝中流動。
* [!UICONTROL 針對已封存的活動或超過結束日期的活動，活動 QA 不會顯示內容。]如果您停用已結束的活動，您必須再次儲存活動，活動QA]才能運作。[!UICONTROL 
* 匯入至[!DNL Target Standard/Premium]（例如從[!DNL Target Classic]）的活動不支援QA URL。
* 在[!UICONTROL 自動分配]和[!UICONTROL Recommendations]活動中，模型不會受[!UICONTROL 活動QA]中擷取的造訪影響。
* [!UICONTROL 活] 動QA有黏性。在您在[!UICONTROL 活動QA]中瀏覽網站後，您的[!DNL Target]工作階段必須過期，或您必須讓[!DNL Target]從[!UICONTROL 活動QA]中釋放您，才能像一般訪客一樣檢視您的網站。 使用[Target QA書籤小程式](/help/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)強迫自己離開[!UICONTROL 活動QA]。

   您也可以在網站上以帶有空白值的 `at_preview_token` 參數 (例如，`https://www.mysite.com/?at_preview_token=`) 來載入頁面，以手動強迫自己離開。

* 如果您在建立活動[時指定「URL是」表單式撰寫器](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中的細分，或可視化體驗撰寫器中的[頁面傳送選項)](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)，則QA URL無法運作，因為[!UICONTROL 活動QA]會附加URL參數。 若要解決此問題，請按一下 QA URL 前往您的網站，從 URL 中移除附加的參數，然後載入新的 URL。
* 如果您有at.js 1.*x*，如 [!UICONTROL 果] 您使用Safari或其他封鎖第三方Cookie的瀏覽器，活動QA模式就不會有黏性。在這些情況下，您必須將預覽參數新增至導覽至的每個URL。 如果您已實作[CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md)，則情況相同。
* 如果活動使用多個體驗對象（例如，相同活動中包含的美國和英國網站），則這四個組合（體驗A/US網站、體驗A/UK網站、體驗B/US網站、體驗B/UK網站）不會產生QA連結。 只會建立兩個 QA 連結 (體驗 A 和體驗 B)，使用者必須屬於適當的對象，才能看到頁面。英國QA人員看不到美國網站。
* 所有 `at_preview` 參數和值皆已完成 URL 編碼。大多數時候，一切都如預期般運作。 不過，有些客戶必須執行負載平衡器或Web伺服器，才會嘗試將查詢字串參數重新編碼。

   由於編碼兩次，當[!DNL Target]嘗試將`at_preview_token`解碼時，[!DNL Target]無法擷取正確的Token值，導致預覽無法運作。

   Adobe建議您洽詢IT團隊，確定所有預覽參數皆允許列出，這樣這些值就不會以任何方式轉換。

   下表列出可在您的網域中允許列出的參數：

   | 參數 | 類型 | 值 | 說明 |
   |--- |--- |--- |--- |
   | `at_preview_token` | 加密的字串 | 強制；無預設值 | 加密實體，包含可在QA模式中執行的促銷活動ID清單。 |
   | `at_preview_index` | 字串 | 空白 | 參數格式為 `<campaignIndex>` 或 `<campaignIndex>_< experienceIndex>`<br>兩個索引的開頭皆為 1。 |
   | `at_preview_listed_activities_only` | 布林值 (true/false) | 預設值: false | 若設為「true」，則 `at_preview_index` 參數中指定的所有促銷活動都會經過處理。<br>若設為「false」，即使預覽 Token 中未指定促銷活動，頁面的所有促銷活動都會經過處理。 |
   | `at_preview_evaluate_as_true_audience_ids` | 字串 | 空白 | 在[!DNL Target]請求範圍內，應一律（在目標定位與報表層級）以底線分隔的segmentId-s清單(&quot;_&quot;)評估為「true」。 |
   | `_AT_Debug` | 字串 | 視窗或主控台 | 主控台記錄或新視窗。 |
   | `adobe_mc_ref` |  |  | 將預設頁面的轉介 URL 傳給新頁面。與 `AppMeasurement.js` 2.1 版 (或更新版) 一起使用時，[!DNL Adobe Analytics] 會在新頁面上將此參數值當作轉介 URL。 |
   | `adobe_mc_sdid` |  |  | 將[!DNL Supplemental Data Id](SDID)和[!DNL Experience Cloud Org Id]從預設頁面傳給新頁面。 傳遞這些ID可讓[!UICONTROL Analytics for Target](A4T)將預設頁面的[!DNL Target]要求與新頁面的[!DNL Analytics]要求「拼接」起來。 |

* [!UICONTROL Target QA模式] UI只會顯示多頁活動中體驗的第一個URL。 假設您正在建立歷程測試，且從URL1移至URL2。 不過，若要單獨前往 URL2，請複製根據 URL1 提供的所有 URL 參數，並在放置 &quot;?&quot; 後將其套用至 URL2，  就像您在 URL1 中看到的一樣。

## Target JavaScript程式庫[!UICONTROL QA模式]相容性 {#compatibility}

[!DNL Target] 支援下列JavaScript程式庫：

* [at.js 1.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)

下表列出各種活動類型，並指出每個程式庫是否支援[!UICONTROL 活動QA]模式：

| 活動類型 | at.js 1.x | at.js 2.x | 平台Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B 測試] | 是 | 是 | 是 |
| [!UICONTROL 自動分配] | 是 | 是 | 是 |
| [!UICONTROL 自動鎖定目標] | 無 | 無 | 無 |
| [!UICONTROL Automated Personalization] (AP) | 無 | 無 | 無 |
| [!UICONTROL 體驗鎖定] (XT) | 是 | 是 | 是 |
| [!UICONTROL 多變數測試] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |

## 預覽URL {#preview}

可針對所有[!DNL Target]活動類型產生體驗預覽URL。 預覽URL可讓您在活動上線之前，直接在網站上查看體驗內容，以供預覽和QA之用。 體驗預覽URL會略過鎖定目標以強制檢視特定體驗。

如需預覽URL如何搭配[!UICONTROL Automated Personalization](AP)活動運作的詳細資訊，請參閱[使用體驗預覽URL預覽Automated Personalization活動](/help/c-activities/t-automated-personalization/experience-preview.md)。

若要存取和共用預覽URL，請從活動的&#x200B;**[!UICONTROL 概述]**&#x200B;頁面，按一下&#x200B;**[!UICONTROL 活動QA]**&#x200B;連結。

>[!NOTE]
>
>[!UICONTROL 活動QA]連結和預覽URL對於[!DNL Target] AP活動以外的所有活動都相同。

下表列出各種活動類型，並指出每個程式庫或API是否支援預覽URL功能：

| 活動類型 | at.js 1.x | at.js 2.x | 平台Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B 測試] | 是 | 是 | 是 |
| [!UICONTROL 自動分配] | 是 | 是 | 是 |
| [!UICONTROL 自動鎖定目標] | 是 | 是 | 是 |
| [!UICONTROL Automated Personalization] （美聯社） | 是 | 是 | 是 |
| [!UICONTROL 體驗鎖定] (XT) | 是 | 是 | 是 |
| [!UICONTROL 多變數測試] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |

