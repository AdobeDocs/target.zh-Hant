---
keywords: Overview and Reference;SEO;search engine optimization;edge clusters, central clusters
description: 'Adobe Target 透過下列兩個 JavaScript 程式庫之一與網站進行整合: at.js 或 mbox.js'
title: Adobe Target 如何運作
feature: intro
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '2403'
ht-degree: 82%

---


# Adobe Target 如何運作

有關 Adobe Target 如何運作的資訊，包括 Target JavaScript 資料庫 (at.js and mbox.js) 以及 Target 中包含的各種活動類型的相關資訊。

## Target JavaScript 資料庫 {#libraries}

Adobe Target 透過下列兩個 JavaScript 程式庫之一與網站進行整合: at.js 或 mbox.js

* **at.js**: [at.js 資料庫](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)是新的 Target 實作資料庫。at.js 程式庫改善 Web 實作的頁面載入時間，並且為單頁應用程式提供更好的實作選項。at.js 為建議的實作程式庫，且經常更新功能。我們建議所有客戶實作或移轉至[最新版本的 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。
* **mbox.js:** mbox.js 程式庫為舊版的 Target 實作程式庫。系統仍支援 mbox.js 程式庫，但將不會提供功能更新。

>[!IMPORTANT]
>
>所有客戶應該移轉至 at.js。如需詳細資訊，請參閱[從 mbox.js 移轉至 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

您必須在網站的每一個頁面上參照 Target JavaScript 資料庫檔案。例如，您可以將此檔案新增至全域標頭。或者，您也可以考慮使用 [Adobe Launch 標籤管理員](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。

每當訪客請求已針對 Target 而最佳化的頁面時，就會傳送請求給目標系統，以決要提供什麼內容給訪客。每次載入頁面時就會立即發生這個程序，亦即提出內容的請求並由系統履行。內容是由市場行銷人員控制之活動和體驗的規則所管理，且目標鎖定在網站的個別訪客。提供的內容要讓每一位網站訪客最有可能回應、互動、最終購買，以獲得最高的回應率、贏取率、收入。

在 Target 中，頁面上的每一個元素都屬於整個頁面的單一體驗。每一個體驗皆可包含頁面上的多個元素。

對訪客顯示的內容取決於您建立的活動類型。

### A/B 測試

如需詳細資訊，請參閱[建立 A/B 測試](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

基本 A/B 測試中顯示的內容是根據您為每一個體驗所選擇的百分比，從您指派給活動的資產中隨機挑選。因為這樣的隨機流量分割，在平分百分比之前可能需要許多初始流量。例如，如果您建立兩個體驗，則會隨機挑選開始的體驗。如果流量小，該百分比的訪客可能全偏到其中一個體驗。隨著流量增加，百分比會更平均。

您可以指定每個體驗的百分比目標。在這種情況下會產生亂數，使用此數字選擇顯示的體驗。結果百分比可能和指定目標不完全相同，但流量更多表示體驗分割就會更接近定位目標。

1. 客戶向伺服器請求頁面，並在瀏覽器中顯示該頁面。
2. 在客戶瀏覽器中設定第一方 Cookie，以儲存客戶行為。
3. 頁面呼叫目標系統。
4. 根據活動的規則來顯示內容。

### 自動分配

如需詳細資訊，請參閱[自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

自動分配會從兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者體驗以增加轉換，同時測試會繼續執行和學習。

### 自動鎖定目標(AT)

如需詳細資訊，請參閱[自動鎖定目標](/help/c-activities/auto-target/auto-target-to-optimize.md)。

自動鎖定目標使用進階機器學習來從多個高效能之市場行銷人員定義的體驗中選取，並根據訪客的個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗，以便個人化內容並促進轉換。

### 自動個人化 (AP)

如需詳細資訊，請參閱[自動個人化](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。

自動個人化 (AP) 結合選件或訊息，並使用進階機器學習來根據訪客的個別客戶設定檔比對每位訪客的不同選件變數，以便個人化內容並促進提升度。

### 體驗鎖定目標 (XT)

[體驗鎖定目標](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)

體驗鎖定目標 (XT) 會根據一組市場行銷人員定義的規則和條件為特定對象提供內容。

體驗鎖定目標 (包括地理定位) 對於定義將特定體驗或內容鎖定在特定對象的規則大有幫助。您可以在傳送不同內容變數至不同對象的活動中定義數個規則。在訪客檢視您的網站時，體驗鎖定目標 (XT) 會評估他們，以決定他們是否符合您設定的條件。如果他們符合條件，他們會進入活動，並且針對符合資格對象設計的體驗會顯示。您可以為單一活動內的多個對象建立體驗。

### 多變數測試 (MVT)

如需詳細資訊，請參閱[多變數測試](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)。

多變數測試 (MVT) 會比較頁面上元素中選件的組合，以判斷哪個組合對特定對象執行時效果最佳，並識別哪個元素最能影響活動的成功。

### 建議

如需詳細資訊，請參閱 [Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)。

Recommendations 活動可依據先前的使用者行為或其他演算法，自動顯示可能使客戶感興趣的產品或內容。Recommendations 可協助引導客戶至他們可能不知道的相關項目。

## The edge network {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

「Edge」是地理上分散的服務架構，可確保使用者在要求內容時的最佳回應時間，而不論使用者在全球的何處。

為了改善回應時間，Target Edges僅托管活動邏輯、快取描述檔和選件資訊。

Activity and content databases, [!DNL Analytics] data, APIs, and marketer user interfaces are housed in Adobe’s Central Clusters. 更新會傳送至「目標邊緣」。 Central叢集和Edge叢集會自動同步，以持續更新快取的活動資料。 所有1:1模型也會儲存在每個邊緣，因此這些更複雜的要求也可以在邊緣上處理。

每個邊緣叢集都具備回應使用者內容要求及追蹤該要求之分析資料所需的所有資訊。 使用者要求會路由至最接近的邊緣叢集。

如需詳細資訊，請參閱 [Adobe Target 安全性概覽](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)白皮書。

The [!DNL Adobe Target] solution is hosted on Adobe-owned and Adobe-leased data centers around the globe.

中央群集位置同時包含資料收集中心和資料處理中心。 邊緣叢集位置僅包含資料收集中心。 每個報表套裝會被指派至特定的資料處理中心。

客戶站點活動資料由七個邊緣群集中最靠近的群集收集，並定向到客戶的預定中央群集目標(三個位置之一：Oregon、Dublin、Singapore)，以進行處理。 訪客資料會儲存在離網站訪客最近的Edge Cluster（位置包括中央叢集位置，以及維吉尼亞、阿姆斯特丹、雪梨、東京和香港）。

請求由離訪客最近的邊緣叢集處理，而非回應單一位置的所有定位請求，因此可減輕網路／網際網路旅行時間的影響。

![目標伺服器映射類型](/help/c-intro/assets/target-servers.png)

Target Central Clusters位於以下位置：

* 美國俄勒岡州
* 愛爾蘭都柏林
* 新加坡共和國

Target Edge Clusters位於：

* 印度孟買
* 日本東京
* 美國維吉尼亞州
* 美國俄勒岡州
* 澳洲雪梨
* 愛爾蘭都柏林
* 新加坡共和國

此服 [!DNL Target Recommendations] 務位於俄勒岡州 [!DNL Adobe] 的資料中心。

>[!IMPORTANT]
>
>[!DNL Adobe Target] 目前中國沒有Edge Cluster，而且一般使用者的效能仍將受限於中國 [!DNL Target] 客戶。 Because of the firewall and the lack of Edge Clusters within the country, the experiences of sites with [!DNL Target] deployed will be slow to render and page loads will be affected. Also, marketers might experience latency when using the [!DNL Target] authoring UI.

您可以視需要允許列出目標邊緣叢集。 如需詳細資訊，請參 [閱allowlist Target edge nodes](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md)。

## Protected user experience {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe 盡可能確保定位基礎建設的可用度和效能值得信賴。然而，使用者瀏覽器和 Adobe 伺服器之間的通訊中斷可能會造成內容傳輸的中斷。

為了在發生服務中斷和連線問題的情況下提供保護，所有位置都設定為包含預設內容 (由客戶定義)，在使用者的瀏覽器無法連線到 [!DNL Target] 時就會顯示。

如果使用者的瀏覽器無法在已定義的逾時期間內連接 (根據預設: 15 秒)，頁面不會有任何變更。如果達到此逾時臨界值，則會顯示預設位置內容。

Adobe 藉由效能最佳化以及保衛效能的方式保護使用體驗。

* Adobe 會依據產業標準確保基準效能，這一點在 Adobe 的服務等級合約中已給予保證。
* Edge 網路確保資料及時傳送。
* Adobe 採用多層面的方法保護其應用程式，使其為客戶提供最高水準的可用度和可靠度。
* [!DNL Target] 諮詢服務提供實施協助和使用中產品的支援。

## 搜尋引擎最佳化 (SEO) 友善測試 {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] 會符合搜尋引擎對於測試的準則。

Google 鼓勵使用者測試，且已於說明文件中表示只要遵守一些簡單的準則，A/B 和多變數測試並不會影響搜尋引擎自然排名。

如需詳細資訊，請參閱下列 Google 資源:

* [網站測試和 Google 搜尋](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [實驗和隱匿](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

[Google 網站管理員中心部落格](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)文章中已提供準則。雖然文章發佈於 2012 年，但仍為 Google 對這件事的最新表述，準則仍然適用。

* **不隱匿** - 隱匿是指將一份內容顯示給使用者，但會識別搜尋引擎機器人並故意供應不同內容，而將另一份內容顯示給搜尋引擎機器人。

   Target (作為一種平台) 已設定為將搜尋引擎機器人視同任何使用者。這表示機器人可能會納入您執行的測試中 (如果隨機選取) 並「看見」測試變異。

* **使用 rel=&quot;canonical&quot;** - 有時會顧及變異而需要使用不同的 URL 來設定 A/B 測試。在這些情況下，所有變異都應該包含 `rel="canonical"` 標籤來參照原始 (控制) URL。例如，假設 Adobe 針對每一個變異使用不同的 URL 來測試首頁，首頁的下列 canonical 標籤會出現在每一個變異的 `<head>` 標籤中:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **使用 302 (暫時) 重新導向** - 在對測試中的變異頁面使用個別 URL 的情況下，Google 建議使用 302 重新導向，將流量導向測試變異。這會向搜尋引擎表示重新導向只是暫時，只有在測試執行時才有作用。

   302 重新導向是伺服器端重新導向，Target 及其大部分最佳化提供者都使用用戶端功能。因此，在這方面，Target 不完全符合 Google 的建議。但這對測試的影響很小。透過 Target 執行測試的標準方法會要求在單一 URL 內變更內容，因此不需要重新導向。有時，用戶端需要使用多個 URL 來代表測試變異。在這種情況下，Target 會使用 JavaScript `window.location` 命令，將使用者導向測試變異，但這不明確表明重新導向是 301 還是 302。

   雖然我們持續尋找可行的解決方案，以完全符合搜尋引擎準則，但對於必須使用不同 URL 來測試的客戶，我們確信只要適當實施上述的 canonical 標記，就能降低此方法帶來的風險。

* **執行實驗只要夠久即可** - 我們認為「夠久即可」是指達到統計顯著性所花的時間。Target [提供最佳作法](https://docs.adobe.com/content/target-microsite/testcalculator.html)來判斷測試何時達到此點。建議將獲勝測試寫入程式碼的實作納入測試工作流程中，並分配適當的資源。

   雖然可使用 Target 平台來「發佈」獲勝測試，但不建議當作永久解決方案，但只要是基於100% 的時間來針對 100% 的使用者發佈獲勝測試，則在完成將獲勝測試寫入程式碼的程序時可採用此方法。

   也必須考量您的測試已變更的事物。只是更新頁面上的按鈕或其他次要非文字項目的顏色，完全不影響自然排名。不過，對文字的變更應該寫入程式碼中。

   還必須考量您所測試頁面的可存取性。如果頁面無法供搜尋引擎存取，也從未設計成要在自然搜尋引擎中排在第一名，例如電子郵件行銷活動的專用登陸頁面，則上述考量完全沒必要。

Google 表示下列這些準則「應該會讓您的測試幾乎或完全不影響您的網站在搜尋結果中的情形」。

除了這些準則，Google 在說明文件中還對「內容實驗」工具多提供一條準則:

* 「變異頁面應該維持原始頁面內容的本意。這些變異不可變更該原始內容的意義，或使用者對原始內容的普遍認知。」

Google 舉例表示「如果網站的原始頁面所載入的關鍵字與顯示給使用者的組合無關，我們會從索引中移除該網站。」

我們認為在測試變異內非存心變更原始內容的意義並不容易，但建議要注意頁面上的關鍵字主題，並維護這些主題。變更頁面內容 (尤其是新增或刪除有意義的關鍵字) 可能導致 URL 在自然搜尋中的排名發生變化。建議在擬訂測試時與您的 SEO 夥伴合作。

## 機器人 {#bots}

Adobe Target uses [DeviceAtlas](https://deviceatlas.com/) to detect known bots. 識別為由機器人產生的流量仍會提供內容 (例如一般使用者)，確保其符合 SEO 指導方針。在視為一般使用者的情況下，使用機器人流量可能會扭曲 A/B 測試或個人化演算法。因此，如果 Target 活動中偵測到已知機器人，則會以稍微不同的方式看待流量。移除機器人流量可提供更準確的使用者活動測量。

具體而言，針對已知機器人流量，Target 不會:

* 建立或擷取訪客設定檔
* 記錄任何設定檔屬性或執行設定檔指令碼
* 查詢 Adobe Audience Manager (AAM) 區段 (如適用)
* 使用機器人流量，針對 Recommendations、自動鎖定目標、自動個人化或自動分配活動建立模型並提供個人化內容
* 記錄活動造訪以進行回報
* 記錄要傳送至 Adobe Experience Cloud 平台的資料
