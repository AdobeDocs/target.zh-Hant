---
keywords: faq;常見問題集;analytics for target;a4T;重新導向;重新導向選件;adobe-mc-sdid;adobe_mc_ref
description: 尋找在將Analytics用於 [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] 活動時使用重新導向選件的相關問題解答。
title: 哪裡可以找到有關使用A4T重新導向選件的常見問題集？
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 62%

---

# 重新導向選件 - A4T 常見問題集

此主題包含使用[!DNL Adobe Analytics]做為[!DNL Adobe Target](A4T)報表來源時經常詢問關於使用重新導向選件問題的回答。

## Adobe Target適用的Analytics(A4T)支援重新導向選件嗎？ {#section_46B8B03ED4D542C6AD875F5F61176298}

是，如果您的實作使用[!DNL at.js]。 不過，您的實作必須符合下列最低需求，才能在以 Analytics 作為報表來源的活動中使用[重新導向選件](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)。

>[!NOTE]
>
>目前存在一個已知問題，該問題導致搭配 A4T 使用重新導向的部分客戶看見較高的散亂點擊率百分比。請參閱[已知問題和已解決的問題](/help/r-release-notes/known-issues-resolved-issues.md#redirect)。

## 在A4T中使用重新導向選件有何最低需求？ {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

您的實作必須符合下列最低需求:

* Experience Cloud 訪客 ID 服務: [!DNL visitorAPI.js] 版本 2.3.0 或更新版本。
* Adobe Analytics: [!DNL appMeasurement.js] 版本 2.1。
* Adobe Target: [!DNL at.js] 版本 1.6.2 或更新版本。

含有重新導向選件的頁面和訪客重新導向的頁面上，皆必須包含這三個程式庫。

## 為何 A4T 與 Analytics 之間有時會有資料差異?

可能會出現一些資料差異，這在預期之中。如需詳細資訊，請參閱[使用和不使用 A4T 時，Target 與 Analytics 之間的預期資料差異](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)。

## 為何有時會統計原始頁面和重新導向頁面上的頁面檢視? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

使用at.js 1.6.3版或更新版本時，計算兩個頁面上的頁面檢視次數並非問題。 此競爭條件只會影響使用舊版本的客戶。Target 團隊會維護兩個版本的 at.js: 最新版本和次新版本。請視需要升級 at.js，以確保您執行的是[支援的版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

如果您使用不支援的較舊 at.js 版本，可能會發生競爭條件，而可能導致 Analytics 呼叫在重新導向於第一個頁面上執行前引發。此情況可能會導致將原始頁面和重新導向頁面上的頁面檢視全部計入。 此情況導致第一頁有額外的頁面檢視，使訪客從未真正「看過」這第一頁。

建議使用表單式撰寫器來建立重新導向活動，因為頁面上執行程式碼的位置，所以可提高頁面重新導向的速度。 另外，對於重新導向會傳回原始頁面的每個體驗，即使是預設體驗，也最好建立重新導向選件。為每個體驗建立重新導向選件，可確保如果發生誤計，會發生在所有體驗。 報表和分析對測試仍有效。

您可能想要將重新導向選件用於活動中的所有體驗 (包括預設 (控制) 體驗) 的一個原因是，想要對所有體驗設定相同的條件。例如，如果預設體驗沒有重新導向選件，但其他體驗有重新導向選件，沒有重新導向選件之體驗的速度會有沿用的優勢。建議僅將重新導向選件用於臨時案例，例如測試。不建議將重新導向選件用於永久案例，例如個人化。決定「獲勝者」後，您應移除重新導向以改善頁面載入效能。

如需此問題的詳細資訊，請參閱[已知問題](/help/r-release-notes/known-issues-resolved-issues.md#redirect)中的「重新導向選件」資訊。

## 可視化體驗撰寫器 (VEC) 和表單式體驗撰寫器皆有支援嗎? {#section_FDA26FE7909B48539DA770559E687677}

是的，只要您使用內建的重新導向選件，兩個撰寫器就皆支援。

如果使用您自己的自訂程式碼，務必填入與重新導向 URL 相關的兩個新參數 (`adobe_mc_sdid` 和 `adobe_mc_ref`，說明如下)。

## 有哪些新的查詢字串參數加入重新導向 URL 中? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

下列查詢字串參數與重新導向選件相關聯:

| 參數 | 說明 |
|--- |--- |
| `adobe_mc_sdid` | `adobe_mc_sdid`參數會將補充資料ID(SDID)和Experience Cloud組織ID從預設頁面傳給新頁面。 這些ID可讓A4T將預設頁面的Target要求與新頁面的Analytic要求「縫合」起來。 |
| `adobe_mc_ref` | `adobe_mc_ref` 參數會將預設頁面的轉介 URL 傳給新頁面。與AppMeasurement.js 2.1版（或更新版本）搭配使用時，Analytics會在新頁面上將此參數值當作轉介URL。 |

在 VEC 和表單式體驗撰寫器中使用重新導向選件，且頁面上實作訪客 ID 服務時，這些參數會自動加入重新導向 URL 中。如果在 VEC 和表單式撰寫器中使用您自己的自訂重新導向程式碼，務必隨著自訂程式碼傳遞這些參數。

## 我的 Web 伺服器從 URL 中刪除這些參數，怎麼辦? {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

請與IT團隊合作，將這些參數（`adobe_mc_sdid`和`adobe_mc_ref`）列入允許清單。

## 如果不使用 A4T 來處理重新導向活動，且不想在 URL 中多出這些額外的參數，怎麼辦? {#section_9E608D75FF9349FE96C65FEDD7539F45}

如果下列情況，請使用自訂編碼重新導向：

* 您沒有將A4T用於重新導向活動
* 您已實作訪客ID服務
* 您不希望這些參數自動新增至URL

然而，最佳作法是在 URL 中保留 `adobe_mc_ref` 參數，才能正確地向 [!DNL Analytics] 報表轉介者資訊。

## 在我的實作中，adobe_mc_ref 和 adobe_mc_sdid 參數為何經過兩次 URL 編碼? {#section_5EFE5F012B944C40865731EA18E7E79E}

如果您使用 A4T 和重新導向選件，Target 會將 `adobe_mc_ref` 和 `adobe_mc_sdid` 參數附加至 URL。這些值皆已完成 URL 編碼。一切通常皆沒問題，不過，某些客戶可能有負載平衡器或 WEB 伺服器，會嘗試將查詢字串參數再多編碼一次。

因為編碼兩次，當訪客 API 嘗試將 `adobe_mc_sdid` 值解碼時，就無法擷取 SDID 值並產生新的 SDID。此程式會導致傳送至Target和Analytics的SDID值不正確，且您會在Analytics報表中看到重新導向的分割不均。

Adobe建議您洽詢IT團隊，確保`adobe_mc_ref`和`adobe_mc_sdid`皆已允許列出，因此這些值絕不會轉換。

## 為何必須將轉介URL傳遞至新頁面？ {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

假設訪客點按[!DNL `www.google.com`]上的連結來前往您的首頁(`www.mysite.com/index.html`)，其中重新導向活動正在運作，然後重新導向至新頁面(`www.mysite.com/index2.html`)。

在以前，新頁面上的 [!DNL Analytics] 要求所報表的轉介 URL 會是 [!DNL `www.mysite.com/index.html`]，而非 [!DNL `www.google.com`]。這會導致 [!DNL Analytics] 中與轉介 URL 有關的報表不正確 (例如，「行銷通路」報表)。報表已喪失您是從 [!DNL `www.google.com`] 來到網站的事實。

若使用[!DNL at.js]版本0.9.6（或更新版本）和[!DNL AppMeasurement.js] 2.1（或更新版本），新頁面上的[!DNL Analytics]請求會回報轉介URL [!DNL `www.google.com`]。

## 我可以使用自訂/HTML 重新導向選件嗎? {#section_E49F9A83A286488C8F1098A040203D7E}

否，對於以 [!DNL Analytics] 作為報表來源 (A4T) 的活動，您必須使用內建的重新導向選件。對 [!DNL Target] 而言，HTML 選件不透明: [!DNL Target] 無法知道一段特定的 HTML 包含可將重新導向具現化的 JavaScript。

## ![Adobe Experience Platform Web SDK徽](/help/assets/platform.png) 章是否支 [!DNL Adobe Experience Platform Web SDK] 援A4T的重新導向選件？ {#platform}

下列常見問題集提供關於搭配[!DNL Platform Web SDK]使用A4T和重新導向選件的詳細資訊。

### Analytics for Target (A4T) 支援重新導向選件嗎?

是的，透過Platform Web SDK的A4T支援[重新導向選件](/help/c-experiences/c-manage-content/offer-redirect.md)。

### 是否支援[!UICONTROL 可視化體驗撰寫器](VEC)和[!UICONTROL 表單式體驗撰寫器]?

是，如果您使用內建的重新導向選件，則支援[[!UICONTROL 可視化體驗撰寫器]](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)和[[!UICONTROL 表單式體驗撰寫器]](/help/c-experiences/form-experience-composer.md)。

### 我可以搭配[!DNL Platform Web SDK]使用自訂/HTML重新導向選件嗎？

否，對於使用A4T的活動，您必須使用內建的重新導向選件。 從[!DNL Target]的角度來看，HTML選件不透明。[!DNL Target]無法知道一段特定的HTML包含可具現化重新導向的JavaScript。
