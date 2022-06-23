---
keywords: at.js版本；at.js版本；發行說明
description: 查看有關每個版本Adobe更改的詳細資訊 [!DNL Target] at.js JavaScript庫。
title: at.js的每個版本中包含什麼？
feature: at.js
role: Developer
exl-id: ec1f1459-d539-4eac-a8f1-33a2d4910dec
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '4570'
ht-degree: 86%

---

# at.js 版本詳細資料

有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。

>[!IMPORTANT]
>
>目標團隊支援兩個at.js 1。*x* 與 at.js 2.*x* 之間的對應。請升級到at.js的任一主版本的最新更新，以確保您正在運行受支援的版本。
>
>中的標籤 [Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) 是升級at.js的首選方法。 擴展開發人員不斷向其擴展添加新功能，並經常修復錯誤。 這些更新被打包到擴展的新版本中，並在 [!DNL Adobe Experience Platform] 編錄為升級。 有關詳細資訊，請參見 [擴展升級](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/extension-upgrade.html) 的 *標籤概述* 的子菜單。

## at.js 2.9.0 版 (2022 年 5 月 27 日)

* 新增的「[使用者代理用戶端提示](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/)」支援。
* 修正了同一個頁面上多個 mbox 請求有不同印象 ID 的問題。

## at.js 2.8.1 版 (2022 年 1 月 28 日)

* 已修正以下問題：`pageLoad` 在[!UICONTROL 裝置上決策] (ODD) 混合執行模式中未對應到 target-global-mbox。
* 已修正 mbox 要求的分析詳細資料問題。
* 已升級 dev 相依項目，修正安全漏洞。

## at.js 2.8.0 版 (2022 年 1 月 7 日)

[!DNL Target] at.js JavaScript 程式庫現在會收集功能使用情況和效能遙測資料。不會收集個人資料。可透過將 `targetGlobalSettings` 中的 `telemetryEnabled` 設定為 False，選擇退出此功能。如需詳細資訊，請參閱 [targetGlobalSettings 中的 telemetryEnabled](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。

## at.js 2.7.0 版 (2021 年 10 月 28 日)

此版本包含下列增強功能：

* 新增 [Web 元件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)的支援。在自訂元素及其內部元素上建立和測試個人化體驗和選件，必須有此版本的 at.js。此功能包含在 [!DNL Target Standard/Premium] 21.10.5 版。

## at.js 1.8.3（2021年9月21日） {#183}

此版本包含以下更改：

* 已刪除 `reactor-window` 和 `reactor-document` [!DNL Adobe Experience Platform Launch] 模組以確保 [!DNL Platform Launch] 正確為那些 `window.default` 或 `document-default` 的下界。
* at.js 1.8.3現在顯式集 `Samesite=None` 和 `Secure` 以確保正確設定第三方域cookie。

## at.js 2.6.1 (2021 年 8 月 16 日)

* 當使用裝置上決策功能時，發生「沒有適用於混合模式的緩存成品」的錯誤修正。

## at.js 2.6.0 (2021 年 7 月 16 日)

* 當 at.js 設定 `secureOnly` 設為 `true` 時，為 Cookie 新增安全屬性。
* 現在可以在使用 `triggerView()` 時使用回應 Token。
* 修正了與 `CONTENT_RENDERING_NO_OFFERS` 事件相關的問題。現在，只要沒有從 [!DNL Target] 傳回內容，就會正確觸發此事件。
* 使用 `prefetch` 請求時會正確傳回 [!DNL Anlytics for Target] (A4T) 點擊量度詳細資料。
* UUID 產生不再使用 `Math.random()`，但須依賴 `window.crypto`。
* `sessionId` Cookie 過期在每次網路呼叫時會正確延長。
* [!UICONTROL 單頁應用程式] (SPA) 檢視快取初始化現在可以正確處理並接受 `viewsEnable` 設定。

## at.js 2.5.0（2021年5月13日）

此 at.js 版本包含下列增強功能和變更：

* [針對 at.js 的裝置上決策](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/on-device-decisioning/)支援。
* [預覽連結](/help/main/c-activities/c-activity-qa/activity-qa.md)對 Automated Personalization 活動的支援

此版本也會移除對 Microsoft Internet Explorer 10 和更高版本的支援。

## at.js 2.4.1 (2021 年 3 月 23 日)

此 at.js 版本為維護版本，包含下列增強功能和修正：

* 已修正 `targetPageParams` 包含在 mbox 要求中的問題。 `targetPageParams` 應該只能包含在 `pageLoad` 要求中。 (TNT-40247)
* 在中引用的優化窗口和文檔全局 [!DNL Adobe Experience Platform] 擴展。 (TNT-37124)

## at.js 2.4.0 (2021 年 1 月 14 日)

此 at.js 版本為維護版本，包含下列修正：

* 新增對傳送 API customerId 的統一設定檔／平台 ID 支援。
* 修正無效樣式標籤插入。

## at.js 2.3.3（2020年11月13日）

此 at.js 版本為維護版本，包含下列修正：

* 已修復與mbox clacking和A4T相關的問題。 按一下0n後，Target使用正確的mbox和mbox參數觸發了Delivery API調用。 但是，SDID與 [!DNL Analytics] 呼叫，所以沒有拼接和轉換。 (TNT-38372)

## at.js 2.3.2 (2020 年 7 月 24 日)

此 at.js 版本為維護版本，包含下列修正：

* 修正指令碼或程式碼新增預設屬性至視窗或檔案時的錯誤。

## at.js 1.8.2（2020年6月15日）

此 at.js 版本為維護版本，包含下列修正：

* 修正使用 CNAME 和 Edge Override (at.js 1) 時的問題。*x* 可能會錯誤建立伺服器網域，導致請 [!DNL Target] 請求失敗。(TNT-35064)

## at.js 2.3.1版（2020年6月15日）

此 at.js 版本為維護版本，包含下列增強功能和修正：

* 透過 [targetGlobalSettings](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) 將 `deviceIdLifetime` 設定設為可覆寫。(TNT-36349)
* 修正使用 CNAME 和 Edge Override (at.js 2) 時的問題。*x* 可能會錯誤建立伺服器網域，導致請 [!DNL Target] 請求失敗。(TNT-35065)
* 修正使用 [!DNL Target] 擴充功能 v2 和 [!DNL Adobe Analytics] [!DNL Launch]擴充功能時，[!DNL Target] 延遲 [!DNL Analytics]`sendBeacon` 呼叫的問題。(TNT-36407、TNT-35990、TNT-36000)

## at.js 版本 2.3.0 (2020 年 3 月 25 日)

此 at.js 版本為維護版本，包含下列增強功能和修正：

* 支援在應用已交付的目標提供時，將內容安全策略設定為附加到頁DOM的SCRIPT和STYLE標籤上的不可用項。 客戶可以設定 `targetGlobalSettings.cspScriptNonce` 和 `targetGlobalSettings.cspStyleNonce` 以便at.js可以在應用的優惠中設定相應的指令碼和樣式標籤。 請參閱  [目標全局設定](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) 的子菜單。
* 使用Google關閉編譯器編譯at.js(用於Google標籤管理器部署)時，已修復問題。
* 已從中更名at.js檢查cookie `check` 至 `at_check` 以避免與客戶的實施發生衝突。

## at.js 版本 1.8.1 (2020 年 3 月 25 日)

此 at.js 版本為維護版本，包含下列增強功能和修正：

* 已從中更名at.js檢查cookie `check` 至 `at_check` 以避免與客戶的實施發生衝突。

## at.js 2.2.0 版 (2019 年 10 月 10 日)

此版本的at.js包括以下增強和修復：

* 修復了在頁元素上不存在Adobe Analytics代碼時，按一下跟蹤未報告目標分析(A4T)中的轉換的問題。
* 在網頁上同時使用Experience CloudID服務(ECID)v4.4和at.js 2.2時，效能得到改善。
* 之前，ECID 曾進行兩次封鎖呼叫，之後 at.js 才能擷取體驗。 這已簡化為單一呼叫，可大幅提升效能。
* 已修復不正確的預取視圖處理，其中預設優惠中的事件令牌未包括在發送的通知中。

   >[!NOTE]
   >
   >將ECID擴展升級到v4.4以利用此效能增強。

* at.js 2.2版還提供了名為 `serverState`。 當實現Target的混合整合時，可使用此設定來優化頁面效能。 混合整合意指您在用戶端上同時使用 at.js v2.2+ 和伺服器端的傳送 API 或 Target SDK 來傳送體驗。`serverState` 讓 at.js v2.2+ 能夠直接從伺服器端擷取並傳回至用戶端的內容套用體驗，做為所提供頁面的一部分。如需詳細資訊，請參閱 [targetGlobalSettings](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) 中的 「serverState」。

## at.js 1.8.0 版 (2019 年 10 月 10 日)

此版本的at.js包括以下增強和修復：

* 在網頁上同時使用Experience CloudID服務(ECID)v4.4和at.js 1.8時，效能得到改善。
* 之前，ECID 曾進行兩次封鎖呼叫，之後 at.js 才能擷取體驗。 這已簡化為單一呼叫，可大幅提升效能。

>[!NOTE]
>
>將ECID擴展升級到v4.4以利用此效能增強。

## at.js 版本 2.1.1 (2019 年 7 月 24 日)

此 at.js 版本為維護版本，包含下列增強功能和修正:

(括號內的問題編號供 Adobe 內部使用。)

* 修正在可視化體驗撰寫器 (VEC) 的目標與設定頁面上使用點擊追蹤量度時，導致多個指標引發的問題。(TNT-32812)
* 修正導致 `triggerView()` 無法多次呈現選件的問題。(TNT-32780)
* 修正 `triggerView()` 的問題，確保要求包含 Marketing Cloud ID (MCID) 資訊。(TNT-32776)
* 修正在即使沒有已儲存的視圖時，仍阻止 `triggerView()` 通知引發的問題。(TNT-32614)
* 修正由於使用 decodeURIcomponent 而導致錯誤的問題，在 URL 包含故障的查詢字串參數時會造成問題。(TNT-32710)
* 在透過 `Navigator.sendBeacon()` API 傳送的傳送要求內容中，指標標幟現已設定為「true」。(TNT-32683)
* 修正 Recommendations 選件無法在一些客戶的網站上顯示的問題。客戶可以看到傳送 API 呼叫中的選件內容，但網站上未套用該選件。(TNT-32680)
* 修正導致多個體驗中點擊追蹤無法如運期般運作的問題。(TNT-32644)
* 修正在無法呈現第一個量度後，阻止 at.js 套用第二個量度的問題。(TNT-32628)
* 修正使用 `targetPageParams` 函數傳送 `mboxThirdPartyId` 時發生的問題，導致要求裝載無法出現於查詢參數或要求裝載中。(TNT-32613)
* 修正導致基於 Chromium 的瀏覽器 (包括 Google Chrome) 封鎖顯示和點按通知回應的問題。(TNT-32290)

## at.js version 2.1.0 (2019 年 6 月 3 日)

此版本包含下列功能和增強功能:

* **Adobe 選擇加入支援**: Adobe 選擇加入是簡化 Adobe 解決方案與同意管理平台整合的方法。如需 Adobe 選擇加入的詳細資訊，請參閱[隱私權與一般資料保護規範 (GDPR)](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/)。

* **符合 CSP 產業標準**: at.js 不再使用 eval() 執行 JavaScript。

* **用戶端 Analytics 記錄**: 無論是在用戶端或伺服器端，皆可讓客戶完全掌控要以何種方式將分析資料傳送至 Adobe Analytics。

   如需詳細資訊，請參閱&#x200B;*實作之前*&#x200B;中的[用戶端 Analytics 記錄](/help/main/c-integrating-target-with-mac/a4t/before-implement.md#client-side)。

* **傳送通知**: 可讓開發人員在透過體驗的程式碼 (而不是透過 `applyOffer()` 或 `applyOffers()`) 呈現體驗時傳送通知。

   如需詳細資訊，請參閱 [adobe.target.sendNotifications(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-sendnotifications-atjs-21/)。

* **at.js 的大小約縮小了 24%**: at.js 的大小約縮小了 24%。較小的檔案大小可改善頁面載入效能，並縮短在頁面上載入 at.js 的時間。

## at.js 版本 2.0.1 (2019 年 3 月 19 日)

此為維護版本，包含下列增強功能和修正:

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

* 修正 DOM 輪詢程式碼中導致某些客戶遇到 JavaScript 例外狀況的的競爭條件。(TNT-31869)
* 呈現的視圖已與點擊追蹤事件處理常式脫鉤的通知。起初，如果屬於某個呈現視圖的點擊事件處理常式無法附加，Target 並不會傳送通知。現在，甚至在找不到點擊元素時，Target 也會傳送視圖通知。(TNT-31969)
* 修正導致 request-succeeded 事件重新導向標幟一律設為 true 的問題。(TNT-31907)
* 修正導致 VEC 重新排列動作記錄為成功 (甚至在元素遺失時) 的問題。(TNT-31924)
* 修正導致某些客戶的通知不包含企業權限屬性 Token 的問題。(TNT-31999)

## at.js 版本 1.7.1 (2019 年 3 月 19 日)

此為維護版本，包含下列修正:

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

* 修正 DOM 輪詢程式碼中導致某些客戶遇到 JavaScript 例外狀況的的競爭條件。(TNT-31869)

## at.js 版本 2.0.0 {#at-js-200}

at.js 2.x 提供豐富的功能組合，讓貴公司能以新世代用戶端技術為基礎進行個人化。本次的新版本著重於升級 at.js，進而與單一頁面應用程式 (SPA) 產生和諧互動。

以下是幾個使用 at.js 2.x 特有 (舊版未提供) 的優點:

* 可以在頁面載入時將所有選件加入快取，把多次伺服器呼叫減少為一次。
* 大幅改善一般使用者在網站上的體驗，因為選件能透過快取立即顯示，避免傳統伺服器呼叫引發的延遲時間。
* 只要編寫一行程式碼以及請開發人員設定一次，行銷人員就能透過單一頁面應用程式上的可視化體驗撰寫器 (VEC) 建立及執行 A/B 和體驗 (XT) 活動。

at.js 2.x 引進以下新函數:

* getOffers()
* applyOffers()
* triggerView()

導入 at.js 2.x 後，以下函數已遭到淘汰:

* mboxCreate()
* mboxDefine
* registerExtension()

如需詳細資訊，請參閱[從 at.js 1.x 升級為 at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) 與 [at.js 函數](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-functions/)。

>[!NOTE]
>
>如果您需要[一般資料保護規範](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/) (GDPR) 的 Adobe 選擇加入支援，目前必須使用 at.js 1.7.0。

## at.js 版本 1.7.0 {#at-js-170}

at.js 1.7.0 提供 Adobe 選擇加入支援。「Adobe 選擇加入」是簡化 Adobe 解決方案與同意管理平台整合的方法。

如需 Adobe 選擇加入的詳細資訊，請參閱[隱私權與一般資料保護規範 ](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/) (GDPR)。

此版本也修正 Target 可能將重新導向 URL 參數覆寫為來自重新導向 URL 之參數的問題。

>[!NOTE]
>
>如果您需要 GDPR 的 Adobe 選擇加入支援，目前必須使用 at.js 1.7.0 或 2.1.0。<br>如需所有版本的清單，請參閱 [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)。

## at.js 版本 1.6.4 {#at-js-164}

at.js 1.6.4 維護版本解決下列問題:

* 修正 Microsoft Internet Explorer 11 中導致套用重複選件的競爭條件顯現。

## at.js 版本 1.6.3 {#section_484A56774E004282B98FFFF851E4E670}

at.js 1.6.3 包含下列修正和增強功能:

* 從現在開始，當選取器含有開頭為數字、兩個連字號或連字號加數字 (如 #-123) 的 ID 或 CSS 類別時，將會逸出 CSS。(TNT-31061)
* 修正 at.js 1.6.2 導入的問題，亦即將來自不同活動的可視化體驗撰寫器 (VEC) 選件套用至同一個 CSS 選取器時，不會遵守活動優先順序。(TNT-31052)
* 修正在缺少承諾原生支援的環境中讓承諾逾時時發生的問題。(TNT-30974)
* 系統現在能透過內容呈現失敗事件正確擷取問題及回報。先前，系統可能會將 JavaScript 回報為成功執行，即使情況並非如此。(TNT-30599)

## at.js 版本 1.6.2 {#section_88BE2F69943D4280B8170F377886B58E}

此維護版本解決下列問題:

* 修正導致部分客戶網站無限「非同步」迴圈的問題。

>[!IMPORTANT]
>
>此外，at.js 1.6.2 版也包含 1.6.1 和 1.6.0 版的所有增強功能和修正。這兩個版本已無法下載。如果使用 1.6.1 或 1.6.0，建議升級至 1.6.2 版

at.js 1.6.1 版包含下列增強功能和修正:

* at.js 1.6.0 修正造成在 Microsoft Internet Explorer 11 中複製建議體驗的問題。(TNT-30593)
* at.js 現在會確保 Edge 覆寫邏輯檢查是否存在 Edge 叢集 Cookie，避免使用者在工作階段躍過 Edge 時有不同 Edge 編號。(TNT-30563)
* 修正 HTML 內容包含無效 JS 程式碼時，at.js 無法執行後續動作的問題。at.js 現在會記錄錯誤，並正確進行後續動作。(TNT-30546)
* 變更導致在重新導向頁面重新授權重新導向活動時，有例外情況。(TNT-30532)
* 修正正確要求逾時無法自 getOffer() API 要求傳播的問題。(TNT-30498)
* 修正 at.js 1.6.0 在使用檔案通訊協定時，無法儲存 Cookie 的問題。(TNT-30454)
* 修正使用 Analytics for Target (A4T) 時，並非所有體驗均隨重新導向一併傳送的問題。(TNT-30444)
* 修正造成在 Target 呼叫成功後頁面隱藏的問題。(TNT-30358)

at.js 1.6.0 版包含下列增強功能和修正:

* Analytics for Target (A4T) 整合現在自動支援重新導向選件。已移除用戶端解決方案。(TNT-30247)
* 現在預設啟用用戶端 Edge 路由傳送。(TNT-30261)
* 修正動作間有相依性時，進行可視化體驗撰寫器 (VEC) 動作的問題。(TNT-30248)

## at.js 版本 1.5.0 {#section_128C6761884C4DA8AE50D6A605FF6F55}

at.js 版本 1.5.0 現已可用。

* `at-request-succeeded` 事件的詳細資訊內含重新導向旗標。這個旗標是用來判斷頁面是否會重新導向至其他 URL。如果您想知道該 URL，請訂閱 `at-content-rendering-redirect`。(TNT-29834)
* 修正 `window.targetGlobalSettings.enabled` 在執行階段例外設為 false 時會失敗的問題。(TNT-29829)
* 修正使用自訂程式碼觸發全域 mbox 要求，以及使用主體隱藏時，造成頁面在可視化體驗撰寫器 (VEC) 載入失敗的問題。(TNT-29795)
* 新增對 `screenOrientation`、`devicePixelRatio` 和 `webGLRenderer` 的支援。這些新 Target 要求參數可用於偵測 iPhone X 和其他新型裝置。如需詳細資訊，請參閱[行動](/help/main/c-target/c-audiences/c-target-rules/mobile.md#concept_2A794199DC1A4D349FFFBC7DCF1FEB89)。(TNT-29781)
* 修正偶爾未傳送 Adobe Audience Manager (AAM) 位置提示的問題。(TNT-29695)
* 若瀏覽器支援 at.js 1.5.0，at.js 1.5.0 會切換為 MutationObserver 進行選取器輪詢。at.js 1.0.0 以前的版本使用 MutationObserver polyfill，已證實會造成問題。為避免 polyfill 問題，版本 1.5.0 使用下列虛擬程式碼，決定要使用哪個排程機制:

   ```
   if MutationObserver is supported
     scheduler = MutationObserver
   else if document is visible
     scheduler = requestAnimationFrame
   else
     scheduler = setTimeout
   ```

## at.js 版本 1.3.0 {#section_24EAAE1CFA814EF8B19E61842F4D8321}

at.js 1.3.0 版現已可用。

* 下列新事件可協助追蹤、除錯和自訂與 at.js 的互動:

   * LIBRARY_LOADED
   * REQUEST_START
   * CONTENT_RENDERING_START
   * CONTENT_RENDERING_NO_OFFERS
   * CONTENT_RENDERING_REDIRECT

   如需詳細資訊，請參閱 [at.js 自訂事件](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/)。

* 您可以使用來自資料提供者的其他參數來擴大 at.js 要求。資料提供者應新增至 `window.targetGlobalSettings` 下的 `dataProviders key`。

   如需詳細資訊，請參閱[資料提供者](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。

* at.js 要求現在使用 GET，但是當 URL 大小超過 2048 字元時，它會切換為使用 POST。有一個名為 `urlSizeLimit` 的新屬性，您可以在必要時增加大小限制。此變更允許 Target 將 at.js 與使用相同技術的 AppMeasurement 結合。
* Target 現在會強制使用 `mbox` 函數中的 `adobe.target.applyOffer(options)` 機碼。此機碼在過去為必要，但現在 Target 會強制使用它，以確保 Target 有正確的驗證，且客戶能正確使用函數。
* at.js 已改善事件和點擊追蹤功能。at.js 使用 `navigator.sendBeacon()` 來傳送事件追蹤資料，並將在不支援 `navigator.sendBeacon()` 時退回同步 XHR。此次遞補主要影響 Internet Explorer 10 和 11 與一些版本的 Safari。Safari 將在近期的 iOS 11.3 版本中新增對 `navigator.sendBeacon()` 的支援。
* at.js 現在可以呈現選件，即便頁面是在背景索引標籤中開啟亦然。部分 Target 客戶會在 `requestAnimationFrame()` 因背景標籤的瀏覽器節流行為而停用時遭遇問題。
* 此版本新增了許多效能改善，包括檢查 Chrome CPU 設定檔時較短的呼叫堆疊。
* at.js 1.3.0 不再支援 Microsoft Internet Explorer 9 上的內容傳送如需詳細資訊，請參閱[支援的瀏覽器](https://developer.adobe.com/target/before-implement/supported-browsers/)。今後，所有要求會透過 `XMLHttpRequest` 執行，具有 CORS 支援而不沒有 JSONP 要求。此變更大幅改善安全性。

## at.js 版本 1.2.3 {#section_CE4D14AF00D04F4C8A2F0513F5EA1A84}

[!DNL at.js] 版本 1.2.3 現在已可用。

* 新增 JSON 選件的支援。只有在使用表單式體驗撰寫器建立的活動中才支援 JSON 選件。目前使用 JSON 選件的唯一方式是透過直接 API 呼叫。請參閱[建立 JSON 選件](/help/main/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D)。

## at.js 版本 1.2.2 {#section_4E96D13F2DFE4F1F81A1089877D53649}

[!DNL at.js] 版本 1.2.2 現在已可用。

* 已修正使用 QUIRKS 模式在頁面上載入 Target 資料庫時傳回 JavaScript 錯誤的問題。(TNT-28312)
* 已修正造成 Target 點擊追蹤中斷 Analytics 資料收集呼叫的問題。(TNT-28261)
* 已修正當 `getOffer() params` 傳回空白字串時，造成 `targetPageParams()` 失敗的問題。(TNT-28359)
* 已修正使用僅 x 產生工作階段 ID 的問題。(TNT-28361)

## at.js 版本 1.2.1 {#section_F757C8174BBA4F68AC5524ADC3D9C5E3}

[!DNL at.js] 版本 1.2.1 現已可用。

* 已修正在具有 target=&quot;_blank&quot; 的連結上，點擊追蹤防止 Target 在新索引標籤中開啟連結的問題。

## at.js 版本 1.2.0 {#section_1C3A18C595C34B25A14A440D213F3B9C}

[!DNL at.js] 版本 1.2 現在以包括多數錯誤修正的維護版本形式提供。

* 已修正防止點擊追蹤特殊大小寫的預設動作的問題。(TNT-28089)
* 已修正在具有 `target="_blank"` 的連結上點擊追蹤時，會阻止 Target 在新索引標籤中開啟連結的問題。(TNT-28072)
* 可以用作 Cookie 網域的 IP 位址。(TNT-28002)
* 已修正在具有全域 mbox 或其他地區 mbox 的重新導向選件中造成閃爍的問題。(TNT-27978)
* 已修正體驗鎖定目標活動設定在「瀏覽」與「撰寫」之間切換時，於 VEC 內失敗的問題。(TNT-27942)
* 已修正點擊追蹤元素閃爍樣式類別上的不正確處理。(TNT-27896)
* 已修正造成全域 mbox 參數變得與所有 mbox 參數混合的問題。(TNT-27846)
* 進行變更以確保 [!DNL at.js] 已正確處理 Handlebars、Mustache 和其他用戶端範本資料庫。(TNT-27831)
* 進行變更以確保 `sdidParamExpiry` 已正確初始化，並傳遞至訪客 API。這是已新增至 `at.js 1.1.0` 的迴歸。先前的 [!DNL at.js] 版本不受影響。這只會影響使用重新導向選件和 A4T 的用戶端。(TNT-27791)
* 進行變更以確保會執行 `SCRIPT`，而無論使用的類型屬性為何。(TNT-27865)

## at.js 版本 1.1.0 {#section_8F494E1EA94E48A9B169F5CF9FE6DC56}

**日期:** 2017 年 8 月 2 日

[!DNL at.js] 版本 1.1 中包括下列增強功能和修正:

* 已新增回應 Token 處理。如需詳細資訊，請參閱[回應 Token](/help/main/administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4)。
* 已解決問題，使得 `document.currentScript polyfill` 不會干預 Angular 1.X。
* 進行變更以確保點擊追蹤不會干預可見性屬性。點擊追蹤元素會以 `at-element-click-tracking` CSS 類別標記，而非 `at-element-marker`。

## at.js 版本 1.0.0 {#section_37A3D23FC4AD42A68AA831B89E03E725}

**日期:** 2017 年 7 月 7 日

at.js 版本 1.0 中包括下列增強功能和修正:

* 支援非同步載入 at.js，可讓頁面載入更快速。
* 支援在非同步載入 at.js 時預先隱藏頁面內容。
* 停用內容傳遞時有更好的錯誤訊息。
* 傳遞多個活動時的效能改善。
* 支援 YUI Compressor。
* 在活動傳遞期間的自訂事件 Bug/錯誤報表。
* 修正 Microsoft Internet Explorer 11 中的效能問題。
* `getOffer()` 函數在部分網站上發生錯誤的修正。
* 以非同步方式載入 Target 資料庫。如需詳細資訊，請參閱 [at.js 常見問題](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-faq/target-atjs-faq/)。

## at.js 版本 0.9.7 {#section_6C7B698BE21E40E495FD2850EFBF3E80}

**日期:** 2017 年 5 月 22 日

[!DNL at.js] 版本 0.9.7 中包括下列增強功能和修正:

* 修正與可視化體驗撰寫器 (VEC) 中的 `insertAfter` 和 `insertBefore` 動作遺漏資產金鑰相關的問題。這些問題與從視覺選件移轉至選件範本有關。

## at.js 版本 0.9.6 {#section_EEFA6413F2F947AD8C4A88128B90245D}

**日期:** 2017 年 4 月 13 日

[!DNL at.js] 版本 0.9.6 中包括下列增強功能和修正:

* 重新導向選件支援 A4T。下載和安裝 [!DNL at.js] 版本 0.9.6 之後，您可以在使用 [!DNL Adobe Analytics] 做為 [!DNL Target] (A4T) 報表來源的活動中使用重新導向選件。除了 [!DNL at.js] 版本 0.9.6，還有您的實作必須符合以便使用重新導向選件和 A4T 的其他基本需求。如需詳細資訊和須知的其他重要資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
* 在 [!DNL at.js] 0.9.6 之前，當頁面上存在訪客 API，並且 `visitorApiTimeout` 設定太積極時， 可能會遇到 [!DNL Target]Target 要求中未傳送任何 MCID 資料的情況。這可能在使用 A4T 時導致 [!DNL Analytics] 中的問題，例如散亂的點擊。

   在 [!DNL at.js] 0.9.6 中此行為已變更，即便 `visitorApiTimeout` 設為假設 1 毫秒，Target 將嘗試收集 SDID、追蹤伺服器和客戶 ID 資料，並在 Target 要求中傳送那些資料。

* 已新增 `selectorsPollingTimeout` 設定。如需詳細資訊，請參閱 [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。
* 來自 `getOffer()` () 的回應格式已變更。如需詳細資訊，請參閱 [adobe.target.getOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/)。
* 已針對不支援的 `<!DOCTYPE>` 宣告新增主控台記錄。
* 已修正在將多個預設選件傳遞至單一 mbox 時，[!DNL Target Classic] 外掛程式未正確套用的問題。(TGT-22664)
* 改善兩個字母上層網域 (TLD) 的 Cookie 設定，以確保為這些網域 (例如 [!DNL autodrives.ca]、[!DNL test.no]，以此類推) 正確設定 mbox Cookie。
* 用於擷取儲存 Cookie 時應該使用的上層網域的演算法在 at.js 版本 0.9.6 中已變更。因為此變更，無法將 Cookie 儲存至使用 IP 的位址。大部分時候，IP 位址是用於測試用途，但做為解決辦法，您可以使用 DNS 項目或調整本機機器上的主機檔案。
* 已修正當屬性為字串值而非整數時移動和重新排列動作的處理。

## at.js 版本 0.9.4 {#section_A15B12F12CD94F07B3F56613A79A815F}

**日期:** 2017 年 1 月 19 日

* mbox 名稱現在可以包含特殊字元，包括 &amp; 符號 (&amp;)。

   如需允許的特殊字元的清單，請參閱 [at.js 設定](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)。

* 已新增 `secureOnly` 設定，指出 at.js 是否應該僅使用 HTTPS 或根據頁面通訊協定，允許在 HTTP 與 HTTPS 之間切換。這是進階的設定，預設值為 False 並且可透過 `targetGlobalSettings` 覆寫。
* [!UICONTROL 「舊版瀏覽器支援」]選項可在 at.js 版本 0.9.3 和更早版本中取得。此選項已在 at.js 版本 0.9.4 中移除。

## at.js 版本 0.9.3 {#section_DF13BC1D7C994AE7A36B81937A699DF4}

**日期:** 2016 年 10 月 10 日

* 當 at.js 設定中停用舊版瀏覽器時，請確保在 Microsoft Internet Explorer 11 中觸發 mbox 呼叫。
* 確保在動態遠端選件失敗 (例如，如果 URL 不正確並傳回 404 錯誤) 時會轉譯預設內容。
* 當 DOM 中找不到 VEC 點擊追蹤選取器時確保元素快速顯示。

## at.js 版本 0.9.2 {#section_148549CBB4F046BAA8F79C79B64EC889}

**日期:** 2016 年 9 月 21 日

* 已新增 `optoutEnabled` 設定，以啟用或停用裝置圖表選擇退出。如果此設定設為 `true`，並且訪客選擇退出追蹤，訪客的瀏覽器將不會進行任何 mbox 呼叫。裝置圖表目前處於 Beta 版。此設定預設會設為 `false`，但如果您使用裝置圖表，則必須設為 `true`。
* 已針對通知機制新增 `CustomEvent` 支援。之前，您無法透過標準 DOM API (例如 `document.addEventListener()`) ()) 來使用 at.js 事件通知機制。現在您可以使用 `document.addEventListener()` 來訂閱 at.js 事件，例如要求事件和內容呈現事件。
* 已修正關於可視化體驗撰寫器 (VEC) 選件建立的問題。在此版本之前，Target 會隱藏選取器，並且只有在所有選取器都符合時才取消隱藏。在 at.js 0.9.2 中，Target 會在選取器符合時便加以取消隱藏。

## at.js 版本 0.9.1 {#section_DAFB99114D604CFB8416C1BC7DEEAEEE}

**日期:** 2016 年 7 月 14 日

* 為訪客 ID 服務提供 at.js 逾時，其與服務本身的逾時無關。
* 更正0.9.0中影響某些頁上使用at.js和其他頁上的mbox.js（現已棄用）實現的問題。
* 如果您使用 Adobe Analytics 做為活動的報表來源，若您使用的是 mbox.js 61 版 (或更新版本) 或 at.js 0.9.1 版 (或更新版本)，則不需在活動建立期間指定追蹤伺服器。at.js 程式庫會自動傳送追蹤伺服器值給 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL 目標與設定]頁面上的[!UICONTROL 追蹤伺服器]欄位保留空白。

## at.js 版本 0.9.0 {#section_2981CC9792F245389B39BB5B69F84C4E}

**Target 版本:** 16.6.1

**日期:** 2016 年 6 月 23 日

* 修正使用 VEC 選件時白色畫面的問題。使用 [!DNL at.js] 的任何人應該升級至這個新版本。
* 新 `registerExtension` API。

   這個新 API 可讓開發人員存取 [!DNL at.js] 中使用的某些 jQuery 模組，以為資料庫開發擴充功能 (亦稱為外掛程式)。此變更有一些隱含意義。這只會影響使用這些功能的使用者:

   * `getSettings()` API 已移除，但使用 `registerExtension()` 可發揮相同的功能。
   * `getTracking()` API 已移除，但使用 `registerExtension()` 可發揮相同的功能。

   * 必須更新現有的擴充功能 (例如 AngularJS 擴充功能)，才能使用 `registerExtension()` 方法。

* 新建at.js通知API。

   此通知系統的目標是要對 [!DNL at.js] 正在頁面上執行的動作以及發生問題時提供更多深入分析。VEC 的常見問題是 IT 發行變更了頁面、VEC 選擇器中斷，以及測試停止正確傳送內容。此通知系統的一個目標是要讓頁面知道此傳送的問題，讓開發人員可以存取此資訊，將資訊傳遞至 [!DNL Adobe Analytics] 之類的系統，並且可將警示傳送至業務擁有者，通知其測試中斷的訊息。

* 新 `targetGlobalSettings()` API 方法。

   您可以覆寫 at.js 資料庫中的設定，而非在 [!DNL Target Standard/Premium UI] 中或使用 REST API 進行設定。

## at.js 版本 0.8.0 {#section_E1C7B08EC0494388A022C28A8B8FE807}

**日期:** 2016 年 5 月 5 日

這是 [!DNL at.js] 資料庫的第一個官方發行。

[!DNL at.js] 是新的 [!DNL Target] 實施程式庫，專為典型 Web 實施和單頁應用程式而設計。

針對 [!DNL Adobe Target] 實作以 [!DNL at.js] 取代 [!DNL mbox.js]。

除了眾多優點以外，[!DNL at.js] 還能改進 Web 實施的頁面載入時間、改進安全性，以及為單頁應用程式提供更好的實施選項。

[!DNL at.js] 包含 [!DNL target.js] 所附元件，因此不再需要呼叫 [!DNL target.js]。

實施 [!DNL at.js] 時，請注意以下事項:

* 不支援 Internet Explorer 8 版之前的舊版。
* 非同步實施表示舊式整合 (如 [!DNL Test&Target] 至 [!DNL SiteCatalyst] 外掛程式) 可能無法運作。
* [!DNL Target]不支援參考 物件和方法的 外掛程式。[!DNL mbox.js]
* 所有對 [!DNL Target] 的呼叫都是透過 XMLHTTPRequest，而內容是透過 JSON 傳回。
