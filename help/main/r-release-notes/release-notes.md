---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 098415849152065b734cbebbab8dcf1d0805e202
workflow-type: tm+mt
source-wordcount: '1779'
ht-degree: 14%

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

## 資料流更新（2025年9月19日）

[!DNL Adobe Target]個目的地連線的資料串流ID和沙箱組合必須是唯一的。

更新[!DNL Target]目的地連線的驗證邏輯，以強制執行IMS組織內的資料串流ID和沙箱名稱組合必須是唯一的。這表示：

* 相同的資料串流ID +沙箱名稱組無法在多個[!DNL Target]目的地連線中重複使用。
* 相同的資料串流ID只能用於不同的連線，前提是它們是在不同的沙箱中設定。
* 此規則適用於所有資料流選取專案，包括選取「無」時。

此更新可確保一致的設定，並防止多個沙箱環境之間發生衝突。 如需詳細資訊，請參閱[Adobe Target目的地](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank}指南中的&#x200B;*Experience Platform連線*。

## [!DNL Target Standard/Premium] 25.9.1 （2025年9月5日）

此版本包含下列更新和修正：

**[!UICONTROL Experience Fragments]**

+++檢視詳細資料
* **已改善[!UICONTROL AEM Experience Fragment]優惠方案的使用者歸因。**&#x200B;解決VEC中[!UICONTROL Last updated] (XF)選件的「[!UICONTROL AEM Experience Fragment]」欄位未正確顯示程式碼ID而非使用者名稱的問題。 在更新UI中選擇優惠期間發生這種差異，導致與舊版UI和HTML優惠不一致，後者正確顯示上次編輯者的名稱。 此修正可確保跨選件型別的使用者歸因一致，提高透明度並與預期行為一致。 (TGT-52880 和 TGT-52898)

+++

**Offer Decisioning**

+++檢視詳細資料
* 已解決ODE優惠的&#x200B;**優惠決定錯誤。**&#x200B;解決透過[!DNL Target]插入的優惠決定引擎(ODE)優惠由於缺少格式中繼資料而傳回400錯誤的問題。 錯誤訊息指出MIME型別為空，導致無法成功處理優惠決定。 此修正可確保正確處理優惠方案中繼資料、恢復個人化內容傳送的功能，並使行銷活動的執行不會受到干擾。 (TGT-53635)
* **ODS選件轉譯問題已解決。**&#x200B;解決在更新的UI中使用VEC建立活動時，透過[!DNL Offer Decision Service] (AJO)建立的[!DNL Adobe Journey Optimizer] (ODS)選件未呈現的問題。 舊版UI中的相同設定可正確運作，導致混淆並封鎖行銷活動執行。 此修正可確保兩個UI版本間提供一致的選件，還原AJO驅動個人化的預期行為。

+++

**報表**

+++檢視詳細資料
* **更新報告總覽UI的報告區段中已還原下載選項。**&#x200B;解決新的總覽UI中「報表」區段遺失[!UICONTROL Download]按鈕，導致使用者無法匯出屬性重要性分數的問題。 此更新會還原完整的匯出功能，簡化可下載資料的存取，以供分析和報告之用。 (TGT-53222)
* 已在&#x200B;**[!UICONTROL Download full CSV report]檢視中還原[!UICONTROL Important attributes]按鈕。**&#x200B;解決在更新的活動建立UI中，報告檢視的[!UICONTROL Download full CSV report]區段中缺少[!UICONTROL Important Attributes]按鈕的問題。 此修正可恢復對可下載深入分析的存取權，確保更新和舊版UI的功能一致。 (TGT-53238)
* **已解決影響更新總覽UI中[!UICONTROL Auto Target]報告的UI問題。**&#x200B;已修正更新總覽介面中影響[!UICONTROL Auto Target]活動報告的多個UI問題。 這些修正包括：

   * 摘要報表中缺少提升度和信賴度量度
   * 「建立的模型」核取方塊的顏色指示器不正確
   * 無功能圖表報告，儘管[!DNL Analytics]中有資料差異
   * 缺少[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]報告的下載連結
   * [!UICONTROL Automated Segments]報告顯示中斷

  這些修正會還原預期的報告行為，並提升在更新UI中[!UICONTROL Auto Target]效能的可見度。 (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++檢視詳細資料
* **已針對更新的UI中的引數存在條件更正表單驗證。**&#x200B;已解決更新UI中選取「[!UICONTROL Custom mbox parameter value is present]」或「[!UICONTROL Parameter is present]」錯誤地要求客戶輸入值的問題。 此行為與預期邏輯衝突，預期邏輯只會檢查引數是否存在，無論其值為何。 此修正使表單驗證與預期行為一致，可讓您更順暢地設定活動，並支援完全採用更新的UI。 (TGT-53638)
* **已針對頁面傳送中的引數顯示狀態規則修正表單邏輯。」**&#x200B;已解決在更新的UI中選取頁面傳送規則（例如&quot;[!UICONTROL Parameter is present]&quot;、&quot;[!UICONTROL Parameter is not present]&quot;、&quot;[!UICONTROL Parameter value is present]&quot;或&quot;[!UICONTROL Parameter value is not present]&quot;）時，不正確地要求使用者輸入其他引數值的問題。 此行為與舊版UI不一致，且與在不指定值的情況下偵測引數存在的預期邏輯相衝突。 此修正可還原預期的規則設定行為，簡化活動設定並改善可用性。 (TGT-53640)
* 在更新的UI中，多頁規則產生器的&#x200B;**驗證邏輯已改善。**&#x200B;已解決更新UI中多頁規則產生器的多個驗證問題。 這些修正包括：

   * 當mbox引數為空時防止建立規則
   * 顯示無效規則狀態的適當錯誤訊息
   * 更正不需要運算元值的一元運運算元和以引數為基礎的運運算元的驗證邏輯
   * 透過還原儲存功能啟用含一元運運算元的雜湊片段規則

  這些更新可確保精確的規則設定，並提升複雜頁面傳送情境中的可用性。 (TGT-53722)
* **在A/B和MVT活動中已解決的位置重新命名問題。**&#x200B;修正更新UI中重新命名[!UICONTROL A/B Test]或[!UICONTROL Multivariate Test] (MVT)活動中的位置在位置清單、目標定位與返回之間導覽後未持續存在的錯誤。 此更新可確保儲存位置名稱變更，並在整個活動工作流程中一致地反映這些變更。 (TGT-52367)
* **已在更新的UI中修正MVT和AP活動的位置名稱持續性。**&#x200B;已解決在更新的UI中，[!UICONTROL Multivariate Test] (MVT)和[!UICONTROL Automated Personalization] (AP)活動中編輯的位置名稱未正確儲存的問題。 重新命名位置後，在標籤（例如[!UICONTROL Targeting]和[!UICONTROL Experiences]）之間導覽，導致名稱恢復為先前的狀態。 此修正可確保各索引標籤的位置命名一致，並改善活動設定期間的可靠性。 (TGT-52927)
* **已在MVT活動的「管理體驗」面板中修正位置標籤。**&#x200B;已解決更新UI中，[!UICONTROL Manage Experiences] (MVT)活動中的[!UICONTROL Multivariate Test]面板顯示不一致位置編號的問題。 此修正可確保位置標籤順序且正確與使用者定義的修改一致，進而在體驗設定期間提高清晰度和可用性。 (TGT-52929)

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
