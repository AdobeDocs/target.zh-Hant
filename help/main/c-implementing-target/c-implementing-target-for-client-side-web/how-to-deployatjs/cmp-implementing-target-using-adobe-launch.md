---
keywords: 實現；實現；實現；adobe啟動；啟動；競爭；重定向；體驗platform launch;platform launch；標籤；adobe平台
description: 瞭解如何實施 [!DNL Adobe Target] at.js庫使用 [!DNL Adobe Experience Platform]，實現的首選方法 [!DNL Target]。
title: 如何實施 [!DNL Target] 使用 [!DNL Adobe Experience Platform]?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 10%

---

# 實施[!DNL Target] (使用[!DNL Adobe Experience Platform])

中的標籤 [!DNL Adobe Experience Platform] 是來自的新一代標籤管理功能 [!DNL Adobe]。 標籤為客戶提供了部署和管理分析、營銷和廣告標籤的簡單方法，這些標籤是為相關客戶體驗提供動力所必需的。

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] 已經過品牌重塑，現在是 [!DNL Adobe Experience Platform] 中的一套資料彙集技術。 因此，所有產品文件中出現了幾項術語變更。請參閱以下內容 [文檔](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) 的下一頁。

下表列出了各種來源，您可以從中獲取詳細資訊：

| 資源 | 詳細資料 |
|--- |--- |
| [添加 [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | 本教程提供了實施的逐步說明 [!DNL Target] 在網站中 [!DNL Adobe Experience Platform]。 主題包括新增 at.js JavaScript 資料庫、觸發全域 mbox、新增參數以及與其他解決方案整合。本文是演示如何實施的更大教程的一部分 [!DNL Adobe Experience Platform]，其他 [!DNL Adobe Experience Cloud] 解決方案。 |
| [快速入門手冊](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | 有關部署和管理分析、營銷和廣告標籤的資訊，這些標籤是推動相關客戶體驗所必需的。 |
| [Adobe [!DNL Target] 擴展概述](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | 有關實施的資訊 [!DNL Target] 使用 [!DNL Adobe Experience Platform]。 |

## 使用AT.js實現的優點 [!DNL Target] 擴展 {#section_48B3F938B6F8491DAF798E0DB54EF304}

以下優勢僅在使用中的標籤時適用 [!DNL Adobe Experience Platform] 來實施。 因此， [!DNL Adobe] 強烈建議您在 [!DNL Adobe Experience Platform] 而不是手動執行at.js。

* **解決 [!DNL Adobe Analytics] 和 [!DNL Target] 賽跑條件：** 因為 [!DNL Analytics] 電話可以在 [!DNL Target] 呼叫， [!DNL Target] 呼叫未縫入 [!DNL Analytics] 呼叫。 這種排序可能會導致資料不正確。 的 [!DNL Target] 擴展確保 [!DNL Analytics] 信標呼叫等待到 [!DNL Target] 呼叫完成，成功或未成功。 在中使用標籤 [!DNL Adobe Experience Platform] 解決了客戶在手動實施時可能遇到的資料不一致問題。

   >[!NOTE]
   >
   >使用 [!UICONTROL 發送信標] 操作 [!DNL Adobe Analytics] 擴展，這樣 [!DNL Analytics] 呼叫等待 [!DNL Target] 呼叫。 如果你直接 `s.t()` 或 `s.tl()` 使用自定義代碼， [!DNL Analytics] 呼叫等到 [!DNL Target] 呼叫已完成。

* **防止重定向服務處理不正確：** 如果 [!DNL Target] 和 [!DNL Analytics] 頁面上，並且執行的重定向提議 [!DNL Target]，你可以體驗到 [!DNL Analytics] 跟蹤器在不應該時觸發請求（因為用戶正被重定向到其他URL）。 如果您實施 [!DNL Target] 和 [!DNL Analytics] 通過標籤 [!DNL Adobe Experience Platform]，您將不會遇到此問題。 在中使用標籤 [!DNL Adobe Experience Platform]。 [!DNL Target] 指示 [!DNL Analytics] 中止 [!DNL Analytics] 信標請求。
