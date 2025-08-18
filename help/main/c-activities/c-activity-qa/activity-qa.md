---
keywords: qa；qa模式；活動qa；qa url；qa url；預覽url；預覽url
description: 瞭解如何使用Adobe [!DNL Target] QA URL來執行簡易的端對端活動QA，同時具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的QA報表。
title: 如何QA活動？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 99ea312405e397e97e64e32d2685e8a6966d8928
workflow-type: tm+mt
source-wordcount: '1658'
ht-degree: 27%

---

# 活動 QA

在[!DNL Adobe Target]中使用QA URL來執行簡易的端對端活動QA，同時具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的QA報表。

[!UICONTROL Activity QA]可讓您在啟動活動之前，完整測試您的[!DNL Target]活動。 [!UICONTROL Activity QA]功能包括：

* 與永遠不會變更或需要重新產生的團隊成員共用的連結，無論對體驗或活動進行的更新為何。 此功能可讓您完整測試整個使用者歷程中的活動。
* 可選擇是否考量客群狀況，這讓市場行銷人員測試鎖定目標條件或忽略鎖定目標條件，以 QA 體驗的外觀，而不必配合客群狀況。
* 擷取 QA 報表，讓市場行銷人員可以確認量度如預期增加，且 QA 報表資料和生產報表 (適用於非 A4T 報表) 分開。
* 能夠單獨預覽體驗，或搭配其他滿足傳送條件（頁面/[!DNL Target]請求/對象）的已上線活動預覽。
* 能夠 QA 整個使用者旅程。您可以利用 QA 連結來存取一次您的網站，然後在活動 QA 期間瀏覽整個網站。在您結束工作階段或使用[QA Target書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)強制自己離開[!UICONTROL Activity QA]之前，您會一直待在「活動QA」中。 如果您的活動橫跨多個網頁，則此功能相當實用。

  >[!NOTE]
  >
  >此功能適用於版本2的at.js實作。*x*&#x200B;或更新版本。 適用於at.js 1.*x*&#x200B;實作，只有在訪客的瀏覽器未封鎖第三方Cookie時，才能使用此功能。

## 存取和共用 QA URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. 從活動的[!UICONTROL Overview]頁面，按一下&#x200B;**[!UICONTROL Activity QA]**。

1. 完成下列設定:

   * **[!UICONTROL Match audience rules to see experiences]：**&#x200B;您有時想要確認對象比對有效果。 其他時候，您會想要檢查活動的外觀與風格。 如果此設定切換到「開啟」位置，測試者必須符合鎖定目標需求，才有資格看到體驗。對於「體驗鎖定目標 (XT)」活動，只會提供單一活動 URL。您看到的體驗取決於您是否符合其中一個鎖定目標規則。

     如果此設定切換到「關閉」位置，則按一下連結所顯示的體驗不在乎您是否符合資格。執行 QA 時，您可以在是否需要顧及對象鎖定目標之間來回切換。

   * **顯示所有其他活動的預設內容：**&#x200B;如果此選項切換到「開啟」位置，則所有其他活動會顯示預設內容。 例如，單獨顯示預覽，而不考慮相同頁面/[!DNL Target]請求上的所有其他已上線活動。

     如果此設定切換為「關閉」，請考量下列事項:

      * 如果您正在測試的活動與其他上線活動之間發生衝突，請套用[一般優先順序規則](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)。 由於發生衝突，您可能無法看見您想要進行QA的活動。
      * 已檢視的活動會增加量度，但僅限於 QA 報表環境中。

1. 按一下&#x200B;**[!UICONTROL Done]**&#x200B;以儲存變更。
1. 與您的組織成員共用活動連結URL以進行測試。

   活動連結永不過期，如果有人變更活動或體驗，您就不需要重新傳送連結。 不過，若您套用與[!UICONTROL Audience Library]不同的對象，而不只是編輯活動，則會產生您必須再次共用的新連結。

   每個活動連結URL （適用於體驗A、體驗B等）可讓您從對應的體驗開始使用者旅程。 按一下為體驗產生的URL，然後繼續一般的網站瀏覽，以在多個頁面上檢視體驗（如果存在多個頁面）。 即使體驗橫跨多個頁面（範本測試或多頁測試），每個體驗也只會產生一個URL。

   您可以瀏覽網站以檢視其他頁面，因為[!UICONTROL Activity QA]模式有粘性。 此情況適用於版本2的at.js實作。*x*&#x200B;或更新版本。 適用於at.js 1.*x*&#x200B;實作，只有在訪客的瀏覽器未封鎖第三方Cookie時，才會發生這種情況。

1. 若要檢視從活動連結URL產生的報表，請按一下活動的&#x200B;**[!UICONTROL Reports]**&#x200B;頁面，按一下&#x200B;**[!UICONTROL Settings]**&#x200B;圖示( ![icon_gear image](assets/icon_gear.png) )，然後從&#x200B;**[!UICONTROL QA Mode Traffic]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Environment]**。

## 從QA模式中釋出自己

[!UICONTROL Activity QA]有粘性。 在[!UICONTROL Activity QA]中瀏覽網站後，您的[!DNL Target]工作階段必須過期，或您必須從[!DNL Target]中釋放[!UICONTROL Activity QA]您，才能像一般訪客一樣檢視您的網站。

### at.js 2.*x*

如果您的網站有at.js 2.*x*&#x200B;已部署，請使用[Target QA書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)強迫自己離開[!UICONTROL Activity QA]。 載入含有空白值的網站頁面（如下一個專案符號所述），在at.js 2 *不會*&#x200B;從瀏覽器移除QA Cookie。*X* 已部署。

### at.js 1.*x*

如果您的網站有at.js 1.*x*&#x200B;已部署，除了使用[Target QA書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)之外，您也可以在網站上以具有空白值的`at_preview_token`引數載入頁面，以手動強迫自己離開。 例如，

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

如果您的網站已部署[[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}，您可以在網站上以帶有空白值的`at_qa_mode`引數載入頁面，以手動強迫自己離開。 例如，

`https://www.mysite.com/?at_qa_mode=`

## 考量事項 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* 由於活動QA現在可用於所有[!DNL Target]活動型別，因此「使用體驗預覽URL預覽Automated Personalization活動」功能不再需要。
* 如果帳戶中有太多已儲存的活動，已儲存活動的[!UICONTROL Activity QA]預覽連結可能會無法載入。 重試預覽連結應該有效。 為避免繼續發生此情況，請封存不再主動使用的已儲存活動。
* 以[!UICONTROL Activity QA]Analytics作為報告來源[ (A4T)的活動可使用](/help/main/c-integrating-target-with-mac/a4t/a4t.md)個URL。 使用[!UICONTROL Activity QA]執行QA時產生的點選流向相同的報表套裝，即使活動上線後，活動的資料也會流經該報表套裝。
* [!UICONTROL Activity QA]不會顯示已封存活動或超過結束日期之活動的內容。 如果您停用已結束的活動，則必須再次儲存活動以便[!UICONTROL Activity QA]運作。
* 匯入至[!DNL Target Standard/Premium]的活動（例如，從[!DNL Target Classic]）不支援QA URL。
* 在[!UICONTROL Auto-Allocate]與[!UICONTROL Recommendations]活動中，模型不會受[!UICONTROL Activity QA]中擷取的造訪影響。
* 如果您在建立活動時指定「URL是」表單式撰寫器中的[細分](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)或視覺化體驗撰寫器中的[頁面傳送選項)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)，則QA URL無法運作，因為[!UICONTROL Activity QA]會附加URL引數。 若要解決此問題，請按一下 QA URL 前往您的網站，從 URL 中移除附加的參數，然後載入新的 URL。
* 如果您有at.js 1.如果您使用Safari或其他封鎖第三方Cookie的瀏覽器，*x*，[!UICONTROL Activity QA]模式沒有粘性。 在這些情況下，您必須將預覽引數新增至您導覽到的每個URL。 如果您已實作[CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html?lang=zh-Hant){target=_blank}，也同樣如此。
* 如果活動使用多個體驗對象（例如，相同活動中包含的US和UK網站），則這四個組合（體驗A/US網站、體驗A/UK網站、體驗B/US網站、體驗B/UK網站）不會產生QA連結。 只會建立兩個 QA 連結 (體驗 A 和體驗 B)，使用者必須屬於適當的對象，才能看到頁面。英國QA人員看不到美國網站。
* 所有 `at_preview` 參數和值皆已完成 URL 編碼。大部分時間，一切都如預期般運作。 但是，有些客戶必須載入平衡器或Web伺服器，以嘗試再次將查詢字串引數編碼。

  因為編碼兩次，當[!DNL Target]嘗試解碼`at_preview_token`時，[!DNL Target]無法擷取正確的Token值，導致預覽無法運作。

  [!DNL Adobe]建議您洽詢IT團隊，確定所有預覽引數皆已加入允許清單，因此這些值絕不會轉換。

  下表列出可在您的網域中列入允許清單的引數：

  | 參數 | 類型 | 值 | 說明 |
  |--- |--- |--- |--- |
  | `at_preview_token` | 加密的字串 | 強制；無預設值 | 加密的實體，其中包含可在QA模式中執行的促銷活動ID清單。 |
  | `at_preview_index` | 字串 | 空白 | 引數格式為`<campaignIndex>`或`<campaignIndex>_< experienceIndex>`<br>兩個索引的開頭皆為1。 |
  | `at_preview_listed_activities_only` | 布林值 (true/false) | 預設值: false | 若設為「true」，則 `at_preview_index` 參數中指定的所有促銷活動都會經過處理。<br>若設為「false」，即使預覽 Token 中未指定促銷活動，頁面的所有促銷活動都會經過處理。 |
  | `at_preview_evaluate_as_true_audience_ids` | 字串 | 空白 | 區段ID-s的底線分隔(「_」)清單，在[!DNL Target]請求的範圍內，應該一律（在目標定位和報告層級）評估為「true」。 |
  | `_AT_Debug` | 字串 | 視窗或主控台 | 主控台記錄或新視窗。 |
  | `adobe_mc_ref` |  |  | 將預設頁面的轉介 URL 傳給新頁面。與 `AppMeasurement.js` 2.1 版 (或更新版) 一起使用時，[!DNL Adobe Analytics] 會在新頁面上將此參數值當作轉介 URL。 |
  | `adobe_mc_sdid` |  |  | 將[!DNL Supplemental Data Id] (SDID)和[!DNL Experience Cloud Org Id]從預設頁面傳給新頁面。 傳遞這些ID可讓[!UICONTROL Analytics for Target] (A4T)將預設頁面上的[!DNL Target]要求與新頁面上的[!DNL Analytics]要求「拼接」起來。 |

* [!UICONTROL Target QA Mode] UI只會顯示多頁活動中體驗的第一個URL。 假設您要建立歷程測試，並從URL1移至URL2。 不過，若要單獨前往 URL2，請複製根據 URL1 提供的所有 URL 參數，並在放置 &quot;?&quot; 後將其套用至 URL2，  就像您在 URL1 中看到的一樣。
* 如果帳戶中有太多已儲存的活動，已儲存活動的活動 QA 預覽連結可能會無法載入。重試預覽連結。封存已儲存的活動，這些活動不再主動用於防止此問題持續發生。

## Target JavaScript資料庫[!UICONTROL QA Mode]相容性 {#compatibility}

[!DNL Target]支援下列JavaScript資料庫：

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=zh-Hant)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=zh-Hant)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html)

下表列出各種活動型別，並指出每個程式庫是否支援[!UICONTROL Activity QA]模式：

| 活動類型 | at.js 1.x | at.js 2.x | 平台網頁SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B Test] | 是 | 是 | 是 |
| [!UICONTROL Auto-Allocate] | 是 | 是 | 是 |
| [!UICONTROL Auto-Target] | 是 | 是 | 是 |
| [!UICONTROL Automated Personalization] (AP) | 是 | 是 | 是 |
| [!UICONTROL Experience Targeting] (XT) | 是 | 是 | 是 |
| [!UICONTROL Multivariate Test] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |