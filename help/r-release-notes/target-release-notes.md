---
description: 以下版本說明提供最新或即將發行之 Target 版本的功能、增強功能、修正和已知問題等資訊。
keywords: 版本說明
seo-description: 這些發行說明提供最新或即將推出之Adobe Target版本的功能、增強功能、修正和已知問題的相關資訊
seo-title: Target 版本說明 (發行前)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 9f1cab87057a7b8803f795c852a7ffe839dd8f1c

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新日期：2019年月28日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更。若要檢視目前版本的資訊，請參閱 [Target發行說明](release-notes.md)。這些頁面的資訊可能是相同的，或者可能不同，視發行時間而定。

## at. js2.1.0版(2019年月日)

我們很高興宣佈下列令人振奮的功能：js2.1.0：

| 功能/增強功能 | 說明 |
| --- | --- |
| Adobe加入支援 | 「Adobe 選擇加入」是簡化 Adobe 解決方案與同意管理平台整合的方法。<br>如需Adobe選擇加入的詳細資訊，請參閱 [隱私權與通用資料保護規則(GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md))。 |
| 符合業界標準的CSP規範 | at. js不再使用eval()來執行JavaScript。 |
| 用戶端分析記錄 | 可讓客戶完全控制如何將分析資料傳送至Adobe Analytics，不論是在用戶端或伺服器端。 |
| 傳送通知 | 可讓開發人員在使用程式碼轉換體驗時傳送通知，而非使用 `applyOffer()` 或 `applyOffers()`使用。 |
| 縮減檔案大小 | at. js的大小減少了~24%。檔案大小較小可改善頁面載入效能，並減少頁面上下載. js的時間。 |

## [!DNL Target] Standard/Premium19.5.1(2019年月21日) {#release-19-5-1-prerelease}

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

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要接收即將推出的Target產品增強功能與其他Adobe Experience Cloud解決方案的進階通知，請註冊Adobe優先產品更新：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
