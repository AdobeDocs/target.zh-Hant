---
keywords: 實作；adobe launch;launch；競爭；重新導向；體驗platform launch;platform launch；標籤；adobe platform
description: 了解如何使用 [!DNL Adobe Experience Platform], the preferred method to implement [!DNL Target]實作 [!DNL Adobe Target] at.js資料庫。
title: 如何使用 [!DNL Adobe Experience Platform]實作 [!DNL Target] ?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 11%

---

# 使用[!DNL Target]實施 [!DNL Adobe Experience Platform]

[!DNL Adobe Experience Platform]中的標籤是[!DNL Adobe]中的新一代標籤管理功能。 標籤可讓客戶透過簡單的方式部署及管理分析、行銷及廣告標籤，這些標籤是支援相關客戶體驗所必需的。

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] 已經過品牌重塑，現在是 [!DNL Adobe Experience Platform] 中的一套資料彙集技術。 因此，所有產品文件中出現了幾項術語變更。有關術語更改的綜合參考，請參閱以下[document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

下表列出了各種來源，您可在其中取得詳細資訊：

| 資源 | 詳細資料 |
|--- |--- |
| [新增 [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | 本教學課程提供逐步指示，說明如何在具有[!DNL Adobe Experience Platform]中標籤的網站中實作[!DNL Target]。 主題包括新增 at.js JavaScript 資料庫、觸發全域 mbox、新增參數以及與其他解決方案整合。本文是大型教學課程的一部分，說明如何實作[!DNL Adobe Experience Platform]和其他[!DNL Adobe Experience Cloud]解決方案。 |
| [快速入門手冊](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | 關於部署及管理為相關客戶體驗提供支援所需的分析、行銷及廣告標籤的資訊。 |
| [ [!DNL Target] Adobe擴充功能概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | 有關使用[!DNL Adobe Experience Platform]實作[!DNL Target]的資訊。 |

## 使用[!DNL Target]擴充功能實作at.js的優點 {#section_48B3F938B6F8491DAF798E0DB54EF304}

只有在[!DNL Adobe Experience Platform]中使用標籤來實作at.js時，才適用下列優點。 因此，[!DNL Adobe]強烈建議您在[!DNL Adobe Experience Platform]中使用標籤，而非手動實作at.js。

* **解決 [!DNL Adobe Analytics] 和 [!DNL Target] 競爭條件：** 由於可在 [!DNL Analytics] 呼叫之前觸發呼叫，因 [!DNL Target] 此呼 [!DNL Target] 叫不會聯結 [!DNL Analytics] 呼叫。此排序可能會導致資料不正確。 [!DNL Target]擴充功能可確保[!DNL Analytics]信標呼叫等待[!DNL Target]呼叫完成，無論是否成功。 在[!DNL Adobe Experience Platform]中使用標籤可解決客戶手動實施時可能遇到的資料不一致問題。

   >[!NOTE]
   >
   >在[!DNL Adobe Analytics]擴充功能中使用[!UICONTROL 傳送信標]動作，使[!DNL Analytics]呼叫等待[!DNL Target]呼叫。 如果您使用自訂程式碼直接呼叫`s.t()`或`s.tl()`,[!DNL Analytics]呼叫不會等到[!DNL Target]呼叫完成。

* **避免不正確的重新導向選件處理：** 如果頁面上有 [!DNL Target] 和 [!DNL Analytics] ，且有 [!DNL Target]執行的重新導向選件，您可能會遇到 [!DNL Analytics] 追蹤器觸發不應觸發的要求的情況（因為系統正將使用者重新導向至不同的URL）。如果您透過[!DNL Adobe Experience Platform]中的標籤實作[!DNL Target]和[!DNL Analytics]，將不會遇到此問題。 在[!DNL Adobe Experience Platform]中使用標籤， [!DNL Target]指示[!DNL Analytics]中止[!DNL Analytics]信標請求。
