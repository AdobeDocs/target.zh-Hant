---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 065220af5c8e3b6cc25ef7289d006a901d2e932a
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 15%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期： 2025年7月22日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.7.3 （2025年7月24日）

由於最近發現的問題（主要與複雜的客戶自訂有關），此版本包含以下修正和更新：

**活動**

+++查看詳細資料
* 修正Builder類別中的`buildViews`方法不正確將`viewMaxLocalId`設定為檢視總次數，而非指派的最高值`viewLocalId`的問題。 (TGT-53207)
* 引入新的API端點，可讓使用者從次要資料庫還原先前刪除的活動選項。 此功能利用`RemovedCampaignElements`和`RemovedOptionInfo`類別所提供的現有基礎結構，確保刪除的選項可順暢地重新整合至使用中的活動。 (TGT-52903)
* 修正更新[!DNL Target] UI中，[!UICONTROL Automated Personalization] (AP)活動中已刪除的選件顯示為`Deleted option with ID: X`，而非其原始名稱（例如，舊版UI中顯示的`Offer Name [Deleted]`）的問題。 此修正可針對已刪除的選件還原有意義的標籤，進而提高清晰度，並讓報告更準確且更方便使用。 (TGT-52921)
* 修正後端持續層中，已刪除的選項已正確儲存，但無法透過現有API端點存取的問題。 因此，前端應用程式無法為已刪除的選項擷取有意義的名稱，影響歷史報表檢視。 此修正確保保留的已刪除選項資料現在可以在UI中正確顯示。 (TGT-52973)
* 修正從Target前端移轉至Target Central的部分活動因先前修正的同步錯誤而造成量度設定不一致的問題。 具體來說，原本使用轉換量度且後來更新為以Analytics為基礎的量度的活動，會在`primaryMetricType`和`successCriteria`欄位中保留過時的值。 (TGT-52643)

+++

**表單式體驗撰寫器**

+++查看詳細資料
* 修正[!UICONTROL Form-Based Experience Composer]中，在建立或編輯&#x200B;**[!UICONTROL Manage Content]** (AP)活動時，在按一下![圖示（ ](/help/main/assets/icons/Experience.svg)管理內容圖示[!UICONTROL Automated Personalization] ）後導致編輯器當機的問題。 (TGT-53047)

+++

**推薦**

+++查看詳細資料
* 修正捲動至清單底部時，[!UICONTROL Catalog Search]無法載入其他結果的問題，恢復與舊版UI一致的行為。 (TGT-53088)
* 修正更新[!UICONTROL Number of Products] UI中[!UICONTROL Collections]頁面缺少[!DNL Target]欄的問題。 欄現在可正確顯示，並恢復預期的功能。 (TGT-53168)
* 修正[!UICONTROL Collection]規則未根據規則正確篩選的問題。 (TGT-53254)
* 修正封鎖從[!UICONTROL Criteria Details]對話方塊刪除專案的問題。 (TGT-53245)
* 修正無法開啟或無法與無名稱產品互動的問題。 選擇傳回未命名結果的環境時，會發生此問題，導致無法存取產品詳細資料。 (TGT-53007)
* 修正導致[!UICONTROL Catalog Search]頁面當機並在選取特定產品時顯示空白畫面的問題。 (TGT-53087)
* 修正因API限制而無法開啟或編輯包含超過25個字元之量度名稱的[!DNL Recommendations]活動的問題。 此修正可確保與超出字元限制的量度名稱相容，恢復受影響活動的完整存取權。 (TGT-52839)
* 修正使用者無法在[!DNL Recommendation] UI中編輯site_cart_z1 [!DNL Target]活動的問題。 嘗試開啟活動在[!UICONTROL Overview]頁面上觸發錯誤，封鎖編輯器的存取權。 (TGT-53221)

+++

**報告**

+++查看詳細資料
* 修正將報告來源從[!DNL Customer Journey Analytics]或[!DNL Analytics]切換至[!DNL Target]時，活動資料庫中的沙箱欄位未清除的問題。 以前，UI正確傳送沙箱： null，但後端忽略此值，留下過時的沙箱資料。 現在當收到null時，後端會正確清除沙箱欄位。 (TGT-52798)
* 在Target後端重新實作已刪除的選項持續層，以支援[!UICONTROL Automated Personalization] (AP)活動中的精確歷史報告。 先前，刪除選項時，會遺失其名稱，導致難以解譯先前的效能資料。

  **重要改進**：

   * 現在會使用現有的`RemovedCampaignElements`和`RemovedOptionInfo`基礎結構來追蹤刪除的選項。
   * 從AP活動移除選項時，會保留其中繼資料（例如ID和名稱）。
   * 報告UI現在可以顯示原始選項名稱（例如`Option Name [Deleted]`）和歷史量度，提高清晰度和可用性。

  此更新可確保一致且有意義的報告，即使從活動中移除選項後亦然。 (TGT-52986)

* 實作新的移轉端點，以支援將已刪除的活動選項從JCR型活動轉移到[!DNL Target]中央。 此功能可跨系統啟用一致的追蹤和報告。 此功能可確保刪除的選項得以保留並跨[!DNL Target]前端和後端進行同步，進而改善歷史報表和資料完整性。 (TGT-53217)

+++

**可視化體驗撰寫器 (VEC)**

+++查看詳細資料

* 修正VEC中，將修改套用至檢視時造成重複並觸發「無效使用者輸入」錯誤的問題。 (TGT-52886)
* 修正在VEC中設定影像選件時，[!UICONTROL Undo]和[!UICONTROL Insert Before]選項的[!UICONTROL Insert After]功能問題。

  先前，在影像選件上復原[!UICONTROL Insert Before]或[!UICONTROL Insert After]動作會導致不一致的行為或無法正確回覆修改，尤其是在舊版[!DNL Target] UI中建立的活動中。 此問題已解決，以確保復原動作現在能可靠地用於這些修改。 (TGT-52809)

* 修正`contentEditable`屬性無意設定為true並持續存在於已儲存HTML內容中的問題。 此更新可確保輸出更乾淨、預期的HTML，而不會出現非預期的編輯行為。 (TGT-52319)
* 為了防止已刪除的選項永久遺失，並確保各服務間的一致行為，已對UI和相關微服務中的選項實施軟刪除功能。

  **金鑰變更**：

   * 選項不再永久刪除。 相反地，它們會在引數XML物件中標示為新的已刪除： true旗標。
   * 此旗標僅供更新的[!DNL Target] UI使用，以排除轉譯過程中已刪除的選項，並防止這些選項傳送至Edge服務。
   * 刪除的選項在編輯期間仍屬於活動裝載的一部分，以確保可追蹤性，同時避免將不存在的選項傳送給客戶。

  此更新可改善資料完整性，並符合管理分散式系統中刪除的最佳實務。 (TGT-52726)

+++

**工作區**

+++查看詳細資料
* 修正將活動從非預設工作區複製到預設工作區或非預設工作區之間的問題。 選件現在已透過增強追蹤和命名功能複製，以防止衝突。

  **重要改進**：
   * 系統會在目標工作區中重新建立選件，其中包含更新的ID和中繼資料。
   * 系統會使用下列格式重新命名複製的選件：「選件名稱複製」加上隨機數字或時間戳記，以確保唯一性。
   * 系統會更新選件和活動狀態，以反映新的ID。
   * 此功能可防止重複複製動作期間，因多個相同的「選件副本」名稱而發生錯誤。
   * 選件可能不會立即出現在目的地工作區的選件清單中，但會適當地處理並顯示。

  此更新可改善在多個工作區中管理選件時的可靠性和可追蹤性。 (TGT-53080)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
