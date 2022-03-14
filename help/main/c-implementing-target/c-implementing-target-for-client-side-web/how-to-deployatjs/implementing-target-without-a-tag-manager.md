---
keywords: 實現目標；實現；實現at.js；標籤管理器；設備上決策；設備上決策；
description: 瞭解如何指定設定（帳戶詳細資訊、實現方法等） 執行Adobe [!DNL Target] at.js庫而不使用標籤管理器。
title: 能否實施 [!DNL Target] 沒有標籤管理器？
feature: Implement Server-side
role: Developer
exl-id: cb57f6b8-43cb-485d-a7ea-12db8170013f
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 52%

---

# 實施 [!DNL Target] 沒有標籤管理器

有關實施的資訊 [!DNL Adobe Target] 不使用標籤管理器或標籤 [!DNL Adobe Experience Platform]。

>[!NOTE]
>
>中的標籤 [Adobe Experience Platform](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是實現的首選方法 [!DNL Target] 和at.js圖書館。 在中使用標籤時不適用以下資訊 [!DNL Adobe Experience Platform] 執行 [!DNL Target]。

訪問 [!UICONTROL 實施] 的 **[!UICONTROL 管理]** > **[!UICONTROL 實施]**。

可以在此頁上指定以下設定：

* 帳戶詳細資訊
* 實現方法
* 配置檔案API
* 調試器工具
* 隱私權

>[!NOTE]
>
>您可以覆寫 at.js 資料庫中的設定，而非在 [!DNL Target Standard/Premium] UI  中或使用 REST API 進行設定。如需詳細資訊，請參閱 [targetGlobalSettings()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 帳戶詳細資訊

您可以查看以下帳戶詳細資訊。 無法更改這些設定。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 用戶端代碼] | 用戶端代碼是使用 [!DNL Target] API 時通常需要的用戶端專用字元序列。 |
| [!UICONTROL IMS 組織 ID] | 此 ID 會將您的實施連結至 [!DNL Adobe Experience Cloud] 帳戶。 |
| [!UICONTROL 設備上決策] | 要啟用設備上決策，請將切換滑至「開啟」位置。<br>設備上決策允許您快取A/B和 [!UICONTROL 體驗目標] (XT)在伺服器上開展活動，並在接近零的延遲下執行記憶體內決策。 有關詳細資訊，請參見 [設備上決策簡介](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) 的 *[!DNL Adobe Target]SDK* 的子菜單。 |
| [!UICONTROL 在項目中包括所有現有的設備上決策合格活動。] | （條件）如果啟用設備上決策，則顯示此選項。<br>如果希望所有符合設備上決策條件的活動自動包括在項目中，請將切換到「開啟」位置。<br>關閉此切換意味著必須重新建立並激活任何設備上的決策活動，以便將它們包括在生成的規則項目中。 |

## 實現方法

可以在「實施方法」面板中配置以下設定：

### 全局設定

>[!NOTE]
>
>這些設定將應用於所有 [!DNL Target] .js庫。 在「實施方法」部分執行更改後，必須下載庫並在實施中更新它。

| 設定 | 說明 |
| --- | --- |
| 已啟用頁面載入（自動建立全局框） | 選擇是否將全域 mbox 呼叫內嵌在 at.js 檔案中，以便每次載入頁面時自動觸發。 |
| 全域 mbox | 選取全域 mbox 的名稱。依預設，此名稱為 target-global-mbox。<br>對於 at.js，mbox 名稱中可以使用特殊字元 (包括 &amp;)。 |
| 超時（秒） | 如果 [!DNL Target] 在已定義的期間內沒有回應內容，伺服器呼叫會逾時，並顯示預設內容。在訪客工作階段期間會繼續嘗試其他呼叫。預設值為 5 秒。<br>at.js 程式庫會使用 `XMLHttpRequest` 中的逾時設定。逾時是在觸發請求時開始計時，而於 [!DNL Target] 從伺服器收到回應時停止。如需詳細資訊，請參閱 Mozilla 開發人員網路上的 [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout)。<br>如果在收到回應之前就發生指定的逾時，則會顯示預設內容，而訪客可能算為活動的參與者，因為所有資料收集都發生在 [!DNL Target] 邊緣。如果請求到達 [!DNL Target] 邊緣，訪客即納入計算。<br>設定逾時設定時，請考量下列事項:<ul><li>如果值太低，即使訪客應該算為活動的參與者，使用者還是可能幾乎都看到預設內容。</li><li>如果值太高，而如果您長時間使用本文隱藏，訪客可能會在網頁上看到空白區域或空白頁面。</li></ul>若要充分瞭解 mbox 回應時間，請在瀏覽器的開發人員工具中查看「網路」標籤。您也可以使用第三方 Web 效能監控工具，例如 Catchpoint。<br>**注意**: [visitorApiTimeout](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 設定可確保 [!DNL Target] 不會為了訪客 API 回應而等待太久。此設定和這裡說明的 at.js 逾時設定不影響彼此。 |
| 設定檔存留期 | 此設定會決定訪客設定檔儲存多久。依預設，訪客設定檔會儲存兩週。此設定最多可增加90天。<br>若要變更「設定檔存留期」設定，請聯絡[客戶服務](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html)。 |

### 一種主要實現方法

>[!IMPORTANT]
>
>目標團隊支援兩個at.js 1。*x* 與 at.js 2.*x* 之間的對應。升級到at.js的任一主版本的最新更新，以確保您正在運行受支援的版本。

要下載所需的at.js版本，請按一下相應的 **[!UICONTROL 下載]** 按鈕

要編輯at.js設定，請按一下 **[!UICONTROL 編輯]** 的子版本。

>[!IMPORTANT]
>
>在更改這些預設設定之前，請咨詢 [客戶端保護](/help/main/cmp-resources-and-contact-information.md) 這樣您就不會影響當前的實施。

除上述設定外，還提供以下特定的at.js設定：

| 設定 | 說明 |
|--- |--- |
| 自定義庫標題 | 新增任何自訂 JavaScript 以包括在資料庫頂端。 |
| 自定義庫頁腳 | 新增任何自訂 JavaScript 以包含在程式庫底部。 |

### 配置檔案API

啟用或停用透過 API 批次更新的驗證，並產生設定檔驗證 Token。

有關詳細資訊，請參見 [配置檔案API設定](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md)。

### 調試器工具

生成使用高級的授權令牌 [!DNL Target] 調試工具。 按一下 **[!UICONTROL 生成新身份驗證令牌]**。

![產生新驗證權杖](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### 隱私權

這些設定允許您使用 [!DNL Target] 符合適用的資料隱私法。

從「混淆訪問者IP地址」下拉清單中選擇所需的設定：

* 上次八位數模糊處理
* 整個IP混淆
* 無

如需詳細資訊，請參閱[隱私權](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)。

>[!NOTE]
>
>早期瀏覽器支援選項在at.js 0.9.3版及更低版本中提供。 at.js 0.9.4 版中移除了此選項。如需 at.js 支援的瀏覽器清單，請參閱[支援的瀏覽器](/help/main/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。<br>舊版瀏覽器是指不完全支援 CORS (跨來源資源共用) 的舊型瀏覽器。這些瀏覽器包括 Internet Explorer 瀏覽器 11 版以前的版本，以及 Safari 6 版及更舊版本。如果禁用了舊式瀏覽器支援，則目標未在這些瀏覽器上的報告中提供內容或計數訪問者。 如果啟用了此選項，建議跨較舊的瀏覽器執行質量保證以確保獲得良好的客戶體驗。

## 下載 at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

使用 [!DNL Target] 介面或下載API。

>[!NOTE]
>
>* [[!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是實現的首選方法 [!DNL Target] 和at.js圖書館。 在中使用標籤時不適用以下資訊 [!DNL Adobe Experience Platform] 執行 [!DNL Target]。
>
>* 的 [!DNL Target] 團隊支援at.js 1。*x* 與 at.js 2.*x* 之間的對應。請升級到at.js的任一主版本的最新更新，以確保您正在運行受支援的版本。 如需每一個版本有何功能的詳細資訊，請參閱 [at.js 版本詳細資料](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。


### 使用 [!DNL Target] 介面 {#section_1F5EE401C2314338910FC57F9592894E}

若要從 [!DNL at.js] 介面下載 [!DNL Target]:

1. 按一下「**[!UICONTROL 管理]** > 「**[!UICONTROL 實施]**」。
1. 從 [!UICONTROL 實現方法] 的 **[!UICONTROL 下載]** 按鈕。

### 使用 [!DNL Target] 下載API {#section_C0D9D2A9068144708D08526BA5CA10D0}

若要使用 API 來下載 [!DNL at.js]:

1. 取得用戶端程式碼。

   您的客戶端代碼位於 **[!UICONTROL 管理]** > **[!UICONTROL 實施]** 的 [!DNL Target] 。

1. 取得您的管理員編號。

   載入此 URL:

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   替換 `client code` 與步驟1中的客戶機代碼。

   載入此 URL 的結果應該類似下列範例:

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   在此範例中，&quot;6&quot; 是管理員編號。

1. 下載 [!DNL at.js]。

   使用下列結構載入此 URL:

   ```
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * 替換 `admin number` 管理員號碼。
   * 替換 `client code` 與步驟1中的客戶機代碼。
   * 替換 `version number` 帶有所需的at.js版本號（例如2.2）。

   >[!IMPORTANT]
   >
   >Target 團隊只會維護兩個 [!DNL at.js] 版本: 最新版本和次新版本。請視需要升級 [!DNL at.js]，以確保您執行的是支援的版本。如需每一個版本有何功能的詳細資訊，請參閱 [at.js 版本詳細資料](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。

   載入此 URL 會開始下載自訂的 [!DNL at.js] 檔案。

## at.js 實施 {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js 應實作於網站上每個頁面的 `<head>` 元素中。

不使用標籤管理器（如中的標籤）的目標的典型實現 [[!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 看起來是這樣的：

```
<!doctype html> 
<html> 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head>
<body> 
    The default content of the page 
</body> 
</html>
```

請考量下列重要注意事項:

* HTML5 Doctype(例如， `<!doctype html>`)。 不支援或舊版 doctype 可能會造成 Target 無法提出要求。
* 「預先連結」和「預先擷取」可能有助於加速網頁載入。如果使用這些配置，請確保替換 `<client code>` 你自己的客戶代碼，你可以從 **[!UICONTROL 管理]** > **[!UICONTROL 實施] 的子菜單。
* 如果有資料層，最好在 at.js 載入前，盡可能在網頁的 `<head>` 中詳細定義。此位置提供了在目標中使用此資訊進行個性化的最大能力。
* 特殊 Target 函數 (如 `targetPageParamsAll()`、`targetPageParams()`、資料提供者和 `targetGlobalSettings()`)，應在資料層載入後和 at.js 載入前定義。或者，這些函式可保存在 [!UICONTROL 庫標題] 的下界 [!UICONTROL 編輯at.js設定] 並保存為at.js庫本身的一部分。 有關這些功能的詳細資訊，請參見 [at.js函式](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。
* 如果使用JavaScript幫助程式庫（如jQuery），請在Target之前包括它們，以便在生成Target體驗時可以使用它們的語法和方法。
* 在網頁的 `<head>` 中加入 at.js。

## 跟蹤轉換 {#task_E85D2F64FEB84201A594F2288FABF053}

訂購確認 mbox 會記錄關於您的網站上訂單的詳細資料，並允許根據收入和訂單報告。訂購確認 mbox 也可以促進建議演算法，例如「購買了產品 x、也購買了產品 y 的使用者」

>[!NOTE]
>
>如果用戶在您的網站上進行購買，則Adobe建議即使您將目標分析(A4T)用於報告，也應實施「訂單確認」框。

1. 在訂單詳細資料頁面中，請依照下方的模式插入 mbox 指令檔。
1. 使用目錄中的動態或靜態值來取代大寫的字母。

   >[!NOTE]
   >
   >請使用逗號來隔開多個產品 ID。

   **提示:** 您也可以在任何 mbox 中傳遞訂單資訊 (名稱不需是 `orderConfirmPage`)。您也可以將訂單資訊傳遞至同一個促銷活動中的多個 mbox。

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

「訂購確認」mbox 會使用下列參數:

| 參數 | 說明 |
|--- |--- |
| orderId | 要進行轉換計算之訂單的唯一識別值。<br>`orderId` 必須是唯一的。報表中會忽略重複的訂單。 |
| orderTotal | 購買貨幣值。<br>請勿加上貨幣符號。請使用小數點 (而非逗點) 表示小數值。 |
| productPurchasedId (選用) | 訂單中購買之產品 ID 的逗點分隔清單。<br>這些產品 ID 會顯示在稽核報表中，以支援其他報表分析。 |
