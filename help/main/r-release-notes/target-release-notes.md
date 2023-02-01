---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: da159c10bd5100519b58cf2cb9c3d4ce15c4b2d0
workflow-type: ht
source-wordcount: '594'
ht-degree: 100%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2023 年 1 月 26 日**

若要檢視目前版本的相關資訊，請參閱 [Target 版本注意事項](release-notes.md)。這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 22.13.3 (2023 年 1 月 25 - 26 日)

我們將根據以下排程分批發行此版本：

* **1 月 25 日**：歐洲、中東和非洲 (EMEA) 區域
* **1 月 25 日**：亞太 (APAC) 區域
* **1 月 26 日**：美洲區域

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| Automated Personalization (AP) 支援 [JSON 選件](/help/main/c-experiences/c-manage-content/create-json-offer.md) | 使用表單式體驗撰寫器在 [!UICONTROL Automated Personalization] (AP) 活動中新增對 JSON 選件的支援。 (TGT-41460) |
| [AEM 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 新增了區分匯出到 [!DNL Target] 的 [!DNL Adobe Experience Manager] 片段 (AEM XF) 類型的功能。[!DNL Target]現在可讓您透過「HTML XF」和「JSON XF」進行篩選和搜尋，而不是透過「體驗片段」選項。(TGT-44132) |

* 已修正在 [!UICONTROL A/B 測試]和包含推薦的 [!UICONTROL  體驗鎖定] (XT) 活動中導致「500 錯誤」的問題。當 [!DNL Target] 無法從 [!DNL Target] UI 和 [!DNL Recommendations] 後端正確地刪除不再使用的標準物件時，即導致此問題。(TGT-44383)
* 已從 [!UICONTROL  選件層級]報告中移除 [!UICONTROL Automated Personalization] 活動顯示的選件名稱中移除位置。此變更使報告更易讀取。(TGT-44294)
* 已從 AP 和「[!UICONTROL 自動鎖定目標][!UICONTROL 個人化前瞻分析]」和「[!UICONTROL 重要屬性]」報表 ([!DNL Target] UI 中) 移除 45 天和 90 天行事曆選項。 由於使用模式並且為了改善效能，這些日期範圍已被取代。 UI 已更新以反映目前允許的範圍：15、30 和 60 天。 (TGT-39357)
* 已不允許在活動上線後變更「[!UICONTROL 與最佳化目標相同]」設定 (「[!UICONTROL 目標與設定]」頁面上) 的功能。 (TGT-43923)
* 已修正從 [!DNL Target Standard] 升級到 [!DNL Target Premium] 時導致 [!DNL Target] 後端中預設工作區出現問題的問題。(TGT-44081 和 TGT-44306)
* 已進行變更以使名稱包含點字元「.」的 [!DNL Analytics] 報告套裝可用於 [!DNL Target] UI 以建立 [!DNL Analytics] 分類摘要。
* 已變更「使用裝置上決策的實作方法」的 [!UICONTROL 實作]頁面 ([!UICONTROL 管理] > [!UICONTROL 實作]) 上的連結，以指向說明如何使用裝置上決策來操作所有受支援 SDK (Node.js、Java、.NET 和 Python) 的頁面。如需詳細資訊，請參閱[開始使用 Target SDK](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。
* 已修正使用 [!DNL Scene7] 和 [!DNL Target] 時導致檔案上傳問題的問題。
* 已透過使用內部可用性稽核的結果，增強了 [!DNL Target] UI 對殘障人士的無障礙支援。這些無障礙支援增強功能包括存取以前無法透過鍵盤存取的功能、替代文字增強功能、縮放 UI 部分以提高可用性的能力、提升的鍵盤焦點等等。(TGT-42759)
* 對整個 [!DNL Target] UI 進行了各種本地化修正。

## 額外的版本注意事項和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [版本注意事項：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |


## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
