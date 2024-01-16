---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 78bedce2134061edc48baf7023107e1dd48da2a1
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 49%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2023年1月16日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## 從瀏覽器對象屬性淘汰iPad和iPhone （2024年4月30日）

| 淘汰 | 詳細資料 |
|--- |--- |
| [!DNL iPad] 和 [!DNL iPhone] 即將從以下專案停用 [瀏覽器屬性](/help/main/c-target/c-audiences/c-target-rules/browser.md) 用於建立對象。<p>淘汰日期：<P>2024年4月30日 | [!DNL Adobe Target] 可讓您 [鎖定任一類別屬性](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括使用特定 [瀏覽器或瀏覽器選項](/help/main/c-target/c-audiences/c-target-rules/browser.md) 訪客造訪您的頁面時。<P><B>自2024年4月30日起，iPad和iPhone將從可用的中移除 [!UICONTROL 瀏覽器] 建立對象的類別時，輸入下拉式清單。</b><P>如果您的對象是使用 [!UICONTROL 瀏覽器] attribute的環境中，您必須在2024年4月30日之前變更這些設定，以確保這些對象能繼續如預期般運作。<P>日後應使用下列設定：<ul><li>[!UICONTROL 行動] > [!UICONTROL 是平板電腦]<P>![行動就是平板電腦](/help/main/r-release-notes/assets/is-tablet.png)</li><li>[!UICONTROL 行動] > [!UICONTROL 裝置行銷名稱] [!UICONTROL 符合] [!DNL iPad]<P>![iPad](/help/main/r-release-notes/assets/ipad.png)</li><li>[!UICONTROL 行動] > [!UICONTROL 裝置行銷名稱] [!UICONTROL 符合] [!DNL iPhone]<p>![iPhone](/help/main/r-release-notes/assets/iphone.png)</li></ul> |

## [!DNL Target] Standard/Premium 24.1.1 （2024年1月22日、 23日和25日）

此版本預定在下列日期發佈：

* **1 月 22 日**：歐洲、中東和非洲 (EMEA) 區域
* **1 月 23 日**：亞太 (APAC) 區域
* **1 月 25 日**：美洲區域

此版本包含下列增強功能和修正：

* 修正造成報告日期間隔無法正常運作的問題。 (TGT-47396)
* 已修正導致在顯示錯誤狀態的問題 [!UICONTROL 所有活動] 客戶使用或停用活動後的頁面 [!UICONTROL 更多動作] 圖示。 (TGT-47367)
* 已修正導致 [!UICONTROL 重要屬性] 報告不顯示給一個客戶。 (TGT-47272)
* 修正當一個客戶嘗試啟用「需要驗證」時，會顯示「裝載無效」訊息的問題。 (TGT-47195)
* 更新 [!DNL Target] UI。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
