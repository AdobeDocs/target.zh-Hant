---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;搜尋引擎最佳化;搜尋引擎最佳化;seo;邊緣叢集,中央叢集;at.js;mbox.js;
description: 瞭解 [!DNL Adobe Target] 的運作方式，包括有關JavaScript資料庫(AEP Web SDK at.js)、伺服器呼叫使用策略、使用情況、Adobe資料中心、SEO測試和機器人的資訊。
title: ' [!DNL Target] 如何運作？'
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 85edad5c3adb3a7b01ee6d1eaf2c30c7596d5f92
workflow-type: tm+mt
source-wordcount: '2214'
ht-degree: 24%

---

# [!DNL Adobe Target] 運作方式

瞭解[!DNL Adobe Target]的運作方式，包括有關JavaScript資料庫（[!DNL Adobe Experience Platform Web SDK]和at.js）的詳細資料。 本文也涵蓋您可以建立的各種活動型別、[!DNL Target]使用計數策略、[!DNL Target] Edge Network、SEO和機器人偵測。

要點包括：

* **JavaScript Libraries**：瞭解[!DNL Target] JavaScript資料庫： [!DNL Adobe Experience Platform Web SDK]和at.js。
* **伺服器呼叫使用策略**：瞭解[!DNL Target]如何計算各種伺服器呼叫，包括端點、單一mbox、批次mbox、執行、預先擷取和通知呼叫。
* **Edge Network**：探索[!DNL Target]如何與[!DNL Adobe Experience Platform Edge Network]互動。
* **受保護的使用者體驗**：瞭解[!DNL Adobe]如何確保其目標定位基礎結構的可用性和效能。
* **SEO指導方針**：遵循最佳實務來調整[!DNL Target]活動與SEO指導方針。
* **機器人流量**：瞭解Target如何處理機器人流量，以避免測試與個人化演演算法出現偏差。

## [!DNL Adobe Target] JavaScript 資料庫 {#libraries}

Target使用[!DNL Experience Platform Web SDK]或at.js與網站整合：

* **[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}**：此使用者端JavaScript程式庫可讓[!DNL Adobe Experience Cloud]客戶透過[!DNL Experience Platform Edge Network]與各種服務互動。 [!DNL Adobe]建議新[!DNL Target]客戶實作[!DNL Experience Platform Web SDK]。
* **[at.js](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/how-to-deployatjs){target=_blank}**：這個[!DNL Target]的實作程式庫可縮短Web實作的頁面載入時間，並為單頁應用程式提供更好的選項。 經常更新新功能，[!DNL Adobe]建議所有[at.js使用者更新至最新版本](https://experienceleague-review.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}。

>[!NOTE]
>
>mbox.js資料庫是[!DNL Target]的舊版實作，自2021年3月31日起不再支援。 升級至[!UICONTROL Experience Platform Web SDK] （偏好設定）或at.js最新版本。

在您網站的每個頁面上參考[!UICONTROL Experience Platform Web SDK]或at.js。 例如，將其中一個程式庫新增至全域標頭。 或者，使用Adobe Experience Platform[中的](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/home){target=_blank}標籤來實作[!DNL Target]。

下列資源包含協助您實作 [!DNL Experience Platform Web SDK] 或 at.js 的詳細資訊：

* [[!DNL Adobe Experience Platform Web SDK] 副檔名](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=zh-Hant){target=_blank}
* 使用[&#x200B; [!DNL Target] 實作 [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch){target=_blank}

每次訪客請求針對[!DNL Target]最佳化的頁面時，就會傳送即時請求給目標定位系統，以決定要提供的內容。 每次頁面載入時，都會提出並完成此要求，受行銷人員控制的活動和體驗管理。 內容將目標鎖定在個別網站訪客，最大化回應率、贏取率和收入。 個人化內容可協助確保訪客回應、互動或進行購買。

在[!DNL Target]中，頁面上的每個元素都屬於單一體驗，而單一體驗可包含多個元素。

顯示的內容取決於您建立的活動型別：

### [!UICONTROL A/B Test]

在基本A/B測試中，內容是從指派的體驗中隨機選擇。 您可以為每個體驗設定流量分配百分比。 起初，流量可能會因隨機分割而分配不均，但隨著流量增加，其則會相等。 例如，有兩個體驗，會隨機選擇開始體驗。 低流量可能會將訪客百分比扭曲為流向一個體驗，但此情況可平衡更多流量。

指定每個體驗的百分比目標。 系統會產生隨機數字以選取要顯示的體驗。 雖然產生的百分比可能不會完全符合目標，但較高的流量會導致更接近目標的分割。

1. 客戶向您的伺服器要求頁面，並在其瀏覽器中顯示。
1. 在客戶的瀏覽器中設定第一方Cookie，以儲存其行為。
1. 頁面呼叫目標系統。
1. 根據活動規則顯示內容。

如需詳細資訊，請參閱[建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate]會識別兩個或多個選項中的成功體驗。 然後，它會自動重新分配更多流量給成功者，隨著測試持續執行和學習而增加轉換。

如需詳細資訊，請參閱[[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

### [!UICONTROL Auto-Target] (AT)

[!UICONTROL Auto-Target]運用進階機器學習，從多個高效能、行銷人員定義的體驗中進行選擇。 [!UICONTROL Auto-Target]會根據個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗。 使用[!UICONTROL Auto-Target]個人化內容並推動轉換。

如需詳細資訊，請參閱[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

### [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP)結合選件或訊息，並使用進階機器學習來比對每位訪客的不同變數。 AP會根據個別客戶設定檔來個人化內容，以提高提升度。

如需詳細資訊，請參閱 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。

### [!UICONTROL Experience Targeting] (XT)

[!UICONTROL Experience Targeting] (XT)會根據行銷人員定義的規則和條件將內容提供給特定對象。 XT包含地理定位，對於定義將特定體驗或內容鎖定在特定對象的規則大有幫助。 您可以在傳送不同內容變數至不同對象的活動中設定多個規則。 訪客檢視您的網站時，XT會評估訪客，以判斷他們是否符合條件。 如果他們符合資格，他們會進入活動並檢視為他們設計的體驗。 您可以為單一活動內的多個客群建立體驗。

如需詳細資訊，請參閱[體驗鎖定](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)。

### [!UICONTROL Multivariate Test] (MVT)

[!UICONTROL Multivariate Testing] (MVT)會比較頁面元素中選件的組合，以判斷哪個組合對特定對象執行時效果最佳。 MVT 可協助識別最影響活動成功的元素。

如需詳細資訊，請參閱[多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)。

### [!UICONTROL Recommendations]

[!UICONTROL Recommendations]活動可依據客戶先前的活動或其他演演算法，自動顯示可能使客戶感興趣的產品或內容。 Recommendations有助於將客戶導向他們原本可能無法發現的相關專案。

如需詳細資訊，請參閱 [推薦](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)。

<!--
## How [!DNL Target] counts server-call usage {#usage}

[!DNL Target] counts only server calls that provide value to customers. The following table shows how [!DNL Target] counts endpoints, single mbox, batch mbox calls, execute, prefetch, and notification calls.

The following information helps you understand the counting strategy used for [!DNL Target] server calls, as shown in the table below:

* **Count Once**: Counts once per API call.
* **Count the Number of mboxes**: Counts the number of mboxes under the array in the payload of a single API call.
* **Ignore**: Is not counted at all.
* **Count the Number of Views (Once)**: Counts the number of views under the array in the payload. In a typical implementation, a view notification has only one view under the notifications array, making this equivalent to counting once in most implementations.

|Endpoint|Fetch type|Options|Counting strategy|
|--- |--- |--- |-- |
|`rest//v1/mbox`|Single|[!UICONTROL execute]|Count once|
|`rest/v2/batchmbox`|Batch|[!UICONTROL execute]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch]|Ignore|
||Batch|[!UICONTROL notifications]|Count the number of mboxes|
|`/ubox/[raw\|image\|page]`|Single|[!UICONTROL execute]|Count once|
|`rest/v1/delivery`<p>`/rest/v1/target-upstream`|Single|[!UICONTROL execute] > [!UICONTROL pageLoad]|Count once|
||Single|[!UICONTROL prefetch] > [!UICONTROL pageLoad]|Ignore|
||Single|[!UICONTROL prefetch] > [!UICONTROL views]|Ignore|
||Batch|[!UICONTROL execute] > [!UICONTROL mboxes]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch] > [!UICONTROL mboxes]|Ignore|
||Batch|[!UICONTROL notifications] > [!UICONTROL views]|Count the number of views (once)|
||Batch|[!UICONTROL notifications] > [!UICONTROL pageLoad]|Count once|
||Batch|[!UICONTROL notifications] > type ([!UICONTROL conversions])|Count once|
||Batch|[!UICONTROL notifications] > [!UICONTROL mboxes]|Count the number of mboxes|

-->

## 邊緣網路 {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

「Edge」是按地理區域分配服務的架構，可確保請求內容的訪客獲得最佳回應時間，無論其位於何處。

為改善回應時間，[!DNL Target] Edges 僅代管活動邏輯、快取輪廓和產品建議資訊。

活動和內容資料庫、[!DNL Analytics]資料、API和行銷人員使用者介面存放在[!DNL Adobe]中央叢集中。 更新會傳送至[!DNL Target]邊緣，這些邊緣會自動與中央叢集同步，以持續更新快取的活動資料。 所有1:1模型也會儲存在每個邊緣，允許在本機處理複雜的請求。

每個Edge叢集都包含回應訪客內容請求及追蹤分析資料所需的所有必要資訊。 訪客請求會路由至最接近的邊緣叢集。

如需詳細資訊，請參閱 [Adobe Target 安全性概觀](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)白皮書。

[!DNL Target]託管於Adobe擁有和Adobe租用的全球資料中心。

中央叢集位置同時容納資料收集和資料處理中心。 Edge叢集位置僅包含資料收集中心。 每個報告套裝會被指派至特定的資料處理中心。

客戶網站活動資料是由七個Edge叢集中最接近的叢集收集。 然後，這些資料會導向預先決定的中央叢集目的地（奧勒岡州、都柏林或新加坡）進行處理。 訪客資料會儲存在離網站訪客最近的邊緣叢集上。Edge叢集位置包括中央叢集位置，以及維吉尼亞、孟買、雪梨和東京。

請求不會從單一位置處理所有鎖定目標請求，而是由最接近訪客的Edge叢集處理。 此方法可減輕網路和網際網路旅行時間的影響。

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
>[!DNL Target]目前在中國缺少Edge叢集，因此限制了該區域[!DNL Target]客戶的訪客效能。 防火牆和缺少Edge叢集可能會影響網站體驗，導致轉譯和頁面載入速度緩慢。 此外，行銷人員在使用[!DNL Target]編寫UI時可能會遇到延遲。

如有需要，您可以允許列出 [!DNL Target] 邊緣群集。 如需更多資訊，請參閱 [允許列出 Target 邊緣節點](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank}。

## 受保護的使用者體驗 {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe]會儘可能確保其定位基礎建設的可用度和效能值得信賴。 不過，訪客的瀏覽器與[!DNL Adobe]伺服器之間的通訊中斷可能會中斷內容傳送。

為避免服務中斷和連線問題，所有位置都已設定為包含預設內容 (由用戶端定義)。如果訪客的瀏覽器無法連線至[!DNL Target]，則會顯示此預設內容。

如果訪客的瀏覽器無法在定義的逾時期間內連線（預設值： 15秒），頁面不會有任何變更。 如果達到此逾時臨界值，則會顯示預設位置內容。

[!DNL Adobe] 藉由效能最佳化以及保衛效能的方式保護使用體驗。

* [!DNL Adobe]會根據產業標準確保效能基準，並由[!UICONTROL Adobe Service Level Agreement]保證。
* Edge 網路確保資料及時傳送。
* [!UICONTROL Adobe]採用多層面的方法保護其應用程式，為客戶提供最高水準的可用度和可靠性。
* [!DNL Target] 諮詢服務提供實作協助和使用中產品的支援。

## 搜尋引擎最佳化 (SEO) 友善測試 {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target]會符合搜尋引擎對於測試的准則。 [!DNL Google]鼓勵使用者測試，並指出A/B和[!UICONTROL Multivariate Testing]在遵循某些准則時不會損害有機搜尋引擎排名。

[!DNL Adobe Target] 會符合搜尋引擎對於測試的準則。

如需詳細資訊，請參閱下列 Google 資源:

* [網站測試和 Google 搜尋](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [實驗和隱匿](https://support.google.com/analytics/answer/12979939?hl)


[Google 網站管理員中心部落格](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)文章中已提供準則。雖然文章發佈於2012年，但仍為[!DNL Google]對這件事的最新表述，准則仍然適用。

* **無遮蓋**：遮蓋是指將一組內容顯示給使用者，並將一組內容顯示給搜尋引擎機器人，方法是特別識別機器人，並將不同的內容提供給搜尋引擎機器人。

  [!DNL Target]設定為將搜尋引擎機器人視同任何使用者。 因此，如果隨機選取機器人並「檢視」測試變數，則活動中可包含機器人。

* **使用rel=&quot;canonical&quot;**：有時A/B測試需要不同的URL才能顯示變數。 在這些情況下，所有變異都應該包含參照原始（控制） URL的rel=&quot;canonical&quot;標籤。 例如，如果[!DNL Adobe]正在測試其首頁是否有每個變數的不同URL，首頁的下列canonical標籤應該放在每個變數的`<head>`標籤中：

  `<link rel="canonical" href="https://www.adobe.com" />`

* **使用302 （暫時）重新導向**：當測試中的變異頁面使用個別URL時，[!DNL Google]建議使用302重新導向，將流量導向測試變異。 302重新導向會通知搜尋引擎，重新導向是暫時性的，而且只有在測試執行時才有效。

  302重新導向是伺服器端重新導向，而[!DNL Target]和大多數最佳化提供者都使用使用者端功能。 因此，[!DNL Target]與[!DNL Google]的重新導向建議不完全相容。 但是，這只會影響一小部分的測試。 透過[!DNL Target]執行測試的標準方法涉及變更單一URL中的內容，因此不需要重新導向。 在測試變異需要多個URL的情況下，[!DNL Target]會使用JavaScript `window.location`命令，該命令不會指定重新導向是301還是302。

  [!DNL Adobe]正在積極搜尋解決方案，以完全符合搜尋引擎准則。 對於需要不同URL以進行測試的客戶，[!DNL Adobe]認為正確實作標準標籤可減輕相關風險。

* **僅在必要時才執行實驗**： [!DNL Adobe]會將「僅在必要時」定義為達到統計顯著性所需的時間。 [!DNL Target]提供最佳實務和[!DNL Adobe Target] [樣本大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)，以判斷測試何時達到此點。 [!DNL Adobe]建議將成功測試寫入程式碼的實作納入測試工作流程中，並配置適當的資源。

  不建議使用[!DNL Target]來「發佈」成功測試作為永久解決方案。 如果永遠為100%的使用者發佈成功測試，此方法可在永久編碼成功測試時暫時使用。

  考量您的測試已變更哪些專案。 微幅更新（例如按鈕顏色）不會影響自然排名。 不過，文字變更應採用硬式編碼。

  此外，請考量您測試頁面的協助工具。 如果搜尋引擎無法存取頁面，且從來無意在自然搜尋中排名，則這些考量事項不適用。 其中一個範例是電子郵件促銷活動的專屬著陸頁面。

Google 表示下列這些準則「應該會讓您的測試幾乎或完全不影響您的網站在搜尋結果中的情形」。

除了這些準則，Google 在說明文件中還對「內容實驗」工具多提供一條準則:

* 「變異頁面應該維持原始頁面內容的本意。這些變異不可變更該原始內容的意義，或使用者對原始內容的普遍認知。」

Google 舉例表示「如果網站的原始頁面所載入的關鍵字與顯示給使用者的組合無關，我們會從索引中移除該網站。」

[!UICONTROL Adobe]認為在測試變異中，很難無意間改變原始內容的含義。 但是，[!UICONTROL Adobe]建議注意頁面上的關鍵字主題並維護這些主題。 變更頁面內容 (尤其是新增或刪除有意義的關鍵字) 可能導致 URL 在自然搜尋中的排名發生變化。[!DNL Adobe] 建議您與 SEO 合作夥伴互動，以作為測試通訊協定的一部分。

## 機器人 {#bots}

[!DNL Target]使用[DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/)量度「isRobot」，根據在「要求標題」中傳遞的「使用者代理字串」來偵測已知機器人。

>[!NOTE]
>
> 對於 [!DNL Server-Side] 請求，在[請求的「上下文」節點](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)中傳遞的值優先於使用者代理字串進行機器人偵測。

識別為機器人產生的流量仍會提供內容。 機器人會被視為一般使用者，以確保[!DNL Target]符合SEO准則。 但是，如果被視為一般使用者，機器人流量可能會扭曲A/B測試或個人化演演算法。 因此，[!DNL Target]活動中的已知機器人流量會以不同的方式處理。 移除機器人流量可提供更準確的使用者活動測量。

對於已知的機器人流量，[!DNL Target]不會：

* 建立或擷取訪客個人資料
* 記錄設定檔屬性或執行設定檔指令碼
* 查詢 [!DNL Adobe Audience Manager] (AAM) 區段 (如果適用)
* 使用機器人流量，針對[!UICONTROL Recommendations]、[!UICONTROL Auto-Target]、[!UICONTROL Automated Personalization]或[!UICONTROL Auto-Allocate]活動建立模型或提供個人化內容
* 記錄活動造訪以進行回報
* 記錄要傳送至 [!DNL Adobe Experience Cloud] 平台的資料

對於已知的機器人流量，當使用[!UICONTROL Analytics for Target] (A4T)時，[!DNL Target]不會：

* 傳送事件至[!DNL Analytics]

對於使用`client_side`記錄時的已知機器人流量，[!DNL Target]不會傳回：

* `tnta payload`
