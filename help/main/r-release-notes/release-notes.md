---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 223a0f62bcd9a52bd9181e0a439e02164abbfec4
workflow-type: tm+mt
source-wordcount: '7159'
ht-degree: 6%

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

## [!DNL Target Standard/Premium] 25.8.4 （2025年9月1日）

此版本包含下列更新和修正：

**[!UICONTROL Activities]**

+++檢視詳細資料
* **客戶無法從「[!UICONTROL Activity Overview]**」複製活動或檔名稱：以前，客戶無法直接從「[!UICONTROL Activity overview]」在更新的活動建立程式中複製活動名稱或相關的優惠方案/檔案。 此限制會影響可用性，尤其是在較小的熒幕上。 客戶現在可以輕鬆複製活動和檔名稱，無需因應措施。 (TGT-51850)
* **在活動建立期間主動擷取已監管的[!DNL Target]客戶資料**：啟用主動收集[!DNL Target]客戶的報告、內容和熒幕擷取畫面，以改善活動建立流程。 此增強功能解決現有使用案例中發現的資料差距，並幫助確保在活動和實驗設定期間獲得更準確的見解。 (TGT-52415)
* **AP活動未擷取[!UICONTROL Reports]區段中**&#x200B;的模型就緒資料：檢視[!UICONTROL Reports]區段中Automated Personalization (AP)活動的客戶無法在報表群組和選件層級看到模型就緒指標。 發生此問題是因為無法從後端正確擷取模型就緒的資料。 功能已還原，且模型就緒的資料現在如預期般顯示。 (TGT-53600 和 TGT-53601)
* **排程為未來的活動在[!UICONTROL Live]總覽中錯誤顯示「[!UICONTROL Activity]」狀態**：客戶觀察到排程為未來開始的活動在[!UICONTROL Live]總覽中錯誤標籤為「[!UICONTROL Activity]」。 此狀態不符問題已解決，排程活動現在可正確顯示為&quot;[!UICONTROL Scheduled]&quot;，不需要重新整理頁面。 (TGT-52835)

+++

**[!UICONTROL Recommendations]**

+++檢視詳細資料
* **在[!UICONTROL View Collection]對話方塊中看不到產品清單：**&#x200B;之前，客戶在[!UICONTROL Recommendations]索引標籤中檢視集合時無法看到產品清單。 [!UICONTROL View Collection]對話方塊現在可以正確顯示關聯產品，提高更新的[!UICONTROL Recommendations] UI的透明度和可用性。 (TGT-50531)
* **已修正[!UICONTROL Product Catalog Search]進階搜尋中區分大小寫篩選的問題**： [!UICONTROL Product Catalog Search]頁面中的進階搜尋篩選現在會正確忽略區分大小寫功能，並符合後端和GraphQL服務的行為。 此更新可確保為客戶提供一致且準確的建議結果，無論文字大小寫為何。 (TGT-53585)
* **在更新的[!UICONTROL Product Catalog Search] UI中的進階搜尋未提供建議**：在更新的[!UICONTROL Product Catalog Search] UI中使用進階搜尋功能的客戶必須輸入正確拼字的值，因為沒有顯示任何建議。 此問題導致難以有效找到產品。 現在，建議會在進階搜尋輸入期間如預期般顯示。 (TGT-52008)
* **有些核准者無法檢視[!UICONTROL Product Catalog Search]**&#x200B;中的產品：儘管其他具有相同角色的使用者具有存取權，但具有[!UICONTROL Approver]許可權的客戶無法檢視[!UICONTROL Product Catalog Search]中的任何產品。 此問題是因為影響目錄可見性的許可權不一致所導致。 所有核准者現在都能如預期檢視[!UICONTROL Recommendations]區段中的產品。 (TGT-53617)

+++

**[!UICONTROL Reports]**

+++檢視詳細資料
* **由於無效的對象名稱錯誤，無法為案頭對象載入報告**：客戶嘗試在活動建立程式中檢視一個對象的報告時遇到GraphQL錯誤。 系統傳回「無效的對象名稱： XXXXX」訊息，導致無法存取報表資料。 現在，案頭對象的報表可正確載入。 (TGT-53371)
* **在「報表」頁面上切換對象時，導致Target UI發生錯誤**：客戶在[!UICONTROL Reports]區段中選取某些對象時遇到錯誤。 此問題是因為後端GraphQL呼叫中的對象處理無效，導致未預期的錯誤和遺失資料所導致。 問題已解決，現在即使沒有可用資料，案頭受眾仍會載入且不會發生錯誤。 (TGT-53370)
* **[!UICONTROL Graph view]區段中的[!UICONTROL Reports]未顯示來自[!DNL Analytics]**&#x200B;的值：在Re[!UICONTROL Graph view]連線埠區段存取的客戶遇到遺失資料，所有值都顯示為零。 此問題是因為從[!UICONTROL Analytics]擷取的資料不正確所造成。 [!UICONTROL Graph view]現在會如預期顯示正確的值。 (TGT-52792)
+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++檢視詳細資料
* **使用[!UICONTROL Enhanced Experience Composer] (EEC)按一下「接受Cookie」失敗，因為遺失函式**：客戶回報嘗試透過EEC接受Cookie導致主控台錯誤： `handleclickAcceptAllButton is not defined`。 Cookie接受功能現在可如預期運作，確保在更新UI中建立活動期間提供更順暢的體驗。 (TGT-52794)
* **新的EEC UI無法載入舊版UI先前支援的某些頁面**：客戶報告新的EEC無法載入某些頁面，這些頁面可在舊版UI中存取，儘管網站上有防iframe的程式碼。 更新的活動建立流程現在支援載入這些頁面，以恢復活動建立工作流程的相容性。 (TGT-53061)
* **編輯體驗時，VEC顯示空白的白色畫面**：來自特定租使用者的客戶回報，嘗試在更新的VEC中編輯體驗時，VEC畫面變成空白。 此問題會影響新建立和舊的活動，阻礙工作流程的連續性。 VEC現在會正確載入，讓客戶能在不中斷的情況下編輯體驗。 (TGT-53547)
* **載入特定活動時，VEC當機並顯示空白熒幕**：來自特定租使用者的客戶報告VEC無法載入特定活動。 體驗編輯器在當機並顯示空白畫面之前，停留在「套用初始修改」上。 主控台錯誤指出無法讀取未定義的屬性。 編輯器現在會在更新的VEC中載入受影響的活動，而不會發生錯誤。 (TGT-53548)
* **使用Backspace清除所有日期值會導致頁面當機**：使用Backspace清除&quot;[!UICONTROL Goals & Settings]&quot;欄位中的所有值時，排程[!UICONTROL Specified Date & Time]區段中的客戶發生當機問題。 此問題是由日期處理邏輯中的Null參考錯誤所導致。 頁面現在能順利處理空白的日期輸入，而不會當機。 (TGT-53624)
* **由於裝載無效，[!UICONTROL Product Catalog Search]中未出現任何產品**：存取[!UICONTROL Recommendations]中[!UICONTROL Product Catalog Search]區段的客戶遇到因無效GraphQL裝載造成的空白結果。 此後端錯誤導致產品資料無法正確載入。 產品現在會在更新後的UI中如預期般顯示。 (TGT-53630)
* **[!DNL Scene7]個影像已在更新的VEC中以較低解析度儲存**：在更新的VEC中編輯體驗的客戶注意到，[!UICONTROL Scene7]個影像URL儲存時未使用解析度引數，導致傳送的影像品質較低(400×400而不是預期的800×800)。 影像URL現在會保留正確的引數，以確保正確解析度。 (TGT-52631)
* **仍可在VEC中編輯已上線活動**：客戶可存取更新後VEC中已上線活動的編輯選項，這可能會導致意外的變更。 此問題已藉由停用已上線活動的編輯功能而解決。 編輯按鈕現在會隱藏在活動清單和編輯者的概覽中，而核准者和其他角色則不受影響。 (TGT-53055)
* **已停止支援更新VEC中的[!UICONTROL Failed]與[!UICONTROL Draft]活動區段**：已從更新的VEC中移除[!UICONTROL Failed]與[!UICONTROL Draft]活動選項。 新的UI不再支援草稿狀態，且失敗的行銷活動不會儲存在後端。 這些選項已不再相關。 相關篩選器和後端欄位（例如，`uiSyncFailed`、`errorMessage`）也已移除，以簡化活動管理。 (TGT-53150)
* **無法登入VEC進行活動**：嘗試透過VEC登入其網站的客戶被重複重新導向至登入頁面，導致無法存取活動編輯。 此問題無法在內部複製，且可能與網站端工作階段處理有關。 登入流程已穩定，客戶現在可以存取VEC而不會發生重新導向錯誤。 (TGT-53524)
* **在[!UICONTROL Browse]模式中按兩次返回按鈕會導致VEC當機**：在VEC中瀏覽[!UICONTROL Browse]模式的客戶在按兩次瀏覽器的返回按鈕時遭遇當機。 此問題會導致編輯器凍結，並需要重新整理頁面。 編輯器現在能以可靠的方式處理背面導覽，而不會當機。 (GT-53568)
* **無法編輯活動，因為未定義位置對應**：客戶嘗試編輯活動時發生錯誤，原因是`LocationMapping.behaviorTargetedActivity`邏輯中未定義位置ID。 此問題導致400錯誤並封鎖活動更新。 現在可以在沒有位置相關驗證錯誤的情況下編輯活動。 (TGT-53607)
* **儲存活動觸發無效的使用者輸入錯誤**：客戶在更新的VEC中進行微幅修改後，嘗試儲存活動時遇到無效的使用者輸入錯誤。 錯誤是由後端驗證邏輯中的位置對應不符所導致。 現在可以成功儲存活動，而不觸發位置相關錯誤。 (TGT-53603)

+++

## [!DNL Target Standard/Premium] 25.8.3 （2025年8月21日）

此版本包含下列更新和修正：

**[!UICONTROL Activities]**

+++檢視詳細資料
* **修正儲存活動因屬性資料格式錯誤而觸發無效使用者輸入錯誤的問題**：客戶嘗試儲存現有活動時發生嚴重錯誤。 錯誤訊息指出無效的使用者輸入，特別是參考JSON承載中無法識別的屬性名稱內容。 特別要注意的是，使用相同屬性的新活動已成功儲存，這表示問題已隔離到舊版活動資料。 活動建立流程現在可以正確處理舊版屬性設定、防止無效的輸入錯誤，並確保新活動和現有活動之間的一致儲存行為。 (TGT-53507)
* **修正由於InvalidProperty.Json錯誤而導致客戶無法儲存活動的問題**：客戶嘗試在更新的UI中儲存活動時發生錯誤，即使未進行任何修改。 錯誤訊息指出無效的JSON結構：「無效的Json。 無法辨識的屬性名稱&#39;content&#39;。 位置：行 — 1，欄 — 432。」 此問題是由請求承載中無法識別的屬性所導致，現已解決。 客戶可以成功儲存活動，而不會遇到此錯誤。 (TGT-53513)
* **修正排程活動在頁面重新整理前無法正確顯示[!UICONTROL Live]狀態的問題**：客戶觀察到，當排程活動在未來日期和時間上線時，狀態會立即顯示為[!UICONTROL Live]，而非[!UICONTROL Scheduled]。 這會導致混淆，即使確認訊息正確指出活動已排程。 重新整理頁面已更正狀態顯示。 此問題現在已解決，排程活動可正確顯示排程狀態，不需要重新整理。 (TGT-52937)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++檢視詳細資料
* **修正客戶在活動建立程式期間無法輸入報表套裝名稱的問題**：在活動建立程式期間使用[!DNL Adobe Analytics]作為報表來源的客戶無法輸入[!UICONTROL Report Suite]下拉式清單來搜尋特定報表套裝。 這會影響擁有大量報表套裝之組織的工作流程，而手動捲動會大幅延遲設定。 下拉式清單並未依字母順序排序，且未一致回應輸入的內容，因此很難找到「Office + Store - Web - Prod」等報表套裝。 此問題已解決，客戶現在可以透過輸入報告套裝名稱來有效搜尋。 (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++檢視詳細資料
* **修正已過期的「時間範圍」對象在移除後仍封鎖活動儲存的問題**：客戶無法儲存更新UI中的活動，因為發生與已過期的「時間範圍」對象相關的錯誤。 即使在移除受影響的對象後，錯誤訊息仍持續存在：「活動包含具有無效時間範圍的對象。」 發生此問題是因為系統繼續驗證僅限於此活動的對象，即使該對象已不再使用也是如此。 時區差異讓行為變得更複雜。 驗證邏輯已更正，客戶現在可以儲存活動而不會遇到此錯誤。 (TGT-53517)

+++

**[!UICONTROL Experience Fragment]s**

+++檢視詳細資料
* **已修正導致客戶無法在UI中使用[!UICONTROL Insert Before]或[!UICONTROL Insert After]插入體驗片段的問題**&#x200B;客戶嘗試在更新的UI中使用「插入在前」或「插入在後」選項將[!UICONTROL Experience Fragments]插入活動時發生錯誤。 顯示的錯誤訊息為：「選件內容必須包含正好一個HTML元素」。 此問題僅發生在更新的UI中，不會發生在先前的版本中。 此問題現在已解決，客戶可以成功插入[!UICONTROL Experience Fragments]，而不會遇到此錯誤。 (TGT-53442)

+++

**[!UICONTROL Offer decisions]**

+++檢視詳細資料
* **修正客戶無法編輯決策優惠和在更新的UI中選取特定頁面元素的問題**：在更新的活動建立程式中，客戶無法編輯現有的決策優惠或在視覺化體驗撰寫器(VEC)中選取特定頁面元素。 決策優惠無法正確顯示為HTML優惠，且編輯期間所做的變更並未儲存。 此外，某些地區URL （例如日本網站）無法在VEC中正確載入，導致活動建立和更新受阻。 決策優惠現在可正確顯示，頁面元素可如預期選取，而區域URL可在VEC中正確載入，藉此還原完整的編輯功能。 (TGT-53425)
* **修正[!UICONTROL Offer Decision]選取器在儲存後無法修改和意外變更的問題**：在更新的活動建立程式中，客戶無法如預期修改[!UICONTROL Offer Decision]選取器。 嘗試變更選擇器失敗，選擇器在儲存後恢復到不正確的值。 此行為導致決定選件從視覺化體驗撰寫器(VEC)中消失，並封鎖進一步編輯。 選取器變更現在會正確保留，並且決定選件在儲存後仍可在VEC中看到和編輯。(TGT-53433)
* **修正儲存[!UICONTROL Offer Decisions]後**&#x200B;從活動中消失的問題： [!UICONTROL Offer Decisions]在活動建立程式期間新增，但在儲存並重新開啟活動後並未保留。 編輯動態內容並使用特定選取器和屬性插入[!UICONTROL Offer Decisions]時，就會發生此問題。 [!UICONTROL Offer Decisions]現在會在儲存後正確保留，而選取器會維持不變，確保目標定位和編輯行為的一致性。 (TGT-53434)

+++

**[!DNL Recommendations]**

+++檢視詳細資料
* **修正[!DNL Recommendations] UI中自訂條件CSV下載傳回404錯誤的問題**：修正客戶無法在活動建立程式中下載自訂條件CSV的問題。 下載連結現在可以正常運作，讓客戶如預期匯出自訂條件。 (TGT-51966)
* **修正[!UICONTROL Catalog Search]**&#x200B;中載入的影像不一致：修正[!UICONTROL &#x200B; Catalog Search]中的縮圖與影像在活動建立程式中無法一致載入的問題。 除非顯示「縮圖URL」欄，且在導覽或搜尋動作後已載入部分或完全未載入某些產品影像，否則影像無法顯示。 影像載入行為已穩定，現在無論欄可見度或導覽動作為何，縮圖都會以可靠的方式顯示。 (TGT-52778)
* **修正了在重複體驗中編輯建議會影響原始體驗的問題**：客戶回報在重複體驗中修改建議無意間更改了原始體驗。 具體來說，在活動建立程式中複製體驗B並編輯其設計或條件後，相同的變更會反映在原始體驗B中，儘管它們是單獨的實體。 重複的體驗現在會維護個別的設定，確保對一個體驗的編輯不會影響原始體驗。 (TGT-53369)
* **修正對重複體驗的變更無意中影響活動中原始體驗的問題**：客戶回報說，在活動內複製體驗並指派新對象時，對複製體驗的設計或條件所做的任何變更也會反映在原始體驗中。 即使未直接對原始版本進行任何編輯，也會發生此問題，這會影響在相同活動中建立獨立變體的能力。 活動建立程式現在可以正確隔離重複的體驗，確保對一個體驗所做的編輯不會影響原始體驗。 (TGT-53361)
* **修正[!UICONTROL Recommendation Catalog]斷斷續續地無法顯示完整產品屬性資料的問題**：在更新的[!DNL Recommendations] UI中，客戶遇到即使資料存在於摘要中，[!UICONTROL Catalog Search]結果中仍無法一致顯示某些產品屬性（例如訊息）的問題。 此問題需要客戶手動重新設定欄可見性，以擷取缺少的值。 [!UICONTROL Catalog Search]現在可靠地顯示所有已設定的屬性，不需要手動重設欄。 (TGT-52769)
* **修正無法在已上線的活動中停用[!UICONTROL Front Promotion]的問題**：未儲存嘗試停用已上線的活動中的[!UICONTROL Front Promotion]。 選取[!UICONTROL Change Promotion]並停用它後，促銷活動在重新編輯活動時仍為作用中，以防止更新建議設定。 促銷活動設定現在已正確儲存，可讓客戶如預期停用或修改上線活動中的促銷活動。 (TGT-53231)
* **修正啟用[!DNL Recommendations] [!UICONTROL Promotion] （不含資料）時觸發不明確錯誤訊息的問題**：啟用[!UICONTROL Front]活動中的[!UICONTROL Back Promotion]或[!DNL Recommendations]而未指定必要值，會導致一般「無效的輸入錯誤」訊息。 基礎問題是缺少設定欄位，但錯誤訊息未清楚指出原因，導致疑難排解困難。 活動建立程式現在會在必要欄位（例如`collectionId`或規則）遺失時，提供清楚且可操作的錯誤訊息，協助客戶快速識別及解決設定問題。 (TGT-52616)
* **修正無法在[!UICONTROL Product]索引標籤[!UICONTROL Edit]內的[!UICONTROL Recommendations]強制回應中顯示**&#x200B;清單的問題：客戶在[!UICONTROL collection]索引標籤中編輯[!UICONTROL exclusion]或[!UICONTROL Recommendations]時無法檢視篩選的產品清單。 清單必須根據套用的規則即時更新，但並未如預期顯示。 此問題已解決，產品清單現在會正確顯示，並隨著規則修改而動態更新。 (TGT-53481)
* **修正更新UI中「檢視詳細資料」對話方塊的配置問題**：更新UI中「檢視詳細資料」模組的配置已修改，以提高清晰度和可用性。 對話方塊現在包含兩個索引標籤：
   * [!UICONTROL Details]標籤：顯示所選專案的所有相關資訊。
   * [!UICONTROL Inventory]索引標籤：顯示依目前集合和排除規則篩選的所有產品。

  此增強功能可協助客戶更輕鬆地導覽及瞭解活動建立流程中的專案特定資料和詳細目錄內容。 (TGT-53503)

   * **修正儲存後，建議活動中已移除的促銷活動會重新顯示的問題**：客戶回報從[!UICONTROL front]活動中移除[!UICONTROL back]或[!DNL Recommendations]促銷活動並儲存活動時，促銷活動會在重新開啟時繼續顯示。 此問題在中繼和生產環境中發生，並影響更新的活動建立流程。 問題已解決。 已從活動中移除的促銷活動，現在會在儲存後正確保留。 (TGT-53490)

+++

**報表**

+++檢視詳細資料
* **修正[!UICONTROL Automated Segments]報告顯示null對象值的問題**：客戶報告活動報告中的[!UICONTROL Automated Segments]顯示對象資料為null，無法正確分析區段效能。 存取[!UICONTROL Reports]區段並選取[!UICONTROL Automated Segments]時發生此問題，即使需要有效的對象資料亦然。 [!UICONTROL Automated Segments]現在可以正確顯示對象值，確保可靠的報表和分段深入分析。 (TGT-52793)

+++

**單一頁面應用程式(SPA)**

+++檢視詳細資料
* **修正更新UI中在[!UICONTROL Browse]和[!UICONTROL Design]模式之間切換會重設SPA狀態的問題**：客戶回報在更新UI中在[!UICONTROL Browse]和[!UICONTROL Design]模式之間切換會導致網頁編輯器重新載入，重設SPA的狀態。 此問題會中斷工作流程，並需要客戶重新輸入資訊。 問題已解決。 現在，在模式之間切換時，會保留SPA狀態，以確保在活動建立期間獲得更順暢且一致的體驗。 (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++檢視詳細資料
* **修正在AP活動中，活動建立程式封鎖推進至[!UICONTROL Targeting]步驟的問題**：修正活動建立程式中，除非新增兩個位置，否則客戶無法繼續進行[!UICONTROL Targeting] (AP)活動的[!UICONTROL Automated Personalization]步驟的問題。 此行為與先前體驗不同，先前體驗中，具有多個選件的單一位置已足夠。 已更正此要求，讓客戶能夠繼續使用單一位置設定作為其AP工作流程的一部分。 (TGT-53426)
* **修正新的活動建立程式未設定透明影像的fmt=png-alpha引數的問題**：在更新的UI中，在活動建立程式期間插入的影像預設不再包含`fmt=png-alpha`引數，導致透明度遺失。 此行為與先前的UI不同，後者會自動將引數附加至影像URL，保留透明背景。 活動建立程式現在會在需要透明度時，正確將`fmt=png-alpha`引數套用至影像URL，以確保透明資產呈現的一致性。 (TGT-52615)
* **修正導致客戶無法在更新的UI中搜尋報表套裝的問題**：在更新的UI中，[!UICONTROL Report Suites]區段中的[!UICONTROL Goals & Settings]下拉式清單不允許客戶輸入和搜尋，導致難以找到特定的報表套裝，尤其是具有大量專案的租使用者。 和之前的UI不同，清單沒有排序，缺少基於輸入的篩選。 此問題已解決。 客戶現在可以輸入來搜尋和篩選報表套裝，還原舊版UI中可用的功能。 (TGT-53514)

+++

**[!UICONTROL Workspaces]**

+++檢視詳細資料
* **修正限制在單一工作區的客戶可以從其他工作區檢視活動的問題**：在活動建立程式中選取[!UICONTROL All Workspaces]時，存取限制在單一工作區的客戶意外地能夠檢視所有工作區的活動。 此可見度對其他工作區中的已上線活動造成非預期變更的風險，可能會影響網站效能。 Workspace存取控制已增強，以確保客戶只能檢視其指派的工作區中的活動並與之互動。 (TGT-53101)
* **修正客戶無法存取即可從[!UICONTROL Default Workspace]檢視活動的問題：**&#x200B;存取許可權僅限於中繼工作區的客戶無法透過活動建立程式從[!UICONTROL Default Workspace]檢視活動。 即使後端設定和存取許可權正確，還是會發生此行為。 Workspace存取控制已增強，以確保客戶只能在其指派的工作區內檢視活動。(TGT-53297)

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
