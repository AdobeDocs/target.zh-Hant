---
solution: Target
product: target
title: Adobe Target MCP伺服器工具參考
description: Adobe Target MCP伺服器公開的所有21個唯讀工具完整引數參考。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta 版" type="Informative"
role: Developer, User
level: Intermediate, Experienced
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 11%

---

# [!DNL Adobe Target] MCP伺服器工具參考 {#target-mcp-tools-reference}


>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP伺服器可供&#x200B;**公用Beta**&#x200B;中的所有客戶使用。 目前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支援。

此頁面是[!DNL Adobe Target] MCP伺服器公開之所有唯讀工具的完整參考。 對於每個工具，您都可以找到說明、引數詳細資料、傳回值以及自然語言提示範例。 如需設定指示和使用案例，請參閱[開始使用](target-mcp-get-started.md)和[使用案例和逐步說明](target-mcp-use-cases.md)。

>[!IMPORTANT]
>
>模型內容通訊協定(MCP)是一種新興的開放原始碼標準，可能會帶來安全性或可靠性風險。 Adobe MCP伺服器整合和相關檔案係依「現況」提供，不提供任何形式的保證。
>
>將MCP使用者端或伺服器連線至Adobe產品是客戶選擇的組態，客戶需負責評估任何MCP整合的安全性和適用性。 Adobe對於因設定錯誤、誤用MCP、協力廠商實作中的漏洞，或透過啟用MCP的工作流程執行的意外動作所引起的問題，概不負責。
>
>為了降低風險，Adobe鼓勵您在有效使用之前在沙箱環境中測試整合，並在確認或依賴之前，仔細檢閱及驗證所有MCP啟動的動作和回應。

## 先決條件 {#tools-prerequisites}

您的[!DNL Adobe Target]角色會決定您可用的工具：

* **觀察者**&#x200B;角色或更新版本：存取所有讀取工具
* **編輯者**&#x200B;角色：存取讀取和寫入（建立）工具
* **核准者**&#x200B;角色：讀取、寫入和啟用/停用工具的存取權

如需完整的安裝指示，請參閱[開始使用](target-mcp-get-started.md)。

## 活動工具 {#tools-activities}

+++列出活動

**工具：** `list_target_activities`

列出[!DNL Adobe Target]個具有伺服器端篩選和排序的活動。

擷取活動的分頁清單。 所有篩選器都是由[!DNL Target] Admin API在伺服器端套用。 伺服器每頁最多可傳回200個活動。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `limit` | 整數 | 無 | 要傳回的活動數上限（伺服器上限： 200） |
| `offset` | 整數 | 無 | 為分頁要略過的活動數 |
| `sort_by` | string | 否 | 排序依據的欄位。 遞減順序以`-`為前置詞（例如，`-modifiedAt`）。 選項： `id`、`name`、`state`、`priority`、`startsAt`、`endsAt`、`lifetimeStart`、`lifetimeEnd`、`createdAt`、`createdBy`、`modifiedAt`、`modifiedBy`、`type`、`thirdPartyId` |
| `state` | string | 否 | 依活動狀態篩選： `approved` （即時/作用中）、`deactivated` （非作用中）、`paused`、`saved` （草稿） |
| `activity_type` | string | 否 | 依型別篩選： `ab` （A/B測試）、`xt` （體驗鎖定目標）、`abt` (Automated Personalization) |
| `name_contains` | string | 否 | 篩選名稱包含此字串（不區分大小寫）的活動 |
| `starts_after` | string | 否 | ISO 8601日期 — 在此日期之後開始的活動 |
| `starts_before` | string | 否 | ISO 8601日期 — 在此日期之前開始的活動 |
| `modified_after` | string | 否 | ISO 8601日期 — 在此日期之後修改的活動 |
| `ends_after` | string | 否 | ISO 8601日期 — 在此日期之後結束的活動 |
| `ends_before` | string | 否 | ISO 8601日期 — 在此日期之前結束的活動 |
| `workspace` | string | 否 | 依工作區ID篩選 |
| `segment_id` | string | 否 | 依對象區段ID篩選 |
| `profile_attribute_id` | string | 否 | 依設定檔屬性ID篩選 |
| `priority` | 整數 | 無 | 依確切的優先順序值篩選(0-999) |
| `mbox` | string | 否 | 依mbox/位置名稱篩選 |
| `offer_id` | string | 否 | 依優惠ID篩選 |
| `view_id` | string | 否 | 依SPA檢視ID篩選 |

**傳回：** JSON物件具有`activities` （物件清單包括`id`、`name`、`state`、`type`、`priority`、`modifiedAt`、`startsAt`、`endsAt`）和`total` （總計數，可能會超過傳回的頁面大小）。

**範例提示：**「列出所有依最近修改排序的作用中A/B測試」。

+++

+++取得A/B活動

**工具：** `get_ab_activity`

取得有關A/B活動的詳細資訊。

擷取特定A/B測試的完整設定，包括體驗、位置、量度和目標定位規則。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | A/B活動的唯一識別碼 |

**傳回：**&#x200B;完整的活動詳細資料，包括中繼資料（名稱、狀態、優先順序、日期）、體驗、位置和選件、目標和量度，以及目標規則。

**範例提示：**「取得A/B活動12345的詳細資料」。

+++

+++取得體驗鎖定目標活動

**工具：** `get_xt_activity`

取得體驗鎖定目標(XT)活動的詳細資訊。

擷取特定XT活動的完整設定，包括對象體驗對應、位置和量度。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | XT活動的唯一識別碼 |

**傳回：**&#x200B;完整的活動詳細資料，包括中繼資料、具有對象對應的體驗、位置和選件，以及目標和量度。

**範例提示：**「取得體驗鎖定目標活動12345的詳細資料」。

+++

+++取得Automated Personalization活動

**工具：** `get_abt_activity`

取得有關Automated Personalization (AP)活動的詳細資訊。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | AP活動的唯一識別碼 |

**傳回：**&#x200B;完整的活動詳細資料，包括中繼資料、體驗、位置和演演算法設定。

**範例提示：**「取得自動Personalization活動12345動詳細資料」。

+++

<!--
+++Create an A/B activity

**Tool:** `create_ab_activity`

Create a new A/B test activity.

Creates a new A/B test with the specified configuration including experiences, offers, and targeting.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `audiences` | array | No | Target audience configurations |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an A/B test called 'Homepage Hero Test' with two experiences testing different hero images on the homepage-hero mbox."

+++
-->

<!--
+++Create an Experience Targeting activity

**Tool:** `create_xt_activity`

Create a new Experience Targeting (XT) activity.

Creates an XT activity that delivers different experiences to different audiences based on targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations with audience mappings |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an Experience Targeting activity called 'Geo Personalization' that shows different content to visitors from different regions."

+++
-->

<!--
+++Update an A/B activity

**Tool:** `update_ab_activity`

Update an existing A/B activity.

Uses a read-modify-write pattern: fetches the current state, merges your changes, validates, and sends the update.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity to update |
| `activity` | object | Yes | Fields to update (name, priority, experiences, locations, goals, etc.) |

**Returns:** The updated activity object.

**Example prompt:** "Update activity 12345 to change the traffic allocation to 70/30."

+++
-->

<!--
+++Update an Experience Targeting activity

**Tool:** `update_xt_activity`

Update an existing Experience Targeting activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the XT activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update XT activity 12345 to add a new experience for mobile visitors."

+++
-->

<!--
+++Update an Automated Personalization activity

**Tool:** `update_abt_activity`

Update an existing Automated Personalization activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the AP activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update Auto-Personalization activity 12345 to change the optimization goal."

+++
-->

<!--
+++Update activity schedule

**Tool:** `update_activity_schedule`

Update activity start and end dates.

Updates the schedule for an activity without modifying other settings.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `activity_type` | string | Yes | Type of activity: `ab`, `xt`, or `abt` |
| `starts_at` | string | No | New start date (ISO 8601) |
| `ends_at` | string | No | New end date (ISO 8601) |

**Returns:** Confirmation of the schedule update.

**Example prompt:** "Update the schedule for A/B activity 12345 to run from May 1st to May 31st."

+++
-->

<!--
+++Change activity state

**Tool:** `update_activity_state`

Change activity state (activate, deactivate, or pause).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `state` | string | Yes | New state: `approved` (live/active), `deactivated` (inactive), `paused`, or `saved` (draft) |

**Returns:** The updated activity state.

**Example prompt:** "Activate activity 12345" or "Pause the Homepage Hero Test."

+++
-->

<!--
+++Rename an activity

**Tool:** `update_activity_name`

Rename an activity.

Updates only the name without modifying the full configuration.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `name` | string | Yes | New activity name |

**Returns:** The updated activity object.

**Example prompt:** "Rename activity 12345 to 'Summer Campaign Hero Test'."

+++
-->

<!--
+++Change activity priority

**Tool:** `update_activity_priority`

Change activity priority.

Higher-priority activities take precedence when multiple activities target the same location.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `priority` | integer | Yes | New priority value (0–999; higher = higher priority) |

**Returns:** The updated activity object.

**Example prompt:** "Set the priority of activity 12345 to 100."

+++
-->

<!--
+++Add a variant to an activity

**Tool:** `add_activity_variant`

Add a new experience/variant to an activity.

Handles all structural coordination including creating options, mapping to locations, and rebalancing traffic.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name for the new experience/variant |
| `offer_id` | integer | No | (Form-based) Existing offer ID to use |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `traffic_percentage` | integer | No | Traffic % for the new variant (1–99). If omitted, traffic is rebalanced evenly |
| `audience_id` | integer | No | Audience ID for the variant (XT activities) |
| `modifications` | array | No | (VEC) List of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Add a new variant called 'Holiday Theme' to A/B activity 12345 using offer 67890."

+++
-->

<!--
+++Update traffic split

**Tool:** `update_traffic_split`

Update traffic allocation across variants.

The percentages must sum to exactly 100.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab` or `abt` (XT not supported — audience-targeted) |
| `splits` | object | Yes | Dictionary mapping experience name to percentage. Must include all experiences and sum to 100 |

**Returns:** The updated activity object.

**Example prompt:** "Change the traffic split for activity 12345 to 70% Control and 30% Variant A."

+++
-->

<!--
+++Change a variant's offer

**Tool:** `update_variant_offer`

Change the offer for a specific variant.

Works for both form-based activities (using `offer_id`) and VEC activities (using `modifications`).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to update |
| `offer_id` | integer | No | (Form-based) New offer ID |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `modifications` | array | No | (VEC) New list of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Update the 'Variant A' experience in activity 12345 to use offer 99999."

+++
-->

<!--
+++Remove a variant from an activity

**Tool:** `remove_activity_variant`

Remove an experience/variant from an activity.

Removes the experience, cleans up orphaned options, and rebalances traffic evenly across remaining variants.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to remove |

**Returns:** The updated activity object.

**Example prompt:** "Remove the 'Test Variant' experience from A/B activity 12345."

+++
-->

## 優惠工具 {#tools-offers}

+++列出優惠方案

**工具：** `list_target_offers`

列出您[!DNL Target]租使用者中的所有優惠。

擷取具有選擇性篩選功能的內容選件分頁清單。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `limit` | 整數 | 無 | 要傳回的最大優惠方案數量 |
| `offset` | 整數 | 無 | 略過分頁的優惠方案數量 |
| `type` | string | 否 | 依選件型別篩選： `content` (HTML)、`json`或`redirect` |
| `name` | string | 否 | 依選件名稱篩選（部分符合） |

**傳回：**&#x200B;具有`offers`的JSON物件（物件清單，包括`id`、`name`、`type`、`content`、`modifiedAt`）和`total`。

**範例提示：**「列出所有JSON選件」。

+++

+++取得優惠方案

**工具：** `get_target_offer`

取得特定優惠方案的詳細資訊。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `offer_id` | 整數 | 是 | 優惠方案的唯一識別碼 |

**傳回：**&#x200B;完整優惠詳細資料，包括`id`、`name`、`type`、`content`、`workspace`和`modifiedAt`。

**範例提示：**「取得優惠67890動的詳細資料」。

+++

<!--
+++Create an HTML offer

**Tool:** `create_target_offer`

Create a new HTML content offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | string | Yes | HTML or text content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create an HTML offer called 'Summer Sale Banner' with a promotional banner."

+++

+++Create a JSON offer

**Tool:** `create_target_json_offer`

Create a new JSON offer for delivering structured data.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | object | Yes | JSON content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create a JSON offer called 'Feature Flags Config' with feature toggle settings."

+++

+++Update an offer

**Tool:** `update_target_offer`

Update an existing offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `offer_id` | integer | Yes | The unique identifier of the offer to update |
| `name` | string | No | Updated offer name |
| `content` | string or object | No | Updated offer content |

**Returns:** The updated offer object.

**Example prompt:** "Update offer 67890 with new promotional content."

+++
-->

## 對象工具 {#tools-audiences}

+++列出對象

**工具：** `list_target_audiences`

列出您[!DNL Target]租使用者中的所有對象。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `limit` | 整數 | 無 | 要傳回的對象數量上限 |
| `offset` | 整數 | 無 | 為分頁要略過的對象數 |

**傳回：**&#x200B;具有`audiences`的JSON物件（物件清單，包括`id`、`name`、`description`、`origin`、`modifiedAt`）和`total`。

**範例提示：**「列出所有對象」。

+++

<!--
+++Create an audience

**Tool:** `create_target_audience`

Create a new audience with targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the audience |
| `description` | string | No | Description of the audience |
| `targetRule` | object | No | Targeting rules (geo, browser, custom attributes, etc.) |
| `workspace_id` | string | No | Workspace ID for the audience |

**Returns:** The created audience with its assigned ID.

**Example prompt:** "Create an audience called 'Mobile Visitors from California' targeting mobile users in CA."

+++
-->

## Mbox工具 {#tools-mboxes}

+++清單mbox

**工具：** `list_target_mboxes`

列出您[!DNL Target]租使用者中的所有mbox。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `limit` | 整數 | 無 | 要傳回的mbox數量上限 |
| `offset` | 整數 | 無 | 要略過分頁的mbox數量 |
| `name` | string | 否 | 依mbox名稱篩選（部分符合） |
| `status` | string | 否 | 依狀態篩選 |

**傳回：**&#x200B;具有`mboxes`的JSON物件（物件清單，包括`name`、`status`、`lastRequestTime`）和`total`。

**範例提示：**「列出所有包含&#39;homepage&#39;的mbox」。

+++

+++取得mbox

**工具：** `get_target_mbox`

取得特定mbox的詳細資訊。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `mbox_name` | string | 是 | mbox的名稱 |

**傳回：** Mbox詳細資料，包括`name`、`status`以及使用mbox的活動清單。

**範例提示：**「取得mbox &#39;homepage-hero&#39;的詳細資料」。

+++

+++清單mbox設定檔屬性

**工具：** `list_target_mbox_profile_attributes`

列出所有可用於鎖定目標的mbox設定檔屬性。

不需要引數。

**傳回：**&#x200B;設定檔屬性物件的JSON陣列。

**範例提示：** 「哪些設定檔屬性可用於目標定位？」

+++

## 屬性工具 {#tools-properties}

+++清單屬性

**工具：** `list_target_properties`

列出您[!DNL Target]租使用者中的所有屬性。

屬性可組織活動並控制存取。

不需要引數。

**傳回：**&#x200B;屬性物件清單，包括`id`、`name`、`description`和`channel`。

**範例提示：**「列出所有Target屬性」。

+++

## 報告工具 {#tools-reporting}

+++取得A/B效能報表

**工具：** `get_ab_performance_report`

取得A/B活動的效能報表。

擷取轉換率、提升度和信賴水準。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | A/B活動的唯一識別碼 |
| `report_interval` | string | 否 | 報告的時段（例如`last7days`、`last30days`或自訂日期範圍） |

**傳回：**&#x200B;體驗層級量度（訪客、轉換、轉換率）、提升度計算、統計信賴度及收入量度（如果已設定）。

**範例提示：** 「顯示過去30天A/B測試12345的效能報告。」

+++

+++取得A/B訂單報表

**工具：** `get_ab_orders_report`

取得A/B活動的訂單/收入報表。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | A/B活動的唯一識別碼 |
| `report_interval` | string | 否 | 報告的時段 |

**傳回：**&#x200B;訂單計數、收入，以及體驗的平均訂單值。

**範例提示：**「取得活動12345的訂單報表」。

+++

+++取得體驗鎖定目標效能報表

**工具：** `get_xt_performance_report`

取得體驗鎖定目標活動的效能報表。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | XT活動的唯一識別碼 |
| `report_interval` | string | 否 | 報告的時段 |

**傳回：**&#x200B;體驗層級的效能測量結果。

**範例提示：**「顯示我的體驗鎖定目標活動54321的效能」。

+++

+++取得體驗鎖定目標訂單報表

**工具：** `get_xt_orders_report`

取得體驗鎖定目標活動的訂單/收入報表。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | XT活動的唯一識別碼 |
| `report_interval` | string | 否 | 報告的時段 |

**傳回：**&#x200B;依據體驗的排序量度。

**範例提示：**「取得XT活動54321的訂單資料」。

+++

+++依活動名稱取得效能報表

**工具：** `get_activity_report_by_name`

依名稱搜尋活動並取得其效能報表。

當您知道活動名稱但不知道其ID時，這很有用。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_name` | string | 是 | 要搜尋的活動名稱 |
| `report_interval` | string | 否 | 報告的時段 |

**傳回：**&#x200B;活動詳細資料和績效測量結果。

**範例提示：** 「取得我的『首頁主圖測試』活動的效能報告」。

+++

## 預覽工具 {#tools-preview}

+++預覽活動

**工具：** `preview_activity`

產生[!DNL Target]活動的瀏覽器QA預覽URL。

建立可點按的預覽連結，強制顯示特定體驗，略過對象鎖定目標規則。 適用於A/B、XT和Automated Personalization活動。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要預覽的[!DNL Target]活動識別碼 |
| `experience_index` | 整數 | 無 | 0型體驗索引。 如果省略，會傳回所有體驗的URL |
| `url` | string | 否 | 預覽的頁面URL。 表單式活動的必要專案。 針對VEC活動，會覆寫編寫的位置（如果提供） |

**傳回：**&#x200B;活動資訊（名稱、型別、狀態）、每個體驗的預覽URL，以及體驗名稱和索引。

**範例提示：** 「產生活動12345動的預覽URL，以便我測試瀏覽器中的每一個體驗。」

+++

## 回應Token工具 {#tools-response-tokens}

+++列出回應Token

**工具：** `list_target_response_tokens`

列出您[!DNL Target]租使用者中的所有回應Token。

擷取所有已設定的回應Token，包括內建和自訂。

不需要引數。

**傳回：**&#x200B;回應權杖物件的JSON陣列，狀態為`name`、`type`和`enabled`。

**範例提示：**「列出所有回應Token」。

+++

<!--
+++Create a response token

**Tool:** `create_target_response_token`

Create a new custom response token for collecting additional data in [!DNL Target] responses.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `token_name` | string | Yes | Name of the response token |
| `token_type` | string | Yes | Type of token: `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO`, or `CRS` |

**Returns:** The created response token object.

**Example prompt:** "Create a custom response token called 'campaign_id' of type ACTIVITY."

+++
-->

## 修訂工具 {#tools-revisions}

+++取得稽核記錄

**工具：** `get_target_revisions`

取得資源型別的稽核記錄。

擷取使用作者選擇性篩選對[!DNL Target]資源所做的變更。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `revision_resource_type` | string | 是 | 資源型別： `activity`、`offer`或`audience` |
| `modified_by` | string | 否 | 依進行變更的使用者篩選 |
| `limit` | 整數 | 無 | 要傳回的修訂數量上限 |
| `offset` | 整數 | 無 | 分頁要略過的修訂數量 |

**傳回：**&#x200B;包含時間戳記、使用者和變更說明的修訂歷程記錄。

**範例提示：** 「顯示活動變更的稽核記錄」。

+++

+++取得特定實體的修訂版本

**工具：** `get_target_entity_revisions`

依照ID取得特定實體的所有修訂版本。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `revision_resource_type` | string | 是 | 資源型別： `activity`、`offer`或`audience` |
| `entity_id` | 整數 | 是 | 實體的唯一識別碼 |

**傳回：**&#x200B;指定實體所有修訂的JSON陣列。

**範例提示：** 「顯示活動12345的所有變更。」

+++

## 範本工具 {#tools-templates}

+++列出可用的範本

**工具：** `list_target_templates`

列出可用於建立活動和優惠方案的MCP資源和範本。

不需要引數。

**傳回：** JSON物件列出可用的範本和資源。

**範例提示：** 「哪些範本可用於建立活動？」

+++

## 工具摘要 {#tools-summary}

| 類別 | 計數 | 工具 |
|---|---|---|
| 活動 | 4 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity` |
| 產品建議 | 2 | `list_target_offers`, `get_target_offer` |
| 客群 | 1 | `list_target_audiences` |
| mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| 屬性 | 1 | `list_target_properties` |
| 報表 | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| 預覽 | 1 | `preview_activity` |
| 回應Token | 1 | `list_target_response_tokens` |
| 修訂 | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| 範本 | 1 | `list_target_templates` |
| **總計** | **21** | |

## 相關資源 {#tools-related}

* [使用MCP使用者端](target-mcp.md)
* [[!DNL Adobe Target]管理員API參考](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
