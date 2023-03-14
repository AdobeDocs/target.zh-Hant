---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 59%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期；2023 年 3 月 14 日**

若要檢視目前版本的相關資訊，請參閱 [Target 版本注意事項](release-notes.md)。這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 22.15.1 (2023 年 3 月 8 日和 9 日)

我們將根據以下排程分批發行此版本：

* **3 月 8 日**：美洲區域
* **3 月 9 日**：歐洲、中東和非洲 (EMEA) 區域
* **3 月 9 日**：亞太 (APAC) 區域

>[!NOTE]
>
>由於此後已修正的問題，「針對 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標]「 3月8日和9日發行的功能已暫時移除。 進一步的內部測試後，此功能將在未來幾週內再次發行。

此版本包含下列修正：

* 更新自訂Web元件的編寫，使用 [!UICONTROL 可視化體驗撰寫器] (VEC):

   * 透過改善編寫程式，修正VEC中陰影DOM元素的選取，因此不會依賴 [!DNL Target] 製作陰影根時的實作類型。 現在，在VEC中選取「影子DOM」元素，即可供任何網站使用。
   * 修正無法在VEC中使用#Shadow DOM載入HTML元素的問題。 (TGT-35801)
   * 修正SPA網站使用ShadowDOM的VEC問題。 (TGT-43169)
   * 修正最佳化目標的問題：「已點按元素」未正確識別ShadowDOM中的CSS選取器。

>[!NOTE]
>
>若要確保傳送在VEC中撰寫的變更，請確定您使用 [!DNL Target] SDK([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js))，其版本大於2.8。

**已知問題**:使用 [!DNL Adobe Experience Platform Web SDK] 無法正常運作。 (TNT-47012)

## at.js 版本 2.10.2 (2023 年 3 月 7 日)

* 修正造成 `trackEvent` 函數總是傳回錯誤的問題。

有關所有 at.js 版本的資訊，請參閱 [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。

## 額外的版本注意事項和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [版本注意事項：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |


## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
