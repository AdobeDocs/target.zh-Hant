---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e130c68c838e799228956c598c583038a2f68ecf
workflow-type: ht
source-wordcount: '494'
ht-degree: 100%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Adobe Target] 邊緣已規劃基礎設施的升級 {#edge}

已規劃的邊緣基礎設施升級需要已加入允許清單的其他 IP 位址或網域。檢查邊緣部署 41-48 的 NAT 和 IP 位址/網域，並將其加入允許清單。基礎設施升級將於 2023 年 8 月 9 日開始。


如需詳細資訊，請參閱 *Adobe Target 開發人員指南*&#x200B;中的「[允許清單 Target 邊緣節點](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank}」。

## [!DNL Target] Standard/Premium 23.8.1 (2023 年 8 月 9 日)

此版本包含下列增強功能和修正：

* 修正有時導致活動無法正確同步的問題，如「[!UICONTROL 狀態]」欄 (在「[!UICONTROL 活動]」清單頁面上)。(TGT-46010 和 TGT-44831)
* 修正有時會阻止「[!UICONTROL 在 Analytics 中檢視]」連結顯示在「活動[!UICONTROL 報告]」頁面 (這些是使用 [!UICONTROL Analytics for Target] (A4T) 作為報告來源的活動)。(TGT-45808)
* 調整表格中值的顯示方式，現在以百分比形式顯示，而不是帶小數點的數字。例如，顯示 8%，而非顯示 .08。(TGT-45548)
* 修正讓客戶無法使用鍵盤焦點移至下一個元素的問題 (在「[!UICONTROL 體驗鎖定目標]」(Experience Targeting，XT) 活動的「[!UICONTROL 目標和設定]」頁面內)。(TGT-44526)
* 修正建立活動時開啟「[!UICONTROL 新增對象]」對話框後導致鍵盤失去焦點的問題。(TGT-44525)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

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
