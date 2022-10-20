---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1b737f963fe63770cb04d05f3414ed946548d882
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 62%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2022 年 10 月 19 日**

若要檢視目前版本的相關資訊，請參閱「[Target 版本注意事項](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 22.10.3 (分批發行：2022 年 25 月 10 至 27 日)

我們將根據以下排程分批發行此版本：

* **10 月 25 日**：歐洲、中東和非洲 (EMEA) 區域
* **26 月 10 日**：亞太 (APAC) 區域
* **10 月 27 日**：美洲區域

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| [!DNL Recommendations] | 在中新增好記名稱 [!UICONTROL Analytics for Target] A4T報表。 以前， [!DNL Target] 僅列出體驗ID。 此增強功能會協調報表 [!DNL Adobe Analytics] 和 [!DNL Target] 並協助客戶簡化在A4T中建立報表的程式。 (TGT-41853) |
| 針對 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標]<br>(可供選取客戶進行測試。 將在未來版本中提供給所有客戶使用。) | 請注意下列變更：<ul><li>針對 [!UICONTROL Analytics for Target] A4T 報告中的[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動，新增對二進位和最大化量度的支援</li><li>保留現有活動的行為，直到2023年2月。 在此日期之後，將停止活動以強制現有活動遷移至新行為</li><li>從 2023 年 2 月 20 日開始，將不再支援 [!DNL Target] 活動中的 `averagetimespentonsite`、 `bouncerate` 和 `entries` 量度。</li></ul> |

* 在 [!DNL Target] UI可協助客戶更有效率地導覽受眾建立器，並了解如何使用可能不熟悉的功能。 (TGT-44139)
* 新增功能，以防止客戶編輯已停用的活動 [!DNL Target] 因為它使用不支援的量度。 UI中的訊息會引導客戶複製活動，然後更新轉換量度。

   透過此版本 `averagetimespentonsite`, `bouncerate`，和 `entries` 量度 [!DNL Target] 新活動將遭取代。 在2023年2月之前，現有活動可繼續使用這些量度。 (TGT-43860、TGT-43861和TGT-43650)

* 在 [!DNL Target] UI可協助客戶在建立或編輯 [!UICONTROL 自動鎖定目標] 使用A4T的活動。 (TGT-43713)

## 額外的版本注意事項和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [版本注意事項：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |


## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
