---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
title: 'Adobe Target 版本說明 (最新) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: fe68bfb124a5c8c58fbc6822d31b49257a0cfc0b
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 31%

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!IMPORTANT]
>
>* **Adobe再次在Gartner個人化引擎魔力像限中獲評為領導者**: 在2020年第三年度的Gartner個人化引擎魔力像限報告中，Adobe再次獲評為領導者。 Gartner個人化引擎魔力像限評估了15個標準的供應商，這些標準分為兩類： 願景的完整性與執行能力。 [在Adobe部落格上閱讀相關資訊](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.js淘汰**: 自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請 [參閱At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[和Adobe Target技能產生器： 開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**: 請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。 如需詳細資訊，請參閱 [Target公告](/help/r-release-notes/target-announcements.md)。


括號內的問題編號供 [!DNL Adobe] 內部使用。

## Target Standard/Premium 20.7.1 (2020 年 7 月 27 日)

此版本包含下列變更:

### [!UICONTROL 管理區] UI重新整理

我們使用新技術堆疊逐漸重寫整個 [!DNL Target] UI，以提供改善的效能、縮短發布新功能所需的維護時間，並改善整個產品的使用者體驗。 刷新的第一個部分是 [!UICONTROL Setup] （設定）部分，該部分已更名為 [!UICONTROL Administration]（管理）。

在重新整理時，您將可以使用「管理」區段中的頁面輕鬆執行許多 [!UICONTROL 動作] ，例如：

* 從「實作」標籤(「管理 [!UICONTROL >實作] 」)下載最新的at.js ********&#x200B;檔案。
* 自訂您的at.js設定，並可輕鬆檢閱變更(「管&#x200B;**[!UICONTROL 理]** >實 **[!UICONTROL 作]**」)。
* 修改增強的報表設定，例如預設貨幣和時區、要排除在報表外的IP等。 (管&#x200B;**[!UICONTROL 理]** >報 **[!UICONTROL 告]**)
* 基於隱私權原因模糊化訪客IP位&#x200B;**[!UICONTROL 址(]** 「管理 **[!UICONTROL >]**&#x200B;實作」)
* 在Adobe Admin Console（「管理」>「使用者」）中管理使用者之前，檢視每個工作區及其角色的&#x200B;**[!UICONTROL 現有]****[!UICONTROL 使用者清單]**。
* 在「管理」區段中搜尋並篩選所 [!UICONTROL 有表格] 。

如需詳細資訊，請參 [閱管理目標概述](/help/administrating-target/administrating-target.md)。

### 增強功能、修正和變更

此發行包含下列增強功能、修正和變更：

* 修正重新整理後網站偏好設定無法保留的問題。 (TGT-37239)
* 修正「在後面插入 [!UICONTROL >] 影像」無法與可縮放向量圖形(SVG)影像正常運作的問題。 (TGT-37242)
* 修正具有「發佈者」角色的 [!UICONTROL 使用者] ，無法刪除草稿活動的問題。 (TGT-37358)
* 修正在選取「我的所有工作區」時，使用者無 [!UICONTROL 法編輯活動] 的問題。 (TGT-37276)

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明——目標伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 與Adobe Target伺服器端API相關的發行說明。 |
| [發行說明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 與Adobe Target的Node.js SDK相關的發行說明。 |
| [發行說明——目標Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 與Adobe Target Java SDK相關的發行說明。 |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js JavaScript程式庫各版本變更的詳細資訊。 |
| [mbox.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 本頁面顯示每個 mbox.js 版本的變更。<br>請注意，mbox.js程式庫已不再開發。 所有客戶應該從 mbox.js 移轉至 at.js。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](../r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參 [閱Experience Cloud發行說明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |
