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
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。

## 公告

請注意下列重要聲明:

* 在2019年月20日，在EMEA、日本和APAC地區升級Adobe Target基礎結構，不再使用不支援TLS1.1或更新版本的舊裝置或網頁瀏覽器收集使用者資料。預計於2019 **年月日針對北美地區地區進行相同升級**。轉移至 TLS 1.2 可改善安全性。您必須逐一瞭解具體資訊，並與IT團隊規劃變更，以便順利轉換。如需詳細資訊，請參閱 [TLS(傳輸圖層安全性)加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
* 從 2019 年 3 月 起，[!DNL Target] 和 [!DNL Adobe Marketing Cloud] 將停止支援 Microsoft Internet Explorer 11。這項變更只會影響 [!DNL Target] 編寫，不影響體驗傳送。請改用 Microsoft Edge 或其他瀏覽器。如需更多資訊，請參閱[支援的瀏覽器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。

## Mobile App Visual Experience Composer(2019年月14日){mobile-loc}

| 功能/增強功能 | 說明 |
| --- | --- |
| 行動應用程式Visual Experience Composer(CMS) | Mobile App CMS可讓您在原生行動應用程式上建立活動和個人化內容，而不需持續開發相依性和應用程式發行週期。<br>如需詳細資訊，請參閱:<ul><li>[行動應用程式可視化體驗撰寫器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - 設定行動應用程式](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - 設定行動應用程式](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[在行動版 VEC 中設定點擊追蹤](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li></ul> |

## [!DNL Target] Standard/Premium19.4.2(2019年月30日) {#release-19-4-2}

此版本包含下列功能、變更和增強功能:

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

### 功能更新

| 功能/增強功能 | 說明 |
| --- | --- |
| [!UICONTROL 可視化體驗撰寫器] | [!UICONTROL Visual Experience Composer] (CMS)包含下列增強功能，讓您提高工作效率和效率：<ul><li>設定點按追蹤時，現在可使用DOM路徑功能。<br>如需詳細資訊，請參閱 [點按追蹤](/help/c-activities/r-success-metrics/click-tracking.md#considerations)。</li><li>使用「樣式」面板可檢視或編輯所選元素的現有樣式值。您也可以新增其他樣式。<br>若要存取「樣式」面板，請從CMS中按一下頁面元素，然後按一下 [!UICONTROL 「編輯] &gt; [!UICONTROL 樣式]」。<br>「樣式」面板會顯示在CMS的右側。面板包含可讓您編輯或新增至選取元素的樣式清單。即時CSS編輯器可讓您檢視變更並新增樣式，如果您習慣使用階層式樣式表(CSS)或從開發人員接收程式碼。<br>如需詳細資訊，請參閱 [](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles)*「視覺體驗撰寫器選項*」中的樣式。</li><li>Rich Text Editor現在支援巢狀HTML元素。<br>HTML規格允許新的組合標籤組合。舊版rich text Editor不支援HTML規格允許的新巢狀內嵌標籤。因此，在CMS中選取的任何巢狀元素都無法正確處理，導致HTML不想要的變更。(TGT-33618)<br>如需詳細資訊，請參閱 [Visual Experience](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#edit-text-html) *Composer選項中的編輯文字/HTML*。</li> |

### 增強功能、修正和變更

* 改善您使用 VEC 刪除資產時的工作流程。已刪除的資產現在會從 [!UICONTROL 選件庫] 和來源 [!DNL Scene7] (如果有的話)移除。刪除的資產不再續顯示於搜尋結果中。(TGT-31981)
* 您現在可以刪除資產資料夾，即使它們包含影像(非空白資料夾)。(TGT-33265)

   以前，您無法從Target影像選件庫([!UICONTROL 選件] &gt; [!UICONTROL 影像選件])刪除非空白資料夾。您會得到「資料夾不是空白的！」通知。在此功能中，我們新增了可讓您執行資料夾刪除的功能，以移除包含任何資產和子資料夾的整個資料夾。此功能也適用於Target UI中的Adobe Experience Cloud資產UI。

   * 可以刪除影像選件庫中的非空白資料夾。如果資料夾中的所有影像未參照於任何活動，則會刪除整個資料夾及其內容。如果在任何活動中參考資料夾內的某些影像，都會刪除所有未參照的影像，但會保留包含這些影像的參考影像和檔案夾。
   * 在影像資產選擇器中演算影像選件變得更快速且更有效率。
   如需詳細資訊，請參閱 [「使用資料庫中的內容](/help/c-experiences/c-manage-content/assets-working.md)」。(TGT-32897)

* 改善「資產」選擇器中影像供應項目的顯示效能。現在顯示和選取影像供應項目會更快更有效率。(TGT-32897)
* 改善在 VEC 中取消載入頁面時處理重新導向至 URL 的效能。(TGT-33815)
* 從「系列選擇器」選取 [!UICONTROL 「建議] 」收集後，您現在必須按一下 [!UICONTROL 「儲存] 」按鈕。此工作流程與其他工作流程一致 [!DNL Target]。(TGT-33205)
* 修正了導致一小組前瞻分析報告傳回0%轉換率而非實際轉換率的問題。(TNT-32125)

## [!DNL Target] Standard/Premium19.4.1(2019年月15日) {#release-19-4-1}

此版本為維護版本，包含下列變更:

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

* 更新 [!DNL Adobe Experience Cloud] UI以反映品牌和產品變更。(TGT-33546、TGT-33272 和 TGT-33331)

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