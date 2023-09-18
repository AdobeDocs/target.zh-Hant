---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b0bdb7d5004af73c6dff8323266ea4c58972fd80
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 87%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2023 年 9 月 15 日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 23.9.3 （2023年9月18日）

此版本包含下列增強功能和修正：

* 加強[!UICONTROL 視覺化體驗撰寫器] (VEC) 以支援 Lightning DOM (Web 組件)。(TGT-45422)
* 已修復使 VEC 操作以錯誤順序應用的問題。在某些情況下，VEC 會不同步應用部份修改並將額外修改加入引起錯誤的元素 (如果該元素在[!UICONTROL 插入]行動之後顯示)。(TGT-45983)
* 已修正VEC的問題 [!UICONTROL 覆蓋] 功能，現在支援「陰影DOM」中的元素。 (TGT-45202 和 TGT-45262)
* 修正在VEC中開啟單頁應用程式(SPA)頁面，然後前往 [!UICONTROL 瀏覽] 模式導致「後退」和「前進」箭頭無法正常運作。 (TGT-45956)
* 修正部分網頁無法在VEC中載入的問題。 (TGT-45983)

## [!DNL Target] Standard/Premium 23.9.2 (2023 年 9 月 12-14 日)

我們將根據以下排程分批發行此版本：

* **9 月 12 日**：美洲區域
* **9 月 13 日**：亞太 (APAC) 區域
* **9 月 14 日**：歐洲、中東和非洲 (EMEA) 區域

此版本包含下列增強功能和修正：

* 已將 [!DNL Analytics]API 改成新的[!DNL Analytics] API 2.0 版。 (TGT-45345)
* 已修正影響某些客戶的 [!UICONTROL Automated Personalization](AP) 活動的問題，包括及時同步 [!DNL Target] 後端上的活動以及在預覽連結中提供預期的體驗。 (TGT-46202)

## [!DNL Target] Standard/Premium 23.9.1 (2023 年 9 月 6-11 日)

我們將根據以下排程分批發行此版本：

* **9 月 6 日**：美洲區域
* **9 月 7 日**：歐洲、中東和非洲 (EMEA) 區域
* **9 月 11 日**：亞太 (APAC) 區域

此版本包含下列增強功能和修正：

* 已修復造成 [!DNL Target]UI 和 [!DNL Adobe Analytics] UI (針對[!UICONTROL 自動分配]活動等使用 [!UICONTROL Analytics for Target] (A4T) 作為報告來源) 中報告資料不一致的問題。(TGT-46112)
* 將 PUT 呼叫 Target 傳遞 API 的逾時時間增加到 15 秒，以避免發生逾時錯誤。(TGT-46091)
* 已修復瀏覽單次頁面應用程式 (SPA) 網站時 URL 無法持續&#x200B;&#x200B;更新的問題。(TGT-45417)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
