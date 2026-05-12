---
solution: Target
product: target
title: Adobe Target MCP伺服器概述
description: 瞭解Adobe Target MCP伺服器是什麼、其主要功能，以及它如何連線至您的AI助理。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta 版" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 0%

---

# [!DNL Adobe Target] MCP伺服器 {#target-mcp}


[!DNL Adobe Target] MCP整合可讓您直接從AI助理檢查、分析和管理A/B測試、個人化活動和Recommendations條件。 將[!DNL Target]的讀取和寫入API轉換為純語言的工作流程 — 稽核您的實驗組合、檢閱效能報告、管理對象和選件，以及執行控管動作，而不需導覽UI或寫入API呼叫。

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP伺服器可供&#x200B;**公用Beta**&#x200B;中的所有客戶使用。 目前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支援。 未來版本將新增對其他MCP相容應用程式的支援。


## 什麼是模型內容通訊協定？ {#mcp-overview}

行銷和最佳化團隊越來越仰賴聊天式應用程式和開發人員工具（例如Anthropic Claude、OpenAI ChatGPT、Cursor和Microsoft Copilot Studio）來簡化日常工作。 這些應用程式支援&#x200B;**模型內容通訊協定(MCP)**，這是開放標準，可讓應用程式以統一的方式將後端工具公開給大型語言模型(LLM)。

[!DNL Adobe Target]現在提供MCP伺服器，直接在任何MCP相容應用程式中呈現實驗、個人化和建議作業。 [!DNL Adobe Target]作為決策和執行層，而AI助理處理推理和解釋 — 讓團隊更快存取最佳化深入分析，無需導覽多個產品熒幕或針對[!DNL Adobe Target] REST API撰寫查詢。


>[!IMPORTANT]
>
>模型內容通訊協定(MCP)是一種新興的開放原始碼標準，可能會帶來安全性或可靠性風險。 Adobe MCP伺服器整合和相關檔案係依「現況」提供，不提供任何形式的保證。
>
>將MCP使用者端或伺服器連線至Adobe產品是客戶選擇的組態，客戶需負責評估任何MCP整合的安全性和適用性。 Adobe對於因設定錯誤、誤用MCP、協力廠商實作中的漏洞，或透過啟用MCP的工作流程執行的意外動作所引起的問題，概不負責。
>
>為了降低風險，Adobe鼓勵您在有效使用之前在沙箱環境中測試整合，並在確認或依賴之前，仔細檢閱及驗證所有MCP啟動的動作和回應。

## 主要功能 {#mcp-capabilities}

[!DNL Adobe Target] MCP伺服器提供活動、對象、選件、建議和實作設定的讀寫存取權。 透過整合，您可以：

* **檢查並稽核實驗** — 取得任何活動的狀態、效能、變更記錄和QA預覽連結，而不需瀏覽UI。
* **分析結果** — 擷取A/B、XT、AP和自動鎖定目標活動的效能、收入和A4T報表。
* **管理活動** — 建立、更新及啟用A/B和XT活動；調整流量分割、變體、排程和優先順序。
* **管理對象和選件** — 列出、檢查及建立對象、HTML選件和JSON選件。
* **探索Recommendations條件** — 列出並檢查條件和購物車型演演算法。
* **稽核實作** — 檢閱at.js設定、回應Token和每個實體的修訂歷史記錄。

>[!NOTE]
>
>寫入操作（建立、更新、啟動、停用）包括安全註解。 未經明確的使用者確認，不會執行任何變更。

[!DNL Adobe Target] MCP伺服器會公開10個類別中的52種工具 — 從活動管理和報告，到對象建立和QA預覽。 如需完整的引數參考，請參閱[MCP伺服器工具參考](target-mcp-tools-reference.md)。

若要探索您可以使用[!DNL Adobe Target] MCP伺服器做什麼 — 包括逐步提示逐步說明 — 請參閱[使用案例和逐步說明](target-mcp-use-cases.md)。

若要將[!DNL Adobe Target] MCP伺服器連線到您的AI小幫手（包括先決條件、使用者端特定組態和疑難排解），請參閱[開始使用](target-mcp-get-started.md)。

## 常見問題集 {#mcp-faq}

+++支援哪些MCP使用者端？

[!DNL Adobe Target] MCP伺服器目前可用於&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**。 未來版本可能會新增對其他MCP相容應用程式的支援。
+++

+++我可以透過MCP存取哪些[!DNL Adobe Target]物件？

您可以存取活動(A/B、XT、AP)、對象、選件、屬性、mbox、Recommendations條件、回應Token、at.js設定、A4T報表和實體修訂歷史記錄。 52種工具同時支援讀取和寫入作業 — 寫入作業需要適當的角色和明確的確認。
+++

+++MCP伺服器可以建立或修改活動嗎？

是. 除了讀取作業之外，伺服器也會公開可讓您建立活動、暫停活動、更新優先順序、調整流量分割等的寫入作業。 寫入作業會遵循與[!DNL Adobe Target] UI相同的許可權模式 — 您需要適當的角色才能進行變更，而且不會執行任何動作而不需要明確的使用者確認。
+++

+++我需要開發人員存取權才能使用MCP伺服器嗎？

無. MCP伺服器是專為行銷和技術人員所設計。 行銷人員可以在任何支援的MCP使用者端中使用自然語言提示與其互動，而開發人員則可以在Claude Code或Cursor等工具中使用它。
+++

+++我的[!DNL Adobe Target]資料是否已傳送給MCP使用者端提供者？

當您提交提示時，MCP使用者端可能會傳送相關內容（包括MCP伺服器傳回的[!DNL Adobe Target]資料）到其模型以進行處理。 在連線到生產資料之前，請檢閱MCP使用者端提供者的隱私權和資料處理原則。 Adobe的資料處理受[Adobe隱私權原則](https://www.adobe.com/privacy.html)和[資料保護條款](https://www.adobe.com/go/dpt-ww)所規範。
+++

+++寫入操作是否會對已上線的活動造成非預期的變更？

撰寫工具包括安全註解和確認閘道。 在任何狀態變更動作（例如啟動活動、變更優先順序或更新流量分配）之前，伺服器會顯示結構化的確認，顯示受影響的物件、預估的流量影響和所需的明確核准步驟。 確認前不會進行任何變更。
+++

+++我在[!DNL Adobe Target]中需要哪些許可權？

至少&#x200B;**觀察者**&#x200B;角色會授予所有讀取工具的存取權。 **編輯者**&#x200B;角色可讓您建立活動、對象和選件。 必須有&#x200B;**核准者**&#x200B;角色才能啟用、停用或封存活動。 如果您不確定目前的存取層級，請連絡您的[!DNL Adobe Target]系統管理員。
+++

+++我可以跨多個Target組織或屬性使用MCP伺服器嗎？

MCP伺服器會將作業範圍限定在與您驗證的Adobe IMS憑證關聯的組織。 如果您有權存取該組織內的多個屬性，您可以使用`list_target_properties`工具依屬性查詢，並相應地篩選後續請求。
+++

## 相關資源 {#mcp-related}

* [開始使用](target-mcp-get-started.md)
* [使用案例和逐步說明](target-mcp-use-cases.md)
* [MCP伺服器工具參考](target-mcp-tools-reference.md)
* [模型內容通訊協定檔案](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理員API參考](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [游標檔案](https://docs.cursor.com/){target="_blank"}
