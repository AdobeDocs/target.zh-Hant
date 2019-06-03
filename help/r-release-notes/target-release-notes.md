---
description: 以下版本說明提供最新或即將發行之 Target 版本的功能、增強功能、修正和已知問題等資訊。
keywords: 版本說明
seo-description: 以下版本說明提供最新或即將發行之 Adobe Target 版本的功能、增強功能、修正和已知問題等資訊。
seo-title: Target 版本說明 (發行前)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 3a36b900ac3d24e515be5028ddee3d8f250023c7

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**最近更新: 2019 年 5 月 28 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更。若要檢視關於最新版本的資訊，請參閱 [Target 發行說明](release-notes.md)。視發行的時間點而定，這些頁面上的資訊可能相同或有所不同。

## at. js2.1.0版(2019年月日)

我們很高興宣佈下列令人振奮的功能：js2.1.0：

| 功能/增強功能 | 說明 |
| --- | --- |
| Adobe加入支援 | 「Adobe 選擇加入」是簡化 Adobe 解決方案與同意管理平台整合的方法。<br>如需Adobe選擇加入的詳細資訊，請參閱 [隱私權與通用資料保護規則(GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md))。 |
| 符合業界標準的CSP規範 | at. js不再使用eval()來執行JavaScript。 |
| 用戶端分析記錄 | 可讓客戶完全控制如何將分析資料傳送至Adobe Analytics，不論是在用戶端或伺服器端。 |
| 傳送通知 | 可讓開發人員在使用程式碼轉換體驗時傳送通知，而非使用 `applyOffer()` 或 `applyOffers()`使用。 |
| 縮減檔案大小 | at. js的大小減少了~24%。檔案大小較小可改善頁面載入效能，並減少頁面上下載. js的時間。 |

## [!DNL Target] Standard/Premium 19.5.1 (2019 年 5 月 21 日) {#release-19-5-1-prerelease}

此版本包含下列功能、變更和增強功能:

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

### 功能更新

| 功能/增強功能 | 說明 |
| --- | --- |
| 單一頁面應用程式可視化體驗撰寫器(SPA VEC) | SPA VEC 已改良下列項目，讓您的工作更快更有效率: <ul><li>按一下 SPA 中的動作會醒目顯示將套用該動作之網站上的元素。在檢視下建立的每個 VEC 動作有四個對應的圖示: 資訊、編輯、移動和刪除。此版本中新增的「移動」功能可讓您將動作移動至頁面載入事件，或修改面板中已存在的任何其他檢視。(TGT-33746)</li><li>您可以在 VEC 中的頁面載入前，或甚至頁面完全無法載入時 (例如自訂程式碼無法繼續正常運作) 執行許多動作。無法在網站載入前編輯的動作，都會在 Target UI 中停用。(TGT-33851 和 TGT-34149)</li></ul>如需詳細資訊，請參閱[單頁應用程式 (SPA) 可視化體驗撰寫器](/help/c-experiences/spa-visual-experience-composer.md)。 |

### 增強功能、修正和變更

* 在 VEC 中取消載入頁面後，工具列圖示會正常顯示。如果在完全載入頁面前無法執行特定動作，系統會停用相關工具列圖示。(TGT-33811)

## 行動應用程式可視化體驗撰寫器 (2019 年 5 月 14 日) {#mobile-vec-may14}

| 功能/增強功能 | 說明 |
| --- | --- |
| 行動應用程式可視化體驗撰寫器 (VEC) | 行動應用程式 VEC 可讓您在原生行動應用程式中，自己動手建立活動與個人化內容，不必再經過不斷的開發相依性及應用程式發行週期。<br>如需詳細資訊，請參閱:<ul><li>[行動應用程式可視化體驗撰寫器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - 設定行動應用程式](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - 設定行動應用程式](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[在行動版 VEC 中設定點擊追蹤](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[影片：行動應用程式Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到有關 Target 和其他 Adobe Experience Cloud 解決方案的未來產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
