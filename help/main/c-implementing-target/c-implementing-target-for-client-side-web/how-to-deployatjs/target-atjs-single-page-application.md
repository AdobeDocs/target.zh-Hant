---
keywords: 單頁應用程式實現；單頁應用程式；spa;at.js 2.x;at.js；單頁應用程式；單頁應用程式；spaSPA;
description: 瞭解如何使用Adobe [!DNL Target] at.js 2.x要實現 [!DNL Target] 頁面應用程式(SPA)。
title: 能否實施 [!DNL Target] 是SPA否？
feature: Implement Server-side
role: Developer
exl-id: 624f8e62-b443-4093-8e05-9320a365ea07
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '2794'
ht-degree: 69%

---

# 實作單頁應用程式

傳統的網站採用「頁面至頁面」導覽模型 (又稱為「多頁應用程式」)，網站設計與 URL 緊密結合，而從某網頁轉換到另一個網頁，需要頁面載入。單頁應用程式 (SPA) 這類新式 Web 應用程式採用的模型，則可加速瀏覽器 UI 演算速度，且通常與頁面重新載入無關。這些體驗通常會透過客戶互動觸發，例如捲動、點按和游標動作。隨著現代網路環境的不斷演進，傳統的一般事件 (例如頁面載入) 與部署個人化與實驗法之間的相關性已失效。

![傳統頁面生命週期與 SPA 生命週期比較](/help/main/c-experiences/assets/trad-vs-spa.png)

at.js 2.x 提供豐富的功能，讓貴公司能以新世代用戶端技術為基礎進行個人化。此版本著重於改善 at.js 與 SPA 之間的協調互動。

以下為使用 at.js 2.x 可享有但舊版不提供的優點:

* 可在頁面載入時快取所有選件，以減少對單一伺服器呼叫發出的多個伺服器呼叫。
* 顯著改善網站使用者體驗，因為可透過快取立即顯示選件，而不會發生傳統伺服器呼叫造成的時間延遲。
* 簡單的單行程式碼和一次性開發人員設定，讓行銷人員可透過 VEC 在 SPA 上建立和執行 A/B 和體驗目標鎖定 (XT) 活動。

## Adobe [!DNL Target] 視圖和單頁應用程式

適用於 SPA 的Adobe Target VEC 充分利用「檢視」的新概念: 視覺元素的邏輯組合，共同構成 SPA 體驗。因此，SPA 可以視為根據使用者互動轉換檢視，而不是轉換 URL。檢視通常可代表整個網站或網站內的分組視覺元素。

為了進一步說明檢視，下文將瀏覽這個在 React 中實作的假想線上電子商務網站，並探索一些檢視範例。按一下底下的連結，在新的瀏覽器分頁中開啓此網站。

**連結： [首頁](https://target.enablementadobe.com/react/demo/#/)**

![首頁](/help/main/c-experiences/assets/home.png)

導覽至首頁時，可以馬上看到宣傳復活節特賣活動的主圖影像，以及網站上販售的最新產品。在這個案例中，檢視可定義為整個首頁。請記下這點，因為我們將在下文的「實作 Adobe Target 檢視」一節中更深入說明。

**連結： [產品站點](https://target.enablementadobe.com/react/demo/#/products)**

![產品網站](/help/main/c-experiences/assets/product-site.png)

由於我們對這間商店販賣的產品越來越感興趣，因此決定按一下「產品」連結。與首頁相似，產品網站整體可定義為一個檢視。我們可以將這個檢視命名為「products」，就像 `https://target.enablementadobe.com/react/demo/#/products)` 中的路徑名稱一樣。

![產品網站 2](/help/main/c-experiences/assets/product-site-2.png)

本節的一開始，我們將檢視定義為整個網站或網站上的一組視覺元素。如上所示，網站上顯示的四個產品也可分組並視為檢視。如果想對這個檢視命名，可以將它命名為「Products」。

![產品網站 3](/help/main/c-experiences/assets/product-site-3.png)

我們決定按一下「載入更多」按鈕，探索這個網站上的更多產品。在此情況下，網站 URL 不會變更。但此處的檢視只能呈現上圖中的第二列產品。該檢視的名稱可為「PRODUCTS-PAGE-2」。

**連結： [簽出](https://target.enablementadobe.com/react/demo/#/checkout)**

![結帳頁面](/help/main/c-experiences/assets/checkout.png)

因為我們喜歡網站上展示的一些產品，所以決定購買幾項產品。現在，結帳網站提供我們幾個選項，可選擇一般配送或快捷配送。因為檢視可為網站上的任何一組視覺元素，因此可將這個檢視命名為「View Delivery Preferences」。

此外，檢視概念還可進一步延伸。如果行銷人員想要根據選取的配送偏好設定個人化網站內容，可針對每個配送偏好設定建立一個檢視。在這種情況下，當選取了「一般配送」時，就可以將檢視命名為「一般配送」。如果選取「快捷配送」，就可以將檢視命名為「快捷配送」。

假設現在行銷人員想執行 A/B 測試，以瞭解當選取「快捷配送」時，相較於讓這兩種配送選項的按鈕均保持藍色，按鈕從藍色變為紅色是否能增加轉換次數。

## 實施Adobe [!DNL Target] 視圖

我們已在上文中介紹 Adobe Target 檢視的功能，現在可以在 Target 中運用這個概念，讓行銷人員透過 VEC 在 SPA 上執行 A/B 和 XT 測試。進行測試需要一次性開發人員設定。以下逐一說明設定步驟。

1. 安裝 at.js 2.x。

   首先需要安裝 at.js 2.x。這個 at.js 版本是針對 SPA 所開發。以前版本的at.js和mbox.js（現已棄用）不支援的Adobe Target視圖和VECSPA。

   通過位於以下位置的Adobe TargetUI下載at.js 2.x [!UICONTROL 管理>實施]。 at.js 2.x還可以通過中的標籤進行部署 [!DNL Adobe Experience Platform]。

1. 在您的網站上實作 at.js 2.x 的最新函數 `triggerView()`。

   定義您要執行 A/B 或 XT 測試的 SPA 的檢視後，使用傳入作為參數的檢視來實作 at.js 2.x 的 `triggerView()` 函數。這麼做可讓行銷人員針對已定義檢視，使用 VEC 設計和執行的 A/B 和 XT 測試。如果沒有針對這些檢視定義 `triggerView()` 函數，VEC 將無法偵測檢視，進而導致行銷人員無法使用 VEC 來設計和執行 A/B 和 XT 測試。

   **`adobe.target.triggerView(viewName, options)`**

   | 參數 | 類型 | 必要? | 驗證 | 說明 |
   | --- | --- | --- | --- | --- |
   | viewName | 字串 | 是 | 1. 尾端無空格。<br>2.不得空白。<br>3.所有頁面的檢視名稱都不得重複。<br>4.**警告**: 檢視名稱的開頭或結尾不能為「`/`」。這是因為客戶通常會從 URL 路徑中擷取檢視名稱。對我們來說，「home」和「`/home`」是不一樣的。<br>5.**警告**: 同一個檢視不應使用 `{page: true}` 選項連續觸發多次。 | 傳入任何名稱作為要代表檢視的字串類型。此檢視名稱會顯示在 VEC 的[!UICONTROL 「修改」]面板中，供行銷人員建立動作和執行 A/B 與 XT 活動。 |
   | options | 物件 | 無 |  |  |
   | options > page | 布林值 | 無 |  | **TRUE:** 頁面的預設值為 true。當 `page=true`，會傳送通知至 Edge 伺服器以增加曝光計數。<br>**FALSE**: 當 `page=false`，不會傳送通知以增加曝光計數。只有當您想重新呈現頁面上含有某個選件的元件時，才應使用此項目。 |

   以下提供幾個範例使用案例，說明如何在 React 中叫用 `triggerView()` 函數以用於我們的假想電子商務 SPA:

   **連結： [首頁](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/main/c-experiences/assets/react1.png)

   行銷人員如果想在整個首頁上執行 A/B 測試，可以將該檢視命名為「home」:

```
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

**連結： [產品站點](https://target.enablementadobe.com/react/demo/#/products)**

現在，讓我們來看看更複雜的範例。假設我們是行銷人員，我們想在使用者按下「載入更多」按鈕後，將「價格」標籤的顏色變更為紅色，用這個方式將第二列產品個人化。

![react 產品](/help/main/c-experiences/assets/react4.png)

```
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
     var page = this.state.page + 1; // assuming page number is derived from component’s state
     this.setState({page: page});
     targetView('PRODUCTS-PAGE-' + page);
   }
 }
```

**連結： [簽出](https://target.enablementadobe.com/react/demo/#/checkout)**

![react 結帳](/help/main/c-experiences/assets/react6.png)

如果行銷人員想要根據選取的配送偏好設定個人化網站內容，可針對每個配送偏好設定建立一個檢視。在這種情況下，當選取了「一般配送」時，就可以將檢視命名為「一般配送」。如果選取「快捷配送」，就可以將檢視命名為「快捷配送」。

假設現在行銷人員想執行 A/B 測試，以瞭解當選取「快捷配送」時，相較於讓這兩種配送選項的按鈕均保持藍色，按鈕從藍色變為紅色是否能增加轉換次數。

```
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

## at.js 2.x 系統圖表

下列圖表可協助您瞭解 at.js 2.x 搭配檢視的工作流程，以及如何藉由這套工作流程增強 SPA 整合。要更好地介紹at.js 2.x中使用的概念，請參見 [單頁應用程式實現](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/){target=_blank}。

![使用 at.js 2.x 的 Target 流程](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 步驟 | 詳細資料 |
| --- | --- |
| 1 | 如果使用者已通過驗證，呼叫會傳回 [!DNL Experience Cloud ID]，而另一個呼叫會同步客戶 ID。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>也能使用將頁面上實作的程式碼片段預先隱藏的選項，以非同步方式載入 at.js。 |
| 3 | 提出頁面載入要求，包含所有已設定的參數 (MCID、SDID 和客戶 ID)。 |
| 4 | 個人資料指令碼執行，然後注入個人資料存放區。存放區會從受眾資料庫中請求合格受眾 (例如，從 Adobe Analytics、受眾管理等共用的受眾)。<br>客戶屬性會透過批次程序傳送至個人資料存放區。 |
| 5 | [!DNL Target] 會根據 URL 要求參數和個人資料，決定可針對目前頁面和未來檢視傳回哪些活動和體驗給訪客。 |
| 6 | 目標內容會傳回至頁面，選擇性地包括其他個人化的個人資料值。<br>目前頁面上目標內容會儘快出現，不會有忽隱忽現的預設內容。<br>針對在瀏覽器中快取的使用者 SPA 動作顯示檢視的目標內容，以便在透過 `triggerView()` 觸發檢視時立刻套用，不需額外的伺服器呼叫。 |
| 7 | Analytics 資料傳送至「資料收集」伺服器。 |
| 8 | 目標資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 Analytics for Target (A4T) 報表來檢視 <br>Analytics 資料。 |

現在，SPA 上只要是有實作 `triggerView()` 的位置，系統都會從快取擷取檢視和動作並向使用者顯示，不需要伺服器呼叫。`triggerView()` 也會對 [!DNL Target] 後端發出通知要求，以便增加和記錄曝光計數。

![Target 流程 at.js 2.x triggerView](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 步驟 | 詳細資料 |
| --- | --- |
| 1 | 系統在 SPA 中呼叫 `triggerView()`，以便呈現檢視和套用動作來修改視覺元素。 |
| 2 | 從快取讀取檢視的目標內容。 |
| 3 | 目標內容會儘快出現，不會有忽隱忽現的預設內容。 |
| 4 | 通知要求會傳送至 [!DNL Target] 個人資料存放區，以計算活動中的訪客數和增加量度。 |
| 5 | Analytics 資料傳送至資料收集伺服器。 |
| 6 | Target 資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 A4T 報表來檢視 Analytics 資料。 |

## 單一頁面應用程式可視化體驗撰寫器

安裝 at.js 2.x 並將 `triggerView()` 新增至您的網站後，請使用 VEC 執行 A/B 和 XT 活動。如需詳細資訊，請參閱[單頁應用程式 (SPA) 可視化體驗撰寫器](/help/main/c-experiences/spa-visual-experience-composer.md)。

>[!NOTE]
>
>適用於 SPA 的 VEC 與您用於一般網頁的 VEC 完全相同，不過當您開啟實作了 `triggerView()` 的單頁應用程式時，會提供一些額外功能讓您使用。

## 使用 TriggerView，確保 A4T 可搭配 at.js 2.x 和 SPA 正常運作 {#triggerview}

若要確保 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) 可搭配 at.js 2.x 正常運作，請務必在 Target 要求和 Analytics 要求中傳送相同的 SDID。

SPA 相關最佳實務如下:

* 使用自訂事件通知應用程式中發生了有趣的內容
* 在檢視開始呈現前觸發自訂事件
* 在檢視完成呈現時觸發自訂事件

at.js 2.x添加了一個新API [triggerView()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/){target=_blank}函式。 您應使用 `triggerView(){target=_blank}` 通知 at.js 檢視將開始呈現。

若要查看如何合併自訂事件、at.js 2.x 和 Analytics，請參考以下範例。此範例假設 HTML 頁面包含訪客 API，隨後是 at.js 2.x，隨後是 AppMeasurement。

假設存在下列自訂事件:

* `at-view-start` - 檢視開始呈現時
* `at-view-end` - 檢視完成呈現時

若要確保 A4T 可搭配 at.js 2.x 正常運作，

檢視開始處理常式應如下所示:

```
document.addEventListener("at-view-start", function(e) {
  var visitor = Visitor.getInstance("<your Adobe Org ID>");
  
  visitor.resetState();
  adobe.target.triggerView("<view name>");
});
```

檢視結束處理常式應如下所示:

```
document.addEventListener("at-view-end", function(e) {
  // s - is the AppMeasurement tracker object
  s.t();
});
```

>[!NOTE]
>
>您必須觸發 `at-view-start` 和 `at-view-end` 事件。這些事件不是 at.js 自訂事件的一部分。

儘管這些示例使用JavaScript代碼，但如果使用標籤管理器，則所有這些都可以簡化，如中的標籤 [Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}。

如果您按照上述步驟進行，您應該能擁有適用於 SPA 的健全 A4T 解決方案。

## 實施最佳做法 {#bp}

at.js 2.x API允許您自定義 [!DNL Target] 但在執行過程中，必須遵循正確的操作順序。

以下資訊描述了首次在瀏覽器中載入單頁應用程式時必須遵循的操作順序，以及隨後發生的任何視圖更改。

### 初始頁載入的操作順序

| 步驟 | Action | 詳細資料 |
| --- | --- | --- |
| 1 | 載入VisitorAPI JS | 此庫負責為訪問者分配ECID。 此ID稍後會被其他 [!DNL Adobe] 解決方案。 |
| 2 | 載入at.js 2.x | at.js 2.x載入用於實現的所有必需API [!DNL Target] 請求和視圖。 |
| 3 | 執行 [!DNL Target] 請求 | 如果您有資料層，我們建議您載入發送到的關鍵資料 [!DNL Target] 執行前 [!DNL Target] 請求。 這樣您就可以 `targetPageParams` 發送任何要用於目標的資料。 必須確保在此API調用中請求執行> pageLoad以及預回遷>視圖。 如果你 `pageLoadEnabled` 和 `viewsEnabled`，然後執行> pageLoad和prefetch >視圖隨步驟2自動發生；否則，你需要 `getOffers()` 發出此請求的API。 |
| 4 | 呼叫 `triggerView()` | 因為 [!DNL Target] 在步驟3中啟動的請求可以返回執行頁面載入和視圖的體驗，確保 `triggerView()` 在 [!DNL Target] 請求將返回並完成對快取應用優惠。 每個視圖只能執行此步驟一次。 |
| 5 | 呼叫 [!DNL Analytics] 頁面視圖信標 | 此信標將與步驟3和步驟4關聯的SDID發送到 [!DNL Analytics] 資料拼接。 |
| 6 | 呼叫其他 `triggerView({"page": false})` | 這是框架的可選步驟SPA，該框架可能在不發生視圖更改的情況下重新呈現頁面上的某些元件。 在這些情況下，您必須調用此API以確保 [!DNL Target] 在框架重新呈現元件SPA後重新應用經驗。 您可以執行此步驟的次數，以確保 [!DNL Target] 你的觀點中仍SPA有經驗。 |

### 視圖更改的SPA操作順序（無全頁重裝）

| 步驟 | 操作 | 詳細資料 |
| --- | --- | --- |
| 1 | 呼叫 `visitor.resetState()` | 此API確保在載入新視圖時重新生成SDID。 |
| 2 | 通過調用 `getOffers()` API | 如果此視圖更改有可能限定當前訪問者獲得更多資訊，則此步驟是可選步驟 [!DNL Target] 或取消活動資格。 此時，您還可以選擇向 [!DNL Target] 以啟用進一步的瞄準功能。 |
| 3 | 呼叫 `triggerView()` | 如果已執行步驟2，則必須等待 [!DNL Target] 請求並應用優惠以執行此步驟。 每個視圖只能執行此步驟一次。 |
| 4 | 呼叫 `triggerView()` | 如果尚未執行步驟2，則完成步驟1後即可執行此步驟。 如果已執行步驟2和步驟3，則應跳過此步驟。 每個視圖只能執行此步驟一次。 |
| 5 | 呼叫 [!DNL Analytics] 頁面視圖信標 | 此信標將與步驟2、3和4關聯的SDID發送到 [!DNL Analytics] 資料拼接。 |
| 6 | 呼叫其他 `triggerView({"page": false})` | 這是框架的可選步驟SPA，該框架可能在不發生視圖更改的情況下重新呈現頁面上的某些元件。 在這些情況下，您必須調用此API以確保 [!DNL Target] 在框架重新呈現元件SPA後重新應用經驗。 您可以執行此步驟的次數，以確保 [!DNL Target] 你的觀點中仍SPA有經驗。 |

## 訓練影片

以下影片包含更多資訊:

### 瞭解 at.js 2.x 的運作方式 ![總覽徽章](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/26250)

如需詳細資訊，請參閱[ 了解 at.js 2.x 的運作方式](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html)。

### 在中實現at.js 2.x SPA ![教程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/26248)

請參閱 [在單頁應用程式中實施Adobe Target的at.js 2.x(SPA)](https://helpx.adobe.com/target/kt/using/atjs2-single-page-application-technical-video-implement.html) 的子菜單。

### 將VEC用於SPAAdobe Target ![教程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/26249)

請參閱 [在Adobe Target使用Visual Experience Composer實現單頁應用程SPA序(VEC)](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) 的子菜單。
