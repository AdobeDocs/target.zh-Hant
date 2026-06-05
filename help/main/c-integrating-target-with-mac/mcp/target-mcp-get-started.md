---
solution: Target
product: target
title: 開始使用Adobe Target MCP伺服器
description: 瞭解如何將Adobe Target MCP伺服器連線至您的AI助理，包括先決條件、使用者端設定和疑難排解。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta 版" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 40e87a3a70d51ccda99f046609ba9633719ea540
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 0%

---

# 開始使用[!DNL Adobe Target] MCP伺服器 {#target-mcp-get-started}

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP伺服器可供&#x200B;**公用Beta**&#x200B;中的所有客戶使用。 目前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支援。

此頁面會逐步引導您瞭解將[!DNL Adobe Target] MCP伺服器連線至您的AI助理並驗證設定所需的一切。

>[!IMPORTANT]
>
>模型內容通訊協定(MCP)是一種新興的開放原始碼標準，可能會帶來安全性或可靠性風險。 Adobe MCP伺服器整合和相關檔案係依「現況」提供，不提供任何形式的保證。
>
>將MCP使用者端或伺服器連線至Adobe產品是客戶選擇的組態，客戶需負責評估任何MCP整合的安全性和適用性。 Adobe對於因設定錯誤、誤用MCP、協力廠商實作中的漏洞，或透過啟用MCP的工作流程執行的意外動作所引起的問題，概不負責。
>
>為了降低風險，Adobe鼓勵您在有效使用之前在沙箱環境中測試整合，並在確認或依賴之前，仔細檢閱及驗證所有MCP啟動的動作和回應。

## 先決條件 {#mcp-prerequisites}

在將[!DNL Adobe Target] MCP伺服器連線到您的MCP使用者端之前，請確定下列事項：

* 您與Adobe Experience Platform組織有作用中的[!DNL Adobe Target]授權（Adobe Experience Cloud訂閱）。
* 您有一個支援的MCP相容應用程式（目前為Claude Web、Claude Desktop、Claude Code、Cursor或ChatGPT）。
* 您已在Adobe Admin Console中設定[!DNL Adobe Target]許可權。 所需的角色取決於您要執行的作業：
   * **觀察者**&#x200B;角色或更新版本：存取所有唯讀工具（檢查、報告、稽核）
   * **編輯者**&#x200B;角色或更新版本：存取讀取工具與寫入工具（建立、更新）
   * **核准者**&#x200B;角色：存取所有工具，包括啟用和停用

## 連線[!DNL Adobe Target] MCP伺服器 {#mcp-connect}

>[!NOTE]
>
>[!DNL Adobe Target] MCP伺服器使用OAuth 2.0進行驗證。 第一次使用Target MCP工具時，系統會將您重新導向至Adobe Experience Cloud以登入、選取您的組織並授與要求的許可權。 不需要靜態認證。

**從Claude Desktop或Claude Web連線：**

1. 開啟您的MCP使用者端設定並新增新的MCP伺服器。
1. 輸入伺服器URL： `https://targetmcp.adobe.io/mcp`
1. 出現提示時，請使用您的Adobe Experience Cloud憑證完成Adobe IMS OAuth登入。
1. 一旦通過驗證，所有工具即可立即使用。 請嘗試「列出所有作用中的Target活動」以驗證連線。

**從Claude程式碼連線：**

將下列專案新增至您的Claude程式碼MCP設定：

```json
{
  "mcpServers": {
    "adobe-target": {
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

在第一次使用出現提示時，完成OAuth瀏覽器流程。

**從游標連線：**

1. 開啟&#x200B;**Cursor**&#x200B;並瀏覽至&#x200B;**設定** → **MCP** → **新增全域MCP伺服器**。
1. 新增下列設定：

```json
{
  "mcpServers": {
    "target": {
      "type": "streamable-http",
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

1. 儲存設定。 [!DNL Target] MCP伺服器會出現在您可用的MCP伺服器中。

>[!TIP]
>
>如果出現來自錯誤組織的活動或資料，請完全登出Adobe Experience Cloud，重新連線MCP伺服器，並在重新驗證期間仔細選取正確的組織。

## 疑難排解 {#mcp-troubleshooting}

+++OAuth流程失敗或重新導向不正確

1. 完全登出Adobe Experience Cloud。
1. 清除adobe.com網域的瀏覽器Cookie。
1. 重試驗證流程。
1. 請確保在出現提示時選取正確的組織。
+++

+++出現來自錯誤組織的活動或資料

1. 完全登出Adobe Experience Cloud。
1. 在您的使用者端設定中，中斷連線並重新連線MCP伺服器。
1. 在重新驗證期間，請仔細選取正確的組織。
+++

+++工具傳回錯誤訊息

1. 確認您在[!DNL Adobe Target]中擁有您嘗試之作業的必要角色（請參閱[必要條件](#mcp-prerequisites)）。 唯讀工具需要觀察者或更新的版本；寫入工具需要編輯器或更新的版本；啟動和停用需要核准者。
1. 檢查您的組織中是否存在參考的資源（活動、選件、對象）。
1. 確認活動ID和其他識別碼正確。
+++

+++無法連線到MCP伺服器

1. 驗證您的網際網路連線。
1. 請檢查在使用者端設定中是否正確輸入MCP伺服器URL。
1. 請嘗試在MCP使用者端設定中移除並重新新增伺服器。
+++

## 安全性與許可權 {#mcp-security}

[!DNL Adobe Target] MCP伺服器只能存取您的Adobe使用者帳戶有權檢視或修改的資料。 所有作業都會遵守您的[!DNL Target]角色指派和工作區許可權。

伺服器要求下列OAuth範圍：

* `AdobeID` — 基本Adobe身分
* `openid` — OpenID Connect驗證
* `additional_info.projectedProductContext` — 租使用者探索
* `read_organizations` — 組織層級作業
* `additional_info.roles` — 角色型存取控制

OAuth權杖會在每個請求上根據Adobe IMS進行驗證，不會由MCP伺服器持續儲存，而且所有通訊都會使用HTTPS。

## 相關資源 {#mcp-get-started-related}

* [概觀](target-mcp.md)
* [使用案例和逐步說明](target-mcp-use-cases.md)
* [MCP伺服器工具參考](target-mcp-tools-reference.md)
* [模型內容通訊協定檔案](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理員API參考](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
