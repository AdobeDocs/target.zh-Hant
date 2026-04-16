---
solution: Target
product: target
title: 使用MCP使用者端
description: 瞭解如何使用MCP伺服器將Adobe Target連線至MCP使用者端
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta 版" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
source-git-commit: 17804b5f8cfce7033bffcad826e5510bfc42a832
workflow-type: tm+mt
source-wordcount: '2267'
ht-degree: 1%

---

# 使用MCP使用者端 {#target-mcp}

>[!BEGINSHADEBOX]

目錄：

* **[使用MCP使用者端](target-mcp.md)**
* [MCP伺服器工具參考](target-mcp-tools-reference.md)
* [自行託管MCP伺服器](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP伺服器目前可在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**&#x200B;和&#x200B;**Cursor**&#x200B;中使用。 未來版本將新增對其他MCP相容應用程式的支援。

[!DNL Adobe Target] MCP整合可讓您直接從AI助理檢查、分析和管理A/B測試、個人化活動和Recommendations條件。 將[!DNL Target]的讀取和寫入API轉換為純語言的工作流程 — 稽核您的實驗組合、檢閱效能報告、管理對象和選件，以及執行控管動作，而不需導覽UI或寫入API呼叫。 此頁面說明整合的運作方式、您可以執行哪些操作，以及如何開始使用。

## 什麼是模型內容通訊協定？ {#mcp-overview}

行銷和最佳化團隊越來越仰賴聊天式應用程式和開發人員工具（例如Anthropic Claude、OpenAI ChatGPT、Cursor和Microsoft Copilot Studio）來簡化日常工作。 這些應用程式支援&#x200B;**模型內容通訊協定(MCP)**，這是開放標準，可讓應用程式以統一的方式將後端工具公開給大型語言模型(LLM)。

[!DNL Adobe Target]現在提供MCP伺服器，直接在任何MCP相容應用程式中呈現實驗、個人化和建議作業。 [!DNL Adobe Target]作為決策和執行層，而AI助理處理推理和解釋 — 讓團隊更快存取最佳化深入分析，無需導覽多個產品熒幕或針對[!DNL Adobe Target] REST API撰寫查詢。

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

## 可用的工具 {#mcp-tools}

[!DNL Adobe Target] MCP伺服器公開52個工具。 所有具有檢視許可權的連線使用者都可使用讀取工具；寫入工具需要編輯者或核准者角色。

### 活動工具 — 讀取

| 工具 | 說明 |
|---|---|
| `list_target_activities` | 依狀態、型別、名稱、日期、優先順序、mbox和工作區列出具有伺服器端篩選的活動 |
| `list_all_target_activities` | 擷取和篩選器相符的所有活動，自動對結果進行分頁 |
| `get_ab_activity` | 取得特定A/B活動的完整詳細資料 |
| `get_xt_activity` | 取得特定體驗鎖定目標(XT)活動的完整詳細資料 |
| `get_abt_activity` | 取得特定Automated Personalization (AP)活動的完整詳細資料 |

### 活動工具 — 寫入

| 工具 | 說明 |
|---|---|
| `create_ab_activity` | 建立新的A/B測試活動 |
| `create_xt_activity` | 建立新的體驗鎖定目標(XT)活動 |
| `create_activity_from_modifications` | 根據JavaScript修改建立XT活動 |
| `update_ab_activity` | 更新現有的A/B活動 |
| `update_xt_activity` | 更新現有的XT活動 |
| `update_abt_activity` | 更新現有的Automated Personalization活動 |
| `update_activity_state` | 啟動、停用、暫停或封存活動 |
| `update_activity_schedule` | 更新活動的開始和結束日期 |
| `update_activity_priority` | 更新活動的優先順序 |
| `update_activity_name` | 重新命名活動 |
| `add_activity_variant` | 將新變體（體驗）新增至活動 |
| `update_traffic_split` | 更新變體間的流量分配 |
| `update_variant_offer` | 變更變體的選件或VEC修改 |
| `remove_activity_variant` | 從活動中移除變體 |

### 優惠工具

| 工具 | 說明 |
|---|---|
| `list_target_offers` | 列出具有伺服器端篩選和排序的優惠方案 |
| `list_all_target_offers` | 擷取所有符合篩選器的選件，自動分頁 |
| `get_target_offer` | 取得特定優惠方案的詳細資料 |
| `create_target_offer` | 建立新的HTML選件 |
| `create_target_json_offer` | 建立新的JSON選件 |
| `update_target_offer` | 更新現有的HTML選件 |

### 對象工具

| 工具 | 說明 |
|---|---|
| `list_target_audiences` | 透過伺服器端篩選和排序來列出對象 |
| `create_target_audience` | 使用選用的鎖定目標規則建立對象 |

### Mbox和定位工具

| 工具 | 說明 |
|---|---|
| `list_target_mboxes` | 具有篩選和排序功能的清單mbox |
| `list_all_target_mboxes` | 擷取和篩選器相符的所有mbox，自動分頁 |
| `get_target_mbox` | 依名稱取得特定mbox的詳細資料 |
| `list_target_mbox_profile_attributes` | 列出與mbox相關聯的所有設定檔屬性 |

### 屬性

| 工具 | 說明 |
|---|---|
| `list_target_properties` | 列出所有Target屬性 |

### 報告和見解工具

| 工具 | 說明 |
|---|---|
| `get_ab_performance_report` | 取得A/B、自動分配或自動鎖定目標活動的效能報表 |
| `get_ab_orders_report` | 取得A/B或自動鎖定目標活動的訂單與收入報表 |
| `get_xt_performance_report` | 取得XT活動的效能報表 |
| `get_xt_orders_report` | 取得XT活動的訂單和收入報表 |
| `get_apt_performance_report` | 取得AP或自動鎖定目標活動的效能報表 |
| `get_activity_insights` | 依名稱搜尋活動並取得詳細的效能深入分析 |
| `get_a4t_report` | 取得活動的Analytics for Target (A4T)報表 |

### Recommendations工具

| 工具 | 說明 |
|---|---|
| `list_target_criteria` | 列出所有Recommendations條件 |
| `get_target_criteria` | 取得特定建議條件的詳細資料 |
| `update_target_criteria_cart` | 更新Recommendations購物車型條件 |

### 實作與設定工具

| 工具 | 說明 |
|---|---|
| `get_atjs_settings` | 取得AT.js設定和組態 |
| `get_atjs_versions` | 取得可用的AT.js版本 |
| `list_target_response_tokens` | 列出您Target租使用者中的所有回應Token |
| `create_target_response_token` | 建立新的自訂回應Token |

### 稽核和修訂工具

| 工具 | 說明 |
|---|---|
| `get_target_revisions` | 取得資源型別的稽核記錄，依作者篩選 |
| `get_target_entity_revisions` | 依ID取得特定實體的所有修訂 |

### 公用程式

| 工具 | 說明 |
|---|---|
| `preview_activity` | 產生Target活動的QA預覽URL |
| `create_page_delivery_segment` | 建立VEC活動定位的頁面傳送區段 |
| `list_target_templates` | 列出可用的MCP資源和範本 |
| `debug_token_info` | 檢查目前的OAuth權杖範圍和宣告 |

## 使用案例 {#mcp-use-cases}

下列範例顯示如何使用自然語言與[!DNL Adobe Target] MCP伺服器互動：

| 目標 | 範例提示 |
|---|---|
| **實驗狀態稽核** | 「哪些A/B測試目前在首頁上有效？ 顯示狀態、流量分配，以及每個專案的執行時間。」 |
| **效能檢閱** | 「顯示已達到統計顯著性的所有作用中測試 — 哪些體驗會獲勝？」 |
| **收入分析** | 「取得活動AT4821的訂單和收入報表，並總結哪些體驗是造成每位訪客收入最高的因素。」 |
| **A4T 報告** | 「提取A4T報表以用於我的簽出最佳化測試，並彙總Analytics端的轉換資料。」 |
| **活動管理** | 「暫停活動98765並將活動11111的優先順序更新為200。」 |
| **活動深入分析** | 「深入瞭解我的『夏季銷售橫幅』測試 — 效能是什麼樣子，是否有任何異常？」 |
| **對象管理** | 「列出所有以行動使用者為目標的對象，並向我顯示他們相關聯的活動。」 |
| **QA和預覽** | 「產生活動12345動的QA預覽URL，這樣我就能在啟用之前檢閱所有變體。」 |
| **建議評論** | 「列出此帳戶中設定的所有Recommendations條件，並摘要使用中的演演算法型別。」 |
| **實作稽核** | 「已設定哪個at.js版本，以及目前作用中的回應Token為何？」 |
| **變更稽核** | 「顯示過去30天內對活動98765數所做的所有變更，以及變更對象。」 |

## 使用案例逐步解說 {#mcp-use-case-walkthroughs}

下列逐步說明如何在[!DNL Adobe Target] MCP伺服器上使用自然語言提示來完成一般工作。

+++建立A/B測試

**提示：**
> 「使用兩個體驗建立名為『首頁主圖影像測試』的A/B測試：『Control』顯示目前的主圖，而『Variant』顯示全新夏季主題的主圖影像。 定位首頁mbox。」

AI助理使用`create_ab_activity`工具，以您描述的組態建立活動。 此工具會傳回新活動ID，並對建立的體驗進行確認。

+++

+++檢查活動績效

**提示：**
> 「顯示過去30天我的『結帳流程最佳化』活動的效能量度。」

AI助理使用`get_ab_performance_report`或`get_xt_performance_report` （視活動型別而定）來擷取指定時間範圍的轉換率、訪客計數和其他量度。

+++

+++管理優惠方案

**提示：**
> 「使用『所有夏季專案20%折扣』的促銷橫幅，建立名為『夏季促銷橫幅』的HTML優惠。」

AI助理使用`create_target_offer`工具建立具有您指定HTML內容的選件，並傳回具有新選件ID的確認。

+++

+++建立對象

**提示：**
> 「建立名為『來自加州的行動訪客』的受眾，鎖定位於加州的行動裝置上的使用者。」

AI助理會使用`create_target_audience`工具，搭配從您的說明衍生的適當目標規則。

+++

+++產生QA預覽連結

**提示：**
> 「產生活動12345動的預覽URL，以便測試每個體驗。」

AI助理會使用`preview_activity`工具產生可點選的URL，略過對象鎖定目標，讓您直接在瀏覽器中檢視每個體驗。

+++

+++建立體驗鎖定目標活動

**提示：**
> 「建立稱為『地理Personalization』的體驗鎖定目標活動，對來自不同地區的訪客顯示不同的主圖橫幅。」

AI助理使用`create_xt_activity`，根據您描述的地區，以對象體驗對應來建置活動。

+++

+++排程活動

**提示：**
> 「更新活動12345程表，使其從5月1日開始，到5月31日結束。」

AI助理使用`update_activity_schedule`工具將新的開始和結束日期套用至活動。

+++

## 先決條件 {#mcp-prerequisites}

在將[!DNL Adobe Target] MCP伺服器連線到您的MCP使用者端之前，請確定下列事項：

* 您與Adobe Experience Platform組織有作用中的[!DNL Adobe Target]授權（Adobe Experience Cloud訂閱）。
* 您有一個支援的MCP相容應用程式（目前為Claude Web、Claude Desktop、Claude Code或Cursor）。
* 您已在Adobe Admin Console中設定[!DNL Adobe Target]許可權：
   * **觀察者**&#x200B;角色：唯讀工具
   * **編輯者**&#x200B;角色：讀取+建立工具
   * **核准者**&#x200B;角色：讀取+建立+啟用/停用工具

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

1. 確認您在[!DNL Adobe Target]中擁有作業所需的許可權（請參閱[必要條件](#mcp-prerequisites)）。
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

## 常見問題集 {#mcp-faq}

+++支援哪些MCP使用者端？

[!DNL Adobe Target] MCP伺服器目前可用於&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**&#x200B;和&#x200B;**Cursor**。 未來版本可能會新增對其他MCP相容應用程式的支援。
+++

+++我可以透過MCP存取哪些[!DNL Adobe Target]物件？

您可以存取活動(A/B、XT、AP)、對象、選件、屬性、mbox、Recommendations條件、回應Token、at.js設定、A4T報表和實體修訂歷史記錄。 52種工具同時支援讀取和寫入作業 — 寫入作業需要適當的角色和明確的確認。
+++

+++MCP伺服器可以建立或修改活動嗎？

是.除了讀取作業之外，伺服器也會公開可讓您建立活動、暫停活動、更新優先順序、調整流量分割等的寫入作業。 寫入作業會遵循與[!DNL Adobe Target] UI相同的許可權模式 — 您需要適當的角色才能進行變更，而且不會執行任何動作而不需要明確的使用者確認。
+++

+++我需要開發人員存取權才能使用MCP伺服器嗎？

無.MCP伺服器是專為行銷和技術人員所設計。 行銷人員可以在任何支援的MCP使用者端中使用自然語言提示與其互動，而開發人員則可以在Claude Code或Cursor等工具中使用它。
+++

+++我的[!DNL Adobe Target]資料是否已傳送給MCP使用者端提供者？

當您提交提示時，MCP使用者端可能會傳送相關內容（包括MCP伺服器傳回的[!DNL Adobe Target]資料）到其模型以進行處理。 在連線到生產資料之前，請檢閱MCP使用者端提供者的隱私權和資料處理原則。 Adobe的資料處理受[Adobe隱私權原則](https://www.adobe.com/tw/privacy.html)和[資料保護條款](https://www.adobe.com/go/dpt-ww)所規範。
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

* [MCP伺服器工具參考](target-mcp-tools-reference.md)
* [自行託管 [!DNL Adobe Target] MCP伺服器](target-mcp-self-hosted.md)
* [模型內容通訊協定檔案](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] 管理員API參考](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [資料指標檔案](https://docs.cursor.com/){target="_blank"}
