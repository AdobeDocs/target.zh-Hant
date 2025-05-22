---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新、目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: dc9797cc0afdb3fed5b4bb95cf134e702cec42d7
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 26%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 25.5.3 （2025年5月22日）

此版本包含下列修正和更新：

* 修正[!UICONTROL Activities]清單中的依名稱搜尋功能無法正確搭配多字查詢運作的問題。 (TGT-52529)
* 修正無法從[!UICONTROL Automated Personalization] (AP)活動中排除體驗的問題。 (TGT-52383)
* 修正管理AP活動中的內容時，「[!UICONTROL Filter Rules]」中缺少「[!UICONTROL Contains]」選項的問題。 (TGT-52384)
* 修正[!UICONTROL Automated Personalization] (AP)活動中報告不一致的問題，特別是有關如何使用[!DNL Target]內部系統的`optionLocalId`值追蹤及報告預設優惠的問題。
* 修正QA連結無法傳遞預期活動體驗的問題。 (TGT-52163)
* 修正具有[!UICONTROL Approver]許可權的使用者無法正確編輯已上線活動的問題，收到「存取遭拒」錯誤訊息。 (TGT-52416)
* 修正在更新的[!DNL Target] UI中，某些活動的對象細分無法顯示的問題。 (TGT-52057)
* 已修正導致在更新的UI中回覆對象細分和活動對象的問題。 (TGT-52158)
* 修正產生臨時優惠方案導致重複優惠方案的問題。 (TGT-51938)
* 修正封鎖選件更新並錯誤顯示「無效使用者」錯誤的問題。 (TGT-52361)
* 修正無法儲存現有活動，觸發「無效使用者輸入」錯誤的問題。 (TGT-52422)
* 修正封鎖編輯現有HTML選件的問題，即使未進行任何程式碼變更，儲存時也會觸發「無效使用者輸入」錯誤。 (TGT-52351)
* 修正導致[!DNL Target]無法辨識網站URL中「#」字元的問題。 (TGT-52093)
* 修正無法編輯[!DNL Recommendations]活動以新增或更新促銷活動，進而造成儲存失敗和重複促銷活動的問題。 (TGT-52343)
* 修正在[!DNL Recommendations]活動中無法變更條件或設計，而導致「無效的JSON：無法辨識的屬性名稱」錯誤的問題。 (TGT-52375)
* 修正[!DNL Recommendations]活動的[!UICONTROL Visual Experience Composer] (VEC)中無法正確顯示序列條件的問題。 (TGT-52435)
* 修正使用[!DNL Adobe Experience Platform Web SDK]時SPA頁面上未正確識別檢視的問題。 (TGT-52106)
* 修正「裝置上決策(ODS)」詳細資料（儘管包含在批次作業裝載中）未正確儲存的問題。 (TGT-52406)
* 已將`audienceMetadata`欄位新增至活動，使其可在編輯期間被讀取和更新。 (TGT-51004)
* 新增錯誤訊息，以在對象時間範圍無效時提醒使用者。 (TGT52522)
* 更新活動結構以支援不同型別的重複對象。 (TGT-51200)

## [!DNL Adobe Target] [!DNL AI Assistant]版本（2025年5月16日）

我們很高興在[!DNL Adobe Target]中宣佈[!DNL AI Assistant]的啟動！ 這個強大的使用者介面功能可協助您輕鬆瀏覽及瞭解[!DNL Target]概念。 在[!DNL Adobe Experience Cloud]的多個產品（包括[!DNL Target]）中都有提供，[!DNL AI Assistant]可在此為您帶來全新的體驗。

[!UICONTROL Target]中的[!DNL AI Assistant]是一種對話工具，可用來加速處理[!DNL Experience Platform]應用程式和服務的工作流程。 使用[!DNL AI Assistant]提升整體生產力並提升您對產品知識的理解

在[!DNL Target]中，[!DNL AI Assistant]的第一階段以[!DNL Experience League]檔案為基礎，提供寶貴的產品知識。 無論您是要設定設定檔指令碼、疑難排解錯誤，還是要考慮升級至AEP Web SDK，[!DNL AI Assistant]皆已涵蓋您的所有事項。

如需詳細資訊，請參閱[Adobe Experience Platform AI助理概述](/help/main/c-intro/ai-assistant.md)。

## [!DNL Target Standard/Premium] 25.5.2 （2025年5月8日）

此版本包含下列修正和更新：

* 具有[!UICONTROL Product Administrator]和[!UICONTROL System Administrator]許可權的[!DNL Target]使用者現在可以編輯[!UICONTROL Administration]頁面上的所有設定，無論他們在[!DNL Target]中的角色為何。 沒有這些許可權的使用者擁有這些設定的唯讀存取權。 此更新可確保對[系統管理設定](/help/main/administrating-target/administrating-target.md)進行更嚴格的存取控制。 (TGT-48179)
* 修正無法儲存活動[網站偏好設定](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings)的快取問題。 (TGT-52213)
* 修正在VEC中載入網站後，客戶無法在[!UICONTROL Site Preferences]區段中依ID和類別啟用選取功能的問題。 [!UICONTROL Site Preferences]設定在啟用後也會自動回覆為停用。 (TGT-52207)
* 修正[頁面傳送](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings)URL以正斜線(/)結尾時，[!UICONTROL Visual Experience Composer] (VEC)無法顯示正確頁面的問題。 (TGT-52237)
* 修正無法在變更體驗時移除自訂程式碼修改的問題。 (TGT-52240)
* 修正VEC中HTML修改覆蓋現有頁面元素的問題。 (TGT-52265)
* 修正因編輯器中看不到現有自訂程式碼而無法在已更新VEC中編輯自訂程式碼的問題。 (TGT-52272)
* 修正儲存Recommendations活動時，造成「不允許重複名稱」錯誤訊息的問題。 (TGT-52318)
* 已修正更新VEC中導致客戶無法編輯文字元素或移除容器物件的問題。 (TGT-52348)
* 修正封鎖[!DNL Customer Journey Analytics]在活動[!UICONTROL Overview]頁面上正確顯示的問題。 (TGT-52359)
* 修正報表群組無法在[!UICONTROL Automated Personalization] (AP)活動中持續存在的問題。 (TGT-52368)
* 修正無法儲存包含Offer Decisioning之活動的問題。 (TGT-52390)
* 修正已選取預設選件，但在[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Multivariate Test] (MVT)活動中顯示其他選件內容的問題。 (TGT-52372)
* 修正GET許可權邏輯，以在完整組織存取權與特定組織+使用者存取權之間檢查或。 (TGT-52374)
* 修正為[!UICONTROL Managed Content]和[!UICONTROL Reporting Audiences]選取對象後未顯示對象名稱的問題，即使[!UICONTROL Show Only Selected]已啟用。 (TGT-52393)

## [!DNL Target Standard/Premium] 25.5.1 （2025年5月5日）

此版本包含下列修正和更新：

* 已修正無法在更新的UI中顯示特定活動的對象細分的問題。 (TGT-52057)
* 修正無法在活動中使用合併受眾的問題。 (TGT-52346)
* 修正了無法使用相同工作區中僅限活動的對象，在非預設工作區中建立新活動的問題。 (TGE-52349)
* 修正造成在建立及選取新對象後，僅限於此活動的對象從更新的UI中消失的問題。 (TGT=52091)
* 修正無法在活動中使用重複受眾的問題。 (TGT-51200 和 TGT-52057)
* 已修正導致在更新的UI中回覆對象細分和活動對象的問題。 (TGT-52158)
* 修正由於使用者輸入錯誤「此使用者不允許非預設工作區」而無法建立新活動的問題。 (TGT-52267)
* 已修正導致無法在預設和非預設工作區的更新UI中顯示選件的問題。 [!DNL Target]現在會顯示來自兩個工作區的選件。 (TGT-52339)
* 修正[!DNL Target]在編輯活動和變更已修改的網站元素時未警告客戶的問題。 (TGT-52100)
* 修正編輯具有臨時優惠方案的優惠方案時，會建立新優惠方案而非更新現有優惠方案的問題。 (TGT-52135)
* 修正將優惠方案移至資料夾時，造成無效裝載錯誤的問題。 (TGT-52325)
* 修正將優惠方案移至資料夾時造成使用者輸入錯誤的問題。 (TGT-52296)
* 為每個活動新增`audienceMetadata`欄位，並確保在編輯活動時已讀取和更新它。 (TGT-51004)

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
