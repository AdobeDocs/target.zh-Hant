---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: dd8c0f3781625985f53aeb3b659fb4498a3e10e8
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 49%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外， [!DNL Target] API、SDK、 [!DNL Adobe Experience Platform Web SDK]、 at.js和其他平台更改（如果適用）也包括在內。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 22.3.1（錯開釋放，確定日期）

此版本包含以下更改和增強：

* 修復了在編輯、激活和停用指令碼後導致對配置檔案指令碼進行編輯以還原為原始未編輯指令碼的問題。 配置檔案指令碼現在仍處於編輯狀態。 (TGT-43249)
* 已修復導致 [!DNL Target] 移動「草稿」狀態的活動中使用的受眾時使用的UI:「我們無法完成您的請求。 如果問題仍然存在，請與Adobe客戶服務部聯繫。」 (TGT-43212)
* 已修復導致 [!UICONTROL 包括] 和 [!UICONTROL 排除] 編輯活動時要為組合的受眾禁用的選項。 (TGT-43422)
* 修復了在編輯活動時阻止某些客戶查看可用受眾清單的問題。 (TGT-43404)
* 已修復阻止某些客戶從「 」中刪除IP地址的問題[!UICONTROL 要從中排除的IP [!DNL Target] 報告資料]&quot;清單 [!UICONTROL 管理] > [!UICONTROL 報告]。 (TGT-43384)
* 已修復阻止在受眾標準中使用負數的問題，該問題檢查任何變數是否「大於」、「大於或等於」、「小於」或「小於或等於」。 (TGT-43367)
* 已修復阻止客戶看到 [!UICONTROL 受眾詳細資訊] 建立組合受眾時打卡。 (TGT-43303)
* 已修復導致 [!DNL Target] UI或新 [!UICONTROL 觀眾] UI為某些客戶提前超時。 (TGT-42590 和 TGT-43273)

## [!DNL Target] 平台發佈（3月30日）

此版本包含下列增強功能：

* 按一下跟蹤度量將在Delivery API請求中包括將Analytics用作報告源(A4T)和處理客戶端事件的活動的分析負載。 (TNT-43073)

## [!DNL Target Standard] 觀眾更新（3月28日）

此版本包含以下更新：

* 新 [!UICONTROL 觀眾] 將為所有用戶啟用UI [!DNL Target Standard] 客戶。

## 目標標準/高級客戶工程修復（2022年3月22日）

此維護版本包含以下增強功能：

* 添加要返回的功能 [!DNL Analytics] 負載資料 `prefetch` 視圖和 `pageLoad` 使用 [!UICONTROL 傳遞API] 與使用 [!UICONTROL 分析作為報告源] (A4T)。 (TNT-43198)
* 已更新bot篩選用戶代理清單，以允許在日本常用的瀏覽器類型。 (TNT-43867)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh_Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。如需詳細資訊，請參閱「<br>Creative Cloud 發行說明[」。](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant) |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 發行說明 - 發行前](/help/main/r-release-notes/target-release-notes.md)頁面。 |