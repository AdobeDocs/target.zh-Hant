---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新、目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 576ec970f572176b28d1b9f050706574e6813b0c
workflow-type: tm+mt
source-wordcount: '2514'
ht-degree: 13%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些主要重點專案：

### [!DNL Target] UI版本切換為棄用

+++檢視詳細資料
[!DNL Target]團隊提供暫時功能，可讓您使用切換按鈕，在更新的[!DNL Target] UI和舊版之間切換。 此選項僅在UI轉出的最後階段可用。

![目標UI版本切換](/help/main/r-release-notes/assets/toggle.png)

轉出完成後，切換將會移除，所有使用者將永久轉換為更新後的UI。 [!DNL Adobe]建議提前規劃，因為此功能將很快淘汰。

#### 淘汰時間表

由於最近發現的問題（主要與複雜的客戶自訂有關），[!DNL Target]團隊已調整淘汰時間表：

* **2025年6月17日**：所有IMS組織均已針對特定使用者或整個組織啟用更新的[!DNL Target] UI，以開始測試新體驗。

* **2025年6月30日**： [已更新 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)成為已啟用UI版本切換之所有IMS組織的預設體驗。

   * 目前看到舊版UI的客戶，預設會在登入時看到更新的UI。
   * UI版本切換在7月底之前仍然可用，以便使用者在需要時切換回去。

  >[!IMPORTANT]
  >
  > [!DNL Adobe]強烈建議使用更新的[!DNL Target] UI。 只有在發生封鎖程式問題時，才能切換回舊版UI，因為切換切換行為[的限制](#limitations)。

* **2025年7月15日至7月30日**： UI版本切換將會分階段永久停用。 受影響的IMS組織無法再還原至舊版UI。

   * 例外會根據不同情況逐一審查。
   * 在封鎖程式問題解決期間，僅會短暫地允許切換式淘汰的延遲（幾天）。

如有任何疑慮或您預期在此轉換期間發生問題，請聯絡[Adobe客戶服務](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md)。

#### UI切換行為的限制 {#limitations}

下列資訊說明選擇使用版本切換時應該注意的限制：

* **新活動的可見性**：如果您切換回舊版使用者介面，在更新的UI中建立的活動將不可見。
* **編輯現有活動**：使用更新的UI時，對現有活動所做的變更（原本是在舊版UI中建立的）將會發佈至您的網站。 不過，如果您切換回去，這些更新將不會顯示在舊版UI中；那裡只會顯示舊版UI進行的最後更新。
* **活動詳細資料的一致性**：無論您使用哪種UI，最新變更都會反映在您已上線的網站上。 不過，舊版UI將只會顯示該版本中執行的最新變更。 如果在更新的UI中編輯的活動看起來與您在舊版UI中看到的不同，這可能會導致混淆。

#### 深入瞭解更新UI的資源

* [[!DNL Target] UI更新常見問題集](/help/main/c-intro/updated-ui-faq.md)：此常見問題集解決有關新[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常見問題，包括導覽變更、功能位置以及暫時性UI版本切換的淘汰。 無論您是行銷人員、開發人員或管理員，此FAQ可協助您順利轉換，並充分運用更新後的UI。
* [[!DNL Target Standard/Premium] 25.2.1 （2025年2月17日）發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的關鍵UI變更摘要。
* [[!DNL Target Standard/Premium] 25.1.1 （2025年1月9日）發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!DNL Target]中[!UICONTROL Offers Library]主要UI變更的摘要。
* [瞭解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供簡短的總覽，協助您熟悉[!DNL Target]，並提供連結，以取得更深入的資訊和逐步指示。
* [[!UICONTROL Visual Experience Composer]個變更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）推出更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文說明VEC舊版和更新版本之間的差異。
* [[!UICONTROL Visual Experience Composer]選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文說明更新的VEC UI及其選項。

+++

## [!DNL Target Standard/Premium] 25.7.1 （2025年7月11日）

由於最近發現的問題（主要與複雜的客戶自訂有關），此版本包含以下修正和更新：

**活動**

+++查看詳細資料
* 修正[!UICONTROL Activity QA] URL包含不必要查詢引數的問題： `at_preview_evaluate_as_true_audience_ids`。 (TGT-52907)
* 修正預覽URL不正確地包含使用者明確輸入之對象以外的其他對象的問題。 已修正此行為，以確保在產生QA或預覽連結時僅套用指定的對象。 (TGT-52912)
* 修正了在流量配置設定期間先選取[!UICONTROL Auto-Target] (AA)時，使用者無法建立[!UICONTROL Auto-Allocate] (AT)活動的問題。 此問題會導致後端驗證錯誤，且無法儲存活動。 (TGT-53096)

+++

**客群**

+++查看詳細資料
* 修正使用者具有[!UICONTROL Approver]角色時，無法新增或儲存僅限於此活動的對象細分的問題。 嘗試這麼做會導致403禁止錯誤，指出「[編輯者]」許可權是必要的，即使使用者擁有足夠的許可權可核准和管理活動。 (TGT-52984)
* 修正使用[!UICONTROL Remove Audience Refinement]選項移除活動特定對象時，同一活動內不再有對象出現在對象清單中供重新選取的問題。 除非從頭重新建立，否則此行為會防止使用者重新新增相同的對象。 (TGT-52979)
* 修正從位置移除後，甚至在儲存活動之前，僅限活動的對象細分立即從UI消失的問題。 此行為與預期功能和工具提示指引有所抵觸，指引指出：「一旦儲存活動，將會刪除此資料庫中所有未使用的對象」。 (TGT-52982)
* 修正嘗試將[!UICONTROL All Visitors]以外的對象指派至活動時發生的問題。 儲存後，顯示下列錯誤訊息：「我們無法完成您的要求。 如果問題仍然存在，請聯絡[!UICONTROL Adobe Client Care]。」 (TGT-53008)
* 修正在活動編輯器中建立和指派新對象後，無法儲存活動的問題。 顯示的錯誤訊息為：「我們無法完成您的要求。 如果問題仍然存在，請聯絡[!UICONTROL Adobe Client Care]。」 (TGT-52977)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++查看詳細資料
* 修正複製現有活動並將報告來源變更為[!DNL Adobe Analytics] (A4T)會導致「無效使用者輸入」錯誤的問題。 當某些與[!DNL Analytics]報告不相容的量度動作（例如`restart_same_experience`、`restart_random_experience`和`restart_new_experience`）從原始活動中保留時觸發此錯誤。 (TGT-52900)
* 修正在[!DNL Adobe Analytics]步驟中選取[!UICONTROL Goals & Settings] (A4T)作為報告來源時，封鎖客戶建立或儲存活動的問題。 選取[!UICONTROL Custom Event]量度（例如「自訂事件16」）時，會發生特定問題，導致下列錯誤：「無效的使用者輸入」。 (TGT-52910)
* 修正按一下&quot;[!UICONTROL View in Analytics]&quot;連結時，將使用者重新導向至首頁而非預定的[!DNL Analytics]儀表板的問題。 (TGT-53092 和 TGT-53093)
<!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)
* Fixed an issue when viewing a [!DNL Recommendations] activity in the updated [!UICONTROL Overview] UI, the [!UICONTROL Goals & Settings] section fails to load when [!DNL Adobe Analytics] (A4T) is selected as the reporting source. The following error message was displayed: "Something went wrong. We cannot complete your request. Please contact Adobe Client Care if the problem persists." (TGT-52999)-->

+++

**[!UICONTROL Experiences]和[!UICONTROL Offers]**

+++檢視詳細資料
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* 修正移除所有內容選項後，[!UICONTROL Manage Content]功能無法正確驗證位置狀態的問題。 這可能會在嘗試儲存或繼續活動設定時導致不一致的行為或錯誤。 (TGT-52801)
* 修正使用者新增頁面及刪除不同體驗中的特定元素時，發生「輸入無效」錯誤的問題。 在元素操作期間產生重複的`LocalIds`，尤其是當在體驗之間切換及修改共用頁面結構時，觸發了錯誤。 (TGT-52720)
* 修正使用[!UICONTROL Generate Adhoc Offer]功能導致[!UICONTROL Manage Content]面板中出現未定義位置的問題。 (TGT-53076 和 TGT-53070)
* 釐清客戶從[!UICONTROL Targeting]步驟導覽回[!UICONTROL Experiences]時，使用HTML選件進行的修改可能遺失的行為。 針對此客戶，受影響的網站會動態產生多個DOM選取器，並隨著每次頁面載入而變更。 因此，重新開啟編輯器時，找不到原來用於修改的選取器，導致修改遺失或無效。 一切如預期般運作。 為了確保修改內容可在編輯器中持續顯示，建議使用者端使用穩定、一致的選取器，且這些選取器不會在頁面重新載入時變更。 (TGT-52874)
* 修正嘗試刪除或停用屬於排除體驗之優惠並觸發「無效使用者輸入」錯誤的問題。 即使未主動在所包含體驗中使用選件，也會發生此問題。 (TGT-52917)

+++

**表單式體驗撰寫器**

+++查看詳細資料
* 修正在表單式活動中複製體驗以及在其中一個複製的體驗中編輯自訂程式碼時，會無意間將這些變更套用至所有複製的體驗的問題。 現在，每個體驗在複製後都會獨立保留自己的自訂程式碼。 (TGT-51600)

+++

**本地化**

+++查看詳細資料
* 修正字串「預覽體驗」的韓文地區設定(ko-KR)中的內容翻譯問題。 (TGT-52928)
* 已修正多個文字字串的簡體中文(zh_CN)翻譯中發現的術語不一致。 (TGT-52954 和 TGT-52955)

+++

**[!DNL Recommendations]**

+++查看詳細資料
* 已新增新的[!DNL Recommendations]摘要[狀態](/help/main/c-recommendations/c-products/feeds.md#status)： [!UICONTROL Partial Import Failed]。 (KB-2215)
* 修正使用[!DNL Recommendations]新增[!UICONTROL promotions]時，影響活動建立工作流程的問題。 當使用者選取&quot;[!UICONTROL Promote by Attribute]&quot;並新增篩選規則（例如[!UICONTROL Parameter Matching]）時，儲存並重新編輯活動後未保留選取的規則型別和運算元值。 重新開啟時，篩選規則型別會意外變更，且遺失運算元值。 (TGT-53059)
* 修正在[!DNL Recommendations] UI中，無論規則的邏輯為何，使用單一規則建立的任何促銷活動都會被錯誤解譯並顯示為「專案清單」促銷活動型別的問題。 (TGT-53063)
* 修正使用更新的[!UICONTROL Overview]UI時，包含[!UICONTROL Download Recommendations Data]的[!UICONTROL Experience Targeting] (XT)活動缺少「[!DNL Recommendations]」按鈕的問題。 (TGT-52730 和 TGT-52756)
* 以前，Recommendations UI只會顯示已成功從摘要匯入的實體數。 但是，後端訊息格式包含匯入的實體數目以及格式中的實體總數： `# of entities imported / # of total entities`。 由於這種差異，使用者在UI中只看到第一個值（匯入計數），這會導致混淆。 UI現在會顯示這兩個數字。 (TGT-53073)

+++

**報表**

+++查看詳細資料
* 修正從[!UICONTROL Export order details to CSV]頁面選取「[!UICONTROL Reports]」導致下載空白檔案的問題。 即使活動中存在有效的訂單資料，也會發生此問題。 (TGT-52225)
* 修正在建立和指派新報表對象後嘗試儲存活動的問題。 傳回的錯誤訊息為：「存取遭拒。 若要執行此作業，需要下列所有許可權： [編輯器]。」 儘管使用者擁有核准者層級的存取權，仍發生此問題。 (TGT-53103)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++查看詳細資料
* 解決套用修改至檢視會造成檢視重複和活動傳回「無效使用者輸入」錯誤的問題。 此修正可確保正確套用檢視修改，而不會觸發複製或驗證錯誤。 (TGT-52886)
* 修正自訂程式碼修改因錯誤體驗而錯誤顯示的問題。 具體而言，針對一個體驗而做的變更會顯示在不同的體驗中，導致混淆和使上線活動可能設定錯誤。 (TGT-52776)
* 修正無法在新的VEC UI中編輯或儲存自訂程式碼修改的問題。 具體來說：

   * 編輯自訂程式碼區塊並儲存後，變更未反映在UI或QA預覽中。
   * 在某些情況下，除非關閉並重新開啟活動，否則無法刪除修改。
   * 作為因應措施，使用者必須複製計畫碼，刪除修改，然後使用更新的內容手動重新建立。 (TGT-53072)

* 修正編輯和儲存自訂程式碼導致[!UICONTROL Modifications]面板無回應的問題。 (TGT-53075)
* 修正對變體體驗中自訂程式碼所做的修改無意反映在[!UICONTROL Control]體驗中的問題。 這會導致傳送行為發生非預期的變更。 [!UICONTROL Control]體驗現在仍與對其他體驗所做的自訂程式碼編輯分開。 (TGT-52413)
* 修正在編輯器完全載入之前，如果使用者按一下第二個體驗，對某個體驗（例如體驗B）所做的修改會無意間複製到另一個體驗（體驗A）的問題。 如果最初選取的體驗沒有變更，此行為也可能導致修改遺失。 (TGT-52597)
* 修正在活動建立的[!UICONTROL Modifications]步驟中所做的變更無法一致儲存的問題。 在某些情況下，完成所有步驟並按一下[!UICONTROL Save]後，新增到[!UICONTROL Modifications]區段中的自訂指令碼將不會反映在已上線的網站上，儘管在儲存過程中沒有可見錯誤。 (TGT-52661)
* 修正自訂程式碼變更未正確儲存，且無意間映象至相同活動內多個體驗的問題。 此外，使用者在開啟或重新整理特定活動時遇到存取問題，導致空白熒幕。 這些問題現已解決，以確保穩定的活動編輯和精確的體驗隔離。 (TGT-52594)
* 修正使用者在[!UICONTROL Browse Mode]中無法瀏覽至其他URL的問題。 這可防止測試者和編輯者驗證或預覽相同活動工作階段內的替代頁面。 (TGT-53052)
* 修正在活動建立期間同時開啟多個[!UICONTROL Visual Experience Composer] (VEC)執行個體的問題。 當使用者停用[!UICONTROL Enhanced Experience Composer] (EEC)並在[!UICONTROL Page Delivery]步驟中移除網站URL的結尾斜線時，就會發生此問題。 (TGT-52782)
* 修正[!UICONTROL Revenue]步驟中的[!UICONTROL Goals & Settings]量度下拉式清單錯誤地預設為[!UICONTROL Revenue per Visit] (RPVISIT)的問題，即使在使用者選取了不同的量度後也是如此。  收合併重新展開量度設定面板時，發生問題，導致重設先前選取的值。 (TGT-52811 和 TGT-52878)
* 修正[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Multivariate Testing] (MVT)活動中與選件命名和內容翻譯相關的活動建立工作流程幾個問題：

  已解決的關鍵問題：

   * 建立多個具有相同名稱的HTML選件（例如「體驗」）時，會觸發「不允許使用重複選件名稱」錯誤，但UI並未清楚指出導致衝突的選件。
   * 透過右側面板重新命名選件更新了UI中的名稱，但變更未反映在[!UICONTROL Manage Content]標籤或[!UICONTROL Offers]標籤中，導致持續性驗證錯誤。
   * 在MVT活動中，雖然重新命名後重複名稱錯誤並未持續存在，但UI仍無法在各個索引標籤中一致地反映更新的選件名稱。 (TGT-52933)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
