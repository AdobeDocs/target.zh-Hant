---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6ecc59588b51da505b8f567a7e87ccef0f375477
workflow-type: tm+mt
source-wordcount: '1959'
ht-degree: 15%

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

## [!DNL Target Standard/Premium] 25.8.1 （2025年8月7日）

此發行包含下列增強功能和修正:

**活動**

+++查看詳細資料
* 已修正數個UI更新問題，包括因輸入值間距而刪除頁面型別時的錯誤、工作區之間的活動複製不可靠，以及QA環境中的頁面傳送規則故障。 (TGT-52703)
* 修正更新的[!DNL Target] UI中，具有[!UICONTROL Editor]角色的使用者能夠存取及嘗試編輯已上線活動的問題，此問題應加以限制。 活動清單和概觀畫面錯誤地顯示已上線活動的編輯選項，導致潛在的意外更改。 (TGT-53055)
* 修正在[!UICONTROL Advanced Search] UI中選取「值存在」或「值不存在」運運算元時，提示使用者輸入運算元的問題，這些條件不應該要求輸入運算元。 (TGT-51961)
* 在更新的UI中，即使在沙箱環境中，嘗試將活動從中繼複製到生產工作區時也始終失敗，此問題已獲修正。 客戶遇到各種錯誤訊息，包括「活動已使用的匿名對象」和「無效的對象ID」，儘管使用有效設定並具有適當的工作區許可權。 (TGT-52394)

+++

**體驗片段(XF)**

+++查看詳細資料
* 修正體驗片段(XF)內容在[!UICONTROL Visual Experience Composer] (VEC)預覽中無法呈現（儘管在內容傳送中正常運作）的問題。 (TGT-53318)

+++

**本地化**

+++查看詳細資料
* 修正「促銷活動」區段中的「新增促銷活動」按鈕在QA租使用者的多個語言環境中顯示為未本地化的本地化問題。 (TGT-53263)

+++

**產品建議**

+++查看詳細資料
* 修正透過視覺化體驗撰寫器(VEC)編輯現有HTML選件時，導致所有修改從內容傳送中移除的問題。 變更會在修改標籤中顯示為灰色，而且不會反映在QA預覽中，儘管已在舊版UI中正確套用。 (TGT-52863)
* 修正更新[!DNL Target] UI中，從[!UICONTROL Visual Experience Composer]索引標籤導覽回[!UICONTROL Targeting]後，[!UICONTROL Experiences] (VEC)中所作HTML選件修改未持續存在的問題。 (TGT-52874)
* 修正更新的[!DNL Target] UI中，在同一選取器之前和之後插入一個HTML選件導致不正確位置產生的問題。 當客戶從[!UICONTROL Targeting]標籤傳回到[!UICONTROL Experience]標籤時，僅保留一個選取器，導致修改遺失和內容傳遞中斷。 此行為與舊版UI不同，後者使用不同的位置識別碼正確保留兩個修改。 (TGT-52891)
* 修正更新[!DNL Target] UI中按一下[!UICONTROL Modifications]邊欄內新增的選件時，導致右側[!UICONTROL Configuration]面板間歇出現並消失的問題，使其難以與選件設定互動。 (TGT-53288)
* 修正新增至活動內對象特定變數的HTML選件，無法一致地儲存或出現在修改區段的問題。 在編輯期間切換對象後，先前套用的選件有時會消失或無法呈現，進而中斷驗證並延遲活動整備。 (TGT-53440)
* 修正複製包含優惠方案的活動時，會在新活動中建立重複優惠方案的問題。 此行為會造成不必要的混亂和混淆，尤其是在工作區之間移動活動時。 此修正可確保[!DNL Target]選件現已正確複製到目的地工作區，而不會重複，可簡化活動管理並提升工作流程效率。 (TGT-53454)

+++

**單頁應用程式(SPA)**

+++查看詳細資料
* 已修正更新VEC中導致客戶無法對[!UICONTROL Single Page Application] (SPA)檢視套用修改的問題。 雖然在舊版UI中建立的活動可支援檢視特定目標定位，但新版UI無法偵測或允許對這些檢視進行編輯，且檢視切換控制項顯示為停用。 (TGT-52556)

+++

**可視化體驗撰寫器 (VEC)**

+++查看詳細資料
* 修正在[!UICONTROL Visual Experience Composer]內對體驗所做的修改無法顯示或在UI中顯示不一致的問題。 (TGT-TGT-53381)
* 修正更新VEC中，[!UICONTROL Manage Content]區段無法顯示體驗縮圖替代文字的問題。 此問題使得使用者難以識別檔案，尤其是當檔案名稱太長或截斷時。 (TGT-52291)
* 修正客戶在VEC活動中設定[!UICONTROL page delivery]規則時遇到錯誤驗證錯誤的錯誤。 具體而言，在輸入文字值時，類似「等於任何」和「不等於任何」的運運算元會觸發「運運算元型別的輸入無效」，即使應該支援文字亦然。 (TGT-52629)
* 修正當使用「選取優惠方案」按鈕選取優惠方案時，在更新UI的[!UICONTROL Modifications]面板中導致不一致行為的幾個問題。 UI未取代現有的選件，而是新增了一個重複專案，並嘗試與任一選件互動導致主控台錯誤，例如`selectorNotFound`。 此外，有些選件不會顯示「選取選件」按鈕，只會顯示可編輯的屬性。 (TGT-53321)
* 修正更新[!DNL Target] UI中，在活動設定期間進行的HTML程式碼變更未持續存在於變化頁面上的問題，即使這些變更已正確儲存給控制組。 儘管嘗試了多次並在沒有頁面分組的情況下重新建立測試，變異頁面始終無法保留修改，影響內容交付和QA驗證。 (TGT-53436)
* 修正更新VEC中頁面傳送規則中「等於任何」運運算元無法接受輸入值的問題。 跨所有mbox設定客戶引數時，選取此運運算元會導致「無效輸入」錯誤，無法建立規則。 (TGT-52623)

+++

**工作區**

+++查看詳細資料
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
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
