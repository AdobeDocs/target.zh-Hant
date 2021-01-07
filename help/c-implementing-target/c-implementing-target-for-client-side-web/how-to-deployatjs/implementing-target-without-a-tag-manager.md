---
keywords: implement target;implementation;implement at.js;tag manager
description: 不使用標籤管理程式 (Adobe Launch 或動態標籤管理) 實作 Adobe Target 的相關資訊。
title: 不使用標籤管理程式實作 Target
feature: Implementation
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '1539'
ht-degree: 70%

---


# 不使用標籤管理程式實作 Target{#implement-target-without-a-tag-manager}

有關不使用標籤管理器（[!DNL Adobe Launch]或[!DNL Dynamic Tag Manager]）實作[!DNL Adobe Target]的資訊。

>[!NOTE]
>
>[推薦使用 Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 實作 Target 和 at.js 程式庫。下列資訊不適用於使用 Adobe Launch 實作 Target。

要訪問[!UICONTROL 實施]頁，請按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 實施]**。

您可以在此頁面上指定下列設定：

* 帳戶詳細資訊
* 實施方法
* 設定檔API
* 除錯工具
* 隱私權

>[!NOTE]
>
>您可以覆寫 at.js 資料庫中的設定，而非在 Target Standard/Premium UI 中或使用 REST API 進行設定。如需詳細資訊，請參閱 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 帳戶詳細資訊

您可以檢視下列帳戶詳細資訊。 這些設定無法變更。

| 設定 | 說明 |
| --- | --- |
| 用戶端代碼 | 用戶端代碼是使用 Target API 時通常需要的用戶端專用字元序列。 |
| IMS 組織 ID | 此 ID 會將您的實施連結至 [!DNL Adobe Experience Cloud] 帳戶。 |

## 實施方法

可在「實施方法」面板中設定下列設定：

### 全域設定

>[!NOTE]
>
>這些設定會套用至所有[!DNL Target] .js程式庫。 在[!UICONTROL 實作方法]區段中執行變更後，您需要下載程式庫並在實作中更新它。

| 設定 | 說明 |
| --- | --- |
| 啟用頁面載入（自動建立全域mbox） | 選擇是否將全域 mbox 呼叫內嵌在 at.js 檔案中，以便每次載入頁面時自動觸發。 |
| 全域 mbox | 選取全域 mbox 的名稱。依預設，此名稱為 target-global-mbox。<br>對於 at.js，mbox 名稱中可以使用特殊字元 (包括 &amp;)。 |
| 逾時（秒） | 如果 [!DNL Target] 在已定義的期間內沒有回應內容，伺服器呼叫會逾時，並顯示預設內容。在訪客工作階段期間會繼續嘗試其他呼叫。預設值為 5 秒。<br>at.js 程式庫會使用 `XMLHttpRequest` 中的逾時設定。逾時是在觸發請求時開始計時，而於 [!DNL Target] 從伺服器收到回應時停止。如需詳細資訊，請參閱 Mozilla 開發人員網路上的 [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout)。<br>如果在收到回應之前就發生指定的逾時，則會顯示預設內容，而訪客可能算為活動的參與者，因為所有資料收集都發生在 [!DNL Target] 邊緣。如果請求到達 [!DNL Target] 邊緣，訪客即納入計算。<br>設定逾時設定時，請考量下列事項:<ul><li>如果值太低，即使訪客應該算為活動的參與者，使用者還是可能幾乎都看到預設內容。</li><li>如果值太高，而如果您長時間使用本文隱藏，訪客可能會在網頁上看到空白區域或空白頁面。</li></ul>若要充分瞭解 mbox 回應時間，請在瀏覽器的開發人員工具中查看「網路」標籤。您也可以使用第三方 Web 效能監控工具，例如 Catchpoint。<br>**注意**: [visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 設定可確保 [!DNL Target] 不會為了訪客 API 回應而等待太久。此設定和這裡說明的 at.js 逾時設定不影響彼此。 |
| 設定檔存留期 | 此設定會決定訪客設定檔儲存多久。依預設，訪客設定檔會儲存兩週。最多可增加至 90 天。<br>若要變更「設定檔存留期」設定，請聯絡[客戶服務](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html)。 |

### 一種主要實現方法

>[!IMPORTANT]
>
>Target團隊同時支援at.js 1。*x* 與 at.js 2.*x* 之間的對應。請升級至任一主要版本的最新更新at.js，以確保您執行的是支援的版本。

若要下載所需的at.js版本，請按一下適當的&#x200B;**[!UICONTROL 下載]**&#x200B;按鈕。

若要編輯at.js設定，請按一下所要at.js版本旁的&#x200B;**[!UICONTROL Edit]**。

>[!IMPORTANT]
>
>在變更這些預設設定之前，請諮詢[Client Care](/help/cmp-resources-and-contact-information.md)，以免影響您目前的實作。

除了上述設定外，還提供下列特定at.js設定：

| 設定 | 說明 |
|--- |--- |
| 自訂資料庫標題 | 新增任何自訂 JavaScript 以包括在資料庫頂端。 |
| 自訂資料庫頁尾 | 新增任何自訂 JavaScript 以包含在程式庫底部。 |

### 設定檔API

啟用或停用透過 API 批次更新的驗證，並產生設定檔驗證 Token。

如需詳細資訊，請參閱[描述檔API設定](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md)。

### 除錯工具

產生授權Token以使用進階的[!DNL Target]除錯工具。 按一下「產生新驗證Token ]**」。**[!UICONTROL 

![產生新的驗證Token](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### 隱私權

這些設定可讓您使用[!DNL Target]，以符合適用的資料隱私法。

從「模糊化訪客IP位址」下拉式清單中選擇所要的設定：

* 最後八位元模糊化
* 整個IP模糊化
* 無

如需詳細資訊，請參閱[隱私權](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)。

>[!NOTE]
>
>at.js 0.9.3版及舊版中提供「舊版瀏覽器支援」選項。 at.js 0.9.4 版中移除了此選項。如需 at.js 支援的瀏覽器清單，請參閱[支援的瀏覽器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。<br>舊版瀏覽器是指不完全支援 CORS (跨來源資源共用) 的舊型瀏覽器。這些瀏覽器包括 Internet Explorer 瀏覽器 11 版以前的版本，以及 Safari 6 版及更舊版本。如果已停用舊版瀏覽器支援，Target不會在這些瀏覽器的報表中傳送內容或計算訪客。 如果啟用此選項，建議您跨舊版瀏覽器執行品質保證，以確保良好的客戶體驗。

## 下載 at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

使用[!DNL Target]介面或下載API下載程式庫的指示。

>[!NOTE]
>
>* [推薦使用 Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 實作 Target 和 at.js 程式庫。下列資訊不適用於使用 Adobe Launch 實作 Target。
   >
   >
* Target團隊同時支援at.js 1。*x* 與 at.js 2.*x* 之間的對應。請升級至任一主要版本的最新更新at.js，以確保您執行的是支援的版本。 如需每一個版本有何功能的詳細資訊，請參閱 [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。


### 使用Target介面{#section_1F5EE401C2314338910FC57F9592894E}下載at.js

若要從 [!DNL at.js] 介面下載 [!DNL Target]:

1. 按一下「**[!UICONTROL 管理]** > **[!UICONTROL 實施]**」。
1. 在[!UICONTROL 實作方法]區段中，按一下所需at.js版本旁的&#x200B;**[!UICONTROL 下載]**&#x200B;按鈕。

### 使用Target Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}下載at.js

若要使用 API 來下載 [!DNL at.js]:

1. 取得用戶端程式碼。

   您的客戶端代碼位於[!DNL Target]介面的&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 實施]**&#x200B;頁面的頂部。

1. 取得您的管理員編號。

   載入此 URL:

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   將`client code`取代為步驟1的用戶端程式碼。

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

   * 將`admin number`取代為您的管理員編號。
   * 將`client code`取代為步驟1的用戶端程式碼。
   * 將`version number`取代為所需的at.js版本號碼（例如2.2）。

   >[!IMPORTANT]
   >
   >Target 團隊只會維護兩個 [!DNL at.js] 版本: 最新版本和次新版本。請視需要升級 [!DNL at.js]，以確保您執行的是支援的版本。如需每一個版本有何功能的詳細資訊，請參閱 [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。

   載入此 URL 會開始下載自訂的 [!DNL at.js] 檔案。

## at.js實作{#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js 應實作於網站上每個頁面的 `<head>` 元素中。

一般 Target 實作 (不使用 [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 或[動態標籤管理](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96)這類標籤管理程式) 看起來就像這樣:

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

* 應使用 HTML5 Doctype (如 `<!doctype html>`)。不支援或舊版 doctype 可能會造成 Target 無法提出要求。
* 「預先連結」和「預先擷取」可能有助於加速網頁載入。如果您使用這些設定，請確定您以您自己的用戶端程式碼取代`<client code>`，您可從&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 實施]頁面取得。
* 如果有資料層，最好在 at.js 載入前，盡可能在網頁的 `<head>` 中詳細定義。這個位置能讓您在 Target 最大限度運用這類資料進行個人化。
* 特殊 Target 函數 (如 `targetPageParamsAll()`、`targetPageParams()`、資料提供者和 `targetGlobalSettings()`)，應在資料層載入後和 at.js 載入前定義。此外，這些函數亦可儲存於[!UICONTROL 「編輯 at.js 設定」]頁面的[!UICONTROL 「程式庫標題」]部分，並存入 at.js 程式庫本身。如需特殊函數的詳細資訊，請參閱 [at.js 函數](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。
* 如果使用 jQuery 等 JavaScript 輔助函式庫，請在 Target 前加入這些函式庫，以便在建立 Target 體驗時使用這些函式庫的語法和方法。
* 在網頁的 `<head>` 中加入 at.js。

## 追蹤轉換{#task_E85D2F64FEB84201A594F2288FABF053}

訂購確認 mbox 會記錄關於您的網站上訂單的詳細資料，並允許根據收入和訂單報告。訂購確認 mbox 也可以促進建議演算法，例如「購買了產品 x、也購買了產品 y 的使用者」

>[!NOTE]
>
>如果使用者在您的網站上進行購買，建議您實作訂購確認 mbox，即便您對報表使用 Analytics for Target (A4T) 亦然。

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