---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新、目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: ffd4cd4c39fca828f265ddfc50e9af297d9300cf
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 37%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Adobe Experience Platform Web SDK] `__view__`範圍最佳化（2024年10月22日）

在2024年7月22日至2024年8月15日期間，[!DNL Target]團隊已最佳化`__view__`範圍，提高活動曝光數、造訪數和訪客報告的準確度。 此最佳化旨在自動擷取自動轉譯主張的報告資料，且對大部分帳戶應該是透明的。

所有新[!DNL Adobe Experience Platform Web SDK]客戶都將啟用此最佳化。 不過，從at.js移轉且未遵循下列實施步驟的客戶會停用最佳化。 我們敦促這些客戶在2025年2月3日前檢閱其實作。 在此日期之後，我們將針對所有客戶啟用最佳化。 如果屆時仍無法檢閱和調整實作，可能會影響報表，如下所述。 如果您需要確認實施是否受到影響，或需要更多時間調整實施，請聯絡[!DNL Adobe Client Care]。

若要在手動呈現主張時受益於此最佳化，請檢閱您的[[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}，以確保您在手動呈現體驗後或使用`applyPropositions`方法（或相對應的[!DNL Launch]動作作為協助程式）呈現體驗時傳送通知。

手動呈現體驗時最常見的案例包括：

* 使用JSON選件
* 在[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)中建立的活動中使用自訂決定範圍
* 擷取使用使用全域`__view__`範圍的[!UICONTROL Form-Based Experience Composer]建立的活動時，未使用`renderDecisions: true`

如果通知未如&#x200B;*資料彙集*&#x200B;指南中的[轉譯個人化內容](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank}中記錄的那樣實作，則報告資料可能會在[!DNL Target]和[Analytics for Target報告](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)中遺失。 在某些情況下，您可能會因為未擷取報表資料而注意到不正確的流量分割。 或者，在其他情況下，重複報告相同的事件。

根據您的實作，檢查[!DNL Analytics]和A4T報告影響。

[!DNL Platform Web SDK]支援呈現體驗和個人化的兩種實作型別：

* **個人化和測量的單一呼叫。**

  一開始建議使用[!DNL Platform Web SDK]的單一呼叫方法，但已排定取代分割呼叫方法。 Adobe建議所有新實施使用新的分割呼叫方法，並建議現有客戶也轉換為分割呼叫方法。

  如果您繼續使用單一呼叫方法，您可能會在[!DNL Analytics]報表中注意到下列非預期的變更：

   * 跳出數下降。
   * A4T和[!UICONTROL Page View]點選未彙整在一起，因此使用[!DNL Analytics]個eVar和事件執行A4T報表的特定劃分和關聯相當困難。

* **分割呼叫（也稱為頁面事件的頂端和底部）。**

  此實作型別是[!DNL Adobe]建議的新[分割呼叫實作方法](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank}。 使用此方法時，新的最佳化不會影響[!DNL Analytics]或A4T報表。

如有疑問，請連絡[Adobe客戶服務](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C)。 (KB-2179)

## at.js 2.11.6版（2024年9月29日）

* 已修正導致[!DNL Target]無法在[!UICONTROL Visual Experience Composer] (VEC)或[!UICONTROL Form-Based Experience Composer]內以重新導向選件正確運作的問題。

如需at.js發行版本的詳細資訊，請參閱&#x200B;*Adobe Target開發人員指南*&#x200B;中的[at.js版本詳細資料](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}。

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
| [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
