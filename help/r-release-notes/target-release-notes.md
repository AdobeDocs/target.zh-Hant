---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 提供最新或即將發行的DNL Adobe Target版本功能、增強功能和修正資訊的發行說明。
title: Adobe Target搶鮮版注意事項
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 7857b9765a9338405b6705046333f11f8255b365
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 20%

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**最近更新: 2020 年 5 月 27 日**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!NOTE]
>
>* **mbox.js淘汰**: 自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都將失敗，並影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 請參 *閱Adobe Target技能產生器： 開發人員聊天，將Adobe Target的mbox.js移轉至下方的at.js* ，以取得詳細資訊。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。


## Adobe Target Skill Builder: 開發人員聊天，將Adobe Target的mbox.js移轉至at.js {#skill-builder}

隨著mbox.js即將於2020年8月30日淘汰，Adobe Target產品經理David Son最近主持了開發人員聊天，討論將mbox.js移轉至at.js的優點。 在接下來的30天中，您可 [以檢視網路研討會錄制](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。

## Target Standard/Premium 20.6.1 (2020 年 6 月 10 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| 目標分析 (A4T) 支援自動分配活動 | 在6月發行時，「自動配置」測試將支援 [Target的Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md)。 此整合可讓您使用Auto-Allocate的多重授權功能，來推動流量流向成功體驗，同時使用Adobe Analytics目標量度和／或Adobe Analytics報告與分析功能。 如果您已實作 [A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) ，以便與A/B測試和體驗定位活動搭配使用，一切就緒！ |
| 發佈者角色 | 此新角色類似於當前的「觀察者」角色（可以查看活動，但不能建立或編輯活動）。 不過，「發佈者」角色對於作用中的活動具有額外權限。 |
| 管理<br>頁面舊稱「設定」。 | 「設定」頁面已重新命名為「管理」，而且所有功能表項目的UI已更新，以改善工作流程和易用性。<br>可用的功能表項目包括：<ul><li>可視化體驗撰寫器</li><li>報表</li><li>Scene7 設定</li><li>實施</li><li>屬性</li><li>主機</li><li>環境</li><li>回應 Token</li><li>使用者</li></ul> |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
