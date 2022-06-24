---
keywords: 實作;at.js;javascript 資料庫
description: 瞭解如何部署Adobe [!DNL Target] at.js JavaScript庫使用Adobe Experience Platform中的標籤或沒有標籤管理器。
title: 如何部署at.js?
feature: Implement Server-side
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 15%

---

# 如何部署 at.js

有關如何部署 [!DNL Adobe Target] JavaScript庫at.js，使用中的標籤 [!DNL Adobe Experience Platform] 或者沒有標籤管理器。

您可使用下列方法部署 at.js:

* **[實施 [!DNL Target] 使用標籤 [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}**:中的標籤 [!DNL Adobe Experience Platform] 是來自的新一代標籤管理功能 [!DNL Adobe]。 標籤為客戶提供了部署和管理分析、營銷和廣告標籤的簡單方法，這些標籤是為相關客戶體驗提供動力所必需的。

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] 已經過品牌重塑，現在是 [!DNL Adobe Experience Platform] 中的一套資料彙集技術。 因此，所有產品文件中出現了幾項術語變更。請參閱以下內容 [文檔](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) 的下一頁。

* **[在沒有標籤管理器的情況下實現目標](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}**:無需使用標籤管理器即可實現目標(例如， [!DNL Adobe Experience Platform])。
* **使用第三方標籤管理器實現目標**: [中的標籤 [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} is the preferred method to implement Target; however, you can also implement Target using a third-party tag manager, including Tealium, Ensighten, and Google Tag. For a list of benefits of using Launch, see [Advantages of implementing at.js using the [!DNL Adobe Target] 擴展](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}。

   但是，如果您知道如何實施 [!DNL Target] 如果沒有標籤管理器，您就可以輕鬆地使用第三方標籤管理器來實現，而不是在站點代碼中使用硬編碼at.js。

   以下是兩個相關主題，將幫助您實施 [!DNL Target] 與第三方標籤管理器一起：

   * [實作之前](https://developer.adobe.com/target/before-implement/)
   * [ [!DNL Target] 不使用標籤管理程式實作 ](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)

   有關詳細資訊，請務必檢查第三方標籤管理器的文檔。

實施 [!DNL Target] 使用單頁應用時(SPA)，請參見 [單頁應用程式實現](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/){target=_blank}。
