---
keywords: SPA VEC; React; Angular; react.js; SPA 可視化體驗撰寫器; SPA 體驗撰寫器選項; 單一頁面應用程式; SPA; 行動體驗選項; Target 檢視
description: 瞭解如何在Adobe [!DNL Target] 中使用SPA VEC，在SPA上自己動手建立測試並個人化內容，無需持續開發的相依性。
title: 如何使用單頁應用程式視覺化體驗撰寫器(SPA VEC)？
feature: Visual Experience Composer (VEC)
exl-id: fd3dcfaa-e5c6-45a1-8229-9c206562e5b0
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '3569'
ht-degree: 64%

---

# 單頁應用程式 (SPA) 可視化體驗撰寫器

在[!DNL Adobe Target]中，[!UICONTROL Visual Experience Composer] (VEC)為行銷人員提供自助式功能，以建立活動並個人化體驗，這些可以透過Adobe Target的全域mbox在傳統多頁應用程式上以動態方式傳送。 不過，這有賴擷取頁面載入上的產品建議或後續伺服器呼叫，但會導致延遲，如下圖所示。由於這種作法會減損使用者體驗與應用程式效能，因此在單頁應用程式 (SPA) 上成效不彰。

![傳統生命週期與 SPA 生命週期的比較](/help/main/c-experiences/assets/trad-vs-spa.png)

在最新版本中，我們現在推出了適用於 SPA 的 VEC。適用於 SPA 的 VEC 能讓行銷人員在 SPA 上，自己動手建立測試並個人化內容，無需持續開發的相依性。VEC 可用來在熱門架構 (React 和 Angular) 上建立 [A/B 測試](/help/main/c-activities/t-test-ab/test-ab.md)和[體驗鎖定目標](/help/main/c-activities/t-experience-target/experience-target.md) (XT) 活動。

## Adobe [!DNL Target]檢視和單頁應用程式

適用於 SPA 的Adobe Target VEC 充分利用「檢視」的新概念: 視覺元素的邏輯組合，共同構成 SPA 體驗。因此，SPA 可以視為根據使用者互動轉換檢視，而不是轉換 URL。檢視通常可代表整個網站或網站內的分組視覺元素。

為了進一步說明檢視，讓我們瀏覽這個在React中實作的假想線上電子商務網站，並探索一些檢視範例。 按一下底下的連結，在新的瀏覽器分頁中開啓此網站。

**連結： [主網站](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/)**

![首頁](/help/main/c-experiences/assets/home.png)

當我們導覽到主網站時，立刻就會看到宣傳復活節特賣以及網站上最新發售產品的主圖影像。在這個案例中，檢視可定義為整個首頁。請記下這點，因為我們將在下文的「實作 Adobe Target 檢視」一節中更深入說明。

**連結： [產品網站](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)**

![產品網站](/help/main/c-experiences/assets/product-site.png)

當我們對產品越來越感興趣時，決定點擊產品連結。與首頁相似，產品網站整體可定義為一個檢視。我們可以將這個檢視命名為「products」，就像 `https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products` 中的路徑名稱一樣。

![產品網站 2](/help/main/c-experiences/assets/product-site-2.png)

本節的一開始，我們將檢視定義為整個網站或網站上的一組視覺元素。如上所示，網站上顯示的四個產品也可分組並視為檢視。如果要命名此檢視，可以命名為「產品」。

![產品網站 3](/help/main/c-experiences/assets/product-site-3.png)

我們決定點擊「載入更多」按鈕來探索網站上更多的產品。在此情況下，網站 URL 不會變更。但此處的檢視只能呈現上圖中的第二列產品。「檢視」名稱可以命名為「PRODUCTS-PAGE-2」。

**連結： [結帳](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/checkout)**

![結帳頁面](/help/main/c-experiences/assets/checkout.png)

因為我們喜歡網站上展示的一些產品，所以決定購買幾項產品。現在，結帳網站提供我們幾個選項，可選擇一般配送或快捷配送。由於「檢視」可以是網站上任一視覺化元素群組，我們可將其命名為「檢視運送偏好設定」。

此外，檢視概念還可進一步延伸。如果行銷人員想要根據選取的配送偏好設定個人化網站內容，可針對每個配送偏好設定建立一個檢視。如果是這種情況，當我們選取「一般運送」，可將「檢視」命名為「一般運送」。如果選取的是「快速運送」，則可將「檢視」命名為「快速運送」。

假設現在行銷人員想執行 A/B 測試，以瞭解當選取「快捷配送」時，相較於讓這兩種配送選項的按鈕均保持藍色，按鈕從藍色變為紅色是否能增加轉換次數。

## 實作Adobe [!DNL Target]檢視

我們已在上文中介紹 Adobe Target 檢視的功能，現在可以在 Target 中運用這個概念，讓行銷人員透過 VEC 在 SPA 上執行 A/B 和 XT 測試。進行測試需要一次性開發人員設定。以下逐一說明設定步驟。

1. 安裝 at.js 2.x。

   首先需要安裝 at.js 2.x。這個 at.js 版本是針對 SPA 所開發。舊版at.js，不支援Adobe Target檢視和適用於SPA的VEC。

   ![實作詳細資料對話方塊](/help/main/c-experiences/assets/imp-200.png)

   透過[!UICONTROL Administration > Implementation]中的Adobe Target UI下載at.js 2.x。 也可透過[Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html?lang=zh-Hant){target=_blank}中的標籤來部署at.js 2.x。 不過，Adobe Target擴充功能目前不是最新版本，且不受支援。

1. 在您的網站上實作at.js 2.x的最新函式： [triggerView()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-triggerview-atjs-2.html?lang=zh-Hant){target=_blank}。

   定義您要執行A/B或XT測試的SPA的檢視後，使用傳入作為引數的檢視來實作at.js 2.x的`triggerView()`函式。 這麼做可讓行銷人員針對已定義檢視，使用 VEC 設計和執行的 A/B 和 XT 測試。如果沒有針對這些檢視定義 `triggerView()` 函數，VEC 將無法偵測檢視，進而導致行銷人員無法使用 VEC 來設計和執行 A/B 和 XT 測試。

   **`adobe.target.triggerView(viewName, options)`**

   | 參數 | 類型 | 必要? | 驗證 | 說明 |
   | --- | --- | --- | --- | --- |
   | viewName | 字串 | 是 | &#x200B;1. 尾端無空格。<br>2.不得空白。<br>3.所有頁面的檢視名稱都不得重複。<br>4.**警告**: 檢視名稱的開頭或結尾不能為「`/`」。這是因為客戶通常會從 URL 路徑中擷取檢視名稱。對我們來說，「home」和「`/home`」是不一樣的。<br>5.**警告**: 同一個檢視不應使用 `{page: true}` 選項連續觸發多次。 | 傳入任何名稱作為要代表檢視的字串類型。此檢視名稱會顯示在VEC的[!UICONTROL Modifications]面板中，供行銷人員建立動作和執行其A/B和XT活動。 |
   | options | 物件 | 無 |  |  |
   | options > page | 布林值 | 無 |  | **TRUE:** 頁面的預設值為 true。當 `page=true`，會傳送通知至 Edge 伺服器以增加曝光計數。<br>**FALSE**：當`page=false`時，將不會傳送通知以增加曝光計數。 只有當您想重新呈現頁面上含有某個產品建議的元件時，才應使用此項目。 |

   現在，讓我們來看看一些使用範例，瞭解如何在React中叫用假設性的電子商務SPA的`triggerView()`函式：

   **連結： [主網站](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/)**

   ![home-react-1](/help/main/c-experiences/assets/react1.png)

   行銷人員如果要在整個主網站上執行 A/B 測試，會想要將檢視命名為「主頁」(可從 URL 擷取):

   ```javascript
   function targetView() {
     var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash
   
     viewName = viewName || 'home'; // view name cannot be empty
   
     // Sanitize viewName to get rid of any trailing symbols derived from URL
     if (viewName.startsWith('#') || viewName.startsWith('/')) {
       viewName = viewName.substr(1);
     }
   
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   // react router v4
   const history = syncHistoryWithStore(createBrowserHistory(), store);
   history.listen(targetView);
   
   // react router v3
   <Router history={hashHistory} onUpdate={targetView} >
   ```

   **連結： [產品網站](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)**

   現在，讓我們來看看更複雜的範例。 假設我們是行銷人員，想要在使用者按一下「載入更多」按鈕後，將價格標籤顏色變更為紅色，以個人化產品的第二列。

   ![react 產品](/help/main/c-experiences/assets/react4.png)

   ```javascript
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   class Products extends Component {
     render() {
       return (
         <button type="button" onClick={this.handleLoadMoreClicked}>Load more</button>
       );
     }
   
     handleLoadMoreClicked() {
       var page = this.state.page + 1; // assuming page number is derived from component's state
       this.setState({page: page});
       targetView('PRODUCTS-PAGE-' + page);
     }
   }
   ```

   **連結： [結帳](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/checkout)**

   ![react 結帳](/help/main/c-experiences/assets/react6.png)

   如果行銷人員想要根據選取的配送偏好設定個人化網站內容，可針對每個配送偏好設定建立一個檢視。如果是這種情況，當我們選取「一般運送」，可將「檢視」命名為「一般運送」。如果選取的是「快速運送」，則可將「檢視」命名為「快速運送」。

   假設現在行銷人員想執行 A/B 測試，以瞭解當選取「快捷配送」時，相較於讓這兩種配送選項的按鈕均保持藍色，按鈕從藍色變為紅色是否能增加轉換次數。

   ```javascript
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   class Checkout extends Component {
     render() {
       return (
         <div onChange={this.onDeliveryPreferenceChanged}>
           <label>
             <input type="radio" id="normal" name="deliveryPreference" value={"Normal Delivery"} defaultChecked={true}/>
             <span> Normal Delivery (7-10 business days)</span>
           </label>
   
           <label>
             <input type="radio" id="express" name="deliveryPreference" value={"Express Delivery"}/>
             <span> Express Delivery* (2-3 business days)</span>
           </label>
         </div>
       );
     }
     onDeliveryPreferenceChanged(evt) {
       var selectedPreferenceValue = evt.target.value;
       targetView(selectedPreferenceValue);
     }
   }
   ```

1. 透過 VEC 啟動 A/B 或 XT 活動。

   當您在 SPA 上實作 `adobe.target.triggerView()` 且已傳入「檢視」名稱作為參數，VEC 就能夠偵測這些檢視，並允許使用者建立 A/B 或 XT 活動的動作或修改。

   >[!NOTE]
   >
   >適用於 SPA 的 VEC 與您用於一般網頁的 VEC 完全相同，不過當您開啟實作了 `triggerView()` 的單頁應用程式時，會提供一些額外功能讓您使用。

VEC 的[「修改」](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)面板和「動作」有兩項重大改進，使得 VEC 可以順利用於 SPA。

**「修改」面板**

[!UICONTROL Modifications]面板（如下所示）會擷取為特定檢視所建立的動作。 請注意，一個「檢視」的所有動作會在該「檢視」下組成群組。

**動作**

按一下動作會醒目顯示將套用該動作之網站上的元素。在檢視下建立的每個 VEC 動作都有下列圖示，如下所示: 資訊、編輯、原地複製、移動和刪除。

![修改](/help/main/c-experiences/assets/modifications.png)

下表說明每個動作:

| 頁面 | 說明 |
| --- | --- |
| 資訊 | 顯示此動作的詳細資料。 |
| 編輯 | 可讓您直接編輯該動作的屬性。 |
| 原地複製 | 將動作原地複製至一或多個存在於[!UICONTROL Modifications]面板上的檢視，或原地複製至一或多個您已在VEC中瀏覽及導覽的目標檢視。 動作不一定存在於[!UICONTROL Modifications]面板中。<br>**附註**：執行復製作業後，您必須透過[!UICONTROL Browse]導覽至VEC中的檢視，才能檢視該複製動作的作業是否有效。 如果無法將動作套用到檢視，則會出現錯誤. |
| 移動 | 可將動作移動至頁面載入事件，或修改面板中已存在的任何其他檢視。<br>[!UICONTROL Page Load Event] — 任何對應至頁面載入事件的動作，都會套用到網頁應用程式的初始頁面載入上。<br>**附註**&#x200B;執行移動作業後，您必須透過瀏覽導覽至VEC中的檢視，才能檢視該移動作業是否有效。 如果無法將動作套用到檢視，則會出現錯誤 |
| 刪除 | 刪除動作。 |

>[!NOTE]
>
>您可以在 VEC 中的頁面載入前，或甚至頁面完全無法載入時執行許多動作。無法在網站載入前編輯的動作，都會在 UI 中停用。

**範例 1**

讓我們回到前面建立「首頁」檢視的範例。 這個檢視有雙重目標:

1. 將「加到購物車」和「讚」按鈕變更為較淺的藍色。由於我們變更的是標頭的元件，這應該要位於「頁面載入」中。
1. 將「2019 年最新產品」標籤變更為「2019 年最暢銷產品」，並將文字顏色變更為紫色。

若要執行這些目標，請在VEC中按一下[!UICONTROL Compose]，然後在[首頁]檢視上套用這些變更。

![範例 1](/help/main/c-experiences/assets/example1.png)

**範例 2**

讓我們回到前面建立PRODUCTS-PAGE-2檢視的範例。 我們的目標是要將「售價」標籤變更為「促銷價」，且標籤顏色為紅色。

1. 按一下「[!UICONTROL Browse]」，然後按一下標頭的「[!UICONTROL Products]」連結。
1. 按一下[!UICONTROL Load More]以取得產品的第二列。
1. 按一下 [!UICONTROL Compose]。
1. 套用動作以將文字標籤變更為「促銷價」，且顏色會變成紅色。

![範例 2](/help/main/c-experiences/assets/example2.png)

**範例 3**

最後，就像之前說過的，您可以在更精細的層級定義「檢視」。「檢視」可以是選項按鈕的一個狀態，甚至作為選項。我們之前是以「CHECKOUT-EXPRESS」和「CHECKOUT-NORMAL」來建立「檢視」。我們的目標是要將「CHECKOUT-EXPRESS」檢視的按鈕顏色變更為紅色。

1. 按一下 [!UICONTROL Browse]。
1. 將一些產品加到購物車。
1. 按一下右上角的購物車圖示。
1. 按一下「訂單結帳」。
1. 按一下「快速運送」選項按鈕。
1. 按一下 [!UICONTROL Compose]。
1. 將「付款」按鈕變更為「完成訂單」字樣的按鈕，並將顏色變更為紅色。

![範例 3](/help/main/c-experiences/assets/example3.png)

>[!NOTE]
>
>在您按下「快速運送」選項按鈕前，「CHECKOUT-EXPRESS」檢視不會顯示在修改面板中。這是因為「快速運送」選項按鈕經選取時才會觸發 `triggerView()` 函數，而且只有這個時候 VEC 才會知道要在修改面板中顯示「檢視」。

## 深入分析 at.js 和 SPA

**我要如何在我的 SPA 上首次頁面載入後，擷取經動作序列化的最新客群資料的檢視?**

at.js 2.x的標準工作流程是當網站載入時，所有的檢視和動作都會經過快取，這樣網站上後續的使用者動作就不會觸發伺服器呼叫來擷取選件。 如果您要根據最新輪廓資料 (視後續的使用者動作而可能有所更新) 來擷取檢視，您可以使用傳入的最新客群使用者或輪廓資料來呼叫 `getOffers()` 和 `applyOffers()`。

例如，試想您是一間電信公司，且您的 SPA 使用的是 at.js 2.x。站在公司的角度，您希望達成下列目標:

* 對於登出或匿名的使用者，要對他們顯示最新的公司促銷活動，例如在`http://www.telecom.com/home`上顯示「第一個月免費」主圖優惠。
* 對於登入的使用者，針對合約即將到期的使用者，顯示升級促銷優惠方案，例如「您符合免費手機的資格！」 例如在 `http://www.telecom.com/loggedIn/home` 上顯示「您符合獲得免費手機的資格!」。

現在，您的開發人員為檢視命名，且以下列方式呼叫 `triggerView()`:

* 若為 `http://www.telecom.com/home`，則檢視名稱為「首頁 (登出)」
   * 叫用的是 `triggerView("Logged Out Home")`。
* 若為 `http://www.telecom.com/loggedIn/home`，則檢視名稱為「首頁 (登入)」
   * 因路徑改變，叫用的是 `triggerView("Logged In Home")`。

您的行銷人員接著透過 VEC 執行下列 A/B 活動:

* 針對引數為&quot;`loggedIn= false`&quot;的對象，搭配「第一個月免費」優惠的A/B活動會顯示在`http://www.telecom.com/home`中，其檢視名稱為「首頁（登出）」。
* A/B活動搭配「您符合取得免費電話的資格！」 引數「`loggedIn=true`」的對象優惠方案會顯示在`http://www.telecom.com/loggedIn/home`，其檢視名稱為「首頁（登入）」優惠。

現在，來看看這個使用者流程:

1. 匿名的登出使用者登陸您的頁面。
1. 由於您使用的是at.js 2.x，您在頁面載入時傳入「`loggedIn = false`」引數，以在對象具有「`loggedIn = false`」引數時，擷取在合格的使用中活動中出現的所有檢視。
1. at.js 2.x接著會擷取「首頁（登出）」檢視與動作以顯示「第一個月免費」優惠，並將其儲存在快取中。
1. 當叫用`triggerView("Logged Out Home")`時，會從快取中擷取「第一個月免費」優惠，且無需伺服器呼叫即可顯示優惠。
1. 使用者現在點選「登入」並提供其認證。
1. 由於您的網站是 SPA，您不會執行完整的頁面載入，而會改將使用者路由至 `http://www.telecom.com/loggedIn/home`。

現在，問題來了。由於我們將此程式碼置於路由變更，使用者登入時我們會碰到 `triggerView("Logged In Home")`。這會告訴 at.js 2.x 要從快取中擷取檢視與動作，但快取中唯一有的檢視是「首頁 (登出)」。

那麼，我們要如何擷取「登入」檢視並顯示「您符合獲得免費手機的資格！」 offer? 而由於您網站上所有的後續動作都會使用登入使用者的視角進行，您要如何確定所有的後續動作會如期向登入使用者顯示個人化產品建議呢?

您可以使用 at.js 2.x 支援的新函數 `getOffers()` 和 `applyOffers()`:

```javascript
adobe.target.getOffers({
  request: {
  prefetch: {
    "views": [
      {
        "parameters": {
          "loggedIn": true
        },
      }
    ]
  },
});
```

將`getOffers()`的回應傳遞給`applyOffers()`，現在，與「loggedIn = true」關聯的所有檢視與動作都會更新at.js快取。

也就是說，at.js 2.x 能以隨需方式，使用最新的客群資料來擷取檢視、動作和產品建議。

**at.js 2.x 是否支援適用於單頁應用程式的 A4T?**

是的，只要您已實作 Adobe Analytics 和 Experience Cloud 訪客 ID 服務，at.js 2.x 便能透過 `triggerView()` 函數支援適用於 SPA 的 A4T。請見下圖的逐步說明。

![Target 流程](/help/main/c-experiences/assets/atjs-spa-flow.png)

| 步驟 | 說明 |
| --- | --- |
| 1 | SPA 會呼叫 `triggerView()` 來轉譯檢視並套用動作，以修改與檢視相關聯的視覺元素。 |
| 2 | 從快取讀取檢視的目標內容。 |
| 3 | 目標內容會儘快出現，不會有忽隱忽現的預設內容。 |
| 4 | 系統會將通知要求傳送到 Target 輪廓存放區，以計算活動中的訪客數並增加量度。 |
| 5 | Analytics 資料傳送至資料收集伺服器。 |
| 6 | Target 資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 A4T 報表來檢視 Analytics 資料。 |

>[!NOTE]
>如果您不希望在每次觸發檢視時，都要將通知傳送到Adobe Analytics進行曝光計數，請將`{page: false}`傳入`triggerView()`函式，這樣當有元件持續再轉譯而多次觸發檢視時，曝光計數也不會膨脹。 例如:
>
>`adobe.target.triggerView("PRODUCTS-PAGE-2", {page:false})`

## 支援的活動

| 活動類型 | 支援? |
| --- | --- |
| [A/B 測試](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| A/B測試和體驗鎖定目標(XT)活動中的[選件形式的建議](/help/main/c-recommendations/recommendations-as-an-offer.md)<br> | 是 |
| [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 是 |
| [體驗鎖定目標](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |
| [多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 無 |
| [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 無 |
| [自動個人化](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 無 |
| [推薦](/help/main/c-recommendations/recommendations.md) | 無 |

**如果我們安裝 at.js 2.x 並在網站上實作了 `triggerView()`，在 SPA VEC 不支援自動鎖定目標的情況下，該如何執行自動鎖定目標 A/B 活動?**

如果您希望使用自動鎖定目標 A/B 活動，可以移動所有的動作，讓它們在 VEC 中的「頁面載入事件」上執行。將游標停留在每個動作上，然後按一下[!UICONTROL Move to Page Load Event]按鈕。 完成後，您可以在下一步中為流量分配方法選取「自動鎖定目標」。

## 支援的整合

| 整合 | 支援? |
| --- | --- |
| [目標分析 (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | 是 |
| [Experience Cloud 客群](/help/main/c-integrating-target-with-mac/mmp.md) | 是 |
| [客戶屬性](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html?lang=zh-Hant){target=_blank} | 是 |
| [AEM 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 是 |

## 支援的功能 {#supported-features}

| 功能 | 支援? |
| --- | --- |
| [工作區與屬性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) | 是 |
| [QA 連結](/help/main/c-activities/c-activity-qa/activity-qa.md) | 是 |
| [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md) | 無 |
| [自訂程式碼](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | 是 |
| [VEC 選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | 全部 |
| [點擊追蹤](/help/main/c-activities/r-success-metrics/click-tracking.md) | 是 |
| [多活動傳送](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md) | 是 |

## SPA VEC的頁面傳送設定 {#page-delivery-settings}

[!UICONTROL Page Delivery]設定可讓您設定規則，判斷受眾是否符合Target活動且可執行。

若要從VEC的三步驟引導式活動建立工作流程中存取[!UICONTROL Page Delivery]選項，請從&#x200B;**[!UICONTROL Experiences]**&#x200B;步驟中按一下「**[!UICONTROL Configure]**」（齒輪圖示） >「**[!UICONTROL Page Delivery]**」。

![頁面傳送選項對話方塊](/help/main/c-experiences/assets/page-delivery.png)

例如，如上方顯示的[!UICONTROL Page Delivery]設定所定義，Target活動會在訪客直接在`https://www.adobe.com` *或*&#x200B;上登陸任何包含`https://www.adobe.com/products`的URL時符合併執行。 這非常適合任何多頁應用程式，其中與頁面的所有互動都會叫用頁面重新載入，而 at.js 會擷取符合使用者導覽之目標 URL 的活動。

不過，由於SPA的運作方式不同，[!UICONTROL Page Delivery]設定的方式必須如SPA VEC活動中所定義，可將所有動作套用至檢視。

### 使用案例範例

請看看這個使用案例範例:

![SPA VEC 修改面板](/help/main/c-experiences/assets/page-delivery-example.png)

以下是所做的變更:

* 變更位於下列URL下的首頁檢視的背景顏色： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/)。
* 變更位於下列URL下的產品檢視中的按鈕顏色： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)。

請思考上述範例，如果我們將[!UICONTROL Page Delivery]設定設為僅包含： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/) (在具有at.js 2.*x* 的 SPA 中)，那麼會發生什麼情況?

![頁面傳送對話方塊](/help/main/c-experiences/assets/spa-page-delivery.png)

下圖顯示 Target 流程 - at.js 2.*x* 中的頁面載入要求:

![Target 流程 - at.js 2.0 頁面載入要求](/help/main/c-experiences/assets/page-load-request.png)

**第 1 個使用者旅程**

* 使用者直接導覽至[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/)。
* at.js 2.*x*&#x200B;會查詢Edge，以檢視下列URL是否有任何需要執行的活動： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/)。
* 在步驟 6 中，Target Edge 會傳回首頁和產品檢視的動作，以便系統快取瀏覽器內的這些動作。

**結果**: 使用者會在首頁檢視中看見綠色的背景顏色。當使用者接著導覽至[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)時，會看見按鈕的藍色背景顏色，因為系統已快取瀏覽器中的產品檢視下的動作。

附註：導覽至[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)的使用者並未觸發頁面載入。

**第 2 個使用者旅程**

* 使用者直接導覽至[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)。
* at.js 2.*x*&#x200B;會查詢Edge，以檢視下列URL是否有任何需要執行的活動： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)。
* 沒有符合[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)的活動。
* 由於沒有任何符合的活動，因此沒有任何快取動作和檢視可供 at.js 2.*x* 觸發。

**結果**：即使您已為產品檢視定義`triggerView()`，並透過SPA VEC對產品檢視執行動作，您也不會看到預期的動作，因為您並未建立在頁面傳送設定中包含[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hant#/products)的規則。

### 最佳做法

您會發現管理使用者旅程可能相當困難，因為使用者可能會在 SPA 的任何 URL 上登陸，並導覽至任何其他頁面。因此，建議您指定包含基底 URL 的頁面傳送規則，這樣就會包含整個 SPA。如此一來，您就不需要思考使用者為了抵達您要顯示A/B測試或體驗鎖定目標(XT)活動的頁面，可能會採取的所有不同歷程和路徑。

例如，為解決遇到的上述問題，我們可以在頁面傳送設定中指定下列基底 URL:

![頁面傳送對話方塊](/help/main/c-experiences/assets/conclusion.png)

這樣可以確保無論訪客在 SPA 上的哪個位置登陸以及導覽至首頁或頁面檢視，都會看見套用的動作。

現在，每當您將動作新增至SPA VEC中的檢視，就會顯示下列快顯訊息，提醒您思考[!UICONTROL Page Delivery]規則。

![頁面傳送設定訊息](/help/main/c-experiences/assets/pop-up-message.png)

當您為建立的每個新活動將第一個動作新增至檢視時，就會顯示此訊息。此訊息可協助確保組織中的所有人都瞭解如何正確套用這些[!UICONTROL Page Delivery]規則。

## 訓練影片: 在 Adobe Target 中使用適用於 SPA 的 VEC

>[!VIDEO](https://video.tv.adobe.com/v/26249)

如需詳細資訊，請參閱[在Adobe Target中使用適用於單頁應用程式的視覺化體驗撰寫器(SPA VEC) ](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html)。
