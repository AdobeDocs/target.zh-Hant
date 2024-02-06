---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 4395caa7e40717c59067eaedff5e53776768eda9
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 92%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 瀏覽器對象屬性停止支援 iPad 和 iPhone (2024 年 4 月 30 日)

| 停止支援 | 詳細資料 |
|--- |--- |
| 建立對象時使用的[瀏覽器屬性](/help/main/c-target/c-audiences/c-target-rules/browser.md)將停止支援 [!DNL iPad] 和 [!DNL iPhone]。<p>停止支援日期：<P>2024 年 4 月 30 日 | [!DNL Adobe Target] 可讓您[鎖定多個類別屬性中的任一屬性](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括當使用特定[瀏覽器或瀏覽器選項](/help/main/c-target/c-audiences/c-target-rules/browser.md)造訪您網頁的使用者。<P><B>從 2024 年 4 月 30 日起，為對象建立類別時，iPad 和 iPhone 將從可用的[!UICONTROL 瀏覽器]類型下拉式清單中移除。</b><P>使用建立的內建對象 [!DNL Target] UI (例如「瀏覽器：iPad」和「瀏覽器：iPhone」)會自動移至新的對象定義。<p>如需必須手動變更的替代設定範例，請參閱 [從瀏覽器對象屬性淘汰iPad和iPhone （2024年4月30日）](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard/Premium 24.1.1 (2024 年 1 月 22、23 和 25 日)

此版本預定在下列日期發佈：

* **1 月 22 日**：歐洲、中東和非洲 (EMEA) 區域
* **1 月 23 日**：亞太 (APAC) 區域
* **1 月 25 日**：美洲區域

此版本包含下列增強功能和修正：

* [!UICONTROL Analytics for Target] (A4T) 活動 (具備收入目標量度) 未將「收入」顯示為列名稱，且收入量度未在報告中以 ($) 格式顯示。這是已經解決的外觀問題。(TGT-46995)
* 修正導致報告日期間隔無法正常運作的問題。(TGT-47396)
* 修正客戶使用[!UICONTROL 更多動作]圖示啟用或停用活動後，導致[!UICONTROL 所有活動]頁面上顯示錯誤狀態的問題。(TGT-47367)
* 修正導致無法為單一客戶顯示[!UICONTROL 重要屬性]報告的問題。(TGT-47272)
* 修正當單一客戶嘗試啟用「需要驗證」時，導致系統顯示「無效的承載」訊息的問題。(TGT-47195)
* 更新 [!DNL Target] UI 中的大量本地化字串。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
