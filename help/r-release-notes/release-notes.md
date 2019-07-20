---
description: 這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
keywords: 版本說明;發行前
seo-description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
seo-title: Adobe Target發行說明(目前)
solution: Target
title: Target 版本說明 (最新)
topic: 建議
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: ce1758df44740213a2d9011ee43f84cb52f6a29d

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。

## 公告

請注意下列重要聲明:

* 2019 年 2 月 20 日，EMEA、日本和 APAC 區域中的 Adobe Target 基礎架構已升級，不再從使用較舊裝置或不支援 TLS 1.1 以上版本的網頁瀏覽器，收集一般使用者的資料。這項升級預計在 **2019 年 4 月 1 日**&#x200B;於北美區域推行。轉移至 TLS 1.2 可改善安全性。請務必詳閱詳細資訊，並與 IT 團隊就變更項目妥善規劃，以順利轉移。如需詳細資訊，請參閱 [TLS (傳輸層安全性) 加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
* 從 2019 年 3 月 起，[!DNL Target] 和 [!DNL Adobe Marketing Cloud] 將停止支援 Microsoft Internet Explorer 11。這項變更只會影響 [!DNL Target] 編寫，不影響體驗傳送。請改用 Microsoft Edge 或其他瀏覽器。如需更多資訊，請參閱[支援的瀏覽器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。

## Target Standard/Premium 19.6.1 (2019 年 6 月 26 日)

此版本包含下列新功能和增強功能:

(括號內的問題編號供 Adobe 內部使用。)

| 功能/增強功能 | 說明 |
| --- | --- |
| 可視化體驗撰寫器 (VEC) | **新的CMS功能表選項**：當您按一下CMS中的頁面元素時，功能表會顯示該元素類型可用的選項。<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**點擊追蹤改進**：我們改善了在CMS和單一頁面應用程式(SPA) CMS中設定點按追蹤的程序。<ul><li>選取要用於點擊追蹤的元素時，所有可用元素的名稱會顯示在右側的「修改」面板中，讓您快速且輕鬆地選取所要的元素。</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. 您可以將滑鼠指標暫留在此數目上，以查看所有選取元素的名稱。(TGT-33878)</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| 單頁應用程式視覺化體驗撰寫器 (SPA VEC) | **引導式工作流程**：新的引導工作流程可協助您瞭解頁面遞送規則設定如何設定，以便在單一頁面應用程式中成功執行和執行活動。(TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**複製修改**：您現在可以使用SPA CMS定義修改，然後將修改複製到您的單一頁面應用程式中的其他檢視中。(TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| 行動版視覺化體驗撰寫器 | **多個應用程式版本**：您現在可以為行動應用程式的多個版本編寫活動。如此可為您節省時間和精力，當版本類似時，您就不需要大幅變更應用程式的UI。(TGT-34231)<br>See "Manage multiple app versions" in [Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#using-the-mobile-vec). |
| ![Premium徽章](/help/assets/premium.png) 自動個人化(AP)與自動目標 | **特定體驗作為控制**：您可以選取在建立AP或自動Target活動時做為控制項的體驗。此功能可讓您根據活動中設定的流量分配百分比，將整個控制流量路由至特定體驗。然後，您可以評估個人化流量的績效報告，以控制該一個體驗的流量。目前的控制選項(隨機提供體驗)將繼續可用。(TGT-32801, TGT-26572, &amp; TGT-26571)<br>See [Select the control for your Automated Personalization or Auto-Target Activity](/help/c-activities/t-automated-personalization/experience-as-control.md). Note that there is a [current known issue](/help/r-release-notes/known-issues-resolved-issues.md) with this feature.<br>**個人化前瞻分析報表**：當訪客在特定位置看到特定內容的特定內容時，行銷人員友好的命名方式提供更有意義的資訊。(TGT-33421 &amp; TGT-34957)<br>See [Data collection for the Target personalization algorithms](/help/c-activities/t-automated-personalization/ap-data.md). |
| ![優質徽章](/help/assets/premium.png) 建議 | 建立「最近查看的項目」邏輯時，您可以使用「先前建議購買的項目」切換按鈕。(TGT-34030)<br>如需詳細資訊，請參閱 [「建立准則」](/help/c-recommendations/c-algorithms/create-new-algorithm.md#previously-purchased) 中最近檢視的項目。 |
| Google Chrome SameSite Cookie 原則 | Google最近宣佈，從Chrome76開始，在2019年月30日發行的Chrome76中，開發人員必須明確指定哪些Cookie可以跨網站運作，以及哪些Cookie可追蹤使用者。<br>隨著產業致力於為消費者建立更安全的網路，Target絕對致力於提供個人化體驗，並超越對訪客的隱私權期望。<br>請參閱 [Google Chrome SameSite Cookie原則](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md)。 |

## at. js2.1.0版(2019年月日)

我們很高興宣佈下列令人振奮的功能：js2.1.0：

| 功能/增強功能 | 說明 |
| --- | --- |
| Adobe加入支援 | 「Adobe 選擇加入」是簡化 Adobe 解決方案與同意管理平台整合的方法。<br>如需Adobe選擇加入的詳細資訊，請參閱 [隱私權與通用資料保護規則(GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md))。 |
| 符合業界標準的CSP規範 | at. js不再使用eval()來執行JavaScript。 |
| 用戶端分析記錄 | 可讓客戶完全控制如何將分析資料傳送至Adobe Analytics，不論是在用戶端或伺服器端。<br>如需詳細資訊，請參閱 [在實施前](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) 登入 *客戶端的Analytics*。 |
| 傳送通知 | Allows developers to send notifications when an experience is rendered by their code instead of using `applyOffer()` or `applyOffers()`.<br>如需詳細資訊，請查看 [adobe. target. sendNotifications(選項)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)。 |
| 縮減檔案大小 | at. js的大小減少了~24%。檔案大小較小可改善頁面載入效能，並減少頁面上下載. js的時間。 |
| at. js文件更新 | For a full list of all articles updated due to the at.js 2.1.0 release, see the June 3, 2019 entries in [Documentation changes](/help/r-release-notes/doc-change.md). |

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
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |