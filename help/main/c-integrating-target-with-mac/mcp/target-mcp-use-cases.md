---
solution: Target
product: target
title: Adobe Target MCP伺服器 — 使用案例和逐步說明
description: 探索Adobe Target MCP伺服器的常見使用案例和逐步提示逐步解說。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta 版" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: d5d7a57ce6a3188f02e680c24849d773cb53457a
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 1%

---

# [!DNL Adobe Target] MCP伺服器 — 使用案例和逐步說明 {#target-mcp-use-cases}

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP伺服器可供&#x200B;**公用Beta**&#x200B;中的所有客戶使用。 目前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支援。

此頁面顯示您可以使用自然語言提示來完成[!DNL Adobe Target] MCP伺服器的工作，從快速查詢到多步驟分析和報告工作。

>[!IMPORTANT]
>
>模型內容通訊協定(MCP)是一種新興的開放原始碼標準，可能會帶來安全性或可靠性風險。 Adobe MCP伺服器整合和相關檔案係依「現況」提供，不提供任何形式的保證。
>
>將MCP使用者端或伺服器連線至Adobe產品是客戶選擇的組態，客戶需負責評估任何MCP整合的安全性和適用性。 Adobe對於因設定錯誤、誤用MCP、協力廠商實作中的漏洞，或透過啟用MCP的工作流程執行的意外動作所引起的問題，概不負責。
>
>為了降低風險，Adobe鼓勵您在有效使用之前在沙箱環境中測試整合，並在確認或依賴之前，仔細檢閱及驗證所有MCP啟動的動作和回應。

## 使用案例 {#mcp-use-cases}

下列範例顯示如何使用自然語言與[!DNL Adobe Target] MCP伺服器互動：

| 目標 | 範例提示 |
|---|---|
| **實驗狀態稽核** | 「哪些A/B測試目前在首頁上有效？ 顯示狀態、流量分配，以及每個專案的執行時間。」 |
| **效能檢閱** | 「顯示已達到統計顯著性的所有作用中測試 — 哪些體驗會獲勝？」 |
| **收入分析** | 「取得活動AT4821的訂單和收入報表，並總結哪些體驗是造成每位訪客收入最高的因素。」 |
| **A4T報告** | 「提取A4T報表以用於我的簽出最佳化測試，並彙總Analytics端的轉換資料。」 |
| **活動深入分析** | 「深入瞭解我的『夏季銷售橫幅』測試 — 效能是什麼樣子，是否有任何異常？」 |
| **對象管理** | 「列出所有以行動使用者為目標的對象，並向我顯示他們相關聯的活動。」 |
| **QA和預覽** | 「產生活動12345動的QA預覽URL，這樣我就能在啟用之前檢閱所有變體。」 |
| **建議評論** | 「列出此帳戶中設定的所有Recommendations條件，並摘要使用中的演演算法型別。」 |
| **實作稽核** | 「已設定哪個at.js版本，以及目前作用中的回應Token為何？」 |
| **變更稽核** | 「顯示過去30天內對活動98765數所做的所有變更，以及變更對象。」 |

## 使用案例逐步解說 {#mcp-use-case-walkthroughs}

下列逐步說明如何在[!DNL Adobe Target] MCP伺服器上使用自然語言提示來完成一般工作。

<!--
+++Creating an A/B test

**Prompt:**
"Create an A/B test called 'Homepage Hero Image Test' with two experiences: 'Control' showing the current hero and 'Variant' showing a new summer-themed hero image. Target the homepage mbox."

The AI assistant uses the `create_ab_activity` tool to create the activity with the configuration you described. The tool returns the new activity ID and a confirmation of the created experiences.

+++
-->

+++檢查活動績效

**提示：**
「顯示過去30天我的『結帳流程最佳化』活動的效能量度。」

AI助理使用`get_ab_performance_report`或`get_xt_performance_report` （視活動型別而定）來擷取指定時間範圍的轉換率、訪客計數和其他量度。

+++

<!--
+++Managing offers

**Prompt:**
"Create an HTML offer called 'Summer Sale Banner' with a promotional banner that says '20% off all summer items'."

The AI assistant uses the `create_target_offer` tool to create the offer with your specified HTML content and returns a confirmation with the new offer ID.

+++

+++Building an audience

**Prompt:**
"Create an audience called 'Mobile Visitors from California' that targets users on mobile devices located in California."

The AI assistant uses the `create_target_audience` tool with the appropriate targeting rules derived from your description.

+++
-->

+++產生QA預覽連結

**提示：**
「產生活動12345動的預覽URL，以便測試每個體驗。」

AI助理會使用`preview_activity`工具產生可點選的URL，略過對象鎖定目標，讓您直接在瀏覽器中檢視每個體驗。

+++

<!--
+++Creating an Experience Targeting activity

**Prompt:**
"Create an Experience Targeting activity called 'Geo Personalization' that shows different hero banners to visitors from different regions."

The AI assistant uses `create_xt_activity` to build the activity with audience-based experience mapping according to the regions you describe.

+++

+++Scheduling an activity

**Prompt:**
"Update the schedule for activity 12345 to start on May 1st and end on May 31st."

The AI assistant uses the `update_activity_schedule` tool to apply the new start and end dates to the activity.

+++
-->

## 相關資源 {#mcp-use-cases-related}

* [概觀](target-mcp.md)
* [開始使用](target-mcp-get-started.md)
* [MCP伺服器工具參考](target-mcp-tools-reference.md)
* [模型內容通訊協定檔案](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理員API參考](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
