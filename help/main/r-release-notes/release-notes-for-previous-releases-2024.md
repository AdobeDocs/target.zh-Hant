---
keywords: 發行說明；發行前說明；未來的增強功能；未來的修正；未來的功能；即將發行的版本
description: 檢視 Adobe Target 舊版版本包含的功能、增強功能與修復清單。
title: 舊版版本包含哪些功能？
feature: Release Notes
source-git-commit: 53cd01d2406b8a2f8560fe380ebb5044872e6711
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 15%
---
# 舊版發行說明

舊版 [!DNL Adobe Target] 的發行說明包括 [!DNL Target Standard/Premium]、[!DNL Target] 平台和 [!DNL Target]Javascript 程式庫 (at.js) 的發行說明。

發行說明以發行年月由新到舊順序列出。

>[!NOTE]
>
>請參閱 [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A)，以取得本月 Target 版本 (平台和 Target Standard/Premium) 的資訊。

## 發行說明 - 2024

### [!DNL Adobe Experience Platform Web SDK] `__view__`範圍最佳化（2024年10月22日）

在2024年7月22日至2024年8月15日期間，[!DNL Target]團隊已最佳化`__view__`範圍，提高活動曝光數、造訪數和訪客報告的準確度。 此最佳化旨在自動擷取自動轉譯主張的報告資料，且對大部分帳戶應該是透明的。

所有新[!DNL Adobe Experience Platform Web SDK]客戶都將啟用此最佳化。 不過，從at.js移轉且未遵循下列實施步驟的客戶會停用最佳化。 我們敦促這些客戶在2025年2月3日前檢閱其實作。 在此日期之後，我們將針對所有客戶啟用最佳化。 如果屆時仍無法檢閱和調整實作，可能會影響報表，如下所述。 如果您需要確認實施是否受到影響，或需要更多時間調整實施，請聯絡[!DNL Adobe Customer Care]。

>[!IMPORTANT]
>
>如果您無法在2025年2月3日前完成實作檢閱並解決任何問題，可以請求一次性的六個月延期。 請確定您的請求已在2025年1月31日之前提交。 Adobe將審閱並決定您的請求。

若要在手動呈現主張時受益於此最佳化，請檢閱您的[[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}，以確保您在手動呈現體驗後或使用`applyPropositions`方法（或相對應的[!DNL Launch]動作作為協助程式）呈現體驗時傳送通知。

手動呈現體驗時最常見的案例包括：

* 使用JSON選件
* 在[[!UICONTROL 表單式體驗撰寫器]](/help/main/c-experiences/form-experience-composer.md)中建立的活動中使用自訂決定範圍
* 擷取使用全域`__view__`範圍的[!UICONTROL 表單式體驗撰寫器]建立的活動時，未使用`renderDecisions: true`

如果通知未如&#x200B;*資料彙集*&#x200B;指南中的[轉譯個人化內容](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank}中記錄的那樣實作，則在[!DNL Target]和[Analytics for Target報告](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)中可能會遺漏報告資料。 在某些情況下，您可能會因為未擷取報表資料而注意到不正確的流量分割。 或者，在其他情況下，重複報告相同的事件。

根據您的實作，檢查[!DNL Analytics]和A4T報告影響。

[!DNL Platform Web SDK]支援呈現體驗和個人化的兩種實作型別：

* **個人化和測量的單一呼叫。**

  一開始建議使用[!DNL Platform Web SDK]的單一呼叫方法，但已排定取代分割呼叫方法。 Adobe建議所有新實作使用新的分割呼叫方法，並建議現有客戶也轉換為分割呼叫方法。

  如果您繼續使用單一呼叫方法，您可能會在[!DNL Analytics]報表中注意到下列非預期的變更：

  * 跳出數下降。
  * A4T和[!UICONTROL 頁面檢視]點選未彙整在一起，因此使用[!DNL Analytics]個eVar和事件執行A4T報表的特定劃分和關聯相當困難。

* **分割呼叫（也稱為頁面事件的頂端和底部）。**

  此實作型別是[!DNL Adobe]建議的新[分割呼叫實作方法](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank}。 使用此方法時，新的最佳化不會影響[!DNL Analytics]或A4T報表。

如有疑問，請連絡[Adobe客戶服務](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C)。 (KB-2179)

### at.js 2.11.6版（2024年9月29日）

* 已修正導致[!DNL Target]無法在[!UICONTROL 視覺化體驗撰寫器] (VEC)或[!UICONTROL 表單式體驗撰寫器]中使用重新導向選件正常運作的問題。

如需at.js版本的詳細資訊，請參閱&#x200B;*Adobe Target開發人員指南*&#x200B;中的[at.js版本詳細資料](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}。

### [!DNL Target]報告於[!DNL Adobe Customer Journey Analytics] （2024年5月8日）

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank}與[!DNL Target]之間的整合為您的最佳化程式提供強大的分析與省時的工具。

使用 [!DNL Customer Journey Analytics] 作為 [!DNL Target] 的報告來源的主要優點如下：

* 市場行銷人員可隨時動態地將 [!DNL Customer Journey Analytics] 成功量度套用至 [!DNL Target] 活動報告。 執行活動之前完全不需要指定。
* 行銷人員可利用[!DNL Customer Journey Analytics]功能（例如[Experimentation面板](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}）來進一步分析其網站個人化。

如需詳細資訊，請參閱[Adobe Customer Journey Analytics中的Target報告](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)。

### [!UICONTROL 視覺化體驗撰寫器] Helper擴充功能（2024年4月23日）

舊版[!DNL Target]視覺化體驗撰寫器Helper擴充功能是使用Manifest V2建立的。 [!DNL Google]宣佈從2024年6月起，將不再允許使用資訊清單V2建立的擴充功能。 如需詳細資訊，請參閱[[!UICONTROL 視覺化體驗撰寫器]協助程式擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

[!DNL Adobe]建議客戶儘快改用較新的[Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

### [!UICONTROL 瀏覽器]對象屬性中`Browser:iPad`和`Browser:iPhone`的更新（2024年4月30日）

| 更新 | 詳細資料 |
|--- |--- |
| [!UICONTROL 瀏覽器:iPad]和[!UICONTROL 瀏覽器:iPhone]已更新建立對象時所用的[瀏覽器屬性](/help/main/c-target/c-audiences/c-target-rules/browser.md)。 | [!DNL Adobe Target]可讓您[鎖定數個類別屬性中的任何一個](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括瀏覽您的頁面時使用特定[瀏覽器或瀏覽器選項](/help/main/c-target/c-audiences/c-target-rules/browser.md)的訪客。<P>從[!DNL Target] Standard/Premium 24.3.1 （2024年3月4至6日）開始，使用Target UI建立的內建對象（例如`Browser:iPad`和`Browser:iPhone`）將會更新，以便使用`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`和`profile.mobile.isTablet`為[!DNL iPad]和[!DNL iPhone]執行適當的鎖定目標。<P>此更新不需要客戶採取任何動作。<p><B>重要</b>：若要讓客戶在設定檔指令碼（和JavaScript區段）中針對[!DNL iPad]和[!DNL iPhone]執行適當的目標定位，客戶必須在&#x200B;**2024年4月30日**&#x200B;之前進行手動變更。 如需必須手動變更的替代設定範例，請參閱[!UICONTROL 瀏覽器]對象屬性[&#128279;](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates)中 [!DNL iPad] 和 [!DNL iPhone] 的更新。 |

### [!UICONTROL Visual Editing Helper]擴充功能（2024年3月14日）

此版本包含[!DNL Google Chrome]之[[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)擴充功能的下列增強功能和修正：

* 增強在客戶網站中執行編寫作業時的iFrame載入機制。
* 修正在[!UICONTROL 視覺化體驗撰寫器] (VEC)中執行撰寫時，導致擴充功能重複Cookie的問題。

### [!DNL Target] Standard/Premium 24.3.1 （2024年3月4日至6日）

此版本包含下列增強功能和修正：

* 修正計算活動中不重複選取器數目的邏輯。 (TGT-47878)
* 修正造成[!UICONTROL Multivariate] (MVT)活動(以[!UICONTROL Analytics for Target] (A4T)報告設定)無法正確顯示的問題。 (TGT-47490)
* 改善當沒有流量的體驗用作控制體驗時，報告中顯示的警告訊息。 (TGT-47537)
* 新增許多後端和本地化修正。

### [!DNL Target] Standard/Premium 24.1.1 (2024 年 1 月 22、23 和 25 日)

此版本包含下列增強功能和修正：

* 具有收入目標量度的[!UICONTROL Analytics for Target] (A4T)活動未顯示「收入」做為欄名稱，且收入量度未在報表中以($)格式顯示。 這是已經解決的外觀問題。 (TGT-46995)
* 修正導致報告日期間隔無法正常運作的問題。 (TGT-47396)
* 修正了客戶使用[!UICONTROL 更多動作]圖示啟動或停用活動後，[!UICONTROL 所有活動]頁面上顯示錯誤狀態的問題。 (TGT-47367)
* 修正造成[!UICONTROL 重要屬性]報告無法針對單一客戶顯示的問題。 (TGT-47272)
* 修正當單一客戶嘗試啟用「需要驗證」時，導致系統顯示「無效的承載」訊息的問題。 (TGT-47195)
* 更新 [!DNL Target] UI 中的大量本地化字串。
