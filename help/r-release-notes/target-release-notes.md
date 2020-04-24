---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 提供最新或即將發行的DNL Adobe Target版本功能、增強功能和修正資訊的發行說明。
title: Adobe Target搶鮮版注意事項
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e9a6545ab65cf1214977f8fa472904527c18a04d

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新時間: 2020 年 4 月 24 月**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!NOTE]
>
>* **mbox.js淘汰**:自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都將失敗，並影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 請參 *閱Adobe Target技能產生器：開發人員聊天、將Adobe Target的mbox.js移轉至下方的at.js* ，以取得註冊即將進行的開發人員聊天的相關資訊。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。


## Adobe Target Skill Builder:開發人員聊天，將Adobe Target的mbox.js移轉至at.js {#skill-builder}

與Adobe Target產品經理David Son一起，說明將mbox.js移轉至at.js的優點。 聽聽最新的at.js更新，瞭解其增強功能以及這些功能如何與技術領域的大趨勢一致，以及一些實用秘訣，以確保您在從mbox.js移轉至at.js時，能夠從Target中獲取同樣多的價值。 Adobe Target開發人員不會想錯過這個！

5月5日，星期二，上午8:00 - 9:00(PDT)

[立即註冊！](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target Standard/Premium 20.4.1 (2020 年 4 月 27 日)

此發行包含下列增強功能、修正和變更：

* 已修正對對象不正確限定裝置和瀏覽器類型的問題。 (TGT-36266)
* 修正在寬度小於963像素的螢幕上檢視報表資料時無法顯示的問題。 (TGT-36549)
* 修正「自動個人化」報表無法正確呈現的問題。 (TGT-36619)
* 修正在使用Analytics for Target(A4t)的「自動分配」和「自動目標」活動中，允許選取不相容量度的問題。 (TGT-36646)
* 修正「視覺體驗撰寫器」(VEC)中某些選項無法正確顯示的問題。 (TGT-36571)
* 修正Target UI中，當使用者在單一體驗中取代內容後，導致其他Recommendations選件預覽顯示已編輯內容的問題。 (TGT-36053 和 TGT-36894)
* 修正部分使用者無法從Recommendations目錄刪除項目的問題。 (TGT-36455)
* 修正使用者無法將Recommendations標準儲存在多頁活動上的問題。 (TGT-36249)
* 修正行為資料來源選項按鈕在連續編輯准則第二次時消失的問題。 (TGT-36796)
* 修正Recommendations演算法在延長期間顯示「擷取結果」的顯示問題。 (TGT-36550 和 TGT-36551)
* 已更新多種語言本地化的UI字串。

## 描述檔批次狀態API v2變更（2020年5月4日）

在5月4日發行中，描述檔批次狀態將只會傳回行層級的失敗資料（不會傳回成功資料）。 API將會傳回失敗的描述檔ID。

舊版和新版API回應如下：

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**我們目前將回應視為：**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>1514187733806-729395</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>1573612762055-214017</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

**在5月4日之後，我們將做出回應：**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
