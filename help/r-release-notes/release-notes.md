---
description: 這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
keywords: 版本說明;發行前
seo-description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
seo-title: Target 版本說明 (最新)
solution: Target
title: Target 版本說明 (最新)
topic: 建議
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 542366ce4c14eab4ee15e3614888f4b335b9a0df

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。

## 公告

請注意下列重要聲明:

* 在2019年月20日，在EMEA、日本和APAC地區升級Adobe Target基礎結構，不再使用不支援TLS1.1或更新版本的舊裝置或網頁瀏覽器收集使用者資料。預計於2019 **年月日針對北美地區地區進行相同升級**。轉移至 TLS 1.2 可改善安全性。您必須逐一瞭解具體資訊，並與IT團隊規劃變更，以便順利轉換。如需詳細資訊，請參閱 [TLS(傳輸圖層安全性)加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
* 從 2019 年 3 月 起，[!DNL Target] 和 [!DNL Adobe Marketing Cloud] 將停止支援 Microsoft Internet Explorer 11。這項變更只會影響 [!DNL Target] 編寫，不影響體驗傳送。請改用 Microsoft Edge 或其他瀏覽器。如需更多資訊，請參閱[支援的瀏覽器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。

## [!DNL Target] Standard/Premium19.5.1(2019年月21日) {#tgt-19-5-1}

此版本包含下列功能、變更和增強功能:

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

### 功能更新

| 功能/增強功能 | 說明 |
| --- | --- |
| 單一頁面應用程式可視化體驗撰寫器(SPA CMS) | SPA VEC 已改良下列項目，讓您的工作更快更有效率: <ul><li>按一下SPA中的動作，會反白顯示將套用此動作的網站上的元素。在「檢視」下建立的每個CMS動作都有個對應圖示：資訊、編輯、移動和刪除。此版本中的新「移動」功能可讓您將動作移至「頁面載入事件」或已存在於修改面板中的任何其他檢視。(TGT-33746)</li><li>您可以在 VEC 中的頁面載入前，或甚至頁面完全無法載入時 (例如自訂程式碼無法繼續正常運作) 執行許多動作。無法在網站載入前編輯的動作，都會在 Target UI 中停用。(TGT-33851 和 TGT-34149)</li></ul>如需詳細資訊，請參閱[單頁應用程式 (SPA) 可視化體驗撰寫器](/help/c-experiences/spa-visual-experience-composer.md)。 |

### 增強功能、修正和變更

* 在 VEC 中取消載入頁面後，工具列圖示會正常顯示。如果在完全載入頁面前無法執行特定動作，系統會停用相關工具列圖示。(TGT-33811)

## Mobile App Visual Experience Composer(2019年月14日){mobile-loc}

| 功能/增強功能 | 說明 |
| --- | --- |
| 行動應用程式Visual Experience Composer(CMS) | Mobile App CMS可讓您在原生行動應用程式上建立活動和個人化內容，而不需持續開發相依性和應用程式發行週期。<br>如需詳細資訊，請參閱:<ul><li>[行動應用程式可視化體驗撰寫器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - 設定行動應用程式](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - 設定行動應用程式](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[在行動版 VEC 中設定點擊追蹤](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[影片：行動應用程式Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](../r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參閱 [Experience Cloud發行說明](https://marketing.adobe.com/resources/help/en_US/whatsnew/)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的Target產品增強功能與其他Adobe Experience Cloud解決方案的進階通知，請註冊Adobe優先產品更新：<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 近期發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |