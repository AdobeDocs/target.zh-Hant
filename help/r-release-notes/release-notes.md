---
description: 這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
keywords: 發行說明；新功能；發行；更新；更新；發行；增強；增強；修正；錯誤修正
seo-description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
seo-title: 'Adobe Target 版本說明 (最新) '
solution: Target
title: Target 版本說明 (最新)
topic: 建議
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 5f05f218e5fdea26827b86cb7fbea05ac6349014

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

括號內的問題編號供 [!DNL Adobe] 內部使用。

## 目標平台（2019年10月31日）

| 功能/增強功能 | 說明 |
| --- | --- |
| Java SDK | Java [!DNL Target] SDK可讓您部署 [!DNL Target] 伺服器端。 此Java SDK可協助您輕鬆 [!DNL Target] 地與其 [!DNL Adobe Experience Cloud] 他解決方案整 [!DNL Adobe Experience Cloud Identity Service]合， [!DNL Adobe Analytics]例如 [!DNL Adobe Audience Manager]。<br>Java SDK透過我們的傳送API與整合時引入最佳實務並免除複雜性， [!DNL Target] 讓您的工程團隊能夠專注在商業邏輯上。 以下是我們在最新版本中推出的主要功能：<ul><li>支援預取和通知，讓您透過快取最佳化效能。</li><li>支援在網頁和伺服器端混合整 [!DNL Target] 合時最佳化效能。 我們將引入由 `serverState` 透過伺服器端擷取的體驗填入的設定，如此at.js 2.2就不會再進行額外的伺服器呼叫來擷取體驗。 此方法可最佳化頁面載入效能。</li><li>支援透過Java SDK擷取VEC建立的活動，此為全新的傳送API所提供。</li><li>開放來源，讓您的開發人員可以為 [Target Java SDK貢獻心力](https://github.com/adobe/target-java-sdk)。</li></ul>如需詳細資訊，請參 [閱版本注意事項——目標Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)。<br>透過全新的Target Java SDK，在Adobe技術部落格——伺服器 [端最佳化中進一步瞭解Target Java SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。 |

## Target Standard/Premium 19.10.2 (2019 年 10 月 31 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Multi-value屬性 | 有時，您想要使用多值欄位。 考量下列範例:<ul><li>您提供影片給使用者。 某部電影有多位演員。</li><li>你賣音樂會的票。 給定用戶有多個喜愛的樂隊。</li><li>你賣衣服。 T恤衫有多種尺寸。</li></ul>若要處理這些案例中的建議，您可以將多值資料傳遞至Target Recommendations，並使用特殊的多值運算子。<br>如需詳細資訊，請 [參閱使用多值屬性](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md)。 |

## Target Standard/Premium 19.10.1 (2019 年 10 月 22 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) User-Based Recommendations<br>（2019年10月24日） | 根據每位訪客的瀏覽、檢視和購買記錄來建議項目。 這些項目通常稱為「為您推薦」。<br>此准則可讓您為新訪客和舊訪客提供個人化內容和體驗。 建議清單會針對訪客的最近活動加權，並會在工作階段中更新，當訪客瀏覽您的網站時，建議清單會變得更個人化。<br>如需詳細資訊，請參閱「准則／演算法」中的「使 [用者建議」](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms)。 |

### Adobe Experience cloud導覽

* 當您登入時， [!DNL Adobe Experience Cloud]將會進入新的標題導覽。 它看起來與先前的導覽非常類似，頂端有黑色列，但提供下列改良功能：

   * 更輕鬆地在 [!DNL Identity Management System] (IMS)組織間切換或切換至不同的解決方案。
   * 改進的使用者說明：搜尋結果包括產品文 [!DNL Target] 件、社群論壇和更多視訊內容，讓您更輕鬆地存取更多內容，以協助您發揮最大效益 [!DNL Target]。 我們也直接在「說明」功能表中新增了意見回 [!UICONTROL 饋機制] ，讓您更輕鬆地報告問題或分享您的想法。

   * 改善網路推廣者分數(NPS)回饋功能，讓調查模式不會干擾您的工作流程。
   * 已改善登入流程。 以前，所 [!DNL Target] 有客戶在按一下頁首中的圖示後，就會著陸 [!DNL Target] 至Target登陸頁面。 然後，本頁允許客戶繼續使用 [!DNL Target Standard/Premium]、 [!DNL Search&Promote]或 [!DNL Recommendations Classic]，如下所示：

      ![登陸頁面](/help/r-release-notes/assets/landing.png)

      我們已取消所有客戶的登陸頁面。 現在，只要按一下新標題導覽列中的 [!UICONTROL 圖示，您就一律會直接進入「活][!DNL Target] 動清單」頁面。

      如果您使 [!DNL Recommendations Classic]用，您可以直接前往解決方案，或從Recommendations標籤上建立的簡短連結  ，如下所示：

      ![Recs Classic深層連結](/help/r-release-notes/assets/recs-classic.png)

      如果您使 [!DNL Search&Promote]用，您必須直接前往 [Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)。 從內部到達 [!DNL Search&Promote] 的路徑已 [!DNL Adobe Target] 完全移除。

   * 頁首的 [!DNL Target] 「通知」下拉式清單 [!UICONTROL 中] ，目前無法使用的通知。
   >[!NOTE]
   >
   >這些功能不會一次推出，也不會一起推出給所有客戶。 我們將在未來幾週內推出這些功能，從 [!DNL Target Standard/Premium] 19.10.1（2019年10月22日）版本開始。
   >
   >在新導覽列的推出過程中，您也會注意到一些URL變更。 所有先前的書籤化連結都會繼續運作，但我們鼓勵您將新連結加入書籤，以加快開啟速度。

## at.js 2.2和1.8版（2019年10月10日）

| 功能/增強功能 | 說明 |
| --- | --- |
| at.js 2.2<br><br>andat.js 1.8版 | 這些版本的at.js提供：<ul><li>已改善在網頁上同時使用Experience Cloud ID Service(ECID)v4.4和at.js 2.2或at.js 1.8時的效能。</li><li>之前，ECID曾進行兩次封鎖呼叫，之後at.js才能擷取體驗。 這已簡化為單一呼叫，可大幅提升效能。</li></ul> 為善用這些效能改良功能，升級至at.js 2.2或at.js 1.8以及ECID程式庫v4.4.<br>at.js 2.2提供：<ul><li>**serverState**:at.js v2.2+中提供的設定，可在實作Target的混合整合時用來最佳化頁面效能。 混合整合意指您在用戶端上同時使用at.js v2.2+和伺服器端的傳送API或Target SDK來傳送體驗。 `serverState` 讓at.js v2.2+能夠直接從伺服器端擷取並傳回至用戶端的內容套用體驗，做為所提供頁面的一部分。<br>如需詳細資訊，請參閱targetGlobalSettings中的 ["serverState"](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state)。</li></ul> |

## 目標平台（2019年10月9日）

| 功能/增強功能 | 說明 |
| --- | --- |
| Node.js SDK 1.0版 | Target Node.js SDK可讓您部署Target伺服器端。<br>此Node.js SDK可協助您輕鬆將Target與其他Experience cloud解決方案整合，例如Adobe Experience Cloud Identity Service、Adobe Analytics和Adobe Audience Manager。<br>Node.js SDK透過我們的傳送API與Adobe Target整合時引入最佳實務並免除複雜性，讓您的工程團隊可專注在商業邏輯上。 以下是我們在最新版本中推出的主要功能：<ul><li>支援預取和通知，讓您透過快取最佳化效能。</li><li>支援在網頁和伺服器端混合整合Target時最佳化效能。 我們將引入一個名為 `serverState` 的設定，由透過伺服器端擷取的體驗填入，如此at.js 2.2就不會再進行額外的伺服器呼叫來擷取體驗。 此方法可最佳化頁面載入效能。</li><li> 支援透過Node.js SDK擷取VEC建立的活動，此為新的傳送API所提供。</li><li>開放來源，讓您的開發人員可以為Node.js SDK貢獻心力。</li></ul><br>如需詳細資訊，請 [參閱版本注意事項- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。<br>在Adobe Tech部落格——開放來源補充新的Adobe Target Node.js SDK中，進一步了 [解Target Node.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)。 |
| 傳送API | 生產環境中提供全新的傳送API端點（/v1/傳送）。 主要功能包括：<ul><li>一個端點，可擷取一或多個mbox的體驗。</li><li>透過API擷取VEC建立的活動。</li><li>支援稱為「檢視」的全新物件，用於單頁應用程式(SPA)和行動應用程式。</li></ul><br>如需詳細資訊，請 [參閱版本注意事項- Target伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明——目標伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 與Adobe Target伺服器端API相關的發行說明。 |
| [發行說明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 與Adobe Target的Node.js SDK相關的發行說明。 |
| [發行說明——目標Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 與Adobe Target Java SDK相關的發行說明。 |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js javaScript程式庫各版本變更的詳細資訊。 |
| [mbox.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 本頁面顯示每個 mbox.js 版本的變更。<br>請注意，mbox.js程式庫已不再開發。 所有客戶應該從 mbox.js 移轉至 at.js。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](../r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參 [閱Experience cloud發行說明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |
