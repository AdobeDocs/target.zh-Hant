---
description: 此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於重新導向選件問題的回答。
keywords: faq;常見問題集;analytics for target;a4T;重新導向;重新導向選件;adobe-mc-sdid;adobe_mc_ref
seo-description: 此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於重新導向選件問題的回答。
seo-title: 重新導向選件 - A4T 常見問題集
solution: Target
title: 重新導向選件 - A4T 常見問題集
topic: Standard
uuid: a45cef89-3003-4177-bf84-3d5a486b950d
translation-type: tm+mt
source-git-commit: 8423f5e8468c131ba9b0a77025968e11012f57f6

---


# 重新導向選件 - A4T 常見問題集{#redirect-offers-a-t-faq}

此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於重新導向選件問題的回答。

## Analytics for Target (A4T) 支援重新導向選件嗎? {#section_46B8B03ED4D542C6AD875F5F61176298}

是，前提是您的實作使用 [!DNL at.js]。不過，您的實作必須符合下列最低需求，才能在以 Analytics 作為報表來源的活動中使用[重新導向選件](../../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)。

## 在 A4T 中使用重新導向選件有何最低需求? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

您的實作必須符合下列最低需求:

* Experience Cloud 訪客 ID 服務: [!DNL visitorAPI.js] 版本 2.3.0 或更新版本。
* Adobe Analytics: [!DNL appMeasurement.js] 版本 2.1。
* Adobe Target： [!DNL at.js] 1.6.2版或更新版本。

   [!DNL mbox.js] 資料庫不支援使用 A4T 重新導向選件。您的實作必須使用 [!DNL at.js]。

含有重新導向選件的頁面和訪客重新導向的頁面上，皆必須包含這三個程式庫。

## A4T和Analytics有時會出現資料不一致的情況嗎？

預期會有一些資料不一致。如需詳細資訊，請參閱 [「Target與Analytics在使用A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)時，預期的資料差異」。

## 為何有時會統計原始頁面和重新導向頁面上的頁面檢視?  {#section_B8F6CC2190B84CF08D945E797C5AF07B}

有可能發生罕見的情況，導致在第一頁執行重新導向之前，Analytics 呼叫就先觸發。這會導致將原始頁面和重新導向頁面上的頁面檢視全部計入。此情況導致第一頁有額外的頁面檢視，使訪客從未真正「看過」這第一頁。

建議使用表單式撰寫器來建立重新導向活動，以加速頁面重新導向。原因在於頁面上執行程式碼的地方。另外，對於重新導向會傳回原始頁面的每個體驗，即使是預設體驗，也最好建立重新導向選件。發生誤算時，這可確保所有體驗皆誤算，因此，報表和分析對於測試仍然有效。

>[!NOTE]
>
>此競爭條件只會影響使用 at.js 1.6.3 版或更舊版本的客戶。請注意，Target 團隊只會維護兩個 at.js 版本: 最新版本和次新版本。請視需要升級 at.js，以確保您執行的是[支援的版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

如需此問題的詳細資訊，請參閱[已知問題](../../../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541)表中的「重新導向選件」欄:

## 如果我使用 mbox.js JavaScript 程式庫，可以在 A4T 中使用重新導向選件嗎? {#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

[!DNL mbox.js] 資料庫不支援使用 A4T 重新導向選件。您的實作必須使用 [!DNL at.js]。

## 可視化體驗撰寫器 (VEC) 和表單式體驗撰寫器皆有支援嗎? {#section_FDA26FE7909B48539DA770559E687677}

是的，只要您使用內建的重新導向選件，兩個撰寫器就皆支援。

如果使用您自己的自訂程式碼，務必填入與重新導向 URL 相關的兩個新參數 (`adobe_mc_sdid` 和 `adobe_mc_ref`，說明如下)。

## 有哪些新的查詢字串參數加入重新導向 URL 中? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

下列查詢字串參數與重新導向選件相關聯:

| 參數 | 說明 |
|--- |--- |
| `adobe_mc_sdid` | `adobe_mc_sdid` 參數會將補充資料 ID(SDID) 和 Experience Cloud 組織 ID 從預設頁面傳給新頁面，以便 A4T 將預設頁面的 Target 要求與新頁面的 Analytic 要求「縫合」起來。 |
| `adobe_mc_ref` | `adobe_mc_ref` 參數會將預設頁面的轉介 URL 傳給新頁面。與 AppMeasurement.js 2.1 版 (或更新版) 一起使用時，Analytics 會在新頁面上將此參數值當作轉介 URL。 |

在 VEC 和表單式體驗撰寫器中使用重新導向選件，且頁面上實作訪客 ID 服務時，這些參數會自動加入重新導向 URL 中。如果在 VEC 和表單式撰寫器中使用您自己的自訂重新導向程式碼，務必隨著自訂程式碼傳遞這些參數。

## 我的 Web 伺服器從 URL 中刪除這些參數，怎麼辦?  {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

您需要與 IT 團隊合作，將這些參數 (`adobe_mc_sdid` 和 `adobe_mc_ref`) 加入白名單。

## 如果不使用 A4T 來處理重新導向活動，且不想在 URL 中多出這些額外的參數，怎麼辦? {#section_9E608D75FF9349FE96C65FEDD7539F45}

如果不使用 A4T 來處理重新導向活動、已實作訪客 ID 服務，且不想讓這些參數自動加入 URL 中，您必須使用自行撰寫的重新導向。

然而，最佳作法是在 URL 中保留 `adobe_mc_ref` 參數，才能正確地向 [!DNL Analytics] 報表轉介者資訊。

## 在我的實作中，adobe_mc_ref 和 adobe_mc_sdid 參數為何經過兩次 URL 編碼? {#section_5EFE5F012B944C40865731EA18E7E79E}

如果您使用 A4T 和重新導向選件，Target 會將 `adobe_mc_ref` 和 `adobe_mc_sdid` 參數附加至 URL。這些值皆已完成 URL 編碼。一切通常皆沒問題，不過，某些客戶可能有負載平衡器或 WEB 伺服器，會嘗試將查詢字串參數再多編碼一次。

因為編碼兩次，當訪客 API 嘗試將 `adobe_mc_sdid` 值解碼時，就無法擷取 SDID 值並產生新的 SDID。這會導致傳給 Target 和 Analytics 的 SDID 值不正確，且您在 Analytics 報表中會看到重新導向分割不平均。

建議您洽詢 IT 團隊，確定 `adobe_mc_ref` 和 `adobe_mc_sdid`·已加入白名單，因此這些值絕不會轉換。

## 為何需要將轉介 URL傳給新頁面? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

假設訪客按一下 [!DNL `www.google.com`] 上的連結來前往您的首頁 (`www.mysite.com/index.html]`)，其中重新導向活動正在運作，接著便重新導向新頁面 ([!DNL `www.mysite.com/index2.html`])。

在以前，新頁面上的 [!DNL Analytics] 要求所報表的轉介 URL 會是 [!DNL `www.mysite.com/index.html`]，而非 [!DNL `www.google.com`]。這會導致 [!DNL Analytics] 中與轉介 URL 有關的報表不正確 (例如，「行銷通路」報表)。報表已喪失您是從 [!DNL `www.google.com`] 來到網站的事實。

若使用 [!DNL at.js] 0.96 版 (或更新版) 和 [!DNL AppMeasurement.js] 2.1 (或更新版) 時，新頁面上的 [!DNL Analytics] 要求會報告轉介 URL 為 [!DNL `www.google.com`]。

## 我可以使用自訂/HTML 重新導向選件嗎? {#section_E49F9A83A286488C8F1098A040203D7E}

否，對於以 [!DNL Analytics] 作為報表來源 (A4T) 的活動，您必須使用內建的重新導向選件。對 [!DNL Target] 而言，HTML 選件不透明: [!DNL Target] 無法知道一段特定的 HTML 包含可將重新導向具現化的 JavaScript。
