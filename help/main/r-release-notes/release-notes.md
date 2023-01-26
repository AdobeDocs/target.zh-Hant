---
keywords: 版本注意事項;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 57030f8f3c1758c60ef00184b4b6d3dee30731fa
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 96%

---

# [!DNL Target] 發行說明 (最新)

這些版本注意事項提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的版本注意事項以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] Standard/Premium 22.13.3 (2023 年 1 月 25 - 26 日)

我們將根據以下排程分批發行此版本：

* **1月25日**:歐洲、中東和非洲(EMEA)地區
* **1月25日**:亞太地區
* **1月26日**:美洲地區

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md) 支援Automated Personalization(AP) | 使用表單式體驗撰寫器在 [!UICONTROL Automated Personalization] (AP) 活動中新增對 JSON 選件的支援。 (TGT-41460) |
| [AEM 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 新增了區分匯出到 [!DNL Target] 的 [!DNL Adobe Experience Manager] 片段 (AEM XF) 類型的功能。[!DNL Target]現在可讓您透過「HTML XF」和「JSON XF」進行篩選和搜尋，而不是透過「體驗片段」選項。(TGT-44132) |

* 已修正在 [!UICONTROL A/B 測試]和包含推薦的 [!UICONTROL  體驗鎖定] (XT) 活動中導致「500 錯誤」的問題。當 [!DNL Target] 無法從 [!DNL Target] UI 和 [!DNL Recommendations] 後端正確地刪除不再使用的標準物件時，即導致此問題。(TGT-44383)
* 已從 [!UICONTROL  選件層級]報告中移除 [!UICONTROL Automated Personalization] 活動顯示的選件名稱中移除位置。此變更使報告更易讀取。(TGT-44294)
* 已從 AP 和「[!UICONTROL 自動鎖定目標][!UICONTROL 個人化前瞻分析]」和「[!UICONTROL 重要屬性]」報表 ([!DNL Target] UI 中) 移除 45 天和 90 天行事曆選項。 由於使用模式並且為了改善效能，這些日期範圍已被取代。 UI 已更新以反映目前允許的範圍：15、30 和 60 天。 (TGT-39357)
* 已不允許在活動上線後變更「[!UICONTROL 與最佳化目標相同]」設定 (「[!UICONTROL 目標與設定]」頁面上) 的功能。 (TGT-43923)
* 已修正從 [!DNL Target Standard] 升級到 [!DNL Target Premium] 時導致 [!DNL Target] 後端中預設工作區出現問題的問題。(TGT-44081 和 TGT-44306)
* 已變更「使用裝置上決策的實作方法」的 [!UICONTROL 實作]頁面 ([!UICONTROL 管理] > [!UICONTROL 實作]) 上的連結，以指向說明如何使用裝置上決策來操作所有受支援 SDK (Node.js、Java、.NET 和 Python) 的頁面。如需詳細資訊，請參閱[開始使用 Target SDK](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。
* 已修正使用 [!DNL Scene7] 和 [!DNL Target] 時導致檔案上傳問題的問題。
* 已透過使用內部可用性稽核的結果，增強了 [!DNL Target] UI 對殘障人士的無障礙支援。這些無障礙支援增強功能包括存取以前無法透過鍵盤存取的功能、替代文字增強功能、縮放 UI 部分以提高可用性的能力、提升的鍵盤焦點等等。(TGT-42759)
* 對整個 [!DNL Target]UI 進行了各種本地化修正。

## 額外的版本注意事項和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [版本注意事項：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的版本注意事項和 Experience Cloud 版本注意事項

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些版本注意事項中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版版本注意事項 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本注意事項](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 版本注意事項 | 檢視 Adobe Experience Cloud 解決方案的最新版本注意事項。<br>如需詳細資訊，請參閱「[Experience Cloud 版本注意事項](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)」。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html) |
| 即將發佈的版本注意事項 | 如需本月的 Target 版本的詳細資訊，包括搶鮮版版本資訊，請參閱 [Target 版本注意事項 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md)頁面。 |
