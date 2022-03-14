---
keywords: VEC; 可視化體驗撰寫器; iFrame; 擴充功能; 瀏覽器
description: 瞭解為什麼某些網站在Visual Experience Composer(VEC)中無法可靠開啟。 VEC Helper瀏覽器擴展允許您可靠地在VEC中載入網站。
title: 如何使用Visual Experience Composer(VEC)幫助器擴展？
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 54%

---

# 可視化體驗撰寫器 Helper 擴充功能

的 [!DNL Adobe Target] [!UICONTROL 視覺體驗作曲家] (VEC)GoogleChrome的幫助瀏覽器擴展允許您可靠地載入VEC中的網站，以快速編寫和QA Web體驗。

>[!NOTE]
>
>VEC幫助程式瀏覽器是Chrome擴展。 使用Mozilla Firefox時不需要此擴展。

## 某些網站無法可靠地在 VEC 中開啟的可能原因

* 網站的安全性原則過於嚴格。
* 網站架設在 iFrame 中。
* 網站尚未實作 at.js 資料庫。
* 外部無法存取客戶的 QA 和/或預備網站 (網站為內部網站)。
* 您正在將GoogleChrome 80+與增強的SameSite Cookie實施策略配合使用。 有關詳細資訊，請參見 [最近宣佈的GoogleChrome SameSite Cookie強制策略對VEC和EEC有何影響](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

Chrome的VEC Helper瀏覽器擴展解決了客戶現在依賴的站點載入問題 [!DNL Target] [增強的體驗作曲家](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) 或第三方擴展，如Requestly。

## 使用 VEC Helper 擴充功能的好處

* 所有的 iFrame 爆破標頭 (例如 X-Frame-Options 和 Content-Security-Policy) 會以隱含的方式從網站上移除。不再需要建立複雜的Requestly規則。
* 如果網站上未包含 [!DNL Target] at.js JavaScript 資料庫，您可以使用擴充功能來插入資料庫，這樣就能為網站撰寫體驗。接著可以使用預覽連結來建立活動和保證品質。

   請注意，使用增強的體驗作曲家(EEC)，擴展不會在at.js中插入，但SameSite Cookie功能仍然存在。 要在網頁上注入at.js，請關閉EEC。

* [移動視區](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) 即使沒有 [!UICONTROL 增強的體驗作曲家] （歐共體）。
* 即使客戶的 IT 開發人員尚未在網站上實作 [!DNL Target]，剛接觸 [!DNL Target] 的客戶還是可以利用擴充功能來試驗 [!DNL Target]。
* 管理多位客戶網站與 [!DNL Target] 帳戶的合作夥伴現在擁有一套簡單的機制可支援 VEC 載入工作，而不必在第三方工作中管理多個規則。

## 取得並安裝 VEC Helper 瀏覽器擴充功能

1. 導航到 [Adobe TargetChrome Web儲存中的VEC幫助程式瀏覽器擴展](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak)。
1. 按一下&#x200B;**[!UICONTROL 「新增至 Chrome > 新增擴充功能」]**。
1. 在中開啟VEC [!DNL Target]。
1. 若要使用擴充功能，請在 VEC 或 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)中時，按一下 Chrome 瀏覽器工具列上的 VEC Helper 瀏覽器擴充功能圖示 (![VEC Helper 圖示](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png))。
1. （條件）滑動 **[!UICONTROL 插入目標庫]** 如果網頁尚未包含 [!DNL Target] at.js JavaScript庫。

   下圖顯示已啟用[!UICONTROL 插入 Target 資料庫]設定的 VEC Helper:

   ![VEC helper 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   下圖顯示詢問您是否要在頁面中插入 [!DNL Target] 資料庫以啟用編寫功能的 VEC Helper:

   ![VEC helper 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （條件）滑動 **[!UICONTROL Cookie]** 切換到「開啟」位置以自動添加 `SameSite=None` 屬性瀏覽器修復。

   ![Cookie在VEC幫助程式擴展中切換](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   有關 `SameSite=None` 屬性瀏覽器修復，請參閱「最近宣佈的GoogleChrome SameSite Cookie實施策略如何影響VEC和EEC？」 [疑難排解 Visual Experience Composer 和 Enhanced Experience Composer 相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)中的「最近宣佈的 Google Chrome SameSite Cookie 實施政策如何影響 VEC 和 EEC？」。

## 附註

* 擴充功能中的[!UICONTROL 「插入 Target 資料庫」]標記預設為「關閉」。如果您要在尚未針對 [!DNL Target] 實作的網站上使用 VEC，可以啟用此標記。

   此標誌是全局設定。 VEC 中開啟的所有網站都會啟用或停用此標記。因此，例如，如果將此標誌設定為&quot;on&quot;並開啟已使用at.js實現的網站，則您會收到一條消息，通知您已載入at.js。 Adobe預計，大多數客戶已在其頁面上實施at.js，並使用預設設定「off」。

* 擴展將載入從 [!DNL Target UI] 在 [!UICONTROL 管理>實施]。
* 在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用此擴充功能來插入 at.js 時，您必須另外開啟一個 Chrome 分頁。此 Chrome 分頁必須授權給您建立活動的相同 [!DNL Adobe Experience Cloud] 組織。
* 以下訊息有助於您瞭解:

   * 如果您嘗試使用 VEC 載入網站卻無法載入，系統會顯示訊息，建議您安裝 VEC Helper 瀏覽器擴充功能。
   * 如果網站尚未實作 at.js，VEC 會顯示訊息，建議您安裝擴充功能。
   * 如果擴充功能已啟用且在執行載入工作，當擴充功能插入 at.js 資料庫 (如有必要) 或協助以可靠的方式在 VEC 中開啟網站時，系統會顯示訊息。
