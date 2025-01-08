---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: f034aba7fe4f54b937dee0846140af140052694c
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 21%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年1月7日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!UICONTROL Offers Library]使用者介面更新（2025年1月9日）

為了增強[!DNL Adobe Target]使用者的使用者體驗，此版本更新了[!UICONTROL Offers Library]使用者介面。 此更新使用最新的[!DNL Adobe Spectrum]設計系統，標準化不一致的設計模式，並引進新的增強功能，包括下列專案：

* **大量選件管理**：同時選取並刪除或移動多個選件。

* **[!UICONTROL Code Editor]升級**：使用語法醒目提示和行編號重新整理HTML和JSON編輯器。

* **改善的優惠方案卡**：加強快速資訊和詳細資訊卡，以更輕鬆存取資訊。

* **持續搜尋和篩選**：新增工作階段持續搜尋和篩選選項。

如需詳細資訊，請參閱本節中的[選件](/help/main/c-experiences/c-manage-content/manage-content.md)和子文章。

以下是重點說明此版本中變更的短片：

![選件UI重新整理影片](/help/main/r-release-notes/assets/offers-video-v2.gif)

## [!DNL Adobe Experience Platform Web SDK] `__view__`範圍最佳化（2024年10月22日）

在2024年7月22日至2024年8月15日期間，[!DNL Target]團隊已最佳化`__view__`範圍，提高活動曝光數、造訪數和訪客報告的準確度。 此最佳化旨在自動擷取自動轉譯主張的報告資料，且對大部分帳戶應該是透明的。

所有新[!DNL Adobe Experience Platform Web SDK]客戶都將啟用此最佳化。 不過，從at.js移轉且未遵循下列實施步驟的客戶會停用最佳化。 我們敦促這些客戶在2025年2月3日前檢閱其實作。 在此日期之後，我們將針對所有客戶啟用最佳化。 如果屆時仍無法檢閱和調整實作，可能會影響報表，如下所述。 如果您需要確認實施是否受到影響，或需要更多時間調整實施，請聯絡[!DNL Adobe Customer Care]。

>[!IMPORTANT]
>
>如果您無法在2025年2月3日前完成實作檢閱並解決任何問題，可以請求一次性的六個月延期。 請確定您的請求已在2025年1月31日之前提交。 Adobe將會稽核並決定您的請求。

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

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
