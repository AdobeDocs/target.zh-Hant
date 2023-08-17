---
keywords: qa；qa模式；活動qa；qa url；qa url；預覽url；預覽url
description: 瞭解如何使用Adobe [!DNL Target] QA URL來執行簡單的端對端活動QA，具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的QA報表。
title: 如何QA活動？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 87cfc86bdabeb87424d2cf9fff7754dd85f7ac0b
workflow-type: tm+mt
source-wordcount: '1767'
ht-degree: 35%

---

# 活動 QA

在中使用品質保證URL [!DNL Adobe Target] 透過永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的QA報表，輕鬆執行端對端活動QA。

[!UICONTROL 活動問答] 可讓您完全測試 [!DNL Target] 活動之前，請將其啟動為上線。 此 [!UICONTROL 活動問答] 功能包括：

* 與團隊成員分享的連結，無論體驗或活動如何更新，這些連結皆不可能變更或需要重新產生. 此功能可讓您完整測試整個使用者歷程中的活動。
* 可選擇是否考量對象狀況，這讓市場行銷人員測試鎖定目標條件或忽略鎖定目標條件，以 QA 體驗的外觀，而不必配合對象狀況。
* 擷取 QA 報表，讓市場行銷人員可以確認量度如預期增加，且 QA 報表資料和生產報表 (適用於非 A4T 報表) 分開。
* 能夠單獨預覽體驗，或搭配其他滿足傳送條件(頁面/[!DNL Target] 請求/對象)。
* 能夠 QA 整個使用者旅程。您可以利用 QA 連結來存取一次您的網站，然後在活動 QA 期間瀏覽整個網站。您會停留在活動 QA 中直到結束工作階段，或直到您使用 [QA Target書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 強迫自己離開 [!UICONTROL 活動問答]. 如果您的活動橫跨多個網頁，則此功能相當實用。

  >[!NOTE]
  >
  >此功能適用於版本2的at.js實作。*x* 或更新版本。 適用於at.js 1.*x* 實作中，只有在訪客的瀏覽器不會封鎖第三方Cookie時，才能使用此功能。

## 存取和共用 QA URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. 從活動的 [!UICONTROL 概觀] 頁面，按一下 **[!UICONTROL 活動問答]**.

   ![活動 QA 連結](assets/qa_link.png)

1. 完成下列設定:

   ![QA 連結設定選項](assets/qa_link_config.png)

   * **[!UICONTROL 匹配對象規則以檢視體驗]：** 有時您會想要確認對象比對有效果。 其他時候，您會想要檢查活動的外觀與風格。 如果此設定切換到「開啟」位置，測試者必須符合鎖定目標需求，才有資格看到體驗。對於「體驗鎖定目標 (XT)」活動，只會提供單一活動 URL。您看到的體驗取決於您是否符合其中一個鎖定目標規則。

     如果此設定切換到「關閉」位置，則按一下連結所顯示的體驗不在乎您是否符合資格。執行 QA 時，您可以在是否需要顧及對象鎖定目標之間來回切換。

   * **顯示所有其他活動的預設內容：** 如果此選項切換到「開啟」位置，則所有其他活動皆會顯示預設內容。 例如，單獨顯示預覽，而不考慮同一頁面上的所有其他已上線活動/[!DNL Target] 要求。

     如果此設定切換為「關閉」，請考量下列事項:

      * 如果您測試的活動與其他已上線的活動之間有衝突，則會套用[標準優先順序規則](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)。由於發生衝突，您可能無法看見您想要進行QA的活動。
      * 已檢視的活動會增加量度，但僅限於 QA 報表環境中。

1. 按一下 **[!UICONTROL 「完成」]**&#x200B;以儲存變更。
1. 與您的組織成員共用活動連結URL以進行測試。

   活動連結永不過期，如果有人變更活動或體驗，您就不需要重新傳送連結。 不過，如果您套用的對象與 [!UICONTROL 對象庫]，而不只是編輯活動，新連結會產生，您必須再次共用。

   每個活動連結URL （適用於體驗A、體驗B等）可讓您從對應的體驗開始使用者旅程。 按一下為體驗產生的URL，然後繼續一般的網站瀏覽，以在多個頁面上檢視體驗（如果存在多個頁面）。 即使體驗橫跨多個頁面 (範本測試或多頁測試)，每個體驗也只會產生一個 URL。

   您可以瀏覽網站以檢視其他頁面，因為 [!UICONTROL 活動問答] 模式為粘性。 此情況適用於版本2的at.js實作。*x* 或更新版本。 適用於at.js 1.*x* 實作時，只有在訪客的瀏覽器不會封鎖第三方Cookie時，才會發生這種情況。

1. 若要檢視從活動連結URL產生的報表，請按一下活動的 **[!UICONTROL 報表]** 頁面，按一下 **[!UICONTROL 設定]** 圖示(  ![icon_gear圖片](assets/icon_gear.png) )，然後選取 **[!UICONTROL QA模式流量]** 從 **[!UICONTROL 環境]** 下拉式清單。

## 從QA模式中釋出自己

[!UICONTROL 活動問答] 有粘性。 在中瀏覽網站之後 [!UICONTROL 活動問答]，您的 [!DNL Target] 工作階段必須過期，或您必須擁有 [!DNL Target] 從以下位置釋出您 [!UICONTROL 活動問答] 之後才能像一般訪客一樣檢視您的網站。

* **at.js 2.*x***：如果您的網站有at.js 2.*x* 已部署，請使用 [Target QA書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 強迫自己離開 [!UICONTROL 活動問答]. 在網站上載入具有空白值的頁面時（如下一個專案符號所述），就會執行 *非* 在at.js 2.*x* 已部署。

* **at.js 1.*x***：如果您的網站有at.js 1.*x* 已部署，除了使用 [Target QA書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)，您也可以手動強迫自己離開，方法是在網站上載入頁面，使用 `at_preview_token` 具有空值的引數。 例如，

  `https://www.mysite.com/?at_preview_token=`

* **[!DNL Adobe Experience Platform Web SDK]**：如果您的網站有 [[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} 已部署，您可以在網站上以手動方式強制離開 `at_qa_mode` 具有空值的引數。 例如，

  `https://www.mysite.com/?at_qa_mode=`

## 考量事項 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* 因為活動QA現在可供所有人使用 [!DNL Target] 活動型別後，「使用體驗預覽URL預覽Automated Personalization活動」功能便不再需要。
* [!UICONTROL 如果帳戶中有太多已儲存的活動，已儲存活動的活動 QA 預覽連結可能會無法載入。]重試預覽連結應該有效。 為避免繼續發生此情況，請封存不再主動使用的已儲存活動。
* [!UICONTROL 活動問答] URL可用於包含下列專案的活動： [Analytics作為報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。 使用執行QA時產生的點選 [!UICONTROL 活動問答] 流向活動的資料流動所在的相同報表套裝，即使活動已上線。
* [!UICONTROL 針對已封存的活動或超過結束日期的活動，活動 QA 不會顯示內容。]如果您停用已結束的活動，則必須再次儲存活動的目的 [!UICONTROL 活動問答] 才能運作。
* 活動已匯入至 [!DNL Target Standard/Premium] (從 [!DNL Target Classic]例如)不支援QA URL。
* 在 [!UICONTROL 自動分配] 和 [!UICONTROL Recommendations] 活動，則模型不會受到中擷取的造訪影響 [!UICONTROL 活動問答].
* 如果您在建立活動時指定「URL是」 [表單式撰寫器中的細分](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) 或 [視覺化體驗撰寫器中的頁面傳送選項)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)，QA URL無法運作，因為 [!UICONTROL 活動問答] 附加URL引數。 若要解決此問題，請按一下 QA URL 前往您的網站，從 URL 中移除附加的參數，然後載入新的 URL。
* 如果您有at.js 1.*x*， [!UICONTROL 活動問答] 如果您使用Safari或其他封鎖第三方Cookie的瀏覽器，模式不會產生粘性。 在這些情況下，您必須將預覽引數新增至您導覽到的每個URL。 如果您已實作，情況也會相同 [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}.
* 如果活動使用多個體驗對象（例如，相同活動中包含的US和UK網站），則這四個組合（體驗A/US網站、體驗A/UK網站、體驗B/US網站、體驗B/UK網站）不會產生QA連結。 只會建立兩個 QA 連結 (體驗 A 和體驗 B)，使用者必須屬於適當的對象，才能看到頁面。英國QA人員看不到美國網站。
* 所有 `at_preview` 參數和值皆已完成 URL 編碼。大部分時間，一切都如預期般運作。 但是，有些客戶必須載入平衡器或Web伺服器，以嘗試再次將查詢字串引數編碼。

  因為這會編碼兩次，當 [!DNL Target] 嘗試解碼 `at_preview_token`， [!DNL Target] 無法擷取正確的Token值，導致預覽無法正常運作。

  [!DNL Adobe] 建議您洽詢IT團隊，確定所有預覽引數皆已加入允許清單，因此這些值絕不會轉換。

  下表列出可在您的網域中列入允許清單的引數：

  | 參數 | 類型 | 值 | 說明 |
  |--- |--- |--- |--- |
  | `at_preview_token` | 加密的字串 | 強制；無預設值 | 加密的實體，其中包含可在QA模式中執行的促銷活動ID清單。 |
  | `at_preview_index` | 字串 | 空白 | 參數格式為 `<campaignIndex>` 或 `<campaignIndex>_< experienceIndex>`<br>兩個索引的開頭皆為 1。 |
  | `at_preview_listed_activities_only` | 布林值 (true/false) | 預設值: false | 若設為「true」，則 `at_preview_index` 參數中指定的所有促銷活動都會經過處理。<br>若設為「false」，即使預覽 Token 中未指定促銷活動，頁面的所有促銷活動都會經過處理。 |
  | `at_preview_evaluate_as_true_audience_ids` | 字串 | 空白 | 區段ID的以底線分隔的(「_」)清單，應一律（在目標定位和報告層級）在 [!DNL Target] 要求。 |
  | `_AT_Debug` | 字串 | 視窗或主控台 | 主控台記錄或新視窗。 |
  | `adobe_mc_ref` |  |  | 將預設頁面的轉介 URL 傳給新頁面。與 `AppMeasurement.js` 2.1 版 (或更新版) 一起使用時，[!DNL Adobe Analytics] 會在新頁面上將此參數值當作轉介 URL。 |
  | `adobe_mc_sdid` |  |  | 傳遞 [!DNL Supplemental Data Id] (SDID)和 [!DNL Experience Cloud Org Id] 從預設頁面移至新頁面。 傳遞這些ID允許 [!UICONTROL 目標分析] (A4T)將 [!DNL Target] 在預設頁面上透過以下方式請求： [!DNL Analytics] 請求。 |

* 此 [!UICONTROL Target QA模式] UI只會顯示多頁活動中體驗的第一個URL。 假設您要建立歷程測試，並從URL1移至URL2。 不過，若要單獨前往 URL2，請複製根據 URL1 提供的所有 URL 參數，並在放置 &quot;?&quot; 後將其套用至 URL2，  就像您在 URL1 中看到的一樣。
* 如果帳戶中有太多已儲存的活動，已儲存活動的活動 QA 預覽連結可能會無法載入。重試預覽連結。封存已儲存的活動，這些活動不再主動用於防止此問題持續發生。

## Target JavaScript 程式庫 [!UICONTROL QA 模式]相容性 {#compatibility}

[!DNL Target] 支援下列JavaScript程式庫：

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html)

下表列出各種活動型別，並指出是否 [!UICONTROL 活動問答] 每個程式庫都支援模式：

| 活動類型 | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B 測試] | 是 | 是 | 是 |
| [!UICONTROL 自動分配] | 是 | 是 | 是 |
| [!UICONTROL 自動鎖定目標] | 是 | 是 | 是 |
| [!UICONTROL Automated Personalization] (AP) | 是 | 是 | 是 |
| [!UICONTROL 體驗鎖定] (XT) | 是 | 是 | 是 |
| [!UICONTROL 多變數測試] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |

