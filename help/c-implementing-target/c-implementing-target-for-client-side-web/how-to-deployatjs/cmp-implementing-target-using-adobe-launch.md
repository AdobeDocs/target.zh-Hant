---
description: Launch 為 Adobe 新一代的標籤管理平台，且為實作 Adobe Target 的推薦方法。Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。
keywords: 實作;adobe launch;launch;競爭;重新導向
seo-description: Launch 為 Adobe 新一代的標籤管理平台，且為實作 Adobe Target 的推薦方法。Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。
seo-title: 使用 Adobe Launch 實作 Target
title: 使用 Adobe Launch 實作 Target
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 使用 Adobe Launch 實作 Target{#implement-target-using-adobe-launch}

Launch 為 Adobe 新一代的標籤管理平台，且為實作 Adobe Target 的推薦方法。Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。

## 使用 Adobe Launch 實作 Target {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch 為 Adobe 新一代的標籤管理平台，且為實作 Adobe Target 的推薦方法。Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。

下表列出可獲取有關 Launch 之更多資訊的各種來源:

| 資源 | 詳細資料 |
|--- |--- |
| [使用Adobe Target延伸模組教學課程實作](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | 本教學課程提供逐步說明，指導您使用 Launch 在網站中實作 Adobe Target。主題包括新增 at.js JavaScript 資料庫、觸發全域 mbox、新增參數以及與其他解決方案整合。本文是大規模教學課程中的一部分，說明如何實作 Adobe Launch 及其他 Adobe Experience Cloud 解決方案。 |
| [Adobe Launch 文件](https://docs.adobelaunch.com/getting-started) | 關於部署及管理為相關客戶體驗提供支援所需的所有分析、行銷和廣告標籤資訊。 |
| [Adobe Target延伸模組文件](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension) | 使用 Launch 實作 Target 的相關資訊。 |

## 使用 Target 啟動擴充功能實作 at.js 的優點 {#section_48B3F938B6F8491DAF798E0DB54EF304}

只有在使用 Adobe Launch 實作 at.js 時，才適用以下優點。基於此原因，我們強烈建議您使用 Adobe Launch 而非 DTM，或手動實作 at.js。

* **允許非同步部署 Target:** 如需詳細資訊，請參閱 [Adobe Target 擴充功能說明文件](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension)中的「具有非同步部署的 Adobe Target 擴充功能」。
* **解決 Analytics 與 Target 競爭條件:**由於可以在 Target 呼叫之前觸發 Analytics 呼叫，因此 Target 呼叫不會聯結 Analytics 呼叫，這可能會造成資料不正確。從 Launch 0.6.0 開始，Target Launch 擴充功能會確保 Analytics 指標呼叫將等待 Target 呼叫完成，無論是否成功。這應該可以解決客戶可能遇到的資料不一致問題。
* **避免不正確的重新導向選件處理**當頁面上同時有 Target 和 Analytics，而且有 Target 正在執行的重新導向選件時，可能會發生 Analytics 追蹤器觸發不應觸發的要求之情況，因為系統正在將使用者重新導向至不同的 URL。如果您透過 Launch 實作 Target 和 Analytics，則不會遇到此問題，因為使用 Launch ，Target 會指示 Analytics 中止 Analytics 指標請求。

