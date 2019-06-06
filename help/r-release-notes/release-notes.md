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
source-git-commit: 3a498a99e333acc92651eb94592af87cfc34c6e1

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。

## 公告

請注意下列重要聲明:

* 在 2019 年 2 月 20 日，EMEA、日本和 APAC 區域中的 Adobe Target 基礎架構已升級，不再從使用較舊裝置或不支援 TLS 1.1 或更新版本的網頁瀏覽器的一般使用者收集資料。我們已規劃於 **2019 年 4 月 1 日** 在北美區域進行這項相同的升級。轉移至 TLS 1.2 可改善安全性。請務必詳閱詳細資訊，並與 IT 團隊針對變更進行規劃，以順利轉移。如需詳細資訊，請參閱 [TLS (傳輸層安全性) 加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
* 從 2019 年 3 月 起，[!DNL Target] 和 [!DNL Adobe Marketing Cloud] 將停止支援 Microsoft Internet Explorer 11。這項變更只會影響 [!DNL Target] 編寫，不影響體驗傳送。請改用 Microsoft Edge 或其他瀏覽器。如需更多資訊，請參閱[支援的瀏覽器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。

## at. js2.1.0版(2019年月日)

我們很高興宣佈下列令人振奮的功能：js2.1.0：

| 功能/增強功能 | 說明 |
| --- | --- |
| Adobe加入支援 | 「Adobe 選擇加入」是簡化 Adobe 解決方案與同意管理平台整合的方法。<br>如需Adobe選擇加入的詳細資訊，請參閱 [隱私權與通用資料保護規則(GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md))。 |
| 符合業界標準的CSP規範 | at. js不再使用eval()來執行JavaScript。 |
| 用戶端分析記錄 | 可讓客戶完全控制如何將分析資料傳送至Adobe Analytics，不論是在用戶端或伺服器端。<br>如需詳細資訊，請參閱 [在實施前](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) 登入 *客戶端的Analytics*。 |
| 傳送通知 | 可讓開發人員在使用程式碼轉換體驗時傳送通知，而非使用 `applyOffer()` 或 `applyOffers()`使用。<br>如需詳細資訊，請查看 [adobe. target. sendNotifications(選項)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)。 |
| 縮減檔案大小 | at. js的大小減少了~24%。檔案大小較小可改善頁面載入效能，並減少頁面上下載. js的時間。 |
| at. js文件更新 | 如需因at. js2.1.0版而更新的所有文章的完整清單，請參閱 [說明文件變更](/help/r-release-notes/doc-change.md)中的2019年月日。 |

## [!DNL Target] Standard/Premium 19.5.1 (2019 年 5 月 21 日) {#tgt-19-5-1}

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

### 功能更新

| 功能/增強功能 | 說明 |
| --- | --- |
| 單一頁面應用程式可視化體驗撰寫器(SPA VEC) | SPA VEC 已改良下列項目，讓您的工作更快更有效率: <ul><li>按一下 SPA 中的動作會醒目顯示將套用該動作之網站上的元素。在檢視下建立的每個 VEC 動作有四個對應的圖示: 資訊、編輯、移動和刪除。此版本中新增的「移動」功能可讓您將動作移動至頁面載入事件，或修改面板中已存在的任何其他檢視。(TGT-33746)</li><li>您可以在 VEC 中的頁面載入前，或甚至頁面完全無法載入時 (例如自訂程式碼無法繼續正常運作) 執行許多動作。無法在網站載入前編輯的動作，都會在 Target UI 中停用。(TGT-33851 和 TGT-34149)</li></ul>如需詳細資訊，請參閱[單頁應用程式 (SPA) 可視化體驗撰寫器](/help/c-experiences/spa-visual-experience-composer.md)。 |

### 增強功能、修正和變更

* 在 VEC 中取消載入頁面後，工具列圖示會正常顯示。如果在完全載入頁面前無法執行特定動作，系統會停用相關工具列圖示。(TGT-33811)

## 行動應用程式可視化體驗撰寫器 (2019 年 5 月 14 日) {#mobile-vec-may14-2}

| 功能/增強功能 | 說明 |
| --- | --- |
| 行動應用程式可視化體驗撰寫器 (VEC) | 行動應用程式 VEC 可讓您在原生行動應用程式中，自己動手建立活動與個人化內容，不必再經過不斷的開發相依性及應用程式發行週期。<br>如需詳細資訊，請參閱:<ul><li>[行動應用程式可視化體驗撰寫器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - 設定行動應用程式](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - 設定行動應用程式](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[在行動版 VEC 中設定點擊追蹤](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[影片：行動應用程式Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

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
| Adobe 優先順序產品更新清單 | 若要收到有關 Target 和其他 Adobe Experience Cloud 解決方案的未來產品增強功能的提前通知，請註冊 Adobe 優先產品更新:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將推出的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |