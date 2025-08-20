---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7fcff4220f5954614867815fb4a67444dfd595ee
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 14%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年8月20日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。本文章中的資訊會經常更新，尤其是在發行版本之前。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.8.3 （2025年8月21日）

此版本包含下列更新和修正：

**優惠決定**

+++檢視詳細資料
* **修正客戶無法編輯決策優惠和在更新的UI中選取特定頁面元素的問題**：在更新的活動建立程式中，客戶無法編輯現有的決策優惠或在視覺化體驗撰寫器(VEC)中選取特定頁面元素。 決策優惠無法正確顯示為HTML優惠，且編輯期間所做的變更並未儲存。 此外，某些地區URL （例如日本網站）無法在VEC中正確載入，導致活動建立和更新受阻。 (TGT-53425)
* **修正[!UICONTROL Offer Decision]選取器在儲存後無法修改和意外變更的問題**：在更新的活動建立程式中，客戶無法如預期修改[!UICONTROL Offer Decision]選取器。 嘗試變更選擇器失敗，選擇器在儲存後恢復到不正確的值。 這會導致決定選件從視覺化體驗撰寫器(VEC)中消失，並封鎖進一步編輯。 (TGT-53433)
* **修正儲存[!UICONTROL Offer Decisions]後**&#x200B;從活動中消失的問題： [!UICONTROL Offer Decisions]在活動建立程式期間新增，但在儲存並重新開啟活動後並未保留。 編輯動態內容並使用特定選取器和屬性插入[!UICONTROL Offer Decisions]時，就會發生此問題。 (TGT-53434)

+++

**推薦**

+++檢視詳細資料
* **修正Recs UI中自訂條件CSV下載傳回404錯誤的問題**：修正客戶無法在活動建立程式中下載自訂條件CSV的問題。 (TGT-51966)
* **修正[!UICONTROL Catalog Search]**&#x200B;中載入的影像不一致：修正[!UICONTROL  Catalog Search]中的縮圖與影像在活動建立程式中無法一致載入的問題。 除非顯示「縮圖URL」欄，且在導覽或搜尋動作後已載入部分或完全未載入某些產品影像，否則影像無法顯示。 (TGT-52778)
* **修正了在重複體驗中編輯建議會影響原始體驗的問題**：客戶回報在重複體驗中修改建議無意間更改了原始體驗。 具體來說，在活動建立程式中複製體驗B並編輯其設計或條件後，相同的變更會反映在原始體驗B中，儘管它們是單獨的實體。 (TGT-53369)
* **修正對重複體驗的變更無意中影響活動中原始體驗的問題：**&#x200B;客戶回報在活動內複製體驗並指派新對象時，對複製體驗的設計或條件所做的任何變更也會反映在原始體驗中。 即使未直接對原始版本進行任何編輯，也會發生這種情況，影響在相同活動內建立獨立變體的能力。 (TGT-53361)
* **修正[!UICONTROL Recommendation Catalog]間歇性地無法顯示完整產品屬性資料的問題**：在更新的[!DNL Recommendations] UI中，客戶遇到某些產品屬性（例如訊息）無法一致顯示在目錄搜尋結果中的問題，即使資料存在於摘要中亦然。 此問題需要客戶手動重新設定欄可見性，以擷取缺少的值。 (TGT-52769)
* **修正無法在已上線的活動中停用[!UICONTROL Front Promotion]的問題**：未儲存嘗試停用已上線的活動中的[!UICONTROL Front Promotion]。 選取[!UICONTROL Change Promotion]並停用它後，促銷活動在重新編輯活動時仍為作用中，以防止更新建議設定。 促銷活動設定現在已正確儲存，可讓客戶如預期停用或修改上線活動中的促銷活動。 (TGT-53231)
* **修正啟用[!DNL Recommendations] [!UICONTROL Promotion] （不含資料）時觸發不明確錯誤訊息的問題**：啟用[!UICONTROL Front]活動中的[!UICONTROL Back Promotion]或[!DNL Recommendations]而未指定必要值，會導致一般「無效的輸入錯誤」訊息。 基礎問題是缺少設定欄位，但錯誤訊息未清楚指出原因，導致疑難排解困難。 活動建立程式現在會在必要欄位（例如`collectionId`或規則）遺失時，提供清楚且可操作的錯誤訊息，協助客戶快速識別及解決設定問題。 (TGT-52616)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++檢視詳細資料
* **修正在AP活動中封鎖推進至[!UICONTROL Targeting]步驟的活動 — 建立程式中的問題**：修正在[!UICONTROL Targeting] (AP)活動中客戶無法繼續進行[!UICONTROL Automated Personalization]步驟的問題（除非新增兩個位置）。 此行為與先前體驗不同，先前體驗中，具有多個選件的單一位置已足夠。 已更正此要求，讓客戶能夠繼續使用單一位置設定作為其AP工作流程的一部分。 (TGT-53426)
* **修正新的活動建立程式未設定透明影像的fmt=png-alpha引數的問題**：在更新的UI中，在活動建立程式期間插入的影像預設不再包含`fmt=png-alpha`引數，導致透明度遺失。 此行為與先前的UI不同，後者會自動將引數附加至影像URL，保留透明背景。 (TGT-52615)

+++

**[!UICONTROL Workspaces]**

+++檢視詳細資料
* **修正限制在單一工作區的客戶可以從其他工作區檢視活動的問題**：在活動建立程式中選取[!UICONTROL All Workspaces]時，存取限制在單一工作區的客戶意外地能夠檢視所有工作區的活動。 此可見度對其他工作區中的已上線活動造成非預期變更的風險，可能會影響網站效能。 (TGT-53101)
* **修正客戶無法存取即可從[!UICONTROL Default Workspace]檢視活動的問題：**&#x200B;存取許可權僅限於中繼工作區的客戶無法透過活動建立程式從[!UICONTROL Default Workspace]檢視活動。 儘管後端設定和存取許可權正確，仍發生此狀況。 (TGT-53297)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
