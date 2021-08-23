---
keywords: 實作；adobe launch;launch；競爭；重新導向；體驗platform launch;platform launch
description: 了解如何使用Adobe Experience Platform Launch實作Adobe [!DNL Target] at.js程式庫，此為實作Adobe [!DNL Target]的慣用方法。
title: 如何使用Launch實作 [!DNL Target] Adobe?
feature: 實作伺服器端
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: fd7d3900f9e5d1a6c3d13fd2452de8528f8fd248
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 5%

---

# 使用[!DNL Adobe Platform Launch]實作[!DNL Target]

[!DNL Adobe Experience Platform Launch] 是新一代標籤管理平台， [!DNL Adobe] 且是實作的推薦方 [!DNL Adobe Target]法。[!DNL Platform Launch] 可讓客戶透過簡單的方式部署及管理分析、行銷及廣告標籤，以便支援相關客戶體驗。

## 使用[!DNL Platform Launch]實作[!DNL Target] {#topic_5234DDAEB0834333BD6BA1B05892FC25}

下表列出了各種來源，您可在其中獲取有關[!DNL Platform Launch]的更多資訊：

| 資源 | 詳細資料 |
|--- |--- |
| [ [!DNL Target] 使用Adobe Target擴充功 [!UICONTROL 能實作教學課程]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | 本教學課程提供逐步指示，說明如何使用[!DNL Platform Launch]在網站中實作[!DNL Target]。 主題包括新增 at.js JavaScript 資料庫、觸發全域 mbox、新增參數以及與其他解決方案整合。本文是大型教學課程的一部分，說明如何實作[!DNL Platform Launch]和其他[!DNL Adobe Experience Cloud]解決方案。 |
| [Adobe Experience Platform中標籤的快速入門手冊](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | 關於部署及管理為相關客戶體驗提供支援所需的分析、行銷及廣告標籤的資訊。 |
| [ [!DNL Target] Adobe擴充功能檔案](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | 有關使用[!DNL Platform Launch]實作[!DNL Target]的資訊。 |

## 使用[!DNL Target] [!DNL Platform Launch]擴充功能實作at.js的優點 {#section_48B3F938B6F8491DAF798E0DB54EF304}

只有在您使用[!DNL Platform Launch]實作at.js時，才適用下列優點。 因此，[!DNL Adobe]強烈建議您使用[!DNL Platform Launch]，而非手動實作at.js。

* **解決 [!DNL Adobe Analytics] 和 [!DNL Target] 競爭條件：** 由於可在 [!DNL Analytics] 呼叫之前觸發呼叫，因 [!DNL Target] 此呼 [!DNL Target] 叫不會聯結 [!DNL Analytics] 呼叫。此排序可能會導致資料不正確。 從0.6.0開始，[!DNL Platform Launch]擴充功能可確保[!DNL Analytics]信標呼叫等待[!DNL Target]呼叫完成，無論是否成功。 使用[!DNL Platform Launch]解決客戶手動實施時可能遇到的資料不一致問題。
* **避免不正確的重新導向選件處理：** 如果頁面上有 [!DNL Target] 和 [!DNL Analytics] ，且有 [!DNL Target]執行的重新導向選件，您可能會遇到 [!DNL Analytics] 追蹤器觸發不應觸發的要求的情況（因為系統正將使用者重新導向至不同的URL）。如果您透過[!DNL Platform Launch]實作[!DNL Target]和[!DNL Analytics]，將不會遇到此問題。 使用[!DNL Platform Launch], [!DNL Target]指示[!DNL Analytics]中止[!DNL Analytics]信標請求。
