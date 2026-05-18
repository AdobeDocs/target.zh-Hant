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
source-git-commit: 53dc7056ca62339a682756fe1b39e6af349f3ae6
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 0%

---

# [!DNL Adobe Target] MCP伺服器 {#target-mcp}

[!DNL Adobe Target] MCP整合可讓您直接從AI助理檢查和分析A/B測試和個人化活動。 將[!DNL Target]的實驗和個人化資料轉換為純語言的工作流程 — 稽核您的實驗組合、檢閱效能報告，以及探索對象和選件，而不需導覽UI或撰寫API呼叫。

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP伺服器可供&#x200B;**公用Beta**&#x200B;中的所有客戶使用。 目前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支援。 未來版本將新增對其他MCP相容應用程式的支援。


## 什麼是模型內容通訊協定？ {#mcp-overview}

行銷和最佳化團隊越來越仰賴聊天式應用程式和開發人員工具（例如Anthropic Claude、OpenAI ChatGPT、Cursor和Microsoft Copilot Studio）來簡化日常工作。 這些應用程式支援&#x200B;**模型內容通訊協定(MCP)**，這是開放標準，可讓應用程式以統一的方式將後端工具公開給大型語言模型(LLM)。

[!DNL Adobe Target]現在提供MCP伺服器，直接在任何MCP相容應用程式中呈現實驗和個人化作業。 [!DNL Adobe Target]作為決策和執行層，而AI助理處理推理和解釋 — 讓團隊更快存取最佳化深入分析，無需導覽多個產品熒幕或針對[!DNL Adobe Target] REST API撰寫查詢。


>[!IMPORTANT]
>
>模型內容通訊協定(MCP)是一種新興的開放原始碼標準，可能會帶來安全性或可靠性風險。 Adobe MCP伺服器整合和相關檔案係依「現況」提供，不提供任何形式的保證。
>
>將MCP使用者端或伺服器連線至Adobe產品是客戶選擇的組態，客戶需負責評估任何MCP整合的安全性和適用性。 Adobe對於因設定錯誤、誤用MCP、協力廠商實作中的漏洞，或透過啟用MCP的工作流程執行的意外動作所引起的問題，概不負責。
>
>為了降低風險，Adobe鼓勵您在有效使用之前在沙箱環境中測試整合，並在確認或依賴之前，仔細檢閱及驗證所有MCP啟動的動作和回應。

## 主要功能 {#mcp-capabilities}

[!DNL Adobe Target] MCP伺服器提供活動、對象、選件及實作組態的讀取存取權。 透過整合，您可以：

* **檢查並稽核實驗** — 取得任何活動的狀態、效能、變更記錄和QA預覽連結，而不需瀏覽UI。
* **分析結果** — 擷取A/B、XT、AP和自動鎖定目標活動的效能、收入和A4T報表。
* **探索活動** — 列出、檢查及分析A/B和XT活動。
* **探索對象和選件** — 列出並檢查對象、HTML選件和JSON選件。
<!-- * **Explore Recommendations criteria** - List and inspect criteria and cart-based algorithms. -->
* **稽核實作** — 檢閱at.js設定、回應Token和每個實體的修訂歷史記錄。

>[!NOTE]
>
>寫入工具（建立、更新、啟用、停用）不會透過&#x200B;**公用Beta**&#x200B;中的公用MCP目錄公開。 所有目前可用的工具都是唯讀的。 未來版本將提供寫入許可權。

[!DNL Adobe Target] MCP伺服器會公開10個類別中的23個唯讀工具 — 從活動檢查和報告，到對象探索和QA預覽。 如需完整的引數參考，請參閱[MCP伺服器工具參考](target-mcp-tools-reference.md)。

若要探索您可以使用[!DNL Adobe Target] MCP伺服器做什麼 — 包括逐步提示逐步說明 — 請參閱[使用案例和逐步說明](target-mcp-use-cases.md)。

若要將[!DNL Adobe Target] MCP伺服器連線到您的AI小幫手（包括先決條件、使用者端特定組態和疑難排解），請參閱[開始使用](target-mcp-get-started.md)。

## 常見問題集 {#mcp-faq}

+++支援哪些MCP使用者端？

[!DNL Adobe Target] MCP伺服器目前可用於&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**。 未來版本可能會新增對其他MCP相容應用程式的支援。
+++

+++我可以透過MCP存取哪些[!DNL Adobe Target]物件？

您可以存取活動(A/B、XT、AP)、對象、選件、屬性、mbox、回應Token、at.js設定、A4T報表和實體修訂歷史記錄。 目前可用的所有23種工具均為唯讀。
+++

+++MCP伺服器可以建立或修改活動嗎？

不在公開Beta中。 公用MCP目錄目前公開23個唯讀工具。 尚未透過公用MCP伺服器提供寫入作業（建立、更新、啟動、停用）。 未來版本將提供寫入許可權。
+++

+++我需要開發人員存取權才能使用MCP伺服器嗎？

無. MCP伺服器是專為行銷和技術人員所設計。 行銷人員可以在任何支援的MCP使用者端中使用自然語言提示與其互動，而開發人員則可以在Claude Code或Cursor等工具中使用它。
+++

+++我的[!DNL Adobe Target]資料是否已傳送給MCP使用者端提供者？

當您提交提示時，MCP使用者端可能會傳送相關內容（包括MCP伺服器傳回的[!DNL Adobe Target]資料）到其模型以進行處理。 在連線到生產資料之前，請檢閱MCP使用者端提供者的隱私權和資料處理原則。 Adobe的資料處理受[Adobe隱私權原則](https://www.adobe.com/privacy.html)和[資料保護條款](https://www.adobe.com/go/dpt-ww)所規範。
+++

+++寫入操作是否會對已上線的活動造成非預期的變更？

無法透過公用Beta中的公用MCP目錄取得寫入工具 — 目前公開的所有23個工具都是唯讀的。 在將來的發行版本中引入寫入工具時，這些工具將包含安全註解和確認閘道，這樣就不會在未明確使用者確認的情況下執行任何狀態變更動作。
+++

+++我在[!DNL Adobe Target]中需要哪些許可權？

**觀察者**&#x200B;角色或更高層級授予對公開Beta中可用的所有23個唯讀工具的存取權。 寫入工具尚未透過公用MCP目錄公開，因此「編輯者」和「核准者」角色許可權目前不會解除鎖定其他MCP工具。 如果您不確定目前的存取層級，請連絡您的[!DNL Adobe Target]系統管理員。
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
