---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 95d8bd994ffdb1d256b7eb0aea1a2462b40ce530
workflow-type: tm+mt
source-wordcount: '2221'
ht-degree: 7%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年8月21日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。本文章中的資訊會經常更新，尤其是在發行版本之前。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.8.3 （2025年8月21日）

此版本包含下列更新和修正：

**[!UICONTROL Activities]**

+++檢視詳細資料
* **修正儲存活動因屬性資料格式錯誤而觸發無效使用者輸入錯誤的問題**：客戶嘗試儲存現有活動時發生嚴重錯誤。 錯誤訊息指出無效的使用者輸入，特別是參考JSON承載中無法識別的屬性名稱內容。 特別要注意的是，使用相同屬性的新活動已成功儲存，這表示問題已隔離到舊版活動資料。 活動建立流程現在可以正確處理舊版屬性設定、防止無效的輸入錯誤，並確保新活動和現有活動之間的一致儲存行為。 (TGT-53507)
* **修正由於InvalidProperty.Json錯誤而導致客戶無法儲存活動的問題**：客戶嘗試在更新的UI中儲存活動時發生錯誤，即使未進行任何修改。 錯誤訊息指出無效的JSON結構：「無效的Json。 無法辨識的屬性名稱&#39;content&#39;。 位置：行 — 1，欄 — 432。」 此問題是由請求承載中無法識別的屬性所導致，現已解決。 客戶可以成功儲存活動，而不會遇到此錯誤。 (TGT-53513)
* **修正排程活動在頁面重新整理前無法正確顯示[!UICONTROL Live]狀態的問題**：客戶觀察到，當排程活動在未來日期和時間上線時，狀態會立即顯示為[!UICONTROL Live]，而非[!UICONTROL Scheduled]。 這會導致混淆，即使確認訊息正確指出活動已排程。 重新整理頁面已更正狀態顯示。 此問題現在已解決，排程活動可正確顯示排程狀態，不需要重新整理。 (TGT-52937)

+++

**[!UICONTROL Analytics for Target](A4T)**

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
* **修正[!UICONTROL Catalog Search]**&#x200B;中載入的影像不一致：修正[!UICONTROL  Catalog Search]中的縮圖與影像在活動建立程式中無法一致載入的問題。 除非顯示「縮圖URL」欄，且在導覽或搜尋動作後已載入部分或完全未載入某些產品影像，否則影像無法顯示。 影像載入行為已穩定，現在無論欄可見度或導覽動作為何，縮圖都會以可靠的方式顯示。 (TGT-52778)
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

**[!UICONTROL Visual Experience Composer](VEC)**

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

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
