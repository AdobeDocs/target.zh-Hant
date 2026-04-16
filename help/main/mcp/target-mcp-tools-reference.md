---
solution: Target
product: target
title: Adobe Target MCP伺服器工具參考
description: Adobe Target MCP伺服器公開的所有39個公用工具的完整引數參考。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta 版" type="Informative"
role: Developer, User
level: Intermediate, Experienced
hide: true
source-git-commit: 17804b5f8cfce7033bffcad826e5510bfc42a832
workflow-type: tm+mt
source-wordcount: '2688'
ht-degree: 15%

---

# [!DNL Adobe Target] MCP伺服器工具參考 {#target-mcp-tools-reference}

>[!BEGINSHADEBOX]

目錄：

* [使用MCP使用者端](target-mcp.md)
* **[MCP伺服器工具參考](target-mcp-tools-reference.md)**
* [自行託管MCP伺服器](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

此頁面是[!DNL Adobe Target] MCP伺服器公開之所有公用工具的完整參考。 對於每個工具，您都可以找到說明、引數詳細資料、傳回值以及自然語言提示範例。 如需設定指示和使用案例，請參閱[使用MCP使用者端](target-mcp.md)。

>[!NOTE]
>
>此處僅記錄公用工具。 排除內部工具和僅限代理程式的工具。 讀取工具可供具有&#x200B;**觀察者**&#x200B;或以上角色的所有連線使用者使用；寫入工具需要&#x200B;**編輯器**&#x200B;或&#x200B;**核准者**&#x200B;角色。

## 活動工具 {#tools-activities}

### list_target_activities

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

### get_ab_activity

取得有關A/B活動的詳細資訊。

擷取特定A/B測試的完整設定，包括體驗、位置、量度和目標定位規則。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | A/B活動的唯一識別碼 |

**傳回：**&#x200B;完整的活動詳細資料，包括中繼資料（名稱、狀態、優先順序、日期）、體驗、位置和選件、目標和量度，以及目標規則。

**範例提示：**「取得A/B活動12345的詳細資料」。

### get_xt_activity

取得體驗鎖定目標(XT)活動的詳細資訊。

擷取特定XT活動的完整設定，包括對象體驗對應、位置和量度。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | XT活動的唯一識別碼 |

**傳回：**&#x200B;完整的活動詳細資料，包括中繼資料、具有對象對應的體驗、位置和選件，以及目標和量度。

**範例提示：**「取得體驗鎖定目標活動12345的詳細資料」。

### get_abt_activity

取得有關Automated Personalization (AP)活動的詳細資訊。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | AP活動的唯一識別碼 |

**傳回：**&#x200B;完整的活動詳細資料，包括中繼資料、體驗、位置和演演算法設定。

**範例提示：**「取得自動Personalization活動12345動詳細資料」。

### create_ab_activity

建立新的A/B測試活動。

使用指定的組態（包括體驗、選件和鎖定目標）建立新的A/B測試。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `name` | string | 是 | 活動的名稱 |
| `state` | string | 否 | 初始狀態： `approved`、`deactivated`或`saved` （預設： `saved`） |
| `priority` | 整數 | 無 | 活動優先順序（0-999，預設： 0） |
| `starts_at` | string | 否 | 活動開始日期(ISO 8601) |
| `ends_at` | string | 否 | 活動結束日期(ISO 8601) |
| `experiences` | 陣列 | 是 | 體驗設定清單 |
| `locations` | 陣列 | 是 | 位置/mbox設定清單 |
| `goals` | 物件 | 否 | 主要和次要目標量度 |
| `audiences` | 陣列 | 無 | Target對象設定 |
| `workspace_id` | string | 否 | 活動的Workspace ID |

**傳回：**&#x200B;已建立的活動物件及其指派的識別碼。

**範例提示：** 「建立名為&#39;Homepage Hero Test&#39;的A/B測試，其中包含兩個體驗，測試homepage-hero mbox上的不同主圖影像。」

### create_xt_activity

建立新的體驗鎖定目標(XT)活動。

建立XT活動，此活動會根據鎖定目標規則將不同的體驗提供給不同的對象。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `name` | string | 是 | 活動的名稱 |
| `state` | string | 否 | 初始狀態： `approved`、`deactivated`或`saved` （預設： `saved`） |
| `priority` | 整數 | 無 | 活動優先順序（0-999，預設： 0） |
| `starts_at` | string | 否 | 活動開始日期(ISO 8601) |
| `ends_at` | string | 否 | 活動結束日期(ISO 8601) |
| `experiences` | 陣列 | 是 | 具有對象對應的體驗設定清單 |
| `locations` | 陣列 | 是 | 位置/mbox設定清單 |
| `goals` | 物件 | 否 | 主要和次要目標量度 |
| `workspace_id` | string | 否 | 活動的Workspace ID |

**傳回：**&#x200B;已建立的活動物件及其指派的識別碼。

**範例提示：** 「建立稱為『地理Personalization』的體驗鎖定目標活動，對來自不同地區的訪客顯示不同的內容。」

### update_ab_activity

更新現有的A/B活動。

使用讀取 — 修改 — 寫入模式：擷取目前狀態、合併您的變更、驗證並傳送更新。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要更新之活動的唯一識別碼 |
| `activity` | 物件 | 是 | 要更新的欄位（名稱、優先順序、體驗、位置、目標等） |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「更新活動12345以將流量分配變更為70/30」。

### update_xt_activity

更新現有的體驗鎖定目標活動。

使用讀寫模式。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要更新的XT活動的唯一識別碼 |
| `activity` | 物件 | 是 | 要更新的欄位 |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「更新XT活動12345以新增行動訪客的體驗」。

### update_abt_activity

更新現有的Automated Personalization活動。

使用讀寫模式。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要更新的AP活動的唯一識別碼 |
| `activity` | 物件 | 是 | 要更新的欄位 |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「更新自動Personalization活動12345動以變更最佳化目標」。

### update_activity_schedule

更新活動的開始和結束日期。

更新活動的排程，而不修改其他設定。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 活動的唯一識別碼 |
| `activity_type` | string | 是 | 活動型別： `ab`、`xt`或`abt` |
| `starts_at` | string | 否 | 新的開始日期(ISO 8601) |
| `ends_at` | string | 否 | 新的結束日期(ISO 8601) |

**傳回：**&#x200B;排程更新的確認。

**範例提示：**「更新A/B活動12345動從5月1日到5月31日執行的排程」。

### update_activity_state

變更活動狀態（啟動、停用或暫停）。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 活動的唯一識別碼 |
| `state` | string | 是 | 新狀態： `approved` （即時/作用中）、`deactivated` （非作用中）、`paused`或`saved` （草稿） |

**傳回：**&#x200B;更新的活動狀態。

**範例提示：**「啟動活動12345」或「暫停首頁主圖測試」。

### update_activity_name

重新命名活動。

只更新名稱，不修改完整設定。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 活動的唯一識別碼 |
| `name` | string | 是 | 新活動名稱 |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「將活動12345重新命名為&#39;Summer Campaign Hero Test&#39;。」

### update_activity_priority

變更活動優先順序。

當多個活動鎖定相同位置時，優先順序較高的活動優先。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 活動的唯一識別碼 |
| `priority` | 整數 | 是 | 新的優先順序值（0-999；較高=較高的優先順序） |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「將活動12345的優先順序設為100。」

### add_activity_variant

將新的體驗/變體新增至活動。

處理所有結構協調，包括建立選項、對應至位置以及重新平衡流量。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要修改之活動的ID |
| `activity_type` | string | 是 | 活動型別： `ab`、`xt`或`abt` |
| `variant_name` | string | 是 | 新體驗/變體的名稱 |
| `offer_id` | 整數 | 無 | （表單式）要使用的現有優惠方案ID |
| `offer_content` | string | 否 | （表單式）新的內嵌選件的HTML內容 |
| `traffic_percentage` | 整數 | 無 | 新變體的流量% (1-99)。 如果省略，流量會平均重新平衡 |
| `audience_id` | 整數 | 無 | 變體的對象ID （XT活動） |
| `modifications` | 陣列 | 無 | (VEC) CSS選取器型修改清單 |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「使用選件67890則12345新增名為&#39;Holiday Theme&#39;的新變體至A/B活動。」

### update_traffic_split

更新變體間的流量分配。

百分比總和必須剛好為100。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要修改之活動的ID |
| `activity_type` | string | 是 | 活動型別： `ab`或`abt` （不支援XT — 以對象為目標） |
| `splits` | 物件 | 是 | 字典對應體驗名稱到百分比。 必須包含所有體驗，且總和必須為100 |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「將活動12345的流量分割變更為70%控制項和30%變體A。」

### update_variant_offer

變更特定變體的選件。

適用於表單式活動（使用`offer_id`）和VEC活動（使用`modifications`）。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要修改之活動的ID |
| `activity_type` | string | 是 | 活動型別： `ab`、`xt`或`abt` |
| `variant_name` | string | 是 | 要更新的體驗/變體的名稱 |
| `offer_id` | 整數 | 無 | （表單式）新優惠方案ID |
| `offer_content` | string | 否 | （表單式）新的內嵌選件的HTML內容 |
| `modifications` | 陣列 | 無 | (VEC) CSS選取器型修改的新清單 |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「更新活動12345中的「變體A」體驗，以使用選件99999。」

### remove_activity_variant

從活動中移除體驗/變體。

移除體驗、清除孤立的選項，以及在其餘變體間平均重新平衡流量。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要修改之活動的ID |
| `activity_type` | string | 是 | 活動型別： `ab`、`xt`或`abt` |
| `variant_name` | string | 是 | 要移除的體驗/變體的名稱 |

**傳回：**&#x200B;更新的活動物件。

**範例提示：**「從A/B活動12345動移除&#39;Test Variant&#39;體驗」。

## 優惠工具 {#tools-offers}

### list_target_offers

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

### get_target_offer

取得特定優惠方案的詳細資訊。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `offer_id` | 整數 | 是 | 優惠方案的唯一識別碼 |

**傳回：**&#x200B;完整優惠詳細資料，包括`id`、`name`、`type`、`content`、`workspace`和`modifiedAt`。

**範例提示：**「取得優惠67890動的詳細資料」。

### create_target_offer

建立新的HTML內容選件。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `name` | string | 是 | 優惠方案名稱 |
| `content` | string | 是 | 選件的HTML或文字內容 |
| `workspace_id` | string | 否 | 優惠的Workspace ID |

**傳回：**&#x200B;已建立的選件及其指派的識別碼。

**範例提示：** 「使用促銷橫幅建立名為&#39;Summer Sale Banner&#39;的HTML優惠。」

### create_target_json_offer

建立新的JSON選件來傳遞結構化資料。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `name` | string | 是 | 優惠方案名稱 |
| `content` | 物件 | 是 | 選件的JSON內容 |
| `workspace_id` | string | 否 | 優惠的Workspace ID |

**傳回：**&#x200B;已建立的選件及其指派的識別碼。

**範例提示：** 「使用功能切換設定建立名為&#39;Feature Flags Config&#39;的JSON選件。」

### update_target_offer

更新現有優惠方案。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `offer_id` | 整數 | 是 | 要更新之優惠方案的唯一識別碼 |
| `name` | string | 否 | 已更新優惠方案名稱 |
| `content` | 字串或物件 | 無 | 更新的優惠內容 |

**傳回：**&#x200B;更新的選件物件。

**範例提示：**「使用新的促銷內容更新優惠67890案」。

## 對象工具 {#tools-audiences}

### list_target_audiences

列出您[!DNL Target]租使用者中的所有對象。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `limit` | 整數 | 無 | 要傳回的對象數量上限 |
| `offset` | 整數 | 無 | 為分頁要略過的對象數 |

**傳回：**&#x200B;具有`audiences`的JSON物件（物件清單，包括`id`、`name`、`description`、`origin`、`modifiedAt`）和`total`。

**範例提示：**「列出所有對象」。

### create_target_audience

使用鎖定目標規則建立新的對象。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `name` | string | 是 | 對象名稱 |
| `description` | string | 否 | 對象說明 |
| `targetRule` | 物件 | 否 | 鎖定目標規則（地理、瀏覽器、自訂屬性等） |
| `workspace_id` | string | 否 | 對象的Workspace ID |

**傳回：**&#x200B;已建立的對象及其指派的識別碼。

**範例提示：** 「在CA中建立名為『來自加州的行動訪客』以行動使用者為目標的對象。」

## Mbox工具 {#tools-mboxes}

### list_target_mboxes

列出您[!DNL Target]租使用者中的所有mbox。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `limit` | 整數 | 無 | 要傳回的mbox數量上限 |
| `offset` | 整數 | 無 | 要略過分頁的mbox數量 |
| `name` | string | 否 | 依mbox名稱篩選（部分符合） |
| `status` | string | 否 | 依狀態篩選 |

**傳回：**&#x200B;具有`mboxes`的JSON物件（物件清單，包括`name`、`status`、`lastRequestTime`）和`total`。

**範例提示：**「列出所有包含&#39;homepage&#39;的mbox」。

### get_target_mbox

取得特定mbox的詳細資訊。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `mbox_name` | string | 是 | mbox的名稱 |

**傳回：** Mbox詳細資料，包括`name`、`status`以及使用mbox的活動清單。

**範例提示：**「取得mbox &#39;homepage-hero&#39;的詳細資料」。

### list_target_mbox_profile_attributes

列出所有可用於鎖定目標的mbox設定檔屬性。

不需要引數。

**傳回：**&#x200B;設定檔屬性物件的JSON陣列。

**範例提示：** 「哪些設定檔屬性可用於目標定位？」

## 屬性工具 {#tools-properties}

### list_target_properties

列出您[!DNL Target]租使用者中的所有屬性。

屬性可組織活動並控制存取。

不需要引數。

**傳回：**&#x200B;屬性物件清單，包括`id`、`name`、`description`和`channel`。

**範例提示：**「列出所有Target屬性」。

## 報告工具 {#tools-reporting}

### get_ab_performance_report

取得A/B活動的效能報表。

擷取轉換率、提升度和信賴水準。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | A/B活動的唯一識別碼 |
| `report_interval` | string | 否 | 報告的時段（例如`last7days`、`last30days`或自訂日期範圍） |

**傳回：**&#x200B;體驗層級量度（訪客、轉換、轉換率）、提升度計算、統計信賴度及收入量度（如果已設定）。

**範例提示：** 「顯示過去30天A/B測試12345的效能報告。」

### get_ab_orders_report

取得A/B活動的訂單/收入報表。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | A/B活動的唯一識別碼 |
| `report_interval` | string | 否 | 報告的時段 |

**傳回：**&#x200B;訂單計數、收入，以及體驗的平均訂單值。

**範例提示：**「取得活動12345的訂單報表」。

### get_xt_performance_report

取得體驗鎖定目標活動的效能報表。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | XT活動的唯一識別碼 |
| `report_interval` | string | 否 | 報告的時段 |

**傳回：**&#x200B;體驗層級的效能測量結果。

**範例提示：**「顯示我的體驗鎖定目標活動54321的效能」。

### get_xt_orders_report

取得體驗鎖定目標活動的訂單/收入報表。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | XT活動的唯一識別碼 |
| `report_interval` | string | 否 | 報告的時段 |

**傳回：**&#x200B;依據體驗的排序量度。

**範例提示：**「取得XT活動54321的訂單資料」。

### get_activity_report_by_name

依名稱搜尋活動並取得其效能報表。

當您知道活動名稱但不知道其ID時，這很有用。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_name` | string | 是 | 要搜尋的活動名稱 |
| `report_interval` | string | 否 | 報告的時段 |

**傳回：**&#x200B;活動詳細資料和績效測量結果。

**範例提示：** 「取得我的『首頁主圖測試』活動的效能報告」。

## 預覽工具 {#tools-preview}

### preview_activity

產生[!DNL Target]活動的瀏覽器QA預覽URL。

建立可點按的預覽連結，強制顯示特定體驗，略過對象鎖定目標規則。 適用於A/B、XT和Automated Personalization活動。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `activity_id` | 整數 | 是 | 要預覽的[!DNL Target]活動識別碼 |
| `experience_index` | 整數 | 無 | 0型體驗索引。 如果省略，會傳回所有體驗的URL |
| `url` | string | 否 | 預覽的頁面URL。 表單式活動的必要專案。 針對VEC活動，會覆寫編寫的位置（如果提供） |

**傳回：**&#x200B;活動資訊（名稱、型別、狀態）、每個體驗的預覽URL，以及體驗名稱和索引。

**範例提示：** 「產生活動12345動的預覽URL，以便我測試瀏覽器中的每一個體驗。」

## 回應Token工具 {#tools-response-tokens}

### list_target_response_tokens

列出您[!DNL Target]租使用者中的所有回應Token。

擷取所有已設定的回應Token，包括內建和自訂。

不需要引數。

**傳回：**&#x200B;回應權杖物件的JSON陣列，狀態為`name`、`type`和`enabled`。

**範例提示：**「列出所有回應Token」。

### create_target_response_token

建立新的自訂回應Token，以在[!DNL Target]個回應中收集其他資料。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `token_name` | string | 是 | 回應Token的名稱 |
| `token_type` | string | 是 | 語彙基元型別： `SCRIPT`、`ACTIVITY`、`MBOX`、`GEO`或`CRS` |

**傳回：**&#x200B;已建立的回應Token物件。

**範例提示：**「建立名為&#39;campaign_id&#39;的自訂回應Token，型別為ACTIVITY。」

## 修訂工具 {#tools-revisions}

### get_target_revisions

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

### get_target_entity_revisions

依照ID取得特定實體的所有修訂版本。

| 參數 | 類型 | 必要 | 說明 |
|---|---|---|---|
| `revision_resource_type` | string | 是 | 資源型別： `activity`、`offer`或`audience` |
| `entity_id` | 整數 | 是 | 實體的唯一識別碼 |

**傳回：**&#x200B;指定實體所有修訂的JSON陣列。

**範例提示：** 「顯示活動12345的所有變更。」

## 範本工具 {#tools-templates}

### list_target_templates

列出可用於建立活動和優惠方案的MCP資源和範本。

不需要引數。

**傳回：** JSON物件列出可用的範本和資源。

**範例提示：** 「哪些範本可用於建立活動？」

## 工具摘要 {#tools-summary}

| 類別 | 計數 | 工具 |
|---|---|---|
| 活動 | 17 | `list_target_activities`、`get_ab_activity`、`get_xt_activity`、`get_abt_activity`、`create_ab_activity`、`create_xt_activity`、`update_ab_activity`、`update_xt_activity`、`update_abt_activity`、`update_activity_schedule`、`update_activity_state`、`update_activity_name`、`update_activity_priority`、`add_activity_variant`、`update_traffic_split`、`update_variant_offer`、`remove_activity_variant` |
| 產品建議 | 5 | `list_target_offers`, `get_target_offer`, `create_target_offer`, `create_target_json_offer`, `update_target_offer` |
| 客群 | 2 | `list_target_audiences`, `create_target_audience` |
| mbox | 3 | `list_target_mboxes`，`get_target_mbox`，`list_target_mbox_profile_attributes` |
| 屬性 | 1 | `list_target_properties` |
| 報表 | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| 預覽 | 1 | `preview_activity` |
| 回應Token | 2 | `list_target_response_tokens`, `create_target_response_token` |
| 修訂 | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| 範本 | 1 | `list_target_templates` |
| **總計** | **39** | |

## 相關資源 {#tools-related}

* [使用MCP使用者端](target-mcp.md)
* [自行託管 [!DNL Adobe Target] MCP伺服器](target-mcp-self-hosted.md)
* [[!DNL Adobe Target] 管理員API參考](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
