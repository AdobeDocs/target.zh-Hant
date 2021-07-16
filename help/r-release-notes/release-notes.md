---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解 [!DNL Adobe Target]目前版本中包含的新功能、增強功能和修正，包括SDK、API和JavaScript程式庫。
title: 目前發行的版本包含哪些新功能？
feature: 發行說明
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b623b7ac3793aa340f0d3072e7453bd988b733ac
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 47%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 Target API、SDK、JavaScript 程式庫 (at.js) 的發行說明，以及其他平台變更 (如適用)。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## at.js 2.6.0（2021年7月16日）

* 每當at.js設定`secureOnly`設為`true`時，新增安全屬性至Cookie。
* 現在使用`triggerView()`時可使用回應Token。
* 修正了與`CONTENT_RENDERING_NO_OFFERS`事件相關的問題。 現在，只要沒有從[!DNL Target]傳回任何內容，就會正確觸發此事件。
* [!DNL Anlytics for Target] (A4T)使用請求時可正確傳回點按量度詳細 `prefetch` 資料。
* UUID產生不再使用`Math.random()`，而是需要`window.crypto`。
* 每個網路呼叫的`sessionId` Cookie過期都已正確延伸。
* [!UICONTROL 單頁應用程式](SPA)檢視快取初始化現在已正確處理，並遵循`viewsEnable`設定。

## [!DNL Target Standard/Premium] 21.6.1（2021年6月30日）

此版本包含下列新功能和增強功能。 括號內的問題編號供 [!DNL Adobe] 內部使用。

| 功能 | 詳細資料 |
| --- | --- |
| 目標分析 (A4T) | 從使用[!DNL Analytics]作為報表來源(A4T)的活動按一下[!UICONTROL 報表]頁面上的「[!UICONTROL 在Analytics中檢視」連結，現在會開啟[!DNL Analysis Workspace]。 ]以前，連結會開啟[!DNL Analytics]報表。 (TGT-36959) |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | 下列增強功能適用於[!DNL Recommendations]人氣演算法：<ul><li>當[!DNL Target]為行為資料來源時，所有人氣（檢視次數最多/最暢銷商品）演算法都可使用新的六小時「回顧期間」（資料範圍）選項。 （當[!DNL Adobe Analytics]為行為資料來源時，此回顧期間為&#x200B;*not*&#x200B;可用。）</li><li>選取後，下列演算法大約每三小時執行一次（而非每12小時）。<ul><li>檢視次數最多</li><li>購買次數最多</li><li>按類別檢視次數最多</li><li>按類別購買次數最多</li><li>按自訂屬性檢視次數最多（使用groupBy功能）</li><li>按自訂屬性購買最多（使用groupBy功能）</li></ul></ul>要宣佈的發行日期。 (TOP-1086) |

## Python SDK 1.0.0（2021年6月16日）

具有裝置決策功能的全新[!DNL Adobe Target] Python SDK現已推出。 這項最新新增功能可支援[!DNL Target]伺服器端SDK套裝。 這些SDK可協助您以您所選擇的語言與[!DNL Target]整合，並加快實現價值的時間。 由於市場正轉向無Cookie的世界，第一方資料很有價值，伺服器端整合正成為熱門選擇。 Target SDK提供市面上最熱門的程式設計語言(Python、Java、JavaScript、C# / .Net)。

如需詳細資訊，請參閱[Adobe Target SDK指南](https://adobetarget-sdks.gitbook.io/docs/)中的[Python SDK檔案](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/python-sdk)。

## ![Adobe Experience Platform Web SDK](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] 版本2.5.0（2021年6月1日）

此版本的[!DNL Platform Web SDK]包含對以下內容的支援：

| 功能 | 詳細資料 |
| --- | --- |
| 透過[!UICONTROL Analytics for Target](A4T)重新導向支援 | 使用[A4T](/help/c-integrating-target-with-mac/a4t/a4t.md)時，Platform Web SDK現在支援[!DNL Target]重新導向。<br>如需詳細資訊，請參閱 [實 [!DNL Target] 作的Analytics](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 |

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。如需詳細資訊，請參閱「<br>Creative Cloud 發行說明[」。](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html??lang=zh-Hant) |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 發行說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |
