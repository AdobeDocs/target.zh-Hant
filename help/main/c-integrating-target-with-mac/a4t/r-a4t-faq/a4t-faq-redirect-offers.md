---
keywords: faq;常見問題集;analytics for target;a4T;重新導向;重新導向選件;adobe-mc-sdid;adobe_mc_ref
description: 在使用Analytics時查找有關使用重定向優惠的問題的答案 [!DNL Target] (A4T)。 A4T允許您使用Analytics報告 [!DNL Target] 活動。
title: 在何處可以找到有關A4T重定向服務的常見問題？
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1475'
ht-degree: 55%

---

# 重新導向選件 - A4T 常見問題集

本主題包含使用重定向優惠時經常詢問的問題的答案 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。

## Adobe Target分析(A4T)是否支援重定向服務？ {#section_46B8B03ED4D542C6AD875F5F61176298}

是，如果實施使用 [!DNL at.js]。 不過，您的實作必須符合下列最低需求，才能在以 Analytics 作為報表來源的活動中使用[重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)。

>[!NOTE]
>
>目前存在一個已知問題，該問題導致搭配 A4T 使用重新導向的部分客戶看見較高的散亂點擊率百分比。請參閱[已知問題和已解決的問題](/help/main/r-release-notes/known-issues-resolved-issues.md#redirect)。

## A4T使用重定向服務的最低要求是什麼？ {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

您的實作必須符合下列最低需求:

* Experience Cloud 訪客 ID 服務: [!DNL visitorAPI.js] 版本 2.3.0 或更新版本。
* Adobe Analytics: [!DNL appMeasurement.js] 版本 2.1。
* Adobe Target: [!DNL at.js] 版本 1.6.2 或更新版本。

含有重新導向選件的頁面和訪客重新導向的頁面上，皆必須包含這三個程式庫。

## 為何 A4T 與 Analytics 之間有時會有資料差異?

可能會出現一些資料差異，這在預期之中。如需詳細資訊，請參閱[使用和不使用 A4T 時，Target 與 Analytics 之間的預期資料差異](/help/main/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)。

## 在 A4T 活動中使用重新導向優惠方案時，如何將流量分佈的差異減至最低？ {#discrepancies}

在配置了重定向服務的活動中使用重定向服務時，有限數量的客戶報告流量分配的差異程度更高 [!UICONTROL 目標分析] (A4T)。

考慮以下事項:

* 順序不正確 [!DNL Target] 和 [!DNL Analytics] 呼叫可能導致差異程度較高。

   的 [!DNL Target] 調用必須位於 [!DNL Analytics] 在源頁面（發生重定向的位置）和目標頁面（重定向結束的位置）上調用。

* 確保在A4T重定向活動中使用重定向服務。
* 如果有多個 [!DNL Target] 源頁面上的位置請求（發生重定向的位置）, [!DNL Adobe] 建議您在第一個 [!DNL Target] 位置請求。

   在第一個 [!DNL Target] 位置請求降低了在其他位置發生任何活動資格的可能性 [!DNL Target] 位置請求和在報告中計數。 被重定向的訪問者不必計入其他活動的報告，因為他們看不到這些經歷。

## 為何有時會統計原始頁面和重新導向頁面上的頁面檢視? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

使用at.js 1.6.3或更高版本時，計算兩個頁面上的頁面視圖不是問題。 此競爭條件只會影響使用舊版本的客戶。Target 團隊會維護兩個版本的 at.js: 最新版本和次新版本。請視需要升級 at.js，以確保您執行的是[支援的版本](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)。

如果您使用不支援的較舊 at.js 版本，可能會發生競爭條件，而可能導致 Analytics 呼叫在重新導向於第一個頁面上執行前引發。這種情況可能導致對原始頁面和重定向頁面上的頁面視圖進行計數。 此情況導致第一頁有額外的頁面檢視，使訪客從未真正「看過」這第一頁。

建議使用基於表單的作曲家構建重定向活動以提高頁面重定向的速度，因為代碼在頁面上的執行位置。 另外，對於重新導向會傳回原始頁面的每個體驗，即使是預設體驗，也最好建立重新導向選件。為每種體驗建立重定向服務可確保在發生錯誤計算時，在所有體驗中都會發生錯誤計算。 報告和分析仍對test有效。

您可能想要將重新導向選件用於活動中的所有體驗 (包括預設 (控制) 體驗) 的一個原因是，想要對所有體驗設定相同的條件。例如，如果預設體驗沒有重新導向選件，但其他體驗有重新導向選件，沒有重新導向選件之體驗的速度會有沿用的優勢。建議僅將重新導向選件用於臨時案例，例如測試。不建議將重新導向選件用於永久案例，例如個人化。決定「獲勝者」後，您應移除重新導向以改善頁面載入效能。

如需此問題的詳細資訊，請參閱[已知問題](/help/main/r-release-notes/known-issues-resolved-issues.md#redirect)中的「重新導向選件」資訊。

## 可視化體驗撰寫器 (VEC) 和表單式體驗撰寫器皆有支援嗎? {#section_FDA26FE7909B48539DA770559E687677}

是的，只要您使用內建的重新導向選件，兩個撰寫器就皆支援。

如果使用您自己的自訂程式碼，務必填入與重新導向 URL 相關的兩個新參數 (`adobe_mc_sdid` 和 `adobe_mc_ref`，說明如下)。

## 有哪些新的查詢字串參數加入重新導向 URL 中? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

下列查詢字串參數與重新導向選件相關聯:

| 參數 | 說明 |
|--- |--- |
| `adobe_mc_sdid` | 的 `adobe_mc_sdid` 參數將補充資料ID(SDID)和Experience Cloud組織ID從預設頁傳遞到新頁。 這些ID允許A4T將預設頁上的目標請求與新頁上的分析請求「拼接」在一起。 |
| `adobe_mc_ref` | `adobe_mc_ref` 參數會將預設頁面的轉介 URL 傳給新頁面。當與AppMeasurement.js 2.1版（或更高版本）一起使用時，Analytics將此參數值用作新頁面上的引用URL。 |

在 VEC 和表單式體驗撰寫器中使用重新導向選件，且頁面上實作訪客 ID 服務時，這些參數會自動加入重新導向 URL 中。如果在 VEC 和表單式撰寫器中使用您自己的自訂重新導向程式碼，務必隨著自訂程式碼傳遞這些參數。

## 我的 Web 伺服器從 URL 中刪除這些參數，怎麼辦? {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

與您的IT團隊合作，以獲得這些參數( `adobe_mc_sdid` 和 `adobe_mc_ref`)允許列出。

## 如果不使用 A4T 來處理重新導向活動，且不想在 URL 中多出這些額外的參數，怎麼辦? {#section_9E608D75FF9349FE96C65FEDD7539F45}

如果：

* 您沒有將A4T用於重定向活動
* 您已實施訪問者ID服務
* 您不希望這些參數自動添加到URL

然而，最佳作法是在 URL 中保留 `adobe_mc_ref` 參數，才能正確地向 [!DNL Analytics] 報表轉介者資訊。

## 在我的實作中，adobe_mc_ref 和 adobe_mc_sdid 參數為何經過兩次 URL 編碼? {#section_5EFE5F012B944C40865731EA18E7E79E}

如果您使用 A4T 和重新導向選件，Target 會將 `adobe_mc_ref` 和 `adobe_mc_sdid` 參數附加至 URL。這些值皆已完成 URL 編碼。一切通常皆沒問題，不過，某些客戶可能有負載平衡器或 WEB 伺服器，會嘗試將查詢字串參數再多編碼一次。

因為編碼兩次，當訪客 API 嘗試將 `adobe_mc_sdid` 值解碼時，就無法擷取 SDID 值並產生新的 SDID。此過程導致將錯誤的SDID值發送到目標和分析，並且您在分析報告中看到重定向的剝離不均。

Adobe建議您與IT團隊進行交談，以確保 `adobe_mc_ref` 和 `adobe_mc_sdid` 清單，以便這些值不會以任何方式轉換。

## 為什麼必須將引用URL傳遞到新頁面？ {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

假設訪問者點擊連結 [!DNL `www.google.com`] 到首頁(`www.mysite.com/index.html`)，其上存在重定向活動，然後被重定向到新頁面(`www.mysite.com/index2.html`)。

在以前，新頁面上的 [!DNL Analytics] 要求所報表的轉介 URL 會是 [!DNL `www.mysite.com/index.html`]，而非 [!DNL `www.google.com`]。這會導致 [!DNL Analytics] 中與轉介 URL 有關的報表不正確 (例如，「行銷通路」報表)。報表已喪失您是從 [!DNL `www.google.com`] 來到網站的事實。

與 [!DNL at.js] 版本0.9.6（或更高版本）和 [!DNL AppMeasurement.js] 2.1（或更高版本）, [!DNL Analytics] 新頁面上的請求報告的引用URL [!DNL `www.google.com`]。

## 我可以使用自訂/HTML 重新導向選件嗎? {#section_E49F9A83A286488C8F1098A040203D7E}

否，對於以 [!DNL Analytics] 作為報表來源 (A4T) 的活動，您必須使用內建的重新導向選件。對 [!DNL Target] 而言，HTML 選件不透明: [!DNL Target] 無法知道一段特定的 HTML 包含可將重新導向具現化的 JavaScript。

## ![Adobe Experience PlatformWeb SDK徽章](/help/main/assets/platform.png) 是否 [!DNL Adobe Experience Platform Web SDK] 支援A4T重定向服務？ {#platform}

以下常見問題提供了有關使用A4T和重定向服務的詳細資訊 [!DNL Platform Web SDK]。

### Analytics for Target (A4T) 支援重新導向選件嗎?

是，通過平台Web SDK支援的A4T [重定向服務](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

### 是 [!UICONTROL 視覺體驗作曲家] (VEC)和 [!UICONTROL 基於表單的體驗作曲家] 支援？

是的， [[!UICONTROL 視覺體驗作曲家]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)和 [[!UICONTROL 基於表單的體驗作曲家]](/help/main/c-experiences/form-experience-composer.md) 如果您使用內置重定向服務，則支援。

### 是否可以使用自定義/HTML重定向服務 [!DNL Platform Web SDK]?

不，您必須使用內置重定向服務來處理使用A4T的活動。 從 [!DNL Target] 從透視角看，HTML的報價是不透明的。 [!DNL Target] 無法知道某個特定HTML包含實例化重定向的JavaScript。
