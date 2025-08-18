---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 1a5c47277bfd5eb1c90887728540bbc3b0433d77
workflow-type: tm+mt
source-wordcount: '3800'
ht-degree: 9%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

+++檢視詳細資料
[!DNL Target]團隊提供暫時功能，可讓您使用切換按鈕，在更新的[!DNL Target] UI和舊版之間切換。 此選項僅在UI轉出的最後階段可用。

![目標UI版本切換](/help/main/r-release-notes/assets/toggle.png)

轉出完成後，切換將會移除，且所有使用者都會永久轉換為更新後的UI。 [!DNL Adobe]建議提前規劃，因為此功能將很快淘汰。

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
* **編輯現有活動**：使用更新的UI時，對現有活動所做的變更（原本是在舊版UI中建立）會發佈至您的網站。 不過，如果您切換回去，這些更新不會顯示在舊版UI中；那裡只會顯示舊版UI進行的最後更新。
* **活動詳細資料的一致性**：無論您使用哪種UI，最新變更都會反映在您已上線的網站上。 不過，舊版UI只會顯示該版本的最新變更。 如果在更新的UI中編輯的活動看起來與您在舊版UI中看到的不同，這種情況可能會導致混淆。

#### 深入瞭解更新UI的資源

* [[!DNL Target] UI更新常見問題集](/help/main/c-intro/updated-ui-faq.md)：此常見問題集解決有關新[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常見問題，包括導覽變更、功能位置以及暫時性UI版本切換的淘汰。 無論您是行銷人員、開發人員或管理員，此FAQ可協助您順利轉換，並充分運用更新後的UI。
* [[!DNL Target Standard/Premium] 25.2.1 （2025年2月17日）發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的關鍵UI變更摘要。
* [[!DNL Target Standard/Premium] 25.1.1 （2025年1月9日）發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!DNL Target]中[!UICONTROL Offers Library]主要UI變更的摘要。
* [瞭解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供簡短的總覽，協助您熟悉[!DNL Target]，並提供連結，以取得更深入的資訊和逐步指示。
* [[!UICONTROL Visual Experience Composer]個變更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）推出更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文說明VEC舊版和更新版本之間的差異。
* [[!UICONTROL Visual Experience Composer]選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文說明更新的VEC UI及其選項。

+++

## [!DNL Target Standard/Premium] 25.8.2 （2025年8月14日）

此版本包含下列修正和更新：

**[!UICONTROL Activities]**

+++檢視詳細資料
* **已修正更新[!DNL Target] UI中的活動載入問題**：已修正更新[!DNL Target] UI中嘗試編輯時某些活動無法載入的問題。 此問題導致客戶將使用者留在無限載入畫面中。 此問題會影響多個活動，且各客戶回報問題的發生方式不一致。 透過此修正，受影響的活動現在可正確載入，允許順暢的編輯並減少活動工作流程的中斷。 (TGT-53209)
* **修正由於`optionLocalId`驗證而在活動建立程式中儲存的錯誤**：修正了活動建立程式中由於後端驗證錯誤而阻止客戶儲存變更的問題： `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:`在修改活動內的特定元素時會發生此問題，導致儲存作業失敗。 此修正可確保`optionLocalId`參考現在已正確驗證，允許客戶儲存活動而不會遇到此錯誤。 (TGT-53293)
* **修正切換頁面時，無效選項參考所導致的活動建立程式當機問題**：修正活動建立程式中，在編輯期間切換頁面三次，導致UI當機的問題。 無效的選項參考觸發當機，導致主控台錯誤，例如「找不到localId為&#39;7&#39;的選項」。 透過此更新，客戶現在可以在頁面之間切換並套用修改，而不會遇到系統故障或中斷。 (TGT-53295)
* **修正編輯體驗時，因無效的使用者輸入而導致活動建立程式發生儲存錯誤**：修正活動建立程式中，因無效的使用者輸入錯誤而導致客戶無法儲存活動變更的問題。 在更新的UI中修改體驗時發生錯誤，導致無法提交更新。 活動現在可以成功儲存，允許客戶在不中斷的情況下編輯和發佈。 (TGT-53267)
* **修正活動建立程式的載入問題，此問題封鎖在更新的UI中進行編輯**：修正活動建立程式中，客戶因連續載入畫面而無法編輯更新之UI中的活動的問題。 客戶現在可以開啟和修改活動，而不會遇到載入失敗的情況。 (TGT-53415)
* **修正更新UI中AP活動的活動建立程式中的體驗需求問題**：修正活動建立程式中，[!UICONTROL Automated Personalization] (AP)活動需要兩個位置，而非更新UI中兩個體驗的問題。 此行為會封鎖客戶將單一位置設定為含有多個選件（先前已支援）的使用案例。 已更正此要求，以符合原始功能，讓客戶無論位置計數為何，都可使用兩個體驗來繼續進行AP活動。 (TGT-53429)
* **修正Click Track模式中追蹤的元素欄位行為，以防止未儲存輸入並改善清晰度**：修正活動建立程式中，[!UICONTROL Tracked Element]模式的[!DNL Click Track]欄位可編輯，但未保留輸入名稱，導致客戶混淆的問題。 欄位現在已停用，以防止未儲存的輸入，並且已澄清所選元素的命名，以改善目標設定和追蹤準確性。** (TGT-53458)
* **修正活動建立程式中，在[!UICONTROL Click Track]模式中封鎖追蹤元件命名的問題**：修正活動建立程式中，客戶無法在[!UICONTROL Click Track]模式中命名追蹤元件的問題。 輸入名稱后，欄位似乎可編輯，但未保留輸入，在編輯模式中預設為一般標籤，例如「MY PRIMARY GOAL 0」。 追蹤的元素欄位現在已停用，並且已釐清命名行為以提高目標設定和追蹤準確性。 (TGT-51396)

+++

**體驗片段(XF)**

+++檢視詳細資料
* **修正活動建立程式中的問題，該問題允許對AEM匯出的片段進行非預期的HTML編輯**：修正活動建立程式中的問題，該問題允許客戶編輯從[!DNL Experience Fragments]內的[!DNL Adobe Experience Manager] (AEM)匯出的[!DNL Target] (XF)的HTML。 這是意外行為，因為從AEM發佈後，XF應該會保持鎖定以便編輯。 此修正可確保「編輯HTML」選項不再適用於AEM匯出的片段，保留內容完整性和預期的控管。 (TGT-53286)
* **修正更新UI中活動建立程式中的XF內容間歇性預覽問題**：修正活動建立程式中，XF內容間歇性無法在更新UI中以預覽模式呈現的問題。 雖然內容正確傳送，但預覽未一致顯示，因此客戶很難驗證優惠方案設定。 XF預覽現在能以可靠的方式載入，提高活動設定期間的信賴度和效率。 (TGT-53318)

+++

**QA模式**

+++檢視詳細資料
* **修正URL中前導空格造成QA連結損毀的活動 — 建立程式問題**：修正活動 — 建立程式中，儲存活動URL中前導空格時未正確裁剪的問題。 這會導致後端的QA連結無效和格式不正確。 更新後，URL現在已完整儲存，避免連結損毀，並改善客戶QA工作流程的可靠性。 (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++檢視詳細資料
* **修正目錄搜尋UI中進階搜尋無法提供建議的問題**：修正新[!UICONTROL Catalog Search] UI中[!UICONTROL Advanced Search]功能無法提供建議的問題。 使用者必須輸入包含精確拼字的確切值，導致搜尋體驗繁瑣且容易出錯。 透過此修正，[!UICONTROL Advanced Search]現在會隨著使用者型別提供相關建議，以提升可用性並減少定位產品時的摩擦。 (TGT-52008)
* **解決多個UI和篩選問題，以改善回應速度與實體互動**：解決數個問題，包括小熒幕裝置上的條件詳細資料回應不良、在環境篩選器中選擇「所有主機群組」時缺少結果，以及無法與沒有名稱的實體互動。 這些修正可提升所有熒幕大小的可用性、確保篩選準確且允許與所有產品實體完全互動，進而增強使用者的整體體驗。 (TGT-52992)
* **修正建立活動期間Recommendations詳細資料檢視中遺失產品ID的問題**：修正[!DNL Recommendations]活動建立程式中，產品詳細資料畫面中遺失產品ID，導致客戶在工作流程期間難以複製或參考產品ID的問題。 產品ID現在會清楚顯示在詳細資料檢視中，不但能改善可見度，還能為客戶提供更有效率的產品管理。 (TGT-51964)
* **修正活動建立程式中，產品訊息無法顯示在建議檢視中的問題**：修正活動建立程式中，[!UICONTROL Message]檢視中的[!DNL Recommendations]欄未顯示產品資料（即使有訊息）的問題。 客戶必須手動移除並重新新增欄以暫時顯示內容，當捲動或搜尋時，內容通常會再次消失。 此更新可恢復產品訊息的一致可見性，並改善目錄導覽和稽核工作流程。 (TGT-52777)
* **修正活動建立程式中，選取「所有主機群組」未在建議檢視中傳回結果的問題**：修正活動建立程式中，在[!DNL Recommendations]檢視中選取「所有主機群組」環境未傳回結果的問題。 客戶現在可以如預期檢視所有主機群組的產品資料，在活動設定期間提高可見度和篩選準確性。 (TGT-53006)
* **修正活動建立程式中，儲存後前端促銷活動切換開關未持續的問題**：修正活動建立程式中，儲存後停用活動設定中的前端促銷活動切換開關未持續的問題。 嘗試移除前端促銷活動的客戶發現，在重新造訪活動時，切換功能會重新啟用，導致無法正確自訂。 此更新可可靠儲存變更，讓客戶完全掌控促銷活動設定。 (TGT-53215)
* **已修正依[!UICONTROL Last Updated]資料行排序不一致的問題：**&#x200B;已修正活動建立程式中，依[!UICONTROL Last updated]資料行排序目錄會產生不一致結果的問題。 客戶無法根據更新時間戳記可靠地組織產品資料，導致目錄檢閱和管理更加困難。 排序現在可如預期運作，改善更新UI中的精確度和可用性。 (TGT-53116)

+++

**可視化體驗撰寫器 (VEC)**

+++檢視詳細資料
* **修正活動載入及[!UICONTROL Cancel]活動建立程式中的按鈕問題**：修正活動建立程式中，某些活動無法載入，導致客戶無法存取修改的問題。 此外，[!UICONTROL Cancel]按鈕無回應，導致客戶無法停止載入程式或退出編輯檢視。 此修正可確保活動現在能可靠地載入，且[!UICONTROL Cancel]按鈕如預期般運作，改善視覺化體驗撰寫器的整體穩定性和使用者體驗。 (VEC)(TGT-53218)
* **修正更新VEC UI中封鎖編輯及停用[!UICONTROL Cancel]按鈕的體驗切換問題**：修正更新VEC UI中在體驗鎖定目標(XT)活動中的體驗之間切換時無法載入修改的問題。 客戶無法編輯超出最初輸入範圍的體驗，且[!UICONTROL Cancel]按鈕遺失或無回應。 此修正可確保修改現在在所有體驗中正確載入，且[!UICONTROL Cancel]按鈕可靠地運作，即使沒有Helper擴充功能也是如此，可改善編輯工作流程並減少挫敗感。 (TGT-53256)
* **修正了在活動建立程式中切換多個體驗時的白熒幕問題**：修正了在多個體驗之間切換時導致白熒幕的問題。 也修正了活動建立程式中，客戶嘗試修改活動內的多個體驗時，遇到白熒幕的問題。 將變更套用至兩個體驗，然後選取第三個體驗（阻止進一步編輯）後，就會發生此問題。 此更新可確保體驗之間順利轉換，讓客戶能夠在不中斷的情況下進行修改。 (TGT-53266)
* **修正VEC中自訂程式碼變更無法可靠地跨編輯工作階段儲存的問題**：修正視覺化體驗撰寫器(VEC)中所做的自訂程式碼修改無法可靠地在單一嘗試中儲存的問題。 客戶回報網站和QA URL斷斷續續遺失樣式更新或HTML編輯等變更，即使同時使用[!UICONTROL Edit Content]和最終[!UICONTROL Save]按鈕亦然。 此回歸已解決，確保所有自訂程式碼變更在整個編輯工作階段中都會如預期般持續存在。** (TGT-53418)
* **修正活動建立期間更新UI中遺失`triggerViews`的問題**：修正活動建立程式中，`triggerViews`未出現在更新UI中的問題（即使已在頁面上正確實作）。 這影響了多位客戶，使得在活動設定期間難以驗證檢視型觸發器。 `TriggerViews`現在會如預期般顯示，讓客戶可靠地完成並測試其設定。 (TGT-53239)
* **修正更新UI中特定網頁的活動 — 建立程式中的檢視載入問題**：修正活動 — 建立程式中，儘管已在傳遞或互動呼叫中正確實作及顯示，仍未在更新UI中載入特定網頁的檢視的問題。 這會影響多個客戶，並使得檢視型鎖定目標驗證變得困難。 檢視現在會一致地填入支援的頁面，在活動設定期間提高可靠性。 (TGT-53246)
* **修正更新UI中活動建立程式間歇性檢視載入問題**：修正活動建立程式中，在活動編輯期間檢視間歇性未出現在更新UI中的問題。 雖然網路裝載中存在正確的檢視名稱，但介面中無法一致地辨識該名稱，這會影響客戶設定檢視型個人化的能力。 檢視現在能以可靠的方式顯示，支援更流暢的設定和驗證工作流程。 (TGT-53223)
* **修正活動建立程式中，追蹤的動作名稱未儲存在更新的UI中的問題**：修正活動建立程式中，追蹤的動作量度無法儲存在更新的UI中的問題。 在命名追蹤的元素並儲存活動後，重新開啟時，名稱會重設為預設標籤，導致混淆並中斷目標設定。 追蹤的動作現在會保留其指派名稱，讓客戶準確設定及管理轉換量度。 (TGT-53453)

+++

## [!DNL Target Standard/Premium] 25.8.1 （2025年8月7日）

此發行包含下列增強功能和修正:

**活動**

+++檢視詳細資料
* 已修正數個UI更新問題，包括因輸入值間距而刪除頁面型別時的錯誤、工作區之間的活動複製不可靠，以及QA環境中的頁面傳送規則故障。 (TGT-52703)
* 修正更新的[!DNL Target] UI中，具有[!UICONTROL Editor]角色的使用者能夠存取及嘗試編輯已上線活動的問題，此問題應加以限制。 活動清單和概觀畫面錯誤地顯示已上線活動的編輯選項，導致潛在的意外更改。 (TGT-53055)
* 修正在[!UICONTROL Advanced Search] UI中選取「值存在」或「值不存在」運運算元時，提示使用者輸入運算元的問題，這些條件不應該要求輸入運算元。 (TGT-51961)
* 在更新的UI中，即使在沙箱環境中，嘗試將活動從中繼複製到生產工作區時也始終失敗，此問題已獲修正。 客戶遇到各種錯誤訊息，包括「活動已使用的匿名對象」和「無效的對象ID」，儘管使用有效設定並具有適當的工作區許可權。 (TGT-52394)

+++

**體驗片段(XF)**

+++檢視詳細資料
* 修正體驗片段(XF)內容在[!UICONTROL Visual Experience Composer] (VEC)預覽中無法呈現（儘管在內容傳送中正常運作）的問題。 (TGT-53318)

+++

**本地化**

+++檢視詳細資料
* 修正「促銷活動」區段中的「新增促銷活動」按鈕在QA租使用者的多個語言環境中顯示為未本地化的本地化問題。 (TGT-53263)

+++

**產品建議**

+++檢視詳細資料
* 修正透過視覺化體驗撰寫器(VEC)編輯現有HTML選件時，導致所有修改從內容傳送中移除的問題。 變更會在修改標籤中顯示為灰色，而且不會反映在QA預覽中，儘管已在舊版UI中正確套用。 (TGT-52863)
* 修正更新[!DNL Target] UI中，從[!UICONTROL Visual Experience Composer]索引標籤導覽回[!UICONTROL Targeting]後，[!UICONTROL Experiences] (VEC)中所作HTML選件修改未持續存在的問題。 (TGT-52874)
* 修正更新的[!DNL Target] UI中，在同一選取器之前和之後插入一個HTML選件導致不正確位置產生的問題。 當客戶從[!UICONTROL Targeting]標籤傳回到[!UICONTROL Experience]標籤時，僅保留一個選取器，導致修改遺失和內容傳遞中斷。 此行為與舊版UI不同，後者使用不同的位置識別碼正確保留兩個修改。 (TGT-52891)
* 修正更新[!DNL Target] UI中按一下[!UICONTROL Modifications]邊欄內新增的選件時，導致右側[!UICONTROL Configuration]面板間歇出現並消失的問題，使其難以與選件設定互動。 (TGT-53288)
* 修正新增至活動內對象特定變數的HTML選件，無法一致地儲存或出現在修改區段的問題。 在編輯期間切換對象後，先前套用的選件有時會消失或無法呈現，進而中斷驗證並延遲活動整備。 (TGT-53440)
* 修正複製包含優惠方案的活動時，會在新活動中建立重複優惠方案的問題。 此行為會造成不必要的混亂和混淆，尤其是在工作區之間移動活動時。 此修正可確保[!DNL Target]選件現已正確複製到目的地工作區，而不會重複，可簡化活動管理並提升工作流程效率。 (TGT-53454)

+++

**單頁應用程式(SPA)**

+++檢視詳細資料
* 已修正更新VEC中導致客戶無法對[!UICONTROL Single Page Application] (SPA)檢視套用修改的問題。 雖然在舊版UI中建立的活動可支援檢視特定目標定位，但新版UI無法偵測或允許對這些檢視進行編輯，且檢視切換控制項顯示為停用。 (TGT-52556)

+++

**可視化體驗撰寫器 (VEC)**

+++檢視詳細資料
* 修正在[!UICONTROL Visual Experience Composer]內對體驗所做的修改無法顯示或在UI中顯示不一致的問題。 (TGT-TGT-53381)
* 修正更新VEC中，[!UICONTROL Manage Content]區段無法顯示體驗縮圖替代文字的問題。 此問題使得使用者難以識別檔案，尤其是當檔案名稱太長或截斷時。 (TGT-52291)
* 修正客戶在VEC活動中設定[!UICONTROL page delivery]規則時遇到錯誤驗證錯誤的錯誤。 具體而言，在輸入文字值時，類似「等於任何」和「不等於任何」的運運算元會觸發「運運算元型別的輸入無效」，即使應該支援文字亦然。 (TGT-52629)
* 修正當使用「選取優惠方案」按鈕選取優惠方案時，在更新UI的[!UICONTROL Modifications]面板中導致不一致行為的幾個問題。 UI未取代現有的選件，而是新增了一個重複專案，並嘗試與任一選件互動導致主控台錯誤，例如`selectorNotFound`。 此外，有些選件不會顯示「選取選件」按鈕，只會顯示可編輯的屬性。 (TGT-53321)
* 修正更新[!DNL Target] UI中，在活動設定期間進行的HTML程式碼變更未持續存在於變化頁面上的問題，即使這些變更已正確儲存給控制組。 儘管嘗試了多次並在沒有頁面分組的情況下重新建立測試，變異頁面始終無法保留修改，影響內容交付和QA驗證。 (TGT-53436)
* 修正更新VEC中頁面傳送規則中「等於任何」運運算元無法接受輸入值的問題。 跨所有mbox設定客戶引數時，選取此運運算元會導致「無效輸入」錯誤，無法建立規則。 (TGT-52623)

+++

**工作區**

+++檢視詳細資料
* 改善在工作區之間複製活動時的工作流程。 在工作區之間複製活動之前會導致同步錯誤，因為缺少對象和未指派的屬性。 此更新引入更聰明、更直覺的工作流程，確保複製的活動已正確設定並準備好發佈。 (TGT-47094)
* 修正由於`copyActivityBatchOperations`突變失敗，客戶無法在工作區之間複製活動的問題。 嘗試重複活動會導致伺服器錯誤(500)和null回應裝載。 (TGT-52405)
* 修正當在設定中參考的選件無法在選取的工作區記憶體取時，活動無法同步的問題。 這會導致發佈錯誤，並使活動處於失敗狀態。 (TGT-52535)
* 修正在更新的[!DNL Target] UI中工作區之間複製活動時的多個問題。 客戶遇到與受眾存取相關的錯誤，尤其是即時活動，以及不正確的許可權驗證，即使使用者在來源和目的地工作區中同時具有「[!UICONTROL Approver]」角色。 (TGT-53002)
* 修正更新UI中，複製相同工作區內的活動不必要地複製相關聯選件和對象的問題。 (TGT-53457)
* 修正問題，以解決非預設工作區之間或從非預設工作區未正確複製臨機（匿名）對象的問題。 雖然先前的更新已確保預設至非預設及相同工作區情況可正確複製，但此增強功能著重於保留橫跨多個工作區的合併受眾設定。 此修正可確保所有工作區轉換中的對象行為一致且目標定位準確。 (TGT-53268)

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
