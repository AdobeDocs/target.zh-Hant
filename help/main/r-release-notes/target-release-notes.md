---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: be371f3631d79c65c632a23776ab08de21b031eb
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 7%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年8月27日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。本文章中的資訊會經常更新，尤其是在發行版本之前。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.8.4 （2025年8月28日）

此版本包含下列更新和修正：

**[!UICONTROL Activities]**

+++檢視詳細資料
* **修正活動建立程式期間，已排程活動在更新UI中錯誤顯示&quot;[!UICONTROL Live]&quot;狀態的問題**：具有未來啟用日期的活動現在正確顯示&quot;[!UICONTROL Scheduled]&quot;狀態。 (TGT-53187)
* **在重新整理頁面之前，已排程的活動錯誤地顯示[!UICONTROL Live]狀態**：客戶回報，當排程活動在未來日期和時間上線時，狀態最初會顯示為[!UICONTROL Live]，而不是[!UICONTROL Scheduled]。 這會導致混淆，儘管確認訊息指出正確的排程行為。 活動狀態現在會在儲存後立即正確反映[!UICONTROL Scheduled]，而不需要重新整理頁面。 (TGT-52937)
* **對重複體驗的變更無意中影響了原始體驗**：客戶回報說，在活動內重複體驗並指派新對象時，對重複體驗所做的任何變更（例如設計或條件）也會反映在原始體驗中。 這會防止建立獨立的變數，並影響生產工作流程。 現在可以獨立編輯複製的體驗，而不會影響原始版本。 (TGT-53361)
* **修正因`InvalidProperty.Json`錯誤而無法儲存活動的問題**：以前，客戶嘗試儲存活動但不進行變更時，會發生「使用者輸入無效」錯誤。 錯誤是由於JSON裝載中無法辨識的屬性名稱「content」所導致。 此問題已解決，現在可以在更新的UI中成功儲存活動，即使未進行任何修改。 (TGT-53513)

+++

**目標分析 (A4T)**

+++檢視詳細資料
* **建立A4T活動時無法輸入報表套裝名稱**：在更新的UI中選取[!UICONTROL Report Suite]作為報表來源時，客戶無法輸入[!UICONTROL Analytics]下拉式清單。  此問題導致難以找到特定報表套裝，尤其是針對擁有大型清單的組織。 下拉式清單現在支援依名稱輸入和搜尋，在活動建立過程中提高效率。 (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++檢視詳細資料
* **過期的「時間範圍」對象甚至在移除後也封鎖活動儲存**：以前，如果客戶之前包含過期的「時間範圍」對象，則無法儲存活動，即使該對象已移除。 此問題是因為僅限於此活動的對象持續進行驗證而造成，持續觸發錯誤。 現在只要移除過期的對象，就能如預期儲存活動。 (TGT-53517)
* **儲存活動後，其他頁面和多個對象消失**：以前，在活動建立程式中建立[!UICONTROL A/B Test]活動的客戶在儲存後會遇到已設定的其他頁面和多個對象遺失的情況。 此行為是未預期的，且在設定期間造成混淆。 儲存活動後，這些設定現在會正確持續存在。 (TGT-52357)

+++

**決定優惠**

+++檢視詳細資料
* **無法在更新的VEC中編輯決定優惠或選取特定頁面元素**：客戶在更新的UI中遇到多個問題，導致其無法更新現有活動或建立新活動：

   * 決策優惠錯誤地顯示為HTML優惠，阻止編輯。
   * 無法在VEC中選取特定頁面元素。
   * 編輯期間所做的變更未儲存。
   * 某些地區URL無法在VEC中正確載入，需要手動Cookie調整。

  客戶現在可以編輯決定優惠方案、準確選取頁面元素，並按預期儲存變更。 區域頁面也會在VEC中正確載入。 (TGT-53425)

* **儲存後，無法修改並意外變更優惠決定選取器**：客戶回報在更新的UI中套用優惠決定時，無法變更選取器的預設值。 嘗試將選取器（例如，修改為`#tf-cq-hr or body`）被忽略，在儲存活動後，選取器已取代為泛型值，例如`#cdq_element_0`。 此問題導致選件從視覺化體驗撰寫器(VEC)中消失，並封鎖進一步編輯。 客戶現在可以依預期修改優惠決定選取器，而且儲存的選取器會正確持續存在，不會發生未預期的變更。 (TGT-53433)
* **儲存活動後，優惠決定從活動中消失**：客戶回報儲存活動後，套用至更新UI中頁面元素的優惠決定不再可見。 在某些情況下，選取器意外變更，且在重新編輯時無法在VEC中呈現選件。 優惠決定現在會在儲存後正確保留，而選取器會維持穩定，確保優惠可如預期般顯示及編輯。 (TGT-53434)

+++

**體驗片段**

+++檢視詳細資料
* **客戶使用[!UICONTROL Experience Fragments]或[!UICONTROL Insert Before]插入[!UICONTROL Insert After]**&#x200B;時發生錯誤：客戶嘗試在更新的UI中使用[!UICONTROL Experience Fragments]或[!UICONTROL Insert Before]選項將[!UICONTROL Insert After]插入活動時發生錯誤。 顯示的錯誤訊息為：

  「選件內容必須包含正好一個HTML元素。」

  此問題僅發生在更新的UI中，不會發生在先前的版本中。 問題現在已解決，客戶可以成功插入[!UICONTROL Experience Fragments]，而不會遇到此錯誤。 (TGT-53432)

* **將[!UICONTROL Experience Fragment]新增至活動時的錯誤訊息**：之前，嘗試使用[!UICONTROL Experience Fragment]或[!UICONTROL Insert Before]選項插入[!UICONTROL Insert After]的客戶遇到錯誤：「選件內容只能包含一個HTML元素」。 儘管片段有效並被舊版UI接受（其中包含支援此設定的切換），仍出現此錯誤。 問題已在更新的VEC中解決。 (TGT-53442)

+++

**本地化**

+++檢視詳細資料
* **[!UICONTROL Goals & Settings]步驟中的快顯通知訊息未本地化**：以前，客戶在活動建立程式的[!UICONTROL Objective]欄位中輸入不支援的字元（例如表情符號）時，會遇到未本地化的快顯通知訊息。 Toast訊息現在已正確所有支援的語言本地化，確保全球客戶獲得一致且易於存取的體驗。 (TGT-52251)
* **[!UICONTROL Create Audience]對話方塊中的字串未本地化**：之前，設定時間範圍屬性時，[!UICONTROL Create Audience]強制回應視窗中會顯示訊息「至少為&#39;does not repeat&#39;選擇開始或結束日期」，但並未本地化。 該字串現在已正確本地化所有支援的語言，確保在[!UICONTROL Audiences]工作流程中全球客戶有一致的體驗。 (TGT-52253)
* **[!UICONTROL Create Audience]對話方塊中的工具提示未本地化**：以前，當客戶在對象名稱欄位中輸入不支援的字元（例如表情符號）之後，將滑鼠游標停留在錯誤工具提示上時，工具提示會顯示為未本地化。 工具提示現在會顯示所有支援語言的正確本地化訊息，確保[!UICONTROL Audiences]工作流程中有一致且可存取的體驗。 (TGT-52254)

+++

**[!DNL Recommendations]**

+++檢視詳細資料
* **無法在已上線的活動中停用[!UICONTROL Front Promotion]**：修正客戶無法使用更新的UI在已上線的活動中停用[!UICONTROL Front Promotion]的問題。 在活動建立程式期間在促銷活動區段中所做的變更現在會如預期般持續存在，以確保在[!UICONTROL Product Catalog Search]中正確設定已上線的活動。 (TGT-53231)
* **編輯重複體驗的建議會影響原始體驗**：客戶回報在活動內重複體驗並修改重複中的建議設計或條件時，這些變更會無意套用至原始體驗。  此問題會導致無法建立獨立的變數，並中斷更新活動建立流程中的預期行為。 現在可以獨立編輯複製的體驗，而不會影響原始版本。 (TGT-53369)
* **在[!UICONTROL Recommendations]索引標籤中編輯集合或排除專案時無法檢視產品清單**&#x200B;之前，已套用規則篩選的產品清單在編輯強制回應視窗中不可見，因此客戶很難確認哪些產品已包含或排除。 產品清單現在會在規則修改時正確顯示並即時更新，提高更新[!DNL Recommendations] UI的可見度和可用性。 (TGT-53481)
* **已更新[!UICONTROL View Details]索引標籤[!UICONTROL Recommendations]中**&#x200B;對話方塊的版面配置：之前，[!UICONTROL View Details]對話方塊缺乏清晰的結構，導致客戶難以存取專案特定資訊和詳細目錄相關資訊。 版面配置已更新為包含兩個索引標籤：一個索引標籤顯示所選專案的詳細資訊，第二個索引標籤顯示按集合或排除的目前規則篩選的詳細目錄。 此項改善增強了更新[!DNL Recommendations] UI的清晰度和可用性。 (TGT-53503)
* **客戶無法在[!UICONTROL Goals & Settings]下拉式清單中搜尋報表套裝**：之前，活動建立程式之[!UICONTROL Goals & Settings]區段中的報表套裝下拉式清單不支援文字輸入以進行搜尋，因此擁有大量報表套裝的客戶很難找到正確的報表套裝。 舊版UI中提供的這項功能已還原。 客戶現在可以更有效地輸入來搜尋及選取報表套裝。 (TGT-53514)
* **客戶無法在[!DNL Recommendations] UI中下載自訂條件CSV**：之前，按一下[!UICONTROL Recommendations]索引標籤中自訂條件CSV的下載連結傳回404錯誤，且無法在新索引標籤中開啟。 下載連結現在會在新標籤中開啟，並正確提供CSV檔案，為管理自訂條件的客戶改善協助工具和使用性。 (TGT-51966)
* **啟用不含輸入資料的[!UICONTROL Recommendations]促銷活動會觸發一般錯誤訊息**：之前，在Recommendationsactions活動中啟用前端或後端促銷活動，但未指定必要欄位的客戶遇到含糊的「無效的輸入錯誤」，錯誤碼為`error.restapi.missingFields`。 系統現在會提供清楚且可行的錯誤訊息，指出哪些欄位遺失，進而改善可用性並減少活動建立程式期間的混淆。 (TGT-52616)
* **在[!UICONTROL Catalog Search]**&#x200B;中的產品縮圖和影像未一致載入：客戶報告[!UICONTROL Catalog Search]中的產品縮圖和全尺寸影像間歇性地遺失或損毀，尤其是在導覽或修改欄可見性之後。 無論欄設定或導覽行為為何，現在都能以可靠的方式載入縮圖和影像，進而改善[!UICONTROL Recommendations]工作流程中的整體體驗。 (TGT-52778)
* **無法在[!UICONTROL Designs]環境中建立[!UICONTROL Criteria]和[!UICONTROL Stage]**：客戶嘗試在[!UICONTROL Designs]環境的[!UICONTROL Criteria]索引標籤中建立[!UICONTROL Recommendations]或[!UICONTROL Stage]時，遇到「無效的使用者輸入」錯誤。 客戶現在可以在[!UICONTROL Designs]環境中成功建立[!UICONTROL Criteria]和[!UICONTROL Stage]，而不會發生錯誤。 (TGT-53205)
* 儲存&#x200B;**[!UICONTROL Promotions]後並未從[!UICONTROL Recommendations]活動中移除**：客戶回報新增至[!DNL Recommendation]活動的促銷活動在被移除並儲存後仍會繼續出現。 此問題會影響中繼和生產環境，且在多次儲存嘗試中持續存在。 現在，促銷活動可正確反映活動編輯期間在更新後的活動建立流程中所做的變更。 (TGT-53490)

+++

**[!UICONTROL Reports]**

+++檢視詳細資料
* **[!UICONTROL Automated Segments]在活動報告**&#x200B;中顯示Null對象：客戶觀察到，在活動的[!UICONTROL Automated Segments]區段中檢視[!UICONTROL Reports]時，對象欄位會顯示為Null，即使需要有效的區段資料。 此問題會影響對象目標定位和報告正確性的可見性。 [!UICONTROL Automated Segments]現在可以在活動報告中正確顯示關聯的對象資訊。 (TGT-52793)
* **無法以CSV格式下載活動報告**：嘗試從[!UICONTROL Reports]索引標籤匯出活動報告的客戶在選取CSV下載選項時遇到失敗。 此問題會影響標準報表和訂單詳細資料匯出。 報表現在可以正確下載CSV格式。 (TGT-53464)

+++

**單頁應用程式(SPA)**

+++檢視詳細資料
* **在[!UICONTROL Browse]和[!UICONTROL Design]模式之間切換會重設網頁編輯器中的單頁應用程式(SPA)狀態**：客戶回報在VEC中的[!UICONTROL Browse]和[!UICONTROL Design]模式之間切換會導致網頁編輯器重新載入、重設SPA狀態並中斷活動建立程式。 編輯器現在會在切換模式時保留SPA導覽狀態，以確保更順暢且更一致的編輯體驗。 (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++檢視詳細資料
* **導覽至[!UICONTROL Automated Personalization]步驟並返回後，[!UICONTROL Multivariate Test] (AP)或[!UICONTROL Targeting] (MVT)活動中的位置重新命名作業沒有持續存在。**&#x200B;客戶現在可以成功編輯及儲存位置名稱，而變更在整個活動建立程式中仍可見。 (TGT-52367)
* **在[!UICONTROL Stage]環境中的租使用者上顯示的舊版VEC UI**：修正存取[!UICONTROL Stage]環境中的某些租使用者時，未正確顯示舊版UI而非更新的VEC的問題。 此問題可在多個登入路徑中重現，並影響[!UICONTROL Activities]區段。 更新後的UI現在可正確顯示給[!UICONTROL Stage]環境中的兩個租使用者。 (TGT-52261)
* **選取背景顏色導致頁面在更新的VEC中當機**：
修正從更新的VEC中的[!UICONTROL Style]面板選取背景顏色導致頁面當機並變空白的問題。 主控台錯誤指出無法從未定義的元素讀取內容，特別是與`querySelector`相關的內容。 客戶現在可以安全地選取背景顏色，而不會觸發當機。 (TGT-53561)
* **無法儲存活動，因為使用者輸入錯誤無效**：修正嘗試在更新的VEC中儲存現有活動時的錯誤。 此錯誤只會在編輯期間出現，不會在使用相同屬性建立新活動時出現。 錯誤訊息包括：

  `Invalid Json. Unrecognized property name 'content'. Location: line - 1, column - 432.`

  使用受影響屬性的活動現在可在編輯後成功儲存。 (TGT-53507)

* **透明影像在更新的VEC**&#x200B;中不再包含「fmt=png-alpha」引數：客戶回報在更新的UI中取代影像時，不再保留透明背景。 由更新的VEC產生的影像URL省略了`fmt=png-alpha`引數，而這個引數先前可確保舊版UI中的透明度。 更新的UI現在會正確附加透明影像的`fmt=png-alpha`引數，以還原預期的演算行為。 (TGT-52615)
* **若未新增兩個位置，客戶就無法繼續前往AP活動中的目標區段**：在更新的UI中建立[!UICONTROL Automated Personalization] (AP)活動的客戶無法繼續前往目標區段，除非新增兩個位置。 此行為與先前的UI不同，因為先前只有單一位置已足夠。 對於只偏好使用一個位置的客戶，此問題會封鎖其活動的建立和儲存。 客戶現在可以使用單一位置繼續目標定位和儲存AP活動，還原預期的功能。 (TGT-53426)
* **切換體驗時，在工作區中重複的HTML選件**：之前，客戶在體驗之間切換後，將HTML選件插入工作區中體驗過重複的內容。 此問題也會造成工作區變成無法捲動，影響可用性。 HTML選件不再重複，且在更新的VEC中切換體驗時，工作區仍可捲動。 (TGT-53487)
* **手動更新CSS選擇器導致VEC畫面變成空白**：客戶回報在VEC中編輯選件時，手動更新CSS選擇器會觸發空白畫面，即使選擇器有效並出現在頁面上亦然。 現在，在活動建立程式中手動更新選取器時，VEC畫面會保持穩定。 (TGT-53553)
* **在[!UICONTROL Goals & Settings]**&#x200B;中選取「指定的日期和時間」時，開始日期欄位中的截斷問題：客戶在活動建立期間於[!DNL Start date]頁面的duration區段中選擇指定的日期和時間選項時，會在[!UICONTROL Goals & Settings]欄位中遇到截斷問題。 現在，支援的區域設定可正確顯示完整日期和時間。 (TGT-47843)
* 將&#x200B;**邊欄中的瀏覽器最小化時，[!UICONTROL Manage Content]篩選圖示消失**：客戶回報在瀏覽器視窗調整大小或最小化時，[!UICONTROL Manage Content]活動建立流程的[!UICONTROL Automated Personalization]邊欄中的篩選圖示消失。 無論瀏覽器大小為何，篩選圖示現在仍可顯示和存取，可提升所有熒幕解析度的可用性。 (TGT-51449)

+++

**[!UICONTROL Workspaces]**

+++檢視詳細資料
* **受限於單一工作區的客戶可以從其他工作區檢視活動**：存取許可權受限於特定工作區的客戶仍然可以在更新的UI中選取[!UICONTROL All Workspaces]，並且可以從其他工作區檢視活動。 此行為可能會對已上線活動在其指派的範圍以外造成非預期的變更。 Workspace限制現在已正確執行，客戶只能在其指派的工作區內檢視活動。 (TGT-53101)
* **客戶可以從[!UICONTROL Default Workspace]檢視沒有存取權的活動**：客戶可以從[!UICONTROL Default Workspace]檢視活動，儘管沒有存取權。 Workspace許可權現在會在更新的UI中正確執行，確保客戶只會看到與其指派的工作區相關聯的活動。 (TGT-53297)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
