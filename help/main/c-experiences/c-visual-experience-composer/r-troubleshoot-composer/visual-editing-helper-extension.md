---
keywords: VEC; 可視化體驗撰寫器; iFrame; 擴充功能; 瀏覽器
description: 探索為何某些網站可能無法可靠地在 [!UICONTROL 可視化體驗撰寫器] (VEC)。 此 [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能可讓您在VEC內以可靠的方式載入網站。
title: 如何使用 [!UICONTROL Visual Editing Helper] 擴充功能？
feature: Visual Experience Composer (VEC)
source-git-commit: 70ab1ec7f5313d8c1f8ecaa9b436d95919cf479a
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 30%

---

# [!UICONTROL Visual Editing Helper] 擴充功能

此 [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] Google Chrome的瀏覽器擴充功能可讓您以可靠的方式在內載入網站 [!UICONTROL Adobe Target] [!UICONTROL 可視化體驗撰寫器] (VEC)來快速撰寫體驗和保證體驗品質。

>[!IMPORTANT]
>
>此新擴充功能取代先前的 [Target VEC Helper瀏覽器擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

## 某些網站無法可靠地在 VEC 中開啟的可能原因

* 網站的安全性原則過於嚴格。
* 網站架設在 iFrame 中。
* 外部無法使用客戶的QA或預備網站（網站為內部網站）。

此 [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] Chrome的瀏覽器擴充功能解決了客戶現在依賴的網站載入問題 [!DNL Target] [增強體驗撰寫器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) 或協力廠商擴充功能，例如Requestly。

## 使用 [!UICONTROL Visual Editing Helper] 擴充功能

* 所有iframe爆破標頭，例如 `X-Frame-Options` 和 `Content-Security-Policy`，則會以隱含的方式從網站中移除。 不需要建立複雜的Requestly規則。
* 如果網站上未包含 [!DNL Target] at.js 資料庫，您可以使用擴充功能來插入資料庫，這樣就能為網站撰寫體驗。接著可以使用預覽連結來建立活動和保證品質。

請注意，使用 [增強體驗撰寫器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)，擴充功能不會插入at.js，但仍有SameSite Cookie功能存在。 若要在網頁上插入at.js，請關閉EEC。

* [行動檢視區](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) 即使沒有 [!UICONTROL 增強體驗撰寫器] (EEC)。
* 即使客戶的 IT 開發人員尚未在網站上實作 [!DNL Target]，剛接觸 [!DNL Target] 的客戶還是可以利用擴充功能來試驗 [!DNL Target]。
* 管理多位客戶網站與 [!DNL Target] 帳戶的合作夥伴現在擁有一套簡單的機制可支援 VEC 載入工作，而不必在第三方工作中管理多個規則。

## 取得並安裝 [!UICONTROL Visual Editing Helper] 瀏覽器延伸功能

1. 導覽至 [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] Chrome線上應用程式商店中的瀏覽器擴充功能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}。
1. 按一下 **[!UICONTROL 新增至Chrome]** > **[!UICONTROL 新增擴充功能]**.
1. 在中開啟VEC [!DNL Target].
1. 若要使用擴充功能，請按一下 [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能圖示( ![可視化編輯擴充功能圖示](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) )，在VEC或QA模式中時，位於Chrome瀏覽器的工具列中。

   此 [!UICONTROL Visual Editing Helper] 會在 [!UICONTROL 目標] VEC可強化編寫功能。 擴充功能沒有任何條件式設定。 擴充功能會自動處理所有設定，包括SameSite Cookie設定。

   如需 `SameSite=None` 屬性瀏覽器修正，請參閱「最近宣佈的Google Chrome SameSite Cookie實作原則如何影響VEC和EEC？」 [排解視覺體驗撰寫器和增強體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中的「最近宣佈的 Google Chrome SameSite Cookie 實施政策如何影響 VEC 和 EEC？」。

## 附註

* 針對 [!DNL Target]，擴充功能會載入最新版的at.js(可透過 [!DNL Target] 中的UI [!UICONTROL 管理] > [!UICONTROL 實作] 和at.js會下載編寫程式庫。
* 在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用此擴充功能來插入 at.js 時，您必須另外開啟一個 Chrome 分頁。此Chrome分頁必須驗證給相同的 [!DNL Adobe Experience Cloud] 您建立活動的組織。
* 以下訊息有助於您瞭解:

   * 如果您嘗試使用無法載入的VEC載入網站，系統會顯示訊息，建議您安裝 [!UICONTROL Visual Editing Helper] 瀏覽器擴充功能。
   * 如果網站上尚未實作at.js或alloy.js,VEC中會顯示訊息，建議您安裝擴充功能。

## 有關此功能的更多幫助

* [疑難排解可視化體驗撰寫器和增強體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)
* [疑難排解可視化體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md)
* [疑難排解增強體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md)



