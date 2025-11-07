---
keywords: faq;常見問題集;analytics for target;a4T;重新導向;重新導向產品建議;adobe-mc-sdid;adobe_mc_ref
description: 尋找在使用Analytics for [!DNL Target] (A4T)時使用重新導向選件的相關問題解答。 A4T可讓您對 [!DNL Target] 個活動使用Analytics報告。
title: 我可以在哪裡找到有關使用A4T重新導向選件的常見問題集？
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: e45ac15a60c83e35b8b2b2ba29a42727faf746df
workflow-type: tm+mt
source-wordcount: '1431'
ht-degree: 50%

---

# 重新導向產品建議 - A4T 常見問題集

此主題包含使用[!DNL Adobe Analytics]做為[!DNL Adobe Target] (A4T)的報表來源時，經常詢問關於重新導向選件問題的回答。

## Analytics for Adobe Target (A4T)支援重新導向選件嗎？ {#section_46B8B03ED4D542C6AD875F5F61176298}

+++回答
是，如果您的實作使用[!DNL at.js]。 不過，您的實作必須符合下列最低需求，才能在以 Analytics 作為報表來源的活動中使用[重新導向產品建議](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)。

+++

## ![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png) [!DNL Adobe Experience Platform Web SDK]是否支援A4T的重新導向選件？ {#platform}

+++回答
下列常見問題集提供搭配[!DNL Platform Web SDK]使用A4T和重新導向選件的詳細資訊。

+++

### Analytics for Target (A4T) 支援重新導向產品建議嗎?

+++回答
是，透過Platform Web SDK的A4T支援[重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

+++

### 是否支援[!UICONTROL Visual Experience Composer] (VEC)和[!UICONTROL Form-Based Experience Composer]？

+++回答
是的，如果您使用內建的重新導向選件，則支援[[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)和[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)。

+++

## 搭配A4T使用重新導向選件有何最低需求？ {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

+++回答
您的實作必須符合下列最低需求:

* Experience Cloud 訪客 ID 服務: [!DNL visitorAPI.js] 版本 2.3.0 或更新版本。
* Adobe Analytics: [!DNL appMeasurement.js] 版本 2.1。
* Adobe Target: [!DNL at.js] 版本 1.6.2 或更新版本。

含有重新導向產品建議的頁面和訪客重新導向的頁面上，皆必須包含這三個程式庫。

+++

## 為何 A4T 與 Analytics 之間有時會有資料差異?

+++回答
可能會出現一些資料差異，這在預期之中。如需詳細資訊，請參閱[使用和不使用 A4T 時，Target 與 Analytics 之間的預期資料差異](/help/main/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)。

+++

## 在 A4T 活動中使用重新導向產品建議時，如何將流量分佈的差異減至最低？ {#discrepancies}

+++回答
在設定[!UICONTROL Analytics for Target] (A4T)的活動中使用重新導向選件時，有限數量的客戶報告流量分佈的差異程度較高。

考慮以下事項：

* [!DNL Target]和[!DNL Analytics]呼叫順序不正確可能會導致較高的變異程度。

  [!DNL Target]呼叫必須在來源頁面（其中發生重新導向）和目的地頁面（其中重新導向結束）上的[!DNL Analytics]呼叫之前。

* 請務必在A4T重新導向活動中使用重新導向選件。
* 如果來源頁面上有多個[!DNL Target]位置要求（發生重新導向），[!DNL Adobe]建議您對第一個[!DNL Target]位置要求執行重新導向活動。

  在前[!DNL Target]個位置要求上執行重新導向活動，可減少其他[!DNL Target]個位置要求上發生任何活動資格並被計入報表中的機會。 被重新導向的訪客不需要計入其他活動的報表中，因為他們看不到體驗。

+++

## 為何有時會統計原始頁面和重新導向頁面上的頁面檢視? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

+++回答
使用at.js 1.6.3版或更新版本時，計算兩個頁面上的頁面檢視次數並不是問題。 此競爭條件只會影響使用舊版本的客戶。Target 團隊會維護兩個版本的 at.js: 最新版本和次新版本。請視需要升級 at.js，以確保您執行的是[支援的版本](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank}。

如果您使用不支援的較舊 at.js 版本，可能會發生競爭條件，而可能導致 Analytics 呼叫在重新導向於第一個頁面上執行前引發。此情況可能會導致計算原始頁面和重新導向頁面上的頁面檢視次數。 此情況導致第一頁有額外的頁面檢視，使訪客從未真正「看過」這第一頁。

由於程式碼在頁面上的執行位置，建議使用表單式撰寫器建立重新導向活動，以提高頁面重新導向的速度。 另外，對於重新導向會傳回原始頁面的每個體驗，即使是預設體驗，也最好建立重新導向產品建議。為每個體驗建立重新導向選件，可確保在發生錯誤計數時，它會在所有體驗中發生。 報告和分析對測試仍然有效。

您可能想要將重新導向產品建議用於活動中的所有體驗 (包括預設 (控制) 體驗) 的一個原因是，想要對所有體驗設定相同的條件。例如，如果預設體驗沒有重新導向產品建議，但其他體驗有重新導向產品建議，沒有重新導向產品建議之體驗的速度會有沿用的優勢。建議僅將重新導向產品建議用於臨時案例，例如測試。不建議將重新導向產品建議用於永久案例，例如個人化。決定「獲勝者」後，您應移除重新導向以改善頁面載入效能。

+++

## 可視化體驗撰寫器 (VEC) 和表單式體驗撰寫器皆有支援嗎? {#section_FDA26FE7909B48539DA770559E687677}

+++回答
是的，只要您使用內建的重新導向產品建議，兩個撰寫器就皆支援。

如果使用您自己的自訂程式碼，務必填入與重新導向 URL 相關的兩個新參數 (`adobe_mc_sdid` 和 `adobe_mc_ref`，說明如下)。

+++

## 有哪些新的查詢字串參數加入重新導向 URL 中? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

+++回答
下列查詢字串參數與重新導向產品建議相關聯:

| 參數 | 說明 |
|--- |--- |
| `adobe_mc_sdid` | `adobe_mc_sdid`引數會將補充資料ID (SDID)和Experience Cloud組織ID從預設頁面傳給新頁面。 這些ID允許A4T將預設頁面上的Target要求與新頁面上的Analytic要求「拼接」起來。<br>在URL中傳遞sdid （針對混合式應用程式或從一個應用程式傳遞至網站或從一個網站傳遞至另一個網站）的預期格式為`ex. adobe_mc_sdid=SDID=123\|MCORGID=123456789@AdobeOrg\|TS=1498569322` |
| `adobe_mc_ref` | `adobe_mc_ref` 參數會將預設頁面的轉介 URL 傳給新頁面。與AppMeasurement.js 2.1版（或更新版）一起使用時，Analytics會在新頁面上將此引數值當作轉介URL。 |

在 VEC 和表單式體驗撰寫器中使用重新導向產品建議，且頁面上實作訪客 ID 服務時，這些參數會自動加入重新導向 URL 中。如果在 VEC 和表單式撰寫器中使用您自己的自訂重新導向程式碼，務必隨著自訂程式碼傳遞這些參數。

+++

## 我的 Web 伺服器從 URL 中刪除這些參數，怎麼辦? {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

+++回答
請與您的IT團隊合作，將這些引數（ `adobe_mc_sdid`和`adobe_mc_ref`）加入允許清單。

+++

## 如果不使用 A4T 來處理重新導向活動，且不想在 URL 中多出這些額外的參數，怎麼辦? {#section_9E608D75FF9349FE96C65FEDD7539F45}

+++回答
使用自訂編碼重新導向，如果：

* 您沒有使用A4T來處理重新導向活動
* 您已實作訪客ID服務
* 您不希望這些引數自動新增至URL

然而，最佳作法是在 URL 中保留 `adobe_mc_ref` 參數，才能正確地向 [!DNL Analytics] 報表轉介者資訊。

+++

## 在我的實作中，adobe_mc_ref和adobe_mc_sdid引數為何經過兩次URL編碼？ {#section_5EFE5F012B944C40865731EA18E7E79E}

+++回答
如果您使用 A4T 和重新導向產品建議，Target 會將 `adobe_mc_ref` 和 `adobe_mc_sdid` 參數附加至 URL。這些值皆已完成 URL 編碼。一切通常皆沒問題，不過，某些客戶可能有負載平衡器或 WEB 伺服器，會嘗試將查詢字串參數再多編碼一次。

因為編碼兩次，當訪客 API 嘗試將 `adobe_mc_sdid` 值解碼時，就無法擷取 SDID 值並產生新的 SDID。此程式會導致傳給Target和Analytics的SDID值不正確，且您在Analytics報表中看到重新導向分割不平均。

Adobe建議您洽詢IT團隊，確定`adobe_mc_ref`和`adobe_mc_sdid`已加入允許清單，因此這些值絕不會轉換。

+++

## 為何必須將轉介URL傳給新頁面？ {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

+++回答
假設訪客按一下[!DNL `www.google.com`]上的連結來前往您的首頁(`www.mysite.com/index.html`)，其中重新導向活動正在運作，接著便重新導向新頁面(`www.mysite.com/index2.html`)。

先前，新頁面上的[!DNL Analytics]要求會報告轉介URL為[!DNL `www.mysite.com/index.html`]而非[!DNL `www.google.com`]。 這會導致 [!DNL Analytics] 中與轉介 URL 有關的報表不正確 (例如，「行銷通路」報表)。報表已喪失您是從[!DNL `www.google.com`]前往網站的事實。

若使用[!DNL at.js]版本0.9.6 （或更新版本）和[!DNL AppMeasurement.js] 2.1 （或更新版本），新頁面上的[!DNL Analytics]要求會報告轉介URL為[!DNL `www.google.com`]。

+++

## 我可以使用自訂/HTML 重新導向產品建議嗎? {#section_E49F9A83A286488C8F1098A040203D7E}

+++回答
否，對於以 [!DNL Analytics] 作為報表來源 (A4T) 的活動，您必須使用內建的重新導向產品建議。對 [!DNL Target] 而言，HTML 產品建議不透明: [!DNL Target] 無法知道一段特定的 HTML 包含可將重新導向具現化的 JavaScript。

+++

### 我可以搭配[!DNL Platform Web SDK]使用自訂/HTML重新導向選件嗎？

+++回答
否，對於使用A4T的活動，您必須使用內建的重新導向選件。 從[!DNL Target]的觀點來看，HTML選件是不透明的。 [!DNL Target]無法得知某段HTML包含可將重新導向具現化的JavaScript。

+++
