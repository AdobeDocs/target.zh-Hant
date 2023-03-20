---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: ht
source-wordcount: '446'
ht-degree: 100%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2023 年 3 月 14 日**

若要檢視目前版本的相關資訊，請參閱 [Target 版本注意事項](release-notes.md)。這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 22.15.1 (2023 年 3 月 8 日和 9 日)

我們將根據以下排程分批發行此版本：

* **3 月 8 日**：美洲區域
* **3 月 9 日**：歐洲、中東和非洲 (EMEA) 區域
* **3 月 9 日**：亞太 (APAC) 區域

>[!NOTE]
>
>因為問題已修正，所以 3 月 8 日和 9 日發行的為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]功能最佳化的 A4T 量度已暫時移除。經過進一步的內部測試後，該功能將在未來幾週內再次發佈。

此版本包含下列修正：

* 為使用 [!UICONTROL Visual Experience Composer] (VEC) 編寫自訂 Web 元件進行更新：

   * 透過改進編寫程序來修正 VEC 中選取 Shadow DOM 元素的問題，因此在編寫 Shadow 根時不依賴 [!DNL Target] 實作類型。現在，在 VEC 中選取 Shadow DOM 元素應該適用於任何網站。
   * 已修正在 VEC 中使用 #Shadow DOM 無法載入 HTML 元素的問題。(TGT-35801)
   * 已修正 SPA 網站使用 ShadowDOM 的 VEC 問題。(TGT-43169)
   * 已修正最佳化目標的問題：「點擊元素」未正確識別 ShadowDOM 中的 CSS 選取器。

>[!NOTE]
>
>為確保傳遞在 VEC 中編寫的變更，請確保您使用的是 2.8 版本以後的 [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js))。

**已知問題**：使用 [!DNL Adobe Experience Platform Web SDK] 時，對 Shadow 根元素的點擊追蹤無法正常運作。(TNT-47012)

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
