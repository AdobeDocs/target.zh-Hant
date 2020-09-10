---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 提供最新或即將發行的DNL Adobe Target版本功能、增強功能和修正資訊的發行說明。
title: Adobe Target搶鮮版注意事項
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 00749d54d0416c57364ff648bd0911e636c84bc7
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 11%

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新: 2020 年 9 月 9 日**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>* **Adobe再次在Gartner個人化引擎魔力像限中獲評為領導者**:在2020年第三年度的Gartner個人化引擎魔力像限報告中，Adobe再次獲評為領導者。 Gartner個人化引擎魔力像限評估了15個標準的供應商，這些標準分為兩類：願景的完整性與執行能力。 [在Adobe部落格上閱讀相關資訊](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.js淘汰**:自2021年1月18日起，Adobe Target將不再支援mbox.js程式庫。 在2021年1月18日後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請 [參閱At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[和Adobe Target技能產生器：開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**:請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。 如需詳細資訊，請參閱 [Target公告](/help/r-release-notes/target-announcements.md)。


## Target Standard/Premium 20.8.2 (2020 年 9 月 10 日)

| 功能 | 詳細資料 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Control recommendations slots within criteria sequences | 「准則序列」現在可讓您控制每個建議准則佔用的槽數，讓您混合和比對不同類型的項目或不同演算法邏輯。<br>如需詳 [細資訊，請參閱](/help/c-recommendations/c-algorithms/create-criteria-sequence.md#sequence) 「建立准則序列」。 |

## Target Standard/Premium 20.8.1 (2020 年 9 月 2 日)

此發行包含下列增強功能、修正和變更：

* 修正在切換組織後載入新的「管理」頁面時， [!UICONTROL 顯示錯誤] 的問題。 (TGT-37730)
* 修正導致「管理>實作」頁面上顯示錯誤用戶端 [!UICONTROL 代碼的顯示問題] 。 (TGT-37849)
* 修正在成功載入VEC後，使用者有時無法在 [!UICONTROL Visual Experience Composer] (VEC)中使用編輯功能的問題。 (TGT-37162)
* 修正即使已安裝VEC Helper擴充功能，仍無法在VEC和Enhanced Experience Composer(EEC)中載入頁面的問題。 這是由於Google Chrome 80+的變更。 下載更 [新的VEC Helper擴充功能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。 (TGT-37893)
* 修正使用者在切換組織後，有時無法從「管理>實作」頁 [!UICONTROL 面下載at.js的問題] 。 (TGT-37668)
* 現在載入時會停用at.js下載按鈕，以防止使用者 [!DNL Target] 多次按一下下載按鈕時傳送多個請求。 (TGT-37633)
* 修正「體驗 [!UICONTROL 定位] (XT)」活動中，導致體驗在較長時間內顯示「擷取結果」的問題。 (TGT-37684)
* 已改善僅限鍵盤使用者的導覽和功能。 (TGT-34479 和 TGT-34473)
* 在UI中新增標籤，以協助使用者使用輔助技術。 (TGT-34480)
* 改進刪除活動中目前使用的行動檢視區時的錯誤訊息。 錯誤訊息現在會顯示：「此視區目前與一或多個活動相關聯。 您必須先從這些活動中移除視區，才能刪除它。」 (TGT-37030)
* 在VEC中新增支援，可允許在符合頁面中多個元素的css選擇器上追蹤點按。 (TGT-37323)
* 修正某些使用者無法顯示「活動」清單 [!UICONTROL 的問] 題。 顯示以下錯誤消息：&quot;無法擷取URL建議。&quot; 在Adobe後端系統中，使用其FirstName(FirstName/r/n)中傳回歸位的使用者發生錯誤。 (TGT-37330)
* 修正當工作區名稱(在適用於企業的 [!UICONTROL Adobe Admin Console中指定])包含縮寫符號時，使用者無法顯示「活動」頁面的問題。 (TGT-37709)
* 修正「自動  分配」活動中，選取最佳化和轉換量度時，即使已指定報表套裝，錯誤訊息仍會錯誤告知使用者選取報表套裝的問題。 (TGT-37689)
* 修正導覽至「定位」頁面後，有時造 [!UICONTROL 成「目標與設定」頁面上的量度空白的] 問題  。 (TGT-37691)
* 修正導致准則上次修改的值不正確的 [!DNL Recommendations] 問題。 (TGT-37666)
* 修正mbox ID顯示在「mbox」下拉式清單中，而非mbox名稱的問題。 (TGT-37739)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
