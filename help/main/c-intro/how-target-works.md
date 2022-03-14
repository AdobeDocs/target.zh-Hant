---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;搜尋引擎最佳化;搜尋引擎最佳化;seo;邊緣叢集,中央叢集;at.js;mbox.js;
description: 瞭解如何Adobe [!DNL Target] 作品，包括 [!DNL Target] JavaScript庫(at.js和Experience PlatformWeb SDK)、Adobe資料中心和SEO測試。
title: ' [!DNL Target] 如何運作？'
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2536'
ht-degree: 99%

---

# Adobe [!DNL Target] 如何運作

了解 [!DNL Adobe Target]的運作，包括有關 [!DNL Adobe Experience Platform Web SDK] 和 JavaScript 資料庫 (at.js 和 mbox.js) 的資訊。此文章也介紹您可以使用 [!DNL Target] 建立的多種活動類型。您還可以了解有關 [!DNL Target] 邊緣網路、Search Engine Optimization (SEO)，以及 [!DNL Target] 如何偵察機器人。

## [!DNL Target] Platform Web SDK 和 JavaScript 程式庫 {#libraries}

[!DNL Target] 使用 [!DNL Experience Platform Web SDK] 或 JavaScript 資料庫與網站整合：

* **Adobe Experience Platform Web SDK：**[Experience Platform Web SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) 是新的用戶端 JavaScript 資料庫。Experience Platform Web SDK 讓 [!DNL Adobe Experience Cloud] 的客戶與 [!DNL Experience Cloud] 內的多種服務互動 (包括透過 [!DNL Experience Platform] Edge Network 的[!DNL Target]。Adobe 建議所有的新 [!DNL Target] 客戶實施 [!DNL Experience Platform Web SDK]。
* **at.js：** at.js 程式庫是 [!DNL Target] 的實施程式庫。at.js 程式庫改善 Web 實施的頁面載入時間，並且為單頁應用程式提供更好的實施選項。at.js 經常更新以包含新功能。Adobe 建議所有使用 at.js 的客戶更新其實施至[ at.js 最新版本](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。
* **mbox.js：** mbox.js 程式庫是 [!DNL Target] 的舊版實施程式庫。自 2021 年 3 月 31 日起不再支援 mbox.js 程式庫。

在您網站的每個頁面上參閱 [!DNL Experience Platform Web SDK] 或 at.js。例如，您可以將其中一個程式庫新增至全域標題。或者，考慮使用 Adobe Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 內的 [標記來實施 [!DNL Target]。

下列資源包含協助您實施 Experience Platform Web SDK或 at.js 的詳細資訊：

* [Adobe Experience Platform Web SDK 擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=en)
* [使用 Adobe Experience Platform 實作 [!DNL Target] ](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

每次訪客要求已針對 [!DNL Target] 最佳化的頁面時，都會傳送請求至目標定位系統。該請求有助於判斷要為該訪客提供哪些內容。此過程會即時進行。每次載入頁面時，系統會提出內容請求並履行。內容是由市場行銷人員控制之活動和體驗的規則所管理，且目標鎖定在網站的個別訪客。所提供的內容是每位網站訪客最有可能回應、互動或最終購買的內容。個人化內容可協助將回應率、贏取率和收入最大化。

在 [!DNL Target] 中，頁面上的每一個元素都屬於整個頁面的單一體驗。每一個體驗皆可包含頁面上的多個元素。

對訪客顯示的內容取決於您建立的活動類型。

### [!UICONTROL A/B 測試]

基本 A/B 測試中顯示的內容是從您指派給活動的體驗中隨機選擇。您可以為每個體驗指派流量分配百分比。由於這種隨機流量分割，在百分比分割之前可能需要大量的初始流量。例如，如果您建立兩個體驗，則會隨機挑選開始的體驗。如果流量小，該百分比的訪客可能全偏到其中一個體驗。隨著流量增加，百分比會相等。

您可以指定每個體驗的百分比目標。在這種情況下會產生亂數，使用此數字選擇顯示的體驗。結果百分比可能和指定目標不完全相同，但流量更多表示體驗分割就會更接近定位目標。

1. 客戶向伺服器請求頁面，並在瀏覽器中顯示該頁面。
1. 在客戶的瀏覽器中設定第一方Cookie，以儲存客戶行為。
1. 頁面呼叫目標系統。
1. 根據活動的規則來顯示內容。

如需詳細資訊，請參閱[建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

### [!UICONTROL 自動分配]

[!UICONTROL 自動分配]可識別兩個或更多體驗中的成功者。 [!UICONTROL 自動分配]會自動將更多流量重新分配給成功體驗，這有助於在測試持續執行和學習的同時提高轉換率。

如需詳細資訊，請參閱「[[!UICONTROL 自動分配]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)」。

### [!UICONTROL 自動鎖定目標] (AT)

自動鎖定目標使用進階機器學習，從多個高效能行銷人員定義的體驗中進行選擇。自動鎖定目標為每位訪客提供最自訂的體驗。體驗傳送是根據個別客戶設定檔和具有類似設定檔的先前訪客的行為。使用自動鎖定目標來個人化內容並推動轉換。

如需詳細資訊，請參閱 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

### [!UICONTROL Automated Personalization] (AP)

Automated Personalization (AP) 結合選件或訊息，並使用進階的機器學習來比對每個訪客的不同選件變化。體驗提供是以個別客戶個人檔案為基礎，以個人化內容並提升提升度。

如需詳細資訊，請參閱 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。

### [!UICONTROL 體驗鎖定] (XT)

體驗鎖定目標 (XT) 會根據一組市場行銷人員定義的規則和條件為特定對象提供內容。

體驗鎖定目標 (包括地理定位) 對於定義將特定體驗或內容鎖定在特定對象的規則大有幫助。您可以在傳送不同內容變數至不同對象的活動中定義數個規則。在訪客檢視您的網站時，體驗鎖定目標 (XT) 會評估他們，以決定他們是否符合您設定的條件。如果他們符合條件，他們會進入活動，並且針對符合資格對象設計的體驗會顯示。您可以為單一活動內的多個對象建立體驗。

如需詳細資訊，請參閱「[體驗鎖定](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)」。

### [!UICONTROL 多變數測試] (MVT)

多變數測試 (MVT) 會比較頁面上元素中選件的組合，以決定哪一種組合對特定讀者最佳。MVT 可協助識別最影響活動成功的元素。

如需詳細資訊，請參閱[多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)。

### [!UICONTROL Recommendations]

Recommendations 活動可依據先前的使用者行為或其他演算法，自動顯示可能使客戶感興趣的產品或內容。Recommendations 可協助引導客戶至他們可能不知道的相關項目。

如需詳細資訊，請參閱 [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)。

## 邊緣網路 {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

「Edge」是按地理區域分配服務的架構，可確保請求內容的訪客獲得最佳回應時間，無論他們身在何處。

為改善回應時間，[!DNL Target] Edges 僅代管活動邏輯、快取設定檔和選件資訊。

活動和內容資料庫、[!DNL Analytics] 資料、API 和市場行銷人員使用者介面都存放在 Adobe 的中央叢集中。然後，更新會傳送至 [!DNL Target] Edges。中央叢集和邊緣叢集會自動同步，以持續更新快取的活動資料。所有 1:1 模型也會儲存在每個邊緣，因此這些更複雜的請求也可以在邊緣上處理。

每個邊緣叢集都具備回應訪客內容請求及追蹤該請求之分析資料所需的所有資訊。訪客請求會路由至最接近的邊緣叢集。

如需詳細資訊，請參閱 [Adobe Target 安全性總覽](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)白皮書。

[!DNL Target] 解決方案在世界各地由 Adobe 擁有和 Adobe 租用的資料業集中進行控管。

中央叢集位置同時包含資料收集中心和資料處理中心。邊緣叢集位置僅包含資料收集中心。每個報告套裝會被指派至特定的資料處理中心。

客戶網站活動資料是由七個邊緣叢集中最靠近的叢集收集。此資料會導向客戶預先確定的中央叢集目的地 (三個位置之一：奧勒岡、都柏林、新加坡)，以進行處理。訪客資料會儲存在離網站訪客最近的邊緣叢集上。邊緣叢集位置包括中央叢集位置以及維吉尼亞、孟買、雪梨和東京。

請求不會回應單一位置的所有定位請求，而是由離訪客最近的邊緣叢集處理。此過程有助於減輕網路／網際網路旅行時間的影響。

![顯示不同類型的 Target 伺服器的地圖](/help/main/c-intro/assets/target-servers.png)

[!DNL Target]中央叢集，由 Amazon Web Services (AWS) 代管，包括：

* 美國奧勒岡
* 愛爾蘭都柏林
* 新加坡共和國

[!DNL Target]邊緣叢集，由 Amazon Web Services (AWS) 代管，包括：

* 印度孟買
* 日本東京
* 美國維吉尼亞
* 美國奧勒岡
* 澳大利亞雪梨
* 愛爾蘭都柏林
* 新加坡共和國

[!DNL Target Recommendations] 服務位於俄勒岡州的 [!DNL Adobe] 資料中心。

>[!IMPORTANT]
>
>[!DNL Adobe Target] 目前在中國沒有邊緣叢集，而且中國 [!DNL Target] 客戶的訪客效能仍然有限。由於中國境內的防火牆和缺乏邊緣叢集，部署了 [!DNL Target] 的網站體驗可能會受到影響。體驗的呈現速度可能緩慢，而頁面載入也會受到影響。此外，行銷人員在使用 [!DNL Target] 編寫 UI 時可能會遇到延遲。

如有需要，您可以允許列出 [!DNL Target] 邊緣群集。 如需更多資訊，請參閱 [允許列出 Target 邊緣節點](/help/main/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md)。

## 受保護的使用者體驗 {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe 盡可能確保定位基礎建設的可用度和效能值得信賴。然而，使用者瀏覽器和 Adobe 伺服器之間的通訊中斷可能會造成內容傳送的中斷。

為避免服務中斷和連線問題，所有位置都已設定為包含預設內容 (由用戶端定義)。如果使用者的瀏覽器無法連線至 [!DNL Target]，則會顯示此預設內容。

如果使用者的瀏覽器無法在已定義的逾時期間內連接 (根據預設：15 秒)，頁面不會有任何變更。如果達到此逾時臨界值，則會顯示預設位置內容。

Adobe 藉由效能最佳化以及保衛效能的方式保護使用體驗。

* Adobe 會依據產業標準確保基準效能，這一點在 Adobe 的服務等級合約中已給予保證。
* Edge 網路確保資料及時傳送。
* Adobe 採用多層面的方法保護其應用程式，使其為客戶提供最高水準的可用度和可靠度。
* [!DNL Target] 諮詢服務提供實施協助和使用中產品的支援。

## 搜尋引擎最佳化 (SEO) 友善測試 {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] 會符合搜尋引擎對於測試的準則。

Google 鼓勵用戶測試。Google 在其文件中指出，如果您遵循特定準則，A/B 和 Multivariate Testing 不會損害有機搜尋引擎排名。

如需詳細資訊，請參閱下列 Google 資源:

* [網站測試和 Google 搜尋](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [實驗和隱匿](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

[Google 網站管理員中心部落格](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)文章中已提供準則。雖然文章發佈於 2012 年，但仍為 Google 對這件事的最新表述，準則仍然適用。

* **無遮蓋**：遮蓋會向使用者顯示一組內容，並向搜尋引擎機器人顯示不同的內容集。遮蓋可通過特別識別機器人並特意提供它們不同的內容來實現。

   [!DNL Target] (作為一種平台) 已設定為將搜尋引擎機器人視同任何使用者。因此，如果隨機選取機器人並「查看」測試變數，則活動中可包含機器人。

* **使用rel=“canonical”**：有時會顧及變異而必須使用不同的 URL 來設定 A/B 測試。在這些情況下，所有變異都應該包含 `rel="canonical"` 標籤來參照原始 (控制) URL。例如，假設 Adobe 正在測試其首頁，針對每個變數使用不同的 URL。針對每個變數，首頁的下列標準標籤會位於 `<head>` 標籤中：

   `<link rel="canonical" href="https://www.adobe.com" />`

* **使用302（臨時）重新導向**：在對測試中的變異頁面使用個別 URL 的情況下，Google 建議使用 302 重新導向，將流量導向測試變異。302重新導向會告訴搜尋引擎，重新導向是暫時的並只在測試執行時才有效。

   302 重新導向是伺服器端重新導向， 及 [!DNL Target] 與其大部分最佳化提供者都使用用戶端功能。因此，在重新導向方面，[!DNL Target] 不完全符合 Google 的建議。但這對測試的影響很小。透過 [!DNL Target] 執行測試的標準方法會要求在單一 URL 內變更內容，因此不需要重新導向。有時，用戶端需要使用多個 URL 來代表測試變異。在這些情況下，[!DNL Target] 使用 JavaScript `window.location` 命令。此命令會指示使用者測試變數，但不會明確表示重新導向是 301 或 302。

   Adobe 持續尋找可行的解決方案，以完全符合搜尋引擎的方針。對於必須使用個別 URL 進行測試的客戶，Adobe 確信正確實施標準標籤可降低與此方法相關的風險。

* **僅在必要時才執行實驗**：Adobe認為「僅在必要時」，意指只要需達到統計顯著性時。[!DNL Target][ 提供最佳實務](https://experienceleague.adobe.com/tools/calculator/testcalculator.html)來判斷測試何時達到此點。Adobe 建議將成功測試寫入程式碼的實施納入測試工作流程中，並分配適當的資源。

   不建議使用 [!DNL Target] 平台來「發佈」成功測試作為永久解決方案。如果成功測試是針對 100% 的使用者發佈，則此方法可在永久編碼成功測試的過程完成時使用。

   您也必須考量您的測試已變更的事物。只是更新頁面上的按鈕或其他次要非文字項目的顏色，完全不影響自然排名。不過，對文字的變更應該寫入程式碼中。

   還必須考量您所測試頁面的可存取性。如果搜尋引擎無法存取頁面，且從來未設計頁面排名在自然搜尋中排名，則上述考量都不適用。 其中一個範例是電子郵件促銷活動的專屬著陸頁面。

Google 表示下列這些準則「應該會讓您的測試幾乎或完全不影響您的網站在搜尋結果中的情形」。

除了這些準則，Google 在說明文件中還對「內容實驗」工具多提供一條準則:

* 「變異頁面應該維持原始頁面內容的本意。這些變異不可變更該原始內容的意義，或使用者對原始內容的普遍認知。」

Google 舉例表示「如果網站的原始頁面所載入的關鍵字與顯示給使用者的組合無關，我們會從索引中移除該網站。」

Adobe 認為，在測試變異中，很難無意間改變原始內容的含義。但是，Adobe 建議注意頁面上的關鍵字主題並維護這些主題。變更頁面內容 (尤其是新增或刪除有意義的關鍵字) 可能導致 URL 在自然搜尋中的排名發生變化。Adobe 建議您與 SEO 合作夥伴互動，以作為測試通訊協定的一部分。

## 機器人 {#bots}

Adobe [!DNL Target] 使用 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) 量度「isRobot」，根據在「請求標題」中傳遞的「使用者代理字串」來偵測已知機器人。

>[!NOTE]
>
> 對於 [!DNL Server-Side] 請求，在[請求的「上下文」節點](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)中傳遞的值優先於用戶代理字串進行機器人檢測。

識別為由機器人產生的流量仍會提供內容。機器人會被視為一般使用者，以確保 [!DNL Target] 符合 SEO 準則。在視為一般使用者的情況下，使用機器人流量可能會扭曲 A/B 測試或個人化演算法。因此，如果 [!DNL Target] 活動中偵測到已知機器人，則會以稍微不同的方式看待流量。移除機器人流量可提供更準確的使用者活動測量。

具體而言，針對已知機器人流量，[!DNL Target] 不會：

* 建立或擷取訪客設定檔
* 記錄任何設定檔屬性或執行設定檔指令碼
* 查詢 Adobe Audience Manager (AAM) 區段 (如適用)
* 使用機器人流量，針對 Recommendations、自動鎖定目標、Automated Personalization 或[!UICONTROL 自動分配]活動建立模型並提供個人化內容
* 記錄活動造訪以進行回報
* 記錄要傳送至 [!DNL Adobe Experience Cloud] 平台的資料
