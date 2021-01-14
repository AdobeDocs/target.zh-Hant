---
keywords: implement;implementing;implementation;adobe launch;launch;race;redirect;experience platform launch
description: Adobe Experience Platform Launch是Adobe的新一代標籤管理平台，是建置Adobe Target的首選方法。 Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。
title: 使用 Adobe Launch 實作 Target
feature: Implement Server-side
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 81%

---


# 使用 Adobe Launch 實作 Target

Adobe Experience Platform Launch是Adobe的新一代標籤管理平台，是建置Adobe Target的首選方法。 Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。

## 使用 Adobe Launch 實作 Target {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch 為 Adobe 新一代的標籤管理平台，且為實作 Adobe Target 的推薦方法。Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。

下表列出可獲取有關 Launch 之更多資訊的各種來源:

| 資源 | 詳細資料 |
|--- |--- |
| [使用Adobe Target擴充功能教學課程實作Target](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | 本教學課程提供逐步說明，指導您使用 Launch 在網站中實作 Adobe Target。主題包括新增 at.js JavaScript 資料庫、觸發全域 mbox、新增參數以及與其他解決方案整合。本文是大規模教學課程中的一部分，說明如何實作 Adobe Launch 及其他 Adobe Experience Cloud 解決方案。 |
| [Adobe Launch 文件](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html) | 關於部署及管理為相關客戶體驗提供支援所需的所有分析、行銷和廣告標籤資訊。 |
| [Adobe Target擴充功能檔案](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | 使用 Launch 實作 Target 的相關資訊。 |

## 使用Target Launch擴充功能{#section_48B3F938B6F8491DAF798E0DB54EF304}實作at.js的優點

只有在使用 Adobe Launch 實作 at.js 時，才適用以下優點。基於此原因，我們強烈建議您使用 Adobe Launch 而非 DTM，或手動實作 at.js。

* **解決 Analytics 與 Target 競爭條件:** 由於可以在 Target 呼叫之前觸發 Analytics 呼叫，因此 Target 呼叫不會聯結 Analytics 呼叫。這可能會造成資料不正確。從 0.6.0 開始，Target Launch 擴充功能會確保 Analytics 指標呼叫等待 Target 呼叫完成，無論是否成功。這應該可以解決客戶可能遇到的資料不一致問題。
* **避免不正確的重新導向選件處理:** 如果頁面上有 Target 和 Analytics，而且有 Target 執行的重新導向選件，可能會發生 Analytics 追蹤器觸發不應觸發之要求的情況 (因為系統正在將使用者重新導向至不同的 URL)。如果您透過 Launch 實作 Target 和 Analytics，則不會遇到此問題。Target 會使用 Launch 指示 Analytics 取消 Analytics 指標要求。
