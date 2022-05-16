---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 71190b0f6c66d4c448121a330e7c07b6255ae8be
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 54%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 22.5.1（錯開釋放）2022年5月11至13日)

我們將根據以下錯開的排程發行此版本：

* **5月11日**:亞太區
* **5月12日**:北美(NA)地區
* **5月13日**:歐洲、中東和非洲(EMEA)地區

此版本包含以下增強和修復：

* 修復了導致JavaScript錯誤並阻止某些客戶訪問某些活動詳細資訊的問題 [!UICONTROL Automated Personalization] （美聯社）活動。 (TGT-43526)
* 修復了阻止某些客戶向AP活動添加（或編輯）特定優惠的問題。 (TGT-43503)
* 已修復 [!DNL Target] 顯示以下錯誤消息的UI:「您的全局框可能不同步。 請嘗試重新儲存。」此問題是UI問題，不會影響客戶的實施。 (TGT-43475)
* 修復了一個問題，如果在新操作之前建立了改進和受眾，則該問題會阻止一個客戶編輯活動的體驗級改進和受眾 [!UICONTROL 觀眾] 已部署UI。 (TGT-43433)
* 修復允許客戶選擇重複的問題 [!DNL Adobe Audience Manager] (AAM)編輯活動的報告受眾時的受眾。 (TGT-43430)
* 已修復一個問題，該問題阻止客戶建立重複的受眾，但是位於不同的工作區中。 (TGT-43423)
* 修復了一個問題，使客戶無法刪除在中建立的活動中具有臨時優惠的位置 [!UICONTROL 基於表單的體驗作曲家]。 (TGT-43315)
* 在按一下影像提供並刷新UI後，修復了阻止客戶訪問代碼提供的問題。 (TGT-43566)
* 修復了在編輯、激活和停用指令碼後導致對配置檔案指令碼進行編輯以還原為原始未編輯指令碼的問題。 配置檔案指令碼現在仍處於編輯狀態。 (TGT-43249)
* 修復了在嘗試將受眾移動到另一個工作區時導致以下錯誤的問題：「我們無法完成您的請求。 如果問題仍然存在，請與Adobe客戶服務部聯繫。」 (TGT-43212)
* 已修復在克隆單頁應用()頁的自定義代碼修改時導致SPA錯誤的錯誤。 (TGT-43137)
* 修復了在複製經驗並編輯促銷後導致原始促銷受到影響的問題。 (TGT-41775)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。如需詳細資訊，請參閱「<br>Creative Cloud 發行說明[」。](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html) |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括搶鮮版版本資訊，請參閱 [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md)頁面。 |
