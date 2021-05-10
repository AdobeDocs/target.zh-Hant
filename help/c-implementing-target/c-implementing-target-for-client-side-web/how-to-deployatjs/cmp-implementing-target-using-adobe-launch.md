---
keywords: 實施；實施；實施；adobe launch;launch;race;redirect；體驗platform launch;platform launch
description: 瞭解如何使用Adobe Experience Platform Launch實作Adobe [!DNL Target] at.js程式庫，這是實作Adobe [!DNL Target]的偏好方法。
title: 如何使用Adobe啟動實施 [!DNL Target] ?
feature: 實作伺服器端
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a69737f49a52cde703627f91d4b97609c1796ee6
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 6%

---

# 使用[!DNL Adobe Platform Launch]實作[!DNL Target]

[!DNL Adobe Experience Platform Launch] 是來自的新一代標籤管理平台， [!DNL Adobe] 且是實作的首選方法 [!DNL Adobe Target]。[!DNL Platform Launch] 為客戶提供簡單的方式，來部署及管理提供相關客戶體驗所需的分析、行銷和廣告標籤。

## 使用[!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25}實作[!DNL Target]

下表列出了各種來源，您可從中取得有關[!DNL Platform Launch]的更多資訊：

| 資源 | 詳細資料 |
|--- |--- |
| [使 [!DNL Target] 用Adobe Target擴 [!UICONTROL 展教程實施]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | 本教學課程提供在具有[!DNL Platform Launch]的網站中實作[!DNL Target]的逐步指示。 主題包括新增 at.js JavaScript 資料庫、觸發全域 mbox、新增參數以及與其他解決方案整合。本文是較大教學課程的一部分，其中說明如何實作[!DNL Platform Launch]和其他[!DNL Adobe Experience Cloud]解決方案。 |
| [[!DNL Adobe Platform Launch] 文件](https://experienceleague.adobe.com/docs/launch/using/get-started/quick-start.html#get-started) | 有關部署和管理分析、行銷和廣告標籤的資訊，這些標籤是推動相關客戶體驗的必要工具。 |
| [ [!DNL Target] AdobeExtension檔案](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | 有關使用[!DNL Platform Launch]實作[!DNL Target]的資訊。 |

## 使用[!DNL Target] [!DNL Platform Launch]擴充功能{#section_48B3F938B6F8491DAF798E0DB54EF304}實作at.js的優點

下列優點僅適用於使用[!DNL Platform Launch]實作at.js時。 因此，[!DNL Adobe]強烈建議您使用[!DNL Platform Launch]，而非手動實作at.js。

* **解決 [!DNL Adobe Analytics] 和 [!DNL Target] 種族條件：** 由於 [!DNL Analytics] 呼叫可在呼叫前 [!DNL Target] 引發， [!DNL Target] 所以呼叫不會銜接至呼 [!DNL Analytics] 叫。此排序可能會導致資料不正確。 從0.6.0開始，[!DNL Platform Launch]擴充功能可確保[!DNL Analytics]信標呼叫會等到[!DNL Target]呼叫完成，無論是否成功。 使用[!DNL Platform Launch]可解決客戶在手動實施時可能遇到的資料不一致問題。
* **防止不正確的重新導向選件處理：** 如果您在頁面上有 [!DNL Target]  [!DNL Analytics]  [!DNL Target] [!DNL Analytics] ，且有重新導向選件由執行，您可能會遇到追蹤器在不應觸發請求時（因為使用者被重新導向至不同的URL）觸發的情況。如果您透過[!DNL Platform Launch]實作[!DNL Target]和[!DNL Analytics]，將不會遇到此問題。 使用[!DNL Platform Launch], [!DNL Target]指示[!DNL Analytics]中止[!DNL Analytics]信標請求。
