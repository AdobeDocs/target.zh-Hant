---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d54f3c4c75031788316a94acf3d14a8db2a17366
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] 平台發行版本 (2022 年 7 月 20 日)

此版本包含以下功能、增強功能和修正：

| 功能 | 說明 |
| --- | --- |
| 透過 IPv6 支援提高對象評估準確性並降低最終使用者延遲 (TNT-43364、TNT-44692) | 訪客的地理位置現在由 IPv6 位址決定 (如果可用)，而不是僅由 IPv4 位址決定。 傳送 API 也支援 IPv6 輸入參數。 篩選和加入允許清單同時支援 IPv4 和 IPv6 位址。 此版本中的 IPv6 支援代表訪客將更準確地包含在對象中 (更準確地符合活動資格或包含在篩選條件中)。 同時改善了資料延遲，因為 IPv6 用戶端將直接路由，避免 IPv6 到 IPv4 閘道的額外負荷。 |
| 修正 A4T 用戶端裝載處理問題 (TNT-44926) | 透過 A4T 伺服器端整合，如果 Adobe Target 將請求識別為來自機器人，則不會將裝載轉送到 Analytics，並且 [!DNL Target] 日誌中不會記錄 mod_stats 事件。 在此版本中，A4T 用戶端記錄已增強，因此有關 A4T 裝載的行為與 A4T 伺服器端相同：被識別為機器人的訪客會排除在 [!DNL Target] 計數/報告之外。 (請注意，討論中的問題僅限於使用用戶端裝載處理的實施；伺服器端不受影響。 在此版本中，伺服器端和用戶端負載處理的行為現在是一致的。) |

## [!DNL Target Standard/Premium]22.6.2 (2022 年 6 月 30 日)

此版本包含以下功能、增強功能和修正：

| 功能 | 說明 |
| --- | ---  |
| 產品內通知 | 獲取以下相關的產品內通知：<ul><li>**活動**：當活動被批准或停用時（手動或達到其開始或結束日期時），所有活動類型的通知。 通知包括活動的名稱，其中包含指向活動概述頁的連結。</li><li>**配置檔案指令碼** 在手動或目標激活或停用配置檔案指令碼時通知。</li><li>**建議摘要**：手動或由目標啟用或停用建議摘要時通知。 當建議摘要失敗時也會傳送送通知。</li></ul> 預設情況下，產品管理員、發佈者和批准者會接收通知。 通知可在 Experience Cloud 首選項內配置。<br>有關詳細資訊，請參閱[通知和公告](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements)。 |
| *Adobe Target 開發人員指南* | 的 *Adobe Target開發人員指南* 合併所有 [!DNL Target] 開發人員內容。 指南包含實施 [!DNL Target] 和 [!DNL Recommendations]、[!DNL Target] SDK 及 [!DNL Target] API 的資訊。<br>有關詳細資訊，請參見 [Adobe Target開發人員指南](https://developer.adobe.com/target/){target=_blank}。 |

* 具有「[!UICONTROL 編輯者]」角色的使用者無法在即時活動中編輯受眾。 (TGT-43582)
* 如果客戶試圖以對象名字的第一個字元 (如 !London) 的嘆號 ( ! ) 來儲存對象，就會出現警告訊號。 (TGT-43643)
* 修正導致一些客戶的對象定義細節卡顯示已結束活動仍然在進行中的問題。 (TGT-43527)

## [!DNL Target Standard/Premium] 22.6.1 (分批發行；2022 年 6 月 7 日至 9 日)

我們將根據以下排程分批發行此版本：

* **6 月 7 日**：亞太 (APAC) 區域
* **6 月 8 日**：美洲區域
* **6 月 9 日**：歐洲、中東和非洲 (EMEA) 區域

此版本包含下列增強功能和修正：

* 新的「[!UICONTROL 受眾]」頁面提供了增強功能，防止在過去儲存受眾的舊資料庫與直接從後端擷取資訊的新架構之間的不一致狀態。 (TGT-43552)
* 已修正導致某些客戶無法儲存由 Target UI 建立「空」容器所引起之合併受眾的問題。 (TGT-43588)

## Target 平台發行版本 (2022 年 5 月 25 日)

此版本包含下列增強功能和修正：

* 新增的「[使用者代理用戶端提示](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}」支援。
* 修正在「[!UICONTROL 體驗鎖定]」 (XT) 活動中提供「[!UICONTROL 優惠方案決策]」時會斷斷續續引起逾時的問題。 (TNT-44611)

## at.js 2.9.0 版 (2022 年 5 月 27 日)

* 新增的「[使用者代理用戶端提示](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}」支援。
* 修正了同一個頁面上多個 mbox 請求有不同印象 ID 的問題。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。<br>如需詳細資訊，請參閱「[Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)」。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括搶鮮版版本資訊，請參閱 [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md)頁面。 |
