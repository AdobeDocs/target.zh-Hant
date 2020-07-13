---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 提供最新或即將發行的DNL Adobe Target版本功能、增強功能和修正資訊的發行說明。
title: Adobe Target搶鮮版注意事項
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 1280d152b749442fe9337dc9eba7321d33f17723
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 16%

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期: 2020 年 7 月 13 日**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!NOTE]
>
>* **mbox.js淘汰**: 自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請 [參閱At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[和Adobe Target技能產生器： 開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**: 請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。 如需詳細資訊，請參閱 [Target公告](/help/r-release-notes/target-announcements.md)。


## Target Standard/Premium 20.7.1 (2020 年 7 月 21 日)

此版本包含下列增強功能:

### [!UICONTROL 管理區] UI重新整理

我們使用新技術堆疊逐漸重寫整個 [!DNL Target] UI，以提供改善的效能、縮短發布新功能所需的維護時間，並改善整個產品的使用者體驗。 刷新的第一個部分是 [!UICONTROL Setup] （設定）部分，該部分已更名為 [!UICONTROL Administration]（管理）。

在重新整理時，您將可以使用「管理」區段中的頁面輕鬆執行許多 [!UICONTROL 動作] ，例如：

* 從「實作」標籤(「管理 [!UICONTROL >實作] 」)下載最新的at.js ********&#x200B;檔案。
* 自訂您的at.js設定，並可輕鬆檢閱變更(「管&#x200B;**[!UICONTROL 理]** >實 **[!UICONTROL 作]**」)。
* 修改增強的報表設定，例如預設貨幣和時區、要排除在報表外的IP等。 (管&#x200B;**[!UICONTROL 理]** >報 **[!UICONTROL 告]**)
* 基於隱私權原因模糊化訪客IP位&#x200B;**[!UICONTROL 址(]** 「管理 **[!UICONTROL >]**&#x200B;實作」)
* 在Adobe Admin Console（「管理」>「使用者」）中管理使用者之前，檢視每個工作區及其角色的&#x200B;**[!UICONTROL 現有]****[!UICONTROL 使用者清單]**。
* 在「管理」區段中搜尋並篩選所 [!UICONTROL 有表格] 。

### 增強功能、修正和變更

此發行包含下列增強功能、修正和變更：

* 修正重新整理後網站偏好設定無法保留的問題。 (TGT-37239)
* 修正「在後面插入 [!UICONTROL >影像」無] 法與可縮放向量圖形(SVG)影像一起正常運作的問題。 (TGT-37242)
* 修正具有「發佈者」角色的 [!UICONTROL 使用者] ，無法刪除草稿活動的問題。 (TGT-37358)
* 修正在選取「我的所有工作區」時，使用者無 [!UICONTROL 法編輯活動] 的問題。 (TGT-37276)
* 增強現有的描述檔指令碼資訊卡與觀眾使用資訊。 (TGT-37302)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
