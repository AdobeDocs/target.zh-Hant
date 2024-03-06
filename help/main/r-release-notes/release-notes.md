---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 63%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 更新 `Browser:iPad` 和 `Browser:iPhone` 在 [!UICONTROL Browser] 對象屬性（2024年4月30日）

| 更新 | 詳細資料 |
|--- |--- |
| [!UICONTROL Browser:iPad] 和 [!UICONTROL Browser:iPhone] 更新於 [瀏覽器屬性](/help/main/c-target/c-audiences/c-target-rules/browser.md) 用於建立對象。 | [!DNL Adobe Target] 可讓您 [鎖定任一類別屬性](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括使用特定 [瀏覽器或瀏覽器選項](/help/main/c-target/c-audiences/c-target-rules/browser.md) 訪客造訪您的頁面時。<P>從 [!DNL Target] Standard/Premium 24.3.1 （2024年3月4日至6日）內建受眾，使用Target UI建立，例如 `Browser:iPad` 和 `Browser:iPhone` 將更新以針對 [!DNL iPad] 和 [!DNL iPhone] 使用 `profile.mobile.deviceVendor`， `profile.mobile.isMobilePhone` 和 `profile.mobile.isTablet`.<P>此更新不需要客戶採取任何動作。<p><B>重要</b>：客戶可執行適當的目標定位： [!DNL iPad] 和 [!DNL iPhone] 在設定檔指令碼（和JavaScript區段）中，客戶必須透過以下方式進行手動變更 **2024年4月30日**. 如需必須手動變更的替代設定範例，請參閱 [更新 [!DNL iPad] 和 [!DNL iPhone] 在 [!UICONTROL Browser] 對象屬性](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## [!DNL Target] Standard/Premium 24.3.1 （2024年3月4至6日）

此版本預定在下列日期發佈：

* **3 月 4 日**：歐洲、中東和非洲 (EMEA) 區域
* **3 月 5 日**：亞太 (APAC) 區域
* **3 月 6 日**：美洲區域

此版本包含下列增強功能和修正：

* 修正計算活動中不重複選取器數目的邏輯。 (TGT-47878)
* 修正導致下列問題的因素： [!UICONTROL Multivariate] (MVT)活動設定了 [!UICONTROL Analytics for Target] (A4T)報告無法正確顯示。 (TGT-47490)
* 改善當沒有流量的體驗用作控制體驗時，報告中顯示的警告訊息。 (TGT-47537)
* 新增許多後端和本地化修正。

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
| [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
