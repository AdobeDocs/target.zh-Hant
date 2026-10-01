---
keywords: Adobe Target；同事；AI；技能；實驗；建議
title: Adobe Target的同事技能
description: 瞭解Adobe Target可用的同事技能，包括活動探索、測試建立、分析、對象構成和建議疑難排解。
feature: Overview
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: cc4c6b77fa6c600723813b939ba1e5323836ebcc
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%
---

# Adobe Target的同事技能 {#coworker-skills}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;探索Adobe Target可用的同事技能，包括探索活動和對象、建立和設定測試、分析績效、撰寫對象和管理建議的技能。

>[!ENDSHADEBOX]

同事技能可協助Adobe Target從業人員使用自然語言來探索其測試和個人化方案、建立及設定活動、分析結果，以及解決傳遞問題。 說明您想在「同事聊天」中做什麼，然後在採取動作前檢閱傳回的建議、設定或分析。

[!DNL Adobe Target] MCP工具與同事分別記錄，並提供不同的功能：

* [目標MCP](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md)會記錄直接MCP伺服器公開的個別工具，包括其支援的活動型別、引數、許可權以及讀取或寫入範圍。
* [Co-worker](https://experienceleague.adobe.com/zh-hant/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/overview#target-activities-and-audiences)提供獨立的自然語言協調層，可以結合功能並套用其他工作流程。

下表為相關功能的高階比較。

| 功能 | 目標MCP | Coworker |
| --- | --- | --- |
| 列出執行中的實驗、對象、選件或最近變更的專案 | 是 | 是 |
| 建立 Automated Personalization 活動 | 無 | 無 |
| 建立Target對象 | 是 | 是 |
| 建立Target VEC活動、體驗鎖定目標活動或A/B測試 | 是 | 是 |
| 建立Target建議活動 | 是 | 是 |
| 在Target中建立HTML或JSON選件 | 是 | 是 |
| 在Target活動中使用AEM內容片段 | 無 | 是 |
| 建議目前運作和後續測試專案 | 沒有或一般建議 | 是 |


## Target外掛程式

**Target**&#x200B;外掛程式提供下列技能：

* **目標瀏覽**

  提供Target實體（包括活動、對象、選件和相關設定）的唯讀探索、檢查和計數。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「列出我的作用中活動。」
  * 「目前執行中的活動數目？」
  * 「顯示此活動使用的對象和選件。」

  >[!ENDSHADEBOX]

* **目標活動裁決**

  使用顯著性計算和設定檢查來判斷活動是否已準備好出貨、應等待更多資料、應停止或需要修正。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「我是否應該送出這項測試？」
  * 「此活動是否準備好停止？」
  * 「目前的活動設定是否有任何問題？」

  >[!ENDSHADEBOX]

* **目標設計**

  建立及設定活動和選件、產生QA URL，以及作者或最佳化選件內容。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「建立首頁的A/B測試。」
  * 「為回訪訪客體驗建立選件。」
  * 「產生此活動的QA URL。」

  >[!ENDSHADEBOX]

* **目標VEC**

  建立和編輯視覺化體驗撰寫器活動及其頁面傳送對象。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「建立首頁的VEC A/B測試。」
  * 「編輯我的VEC活動中的主圖示題。」
  * 「為此VEC活動建立頁面傳送對象。」

  >[!ENDSHADEBOX]

* **目標設定**

  指南會完成A/B、體驗鎖定目標或視覺化體驗撰寫器活動的建立，包括先決條件、排程、QA和啟動。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「協助我建立第一個測試。」
  * 「建立體驗鎖定目標活動之前需要什麼？」
  * 「逐步說明排程、QA和啟動此活動。」

  >[!ENDSHADEBOX]

* **目標智慧**

  稽核Target程式中的風險、衝突、設定錯誤、衛生問題和快速獲勝。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「稽核我的Target活動。」
  * 「尋找我的活動中的衝突或設定風險。」
  * 「哪些快速入選可以改善我的Target程式的衛生？」

  >[!ENDSHADEBOX]

* **目標策略專家**

  分析過去Target資料中的成功模式，並建議未來的測試。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「接下來應該根據過去的結果進行哪些測試？」
  * 「哪些模式會出現在我表現最好的測試中？」
  * 「建議根據此活動結果進行後續測試。」

  >[!ENDSHADEBOX]

* **目標測試電腦**

  針對轉換和收入量度，計畫A/B/n範例大小、持續時間和可偵測提升度，並針對多項比較採取Bonferroni校正。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「我需要什麼樣本量？」
  * 「此A/B測試應該執行多久才能偵測到5%的提升度？」
  * 「我可以使用這個流量測量哪些可偵測的提升度？」

  >[!ENDSHADEBOX]

* **目標Portfolio報告**

  提供唯讀、整個方案的效能統計，以及活動趨勢和動向分析。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「哪些是我最好和最差的測驗？」
  * 「顯示我的活動的效能趨勢。」
  * 「哪些活動最近獲得或失去動力？」

  >[!ENDSHADEBOX]

* **目標對象撰寫器**

  從自然語言說明或明確規則建立或編輯目標原生對象。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「為回訪行動訪客建立受眾。」
  * 「編輯此對象以包含來自有機搜尋的訪客。」
  * 「為檢視定價頁面的訪客建立Target對象。」

  >[!ENDSHADEBOX]

* **目標建議**

  管理與使用Target Recommendations活動和設定。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「建立Recommendations活動。」
  * &quot;顯示我的Recommendations活動和設定。&quot;
  * 「更新此Recommendations活動的設定。」

  >[!ENDSHADEBOX]

* **目標建議診斷**

  診斷Recommendations傳送、設定、目錄和摘要問題。

  >[!BEGINSHADEBOX]

  *範例提示：*

  * 「為何沒有顯示我的建議？」
  * 「診斷此Recommendations活動的摘要和目錄設定。」
  * 「傳送或設定問題是否會影響我的建議？」

  >[!ENDSHADEBOX]
