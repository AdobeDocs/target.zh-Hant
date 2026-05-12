---
solution: Target
product: target
title: 自行託管Adobe Target MCP伺服器
description: 瞭解如何使用Python、Docker或本機開發環境執行您自己的Adobe Target MCP伺服器執行個體。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta 版" type="Informative"
role: Developer
level: Experienced
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 2%

---

# 自行託管[!DNL Adobe Target] MCP伺服器 {#target-mcp-self-hosted}


>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP伺服器可供&#x200B;**公用Beta**&#x200B;中的所有客戶使用。 目前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支援。

此頁面說明如何複製、設定及執行您自己的[!DNL Adobe Target] MCP伺服器執行個體。 當您需要本機開發環境、自訂網路設定，或想要貢獻伺服器程式碼基底時，自行託管會很有用。

>[!AVAILABILITY]
>
>自行裝載部署適用於需要完整控制[!DNL Adobe Target] MCP伺服器執行階段的開發人員和進階使用者。 對於大多數使用者，建議使用裝載端點(`https://targetmcp.adobe.io/mcp`)。 請參閱[使用MCP使用者端](target-mcp.md)。



## 先決條件 {#self-hosted-prereqs}

開始之前，請確定您具備下列條件：

* **Python 3.13或更新版本**
* **[uv](https://github.com/astral-sh/uv){target="_blank"}** — 快速Python套件和專案管理員

  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

* 具有Adobe Experience Cloud存取權的有效[!DNL Adobe Target]授權
* **Artifactory認證** （僅限Adobe內部使用者） — 安裝內部相依性所需

## 安裝 {#self-hosted-install}

**1. 複製存放庫：**

```bash
git clone https://github.com/Adobe-TnT/target-mcp.git
cd target-mcp
```

**2. 建立及啟用虛擬環境：**

```bash
uv venv --python 3.13
source .venv/bin/activate
```

**3. 設定環境變數：**

```bash
cp env.example .env
```

開啟`.env`並以您的認證和組織設定取代預留位置值。

**4. 安裝相依性：**

```bash
make uv-install
```

**5. 啟動伺服器：**

選擇符合您使用案例的模式：

| 模式 | 命令 | 使用時機 |
|---|---|---|
| StreamableHTTP （API伺服器） | `make run-api-server` | 透過HTTP連線MCP使用者端 |
| STDIO （本機MCP使用者端） | `make run-mcp-stdio` | 使用直接程式通訊 |

## 將MCP使用者端連線到本機伺服器 {#self-hosted-connect}

### 游標

將下列專案新增至您的Cursor MCP設定。 以您的實際IMS代號和組織ID取代預留位置值：

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp",
      "headers": {
        "Authorization": "Bearer {IMS_USER_TOKEN}",
        "x-gw-ims-org-id": "{IMS_ORGANIZATION_ID}"
      }
    }
  }
}
```

### 克勞德程式碼

在指向本機伺服器的Claude程式碼MCP組態檔中新增專案：

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp"
    }
  }
}
```

>[!NOTE]
>
>連線到本機伺服器時，必須手動傳遞驗證標題（如上面的游標範例所示）。 OAuth瀏覽器流程僅適用於裝載的`https://targetmcp.adobe.io/mcp`端點。

## Docker部署 {#self-hosted-docker}

存放庫包括用於容器化部署的Docker撰寫配置。

**使用Docker撰寫執行：**

```bash
make run-dc
```

**直接建置並執行Docker映像：**

```bash
make build
make run-docker
```

## api端點 {#self-hosted-endpoints}

自行託管的伺服器會公開下列HTTP端點：

| 端點 | 說明 |
|---|---|
| `/mcp` | AI使用者端的MCP通訊協定端點 |
| `/ping` | 活動檢查 — 傳回`"Pong"` |
| `/health` | 健康情況檢查 — 傳回`{"status": "healthy"}` |
| `/validate` | 輸入驗證端點 |
| `/authorize` | OAuth授權端點 |
| `/token` | OAuth權杖端點 |

**健康情況檢查範例：**

```bash
curl http://localhost:8080/health
# Response: {"status": "healthy"}
```

## 疑難排解 {#self-hosted-troubleshoot}

+++伺服器無法啟動

1. 驗證是否已安裝Python 3.13+： `python --version`
1. 確認虛擬環境已啟動： `source .venv/bin/activate`
1. 檢查`.env`中的所有環境變數是否已正確設定。
1. 再次執行`make uv-install`以確保所有相依性都存在。

+++

+++無法從MCP使用者端連線

1. 確認伺服器正在執行中，而且連線埠可以存取： `curl http://localhost:8080/ping`
1. 確認MCP使用者端設定中的伺服器URL符合執行中的伺服器位址。
1. 對於Cursor，請確定`Authorization`標頭包含有效的、未過期的IMS權杖。

+++

+++相依性安裝失敗（Adobe內部使用者）

1. 確認您的Artifactory認證已正確設定。
1. 檢查您與內部Artifactory執行個體的網路連線。
1. 請聯絡您團隊的DevOps或平台工程連絡人，以取得Artifactory存取權。

+++

## 相關資源 {#self-hosted-related}

* [使用MCP使用者端](target-mcp.md) — 裝載端點設定和工具參考
* [模型內容通訊協定檔案](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理員API參考](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
