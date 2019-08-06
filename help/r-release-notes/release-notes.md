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
source-git-commit: 51f52bb40a0af4dac63236d46e6d6f0286cbb877

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。

## 公告

**2019年月31日**

[!UICONTROL 企業權限] 可讓 [!DNL Target] 客戶使用單一組織，但將其分為不同團隊或工作流程的工作區。[!UICONTROL 企業權限] 功能可協助您有效擴展團隊內部的最佳化程式。雖然此功能可在 [!DNL Target] UI中使用，但是Admin API會在2019 [!DNL Target] 年月發行之前，將其對應的支援失效。Adobe已更新管理員API，讓您可以使用整合帳戶存取組織中建立的所有工作區。因此，在舊版中，管理員API僅限於預設工作區，2019年月更新授予所有具有 [!UICONTROL 核准者] 存取權的工作區存取權。

在即將 [!DNL Target] 推出的2019年月發行版本中 [!UICONTROL ，企業權限] 將為客戶提供下列存取控制：

* 您可以選擇可套用整合的工作區
* 您可以將角色套用至Adobe I/整合： [!UICONTROL 核准者]、 [!UICONTROL 編輯者]或 [!UICONTROL 觀察員]。

**必要動作**：目前針對所有工作區運用API for資源(活動、對象、選件和報告)的客戶，都需要將現有的Adobe I/整合存取權授與所有工作區的所需角色。在月發行版本之前，所有使用 [!UICONTROL 核准者] 存取的整合都會使用，不論從 [!UICONTROL 「產品角色」] 下拉式清單中選取的角色為何。在即將發行的版本中，您現在可以選取所需的角色。

此動作應在2019 **年月的月份**&#x200B;執行。在2019 [!DNL Target] 年月發行後，存取控制將會啓動，而且如果這是您目前設定的方式，您將觀察到僅限預設工作區。預先設定整合角色並沒有負面影響。

如需逐步指示和更多資訊，請參閱 [「授予Adobe I/O整合存取工作區並指派角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)」。

## Target Mobile CMS SDK iOS2.1.0&amp; Android1.1.0(2019年月日)

此版本的Mobile CMS SDK包含下列增強功能和修正：

(括號內的問題編號供 Adobe 內部使用。)

* 已新增行動裝置上「預覽視覺活動」的支援。(TGT-27875)
* 修正 `UIImagePickerController` 因使用情況造成Apple Standard違規的問題。
* 已從Android SDK移除GSON相依性。(TGT-31710)
* 修正製作時無法重設傳送選件的問題。(TGT-35270)

## Target Standard/Premium 19.7.1 (2019 年 7 月 24 日) {#tgt-19-7-1}

此版本包含下列新功能和增強功能:

(括號內的問題編號供 Adobe 內部使用。)

| 功能/增強功能 | 說明 |
| --- | --- |
| 行動應用程式可視化體驗撰寫器 | Mobile App CMS會顯示新的「修改」面板，顯示您已設定用於點按追蹤的元素。(TGT-31741)<br> 請參閱 [「行動應用程式中的設定點按追蹤](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)」。 |
| ![A/B測試與體驗定位(XT)活動](/help/assets/premium.png)<br>中的Premium BadgereCommendations | Recommendations(演算法)狀態會顯示在「概述」頁面上，用於A/B測試和包含Recommendations選件的XT活動。狀態包括：Results Ready、Results not Ready和Feed fails.(TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| 透過Experience Cloud ID(ECID)程式庫對at. js2.0+的跨網域追蹤支援 | 以前，at. js不支援跨網域追蹤。*x* 版本不支援此函數。在此版本中，使用at. js2.0或更新版本的客戶現在可以透過ECID程式庫使用跨網域追蹤。必須將ECID程式庫與at. js2.0或以上版本一起安裝在頁面上，才能讓跨網域追蹤運作。[必須使用Experience Cloud ID庫4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 。<br>請參閱 [at. js2.x中的跨網域追蹤支援](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain)。 |
| Target支援Apple的ITP2.1和ITP2.2透過Experience Cloud ID(ECID)庫4.3 | 如今，Target客戶可以運用Adobe的CNAME認證計劃來降低Apple的ITP2.1和ITP2.2。<br>在此版本中，Target可與ECID程式庫4.3完美整合，後者運用伺服器端Cookie來降低ITP2.1和ITP2.2。強烈建議Target客戶將 [ECID程式庫4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 與Target的JavaScript程式庫搭配部署，以降低任何未來的ITP版本。ECID程式庫將繼續推行增強功能，為不斷變化的瀏覽器引進的Cookie原則提供強大的解決方案。<br>請參閱 [Apple Intelligent Tracking Premiention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。 |

**增強功能、修正和變更**

* 修正新增重復值時，Recommendations活動中排除值無法清除的問題。(TGT-34996)
* 您現在可以從「定位」頁面(三部分引導工作流程的步驟2)中移除「建議」活動中的設計。請注意，若要移除設計，必須選取多個設計。(TGT-35118)
* 修正某些客戶無法在Target UI中正確載入或可編輯的自訂條件卡問題。(TGT-35170)

## at. js2.1.1(2019年月24日)

此版本的at. js是維護發行，包含下列增強功能和修正：

(括號內的問題編號供 Adobe 內部使用。)

* 修正在Visual Experience Composer(CMS)的「目標與設定」頁面上，使用「點擊追蹤」度量時引發多個信標的問題。(TNT-32812)
* 修正無法顯示 `triggerView()` 選件不只一次的問題。(TNT-32780)
* 修正此問題，以確保請求包含Marketing `triggerView()` Cloud ID(MCID)資訊。(TNT-32776)
* 修正即使沒有儲存的檢視， `triggerView()` 通知仍無法觸發的問題。(TNT-32614)
* 修正由於使用decodeURIComponent而導致URL包含格式錯誤查詢字串參數時造成問題的問題。(TNT-32710)
* 透過 `Navigator.sendBeacon()` API傳送的傳送要求內容，信標標幟現在會設為「true」。(TNT-32683)
* 修正某些客戶無法在網站上顯示Recommendations選件的問題。客戶可以在傳送API呼叫中看到選件內容，但選件未套用至網站上。(TNT-32680)
* 修正多個體驗的點按追蹤無法如預期般運作的問題。(TNT-32644)
* 修正無法在第一個量度演算後套用第二個度量的問題。(TNT-32628)
* 修正使用 `mboxThirdPartyId``targetPageParams` 函數傳送時，請求裝載無法顯示在查詢參數或請求裝載中的問題。(TNT-32613)
* 修正導致顯示並按一下Chromium瀏覽器中的通知回應(包括Google Chrome)的問題。(TNT-32290)

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

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
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |
