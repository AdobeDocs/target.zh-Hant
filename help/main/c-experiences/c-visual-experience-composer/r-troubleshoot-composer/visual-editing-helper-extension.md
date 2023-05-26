---
keywords: vec;可視化體驗撰寫器; vec;iframe;擴充功能;瀏覽器;常見問題
description: 探索為什麼有些網站可能無法可靠地在[!UICONTROL 可視化體驗撰寫器] (VEC) 中開啟。 [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能可讓您可靠地在 VEC 內載入網站。
title: 該如何使用 [!UICONTROL Visual Editing Helper]擴充功能？
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 30ad6712d9722854384721ca20d38a605930c4d7
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 100%

---

# [!UICONTROL Visual Editing Helper] 擴充功能

適用於 Google Chrome 的 [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能可讓您可靠地在 [!UICONTROL Adobe Target] [!UICONTROL 可視化體驗撰寫器] (VEC) 內載入網站，以快速撰寫網頁體驗並進行 QA。

>[!IMPORTANT]
>
>這個新的擴充功能會取代之前的 [Target VEC Helper 瀏覽器擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。請參閱該文章頂端的重要注意事項。

## 某些網站可能無法可靠地在 VEC 中開啟的原因

* 網站的安全性原則過於嚴格。
* 網站架設在 iFrame 中。
* 客戶的 QA 或暫存網站無法供外部世界使用 (網站僅供內部使用)。

適用於 Chrome 的 [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能為目前依賴[!DNL Target] [增強型體驗撰寫器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)或協力廠商擴充功能 (例如 Requestly) 的客戶解決網站載入問題。

## 使用 [!UICONTROL Visual Editing Helper] 擴充功能的好處

* 所有 iFrame 失敗的標題 (例如 `X-Frame-Options` 和 `Content-Security-Policy`) 都會以隱含的方式從網站中移除。 不需要建立複雜的 Requestly 規則。
* 如果網頁尚未包含 [!DNL Target] at.js 程式庫，您可以使用此擴充功能來插入此程式庫，這樣就能為網站撰寫體驗。 接著可以使用預覽連結來建立活動及進行 QA。

   使用[增強型體驗撰寫器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)時，此擴充功能不會插入 at.js，但是 SameSite Cookie 功能依然存在。 若要在網頁上插入 at.js，請關閉 EEC。

* [行動檢視區](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)即使沒有[!UICONTROL 增強型體驗撰寫器] (EEC) 還是有受到支援。
* 即使客戶的 IT 開發人員尚未在網站上實作 [!DNL Target]，剛接觸 [!DNL Target] 的客戶還是可以利用擴充功能來試驗 [!DNL Target]。
* 管理多位客戶網站與 [!DNL Target] 帳戶的合作夥伴現在擁有一套簡單的機制可支援 VEC 載入工作，而不必在第三方工作中管理多個規則。

## 取得並安裝 [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能

1. 瀏覽至 Chrome 線上應用程式商店中的 [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}。
1. 按一下「**[!UICONTROL 新增至 Chrome]** > **[!UICONTROL 新增擴充功能]**」。
1. 在 [!DNL Target] 中開啟 VEC。
1. 若要使用此擴充功能，請在 VEC 或 QA 模式中時，按一下 Chrome 瀏覽器工具列上的 [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能圖示 (![Visual Editing 擴充功能圖示](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png))。

   [!UICONTROL Visual Editing Helper] 會在 [!UICONTROL Target] VEC 中開啟網站時自動啟用，以支援撰寫。 此擴充功能沒有任何條件設定。 此擴充功能可自動處理所有設定，包括 SameSite Cookie 設定。

   如需有關 `SameSite=None` 屬性瀏覽器修正的詳細資訊，請參閱[排解可視化體驗撰寫器和增強型體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中的「最近宣布的 Google Chrome SameSite cookie 執行政策對 VEC 和 EEC 有何影響？」。

## 附註

* 對於 [!DNL Target]，此擴充功能會載入最新版的 at.js，這個檔案可從「[!UICONTROL 管理] > [!UICONTROL 實作]」中的 [!DNL Target] UI 取得，而且 at.js 會下載撰寫程式庫。
* 在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用此擴充功能來插入 at.js 時，您必須開啟另一個 Chrome 分頁。 必須向您活動建立所在的相同 [!DNL Adobe Experience Cloud] 組織驗證此 Chrome 分頁。
* 以下訊息有助於您了解：

   * 如果您嘗試使用無法載入的 VEC 載入網站，則會顯示一則訊息，建議您安裝 [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能。
   * 如果網站上尚未實作 at.js 或 alloy.js，則 VEC 中會顯示一則訊息，建議您安裝此擴充功能。
* 如果您嘗試使用新的擴充功能，然後返回[舊擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)，而 [!DNL Target] 無法載入您的網站，請清除所有瀏覽器資料並停用新的擴充功能。

## 常見問題集

### 當擴充功能 (作用中時) 用於 [!DNL Adobe Target] 或 [!UICONTROL Adobe Journey Optimizer] (AJO) 之外時，是否會執行任何操作？

只有當有問題的網站在 [!DNL Adobe] 產品 ([!DNL Target]、[!DNL AJO]) 的 iFrame 中載入時，該擴充功能才會啟動。在此流程之外，該擴充功能不會嘗試新增、移除或修改任何標題，而且該擴充功能不會嘗試在網站內注入任何程式碼。

### 當擴充功能在 [!DNL Adobe Target]VEC 中處於作用中狀態時會採取什麼行動？

當網站載入 [!DNL Adobe] 產品 ([!DNL Target]、[!DNL AJO]) 的 iFrame 中時，擴充功能會在網站上注入程式碼 (和擴充功能整合在一起) 並下載來自 [!DNL Adobe] CDN 的說明檔案，以啟用視覺化撰寫。
