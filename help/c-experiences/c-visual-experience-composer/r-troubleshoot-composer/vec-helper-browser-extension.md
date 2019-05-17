---
description: 提供使用 Target 可視化體驗撰寫器 (VEC) Helper 瀏覽器擴充功能，在 VEC 內以可靠的方式載入網站來迅速撰寫體驗和保證體驗品質的資訊。
keywords: VEC; 可視化體驗撰寫器; iFrame; 擴充功能; 瀏覽器
seo-description: 提供使用 Adobe Target 可視化體驗撰寫器 (VEC) Helper 瀏覽器擴充功能，在 VEC 內以可靠的方式載入網站來迅速撰寫體驗和保證體驗品質的資訊。
seo-title: Adobe Target 可視化體驗撰寫器 (VEC) Helper 擴充功能
solution: Target
title: 可視化體驗撰寫器 Helper 擴充功能
topic: Standard
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 可視化體驗撰寫器 Helper 擴充功能

Google Chrome 的 [!DNL Adobe Target] 可視化體驗撰寫器 (VEC) Helper 瀏覽器擴充功能可讓您在 VEC 內以可靠的方式載入網站，來迅速撰寫體驗和保證體驗品質。

某些網站無法可靠地在 VEC 中開啟的可能原因:

* 網站的安全性原則過於嚴格。
* 網站架設在 iFrame 中。
* 網站尚未實作 at.js 資料庫。
* 外部無法存取客戶的 QA 和/或預備網站 (網站為內部網站)。

Chrome 的 VEC Helper 瀏覽器擴充功能解決了客戶現依賴 [!DNL Target] [!UICONTROL 增強體驗撰寫器]或第三方擴充功能 (例如 Requestly) 會遇到的網站載入問題。

使用 VEC Helper 擴充功能的好處:

* 所有的 iFrame 爆破標頭 (例如 X-Frame-Options 和 Content-Security-Policy) 會以隱含的方式從網站上移除。不再需要建立複雜的 Requestly 規則即可完成相同工作。
* 如果網站上未包含 [!DNL Target] at.js JavaScript 資料庫，您可以使用擴充功能來插入資料庫，這樣就能為網站撰寫體驗。接著可以使用預覽連結來建立活動和保證品質。
* 即使沒有[!UICONTROL 增強體驗撰寫器] (EEC)，亦支援行動檢視區。
* 即使客戶的 IT 開發人員尚未在網站上實作 [!DNL Target]，剛接觸 [!DNL Target] 的客戶還是可以利用擴充功能來試驗 [!DNL Target]。
* 管理多位客戶網站與 [!DNL Target] 帳戶的合作夥伴現在擁有一套簡單的機制可支援 VEC 載入工作，而不必在第三方工作中管理多個規則。

## 取得並安裝 VEC Helper 瀏覽器擴充功能

1. 導覽至Chrome Web Store中 [的Adobe Target CMS Helper瀏覽器延伸模組](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak)。
1. 按一下[!UICONTROL 「新增至 Chrome &gt; 新增擴充功能」]。
1. 若要使用擴充功能，請在 VEC 或 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)中時，按一下 Chrome 瀏覽器工具列上的 VEC Helper 瀏覽器擴充功能圖示 (![VEC Helper 圖示](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png))。

下圖顯示啓用 [!UICONTROL 「插入目標程式庫」] 設定的CMS Helper：

![CMS協助工具1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

下圖顯示CMS Helper詢問您是否要在頁面中插入 [!DNL Target] 程式庫以啓用編寫：

![CMS協助工具2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

## 附註

* 實作必須使用 [!DNL Target] at.js 資料庫。您無法將 mbox.js 實作用於擴充功能。
* 擴充功能中的[!UICONTROL 「插入 Target 資料庫」]標記預設為「關閉」。如果您要在尚未針對 [!DNL Target] 實作的網站上使用 VEC，可以啟用此標記。

   請注意，此標記為全域設定。VEC 中開啟的所有網站都會啟用或停用此標記。因此，假如您將此標記設為「開啟」，然後開啟已使用 at.js 實作的網站，您會收到一則訊息，通知您 at.js 已載入。我們預計大部分客戶都會在網頁上實作 at.js，且都會使用預設設定 (即「關閉」)。

* 此擴充功能會載入最新版本的 at.js (由 [!DNL Target UI] 中的[!UICONTROL 「設定 &gt; 實作」]提供)。
* 在 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)下使用此擴充功能來插入 at.js 時，您必須另外開啟一個 Chrome 分頁。此 Chrome 分頁必須授權給您建立活動的相同 [!DNL Adobe Experience Cloud] 組織。
* 以下訊息有助於您瞭解:

   * 如果您嘗試使用 VEC 載入網站卻無法載入，系統會顯示訊息，建議您安裝 VEC Helper 瀏覽器擴充功能。
   * 如果網站尚未實作 at.js，VEC 會顯示訊息，建議您安裝擴充功能。
   * 如果擴充功能已啟用且在執行載入工作，當擴充功能插入 at.js 資料庫 (如有必要) 或協助以可靠的方式在 VEC 中開啟網站時，系統會顯示訊息。