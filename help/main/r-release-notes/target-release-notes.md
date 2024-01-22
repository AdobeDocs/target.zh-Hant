---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 79%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2024年1月22日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## 瀏覽器對象屬性停止支援 iPad 和 iPhone (2024 年 4 月 30 日)

| 停止支援 | 詳細資料 |
|--- |--- |
| 建立對象時使用的[瀏覽器屬性](/help/main/c-target/c-audiences/c-target-rules/browser.md)將停止支援 [!DNL iPad] 和 [!DNL iPhone]。<p>停止支援日期：<P>2024 年 4 月 30 日 | [!DNL Adobe Target] 可讓您[鎖定多個類別屬性中的任一屬性](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括當使用特定[瀏覽器或瀏覽器選項](/help/main/c-target/c-audiences/c-target-rules/browser.md)造訪您網頁的使用者。<P><B>從 2024 年 4 月 30 日起，為對象建立類別時，iPad 和 iPhone 將從可用的[!UICONTROL 瀏覽器]類型下拉式清單中移除。</b><P>如果您有使用[!UICONTROL 瀏覽器]屬性鎖定 iPad 或 iPhone 的對象，則必須在 2024 年 4 月 30 日之前變更這些設定，以確保這些對象繼續按預期發揮作用。<p>如需替代設定的範例，請參閱 [從瀏覽器對象屬性淘汰iPad和iPhone （2024年4月30日）](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard/Premium 24.1.1 (2024 年 1 月 22、23 和 25 日)

此版本預定在下列日期發佈：

* **1 月 22 日**：歐洲、中東和非洲 (EMEA) 區域
* **1 月 23 日**：亞太 (APAC) 區域
* **1 月 25 日**：美洲區域

此版本包含下列增強功能和修正：

* [!UICONTROL 目標分析] 具有收入目標量度的(A4T)活動未將「收入」顯示為欄名稱，且收入量度未在報表中以($)格式顯示。 這是一個已修正的裝飾問題。 (TGT-46995)
* 修正導致報告日期間隔無法正常運作的問題。(TGT-47396)
* 修正客戶使用[!UICONTROL 更多動作]圖示啟用或停用活動後，導致[!UICONTROL 所有活動]頁面上顯示錯誤狀態的問題。(TGT-47367)
* 已修正導致 [!UICONTROL 重要屬性] 報告不針對單一客戶顯示。 (TGT-47272)
* 修正造成單一客戶嘗試啟用「需要驗證」時顯示「裝載無效」訊息的問題。 (TGT-47195)
* 更新 [!DNL Target] UI 中的大量本地化字串。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
