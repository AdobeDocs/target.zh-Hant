---
description: 提供最新或即將發行的Adobe target版本功能、增強功能和修正資訊的發行說明。
keywords: 發行說明；發行；更新；未來發行；增強；新功能；修正
seo-description: 提供最新或即將發行的DNL Adobe target版本功能、增強功能和修正資訊的發行說明。
seo-title: Adobe target搶鮮版注意事項
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 0a9cf0e98f5f833402b96f37df5513325222ad19

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新: 2019 年 10 月 17 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>括號內的問題編號供 [!DNL Adobe] 內部使用。

## 目標平台

| 功能/增強功能 | 說明 |
| --- | --- |
| Node.js SDK 1.0版<br>（2019年10月9日） | Target Node.js SDK可讓您部署Target伺服器端。<br>此Node.js SDK可協助您輕鬆將Target與其他Experience cloud解決方案整合，例如Adobe Experience Cloud Identity Service、Adobe Analytics和Adobe Audience Manager。<br>Node.js SDK透過我們的傳送API與Adobe Target整合時引入最佳實務並免除複雜性，讓您的工程團隊可專注在商業邏輯上。 以下是我們在最新版本中推出的主要功能：<ul><li>支援預取和通知，讓您透過快取最佳化效能。</li><li>支援在網頁和伺服器端混合整合Target時最佳化效能。 我們將引入一個名為 `serverState` 的設定，由透過伺服器端擷取的體驗填入，如此at.js 2.2就不會再進行額外的伺服器呼叫來擷取體驗。 此方法可最佳化頁面載入效能。</li><li> 支援透過Node.js SDK擷取VEC建立的活動，此為新的傳送API所提供。</li><li>開放來源，讓您的開發人員可以為Node.js SDK貢獻心力。</li></ul>如需詳細資訊，請 [參閱版本注意事項- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。 |
| 傳送API<br>（2019年10月9日） | 生產中將提供全新的傳送API端點（/v1/傳送）。 主要功能包括：<ul><li>一個端點，可擷取一或多個mbox的體驗。</li><li>透過API擷取VEC建立的活動。</li><li>支援稱為「檢視」的全新物件，用於單頁應用程式(SPA)和行動應用程式。</li></ul>如需詳細資訊，請 [參閱版本注意事項- Target伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |
| at.js 2.2<br><br>andat.js 1.8版<br>（2019年10月10日） | 這些版本的at.js提供：<ul><li>已改善在網頁上同時使用Experience Cloud ID Service(ECID)v4.4和at.js 2.2或at.js 1.8時的效能。</li><li>之前，ECID曾進行兩次封鎖呼叫，之後at.js才能擷取體驗。 這已簡化為單一呼叫，可大幅提升效能。</li></ul> 為善用這些效能改良功能，升級至at.js 2.2或at.js 1.8以及ECID程式庫v4.4.<br>at.js 2.2提供：<ul><li>**serverState**:at.js v2.2+中提供的設定，可在實作Target的混合整合時用來最佳化頁面效能。 混合整合意指您在用戶端上同時使用at.js v2.2+和伺服器端的傳送API或Target SDK來傳送體驗。 `serverState` 讓at.js v2.2+能夠直接從伺服器端擷取並傳回至用戶端的內容套用體驗，做為所提供頁面的一部分。<br>如需詳細資訊，請參閱targetGlobalSettings中的 ["serverState"](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state)。</li></ul> |


## Target Standard/Premium 19.10.1 (2019 年 10 月 22 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) User-Based Recommendations | 根據每位訪客的瀏覽、檢視和購買記錄來建議項目。 這些項目通常稱為「為您推薦」。<br>此准則可讓您為新訪客和舊訪客提供個人化內容和體驗。 建議清單會針對訪客的最近活動加權，並會在工作階段中更新，當訪客瀏覽您的網站時，建議清單會變得更個人化。 |

### 增強功能、修正和變更

* 對Adobe Unified shell的變更。

   Adobe會更新現有的殼層（解決方案頂端的黑條），以統一並改善您在所有解決 [!DNL Experience Cloud] 方案中的使用 [!DNL Adobe Experience Cloud] 體驗。

   目前的工作流程沒有變更，而這些看似簡單的變更，旨在以小型但重要的方式讓您的生活更輕鬆。

   當您登入時， [!DNL Adobe Experience Cloud]將會進入新的Unified Shell。 它看起來與上一個Shell非常相似，頂部有黑條，但提供了以下改進：

   * 更輕鬆地在Identity Management System(IMS)組織之間切換，或切換至不同的 [!EExperience cloud解決方案] 。
   * 改進的使用者說明：搜尋結果包括產品文 [!DNL Target] 件、社群論壇和更多視訊內容，讓您更輕鬆地存取更多內容，以協助您發揮最大效益 [!DNL Target]。 我們也在「說明」功能表中新增了意見回應機制，讓您更輕鬆地報告問題或分享您的想法。
   * 已改善淨啟動子分數(NPS)功能。 有時，有些客戶會以比 [!DNL Target] 我們預期的更高頻率看到調查。 此外，調查模式過去會干擾您的工作流程。 我們已完全更新此功能，使它成為不再干擾的小型調查。 此外，有了新的設計，我們可以確保更好地控制調查的頻率。
   * 已改善登入流程。 以前，所 [!DNL Target] 有客戶在按一下Shell上的圖示後，就會著陸 [!DNL Target] 至Target登陸頁面。 然後，本頁可讓客戶繼續使 [!DNL Target Standard/Premium]用 [!DNRecommendations Classic]，或 [!DNL Search&Promote]，如下所示：

      ![登陸頁面](/help/r-release-notes/assets/landing.png)

      我們已取消所有客戶的登陸頁面。 現在，您一律可以按一下圖示 [!UICONTROL 直接進入「活動清單] 」 [!DNL Target] 頁面。

      如果您使 [!DNL Recommendations Classic]用，您可以直接前往解決方案，或從Recommendations標籤上建立的簡短連結  ，如下所示：

      ![Recs Classic深層連結](/help/r-release-notes/assets/recs-classic.png)

      如果您使 [!DNL Search&Promote]用，您必須直接前往連結。 從內部到達Search&amp;Promote的路徑已 [!DNL Adobe Target] 完全移除。
   * 「通知 [!DNL Target] 」下拉式清單中的「通知」  ，目前不再顯示通知。
   >[!NOTE]
   >
   >這些功能不會一次推出，也不會一起推出給所有客戶。 從2019年10月22日的19.10.1版開始，我們將在 [!DNL Target Standard/Premium] 未來幾天內推出這些功能。
   >
   >在新Shell的推出過程中，您也會注意到一些URL變更。 所有先前的書籤化連結都會繼續運作，但我們鼓勵您將新連結加入書籤，以加快開啟速度。

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
