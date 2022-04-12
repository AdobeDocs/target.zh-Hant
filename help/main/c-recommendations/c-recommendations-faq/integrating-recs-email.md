---
keywords: 電子郵件;ESP;電子郵件服務提供者;rawbox;傳送 API;僅供下載的範本;電子郵件範本;批次處理;建置時間電子郵件
description: 了解如何將電子郵件與 Adobe [!DNL Target Recommendations], including using the [!DNL Target] 傳送 API、rawbox 範本及僅供下載的範本整合。
title: 如何將 Recommendations 與電子郵件整合？
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '1712'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) 將 [!DNL Recommendations] 與電子郵件整合

[!DNL Adobe Target] 支援電子郵件中推薦的傳送時間個人化。

三種 [!DNL Target Recommendations] 與電子郵件服務提供者 (ESP) 整合方法可供使用。您的 ESP 功能決定了要使用的方法。您的客戶經理或顧問可以幫助您選擇最適合您的選項。

| 方法 | 詳細資料 |
| --- | --- |
| [方法 1： [!DNL Adobe Target Delivery API]](#delivery-api) (偏好設定) | 使用 [!DNL Adobe Target Delivery API] 針對每位客戶/每封電子郵件提出推薦請求。 |
| [方法 2： [!DNL Adobe Rawbox API]](#rawbox) | 使用 [!DNL Adobe Target Rawbox API] 針對每位客戶/每封電子郵件提出推薦請求。 |
| [方法 3： [!DNL Recommendations Download API]](#download-api) | 使用 Recommendations Download API 以請求產品或類別清單 (CSV 格式) 的大量推薦。 |

使用方法 1 或方法 2 時，ESP 必須根據每位客戶/每封電子郵件對外部 API 進行呼叫，並等待傳回內容。並非所有 ESP 都支援這些方法；請聯絡您的 ESP 以判斷其是否與此整合模式相容。

使用方法 3 時，您的 ESP 必須依產品 ID 或類別 ID 將推薦清單聯結至您的電子郵件清單。此方法可以根據客戶上次檢視的產品、上次購買的產品或最常檢視的類別等屬性。但是，您的 ESP 必須在其客戶設定檔中擁有此資料的存取權，才能執行聯結。請聯絡您的 ESP 以判斷其是否具有此資料的存取權，而且與此整合模式相容。

[!DNL Adobe Target] 不支援推薦的開放時間個人化。

>[!IMPORTANT]
>
>下列容量指導方針適用於底下所述的傳送 API 和 rawbox 電子郵件範本方法 (方法 1 和 2)：
>
>* 請求的速率應該限制為每秒 1,000 個請求或每日尖峰流量的 25 倍，以較低者為準。
>* 每分鐘以每秒 200 個請求的速度遞增流量。
> 
>如果您想要使用較高的速率限制，請聯絡您的客戶經理。

## 方法 1：使用傳送 API (偏好設定) {#delivery-api}

傳送 API 是 POST 要求，可與建置時間電子郵件搭配使用。此選項是用於建置時間電子郵件偏好的方法。

大多數電子郵件用戶端不允許 POST 要求；因此，不建議針對開放時間使用案例使用此 API。 部分電子郵件用戶端 (例如 Gmail 或 Outlook) 可能會快取內容或封鎖影像，並要求收件者主動允許影像呈現。

您無法使用傳送 API 傳回預設內容。

下列程式碼是 API 傳送要求的範例:

```javascript
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

其中 `clientcode` 為您的 [!DNL Target] 用戶端代碼。

>[!NOTE]
>
>各電子郵件收件者 (例如，針對每個 API 呼叫) 的 `sessionId` 及 `tntId` 或 `thirdPartyId` 兩者之一，請務必提供唯一值。 如果您沒有為這些欄位提供唯一值，API 回應可能會因為在單一設定檔中產生的許多事件而變得緩慢或失敗。

如需詳細資訊，請參閱[傳送 API 文件](https://developers.adobetarget.com/api/#server-side-delivery)。

## 方法 2：使用 rawbox 電子郵件範本 {#rawbox}

rawbox 類似於 mbox 請求，但適用於非 Web 環境，例如電子郵件服務提供者 (ESP)。因為您沒有 [!DNL Adobe Experience Platform Web SDK] 或 [!DNL at.js] 可在 rawbox 請求中使用，所以您必須手動建立請求。以下範例說明如何在電子郵件中使用 rawbox 請求。

>[!NOTE]
>
>使用 rawbox 和 [!DNL Target] 時，請參閱「[建立允許清單，指定授權傳送 mbox 呼叫至  [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist) 的主機」底下的重要安全性注意事項。

透過該方法，您可在電子郵件中追蹤推薦的效能，以正常方式測試推薦，並繼續在網站上追蹤。

在 [!DNL Target] 中使用[「表單式體驗撰寫器」](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)選項設定 [!DNL Recommendations] 活動。針對位置，選取您選擇在來自 ESP 的 Rawbox 要求中使用的 mbox 的名稱。選取符合您對電子郵件所需外觀的設計。在電子郵件建置時，ESP 會對每個要產生的電子郵件中的每個 Rawbox 對 [!DNL Target] 伺服器進行呼叫。您的 ESP 必須有一個方式可在傳送的電子郵件中包括傳回的 HTML。

您使用的電子郵件系統必須能夠處理下列案例：

### 收到有效回應，但沒有建議

* 在此情況下，回應會是設為 `mboxDefault` 參數值的內容。 請參閱以下有關此參數的說明。
* 電子郵件提供者應該具有預設的建議 HTML 區塊，以在此情況下使用。

### [!DNL Target] 伺服器逾時，且未傳回任何資料

* 在此情況下，[!DNL Target] 伺服器將傳回下列內容：

   `//ERROR: application server timeout`

* 電子郵件應用程式應該搜尋該文字，而且必須能夠處理錯誤。電子郵件提供者有多個選項可用於處理此情況:

   * 立即嘗試另一個伺服器呼叫 (建議，也許可以使用嘗試計數器)。
   * 去除該特定電子郵件並繼續下一個電子郵件。
   * 將該特定電子郵件加入佇列，並在最初執行結束時，以批次形式重新執行失敗的電子郵件。

### 樣本請求 URL

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### 必要的參數： {#reqparams}

>[!NOTE]
>
>若要在電子郵件中使用 [!DNL Recommendations]，rawbox 呼叫通常必須包含 `entity.id` 或 `entity.categoryId` 或兩者同時包含 (視建議條件的類型而定)。 以上的樣本呼叫包括這兩者。

| 參數 | 值 | 說明 | 驗證 |
|--- |--- |--- |--- |
| `client_code` | *client_code* | 在 Recommendations 中所使用用戶端的程式碼。您的 Adobe 顧問可以提供此值。 |  |
| `mbox` | *mboxName* | 用於鎖定目標的 mbox 名稱。 | 對所有 mbox 呼叫使用相同的驗證身分。<br>250 個字元限制。<br>不能包含下列任一個字元：`', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | 已停用 | 防止回應在非 Web 環境中設定 Cookie。 |  |
| `entity.id`<br> (對某些類型的標準為必要：檢視/檢視、檢視/購買、購買/購買) | *entity_id* | 建議所根據的 productId，例如購物車中放棄的產品或先前的購買。<br>如果條件要求，rawbox 呼叫必須包括 `entity.id`。 |  |
| `entity.event.detailsOnly` | true | 如果傳遞了 `entity.id`，則非常建議您也傳遞此參數，以防止要求為了不要扭曲產品檢視式的演算法，而遞增專為某項目調整的頁面檢視數量。 |  |
| `entity.categoryId`<br> (對某些類型的標準為必要：檢視次數最多類別和最暢銷商品類別) | *category_id* | 類別建議的根據，例如類別中的最暢銷商品。<br>如果條件要求，rawbox 呼叫必須包括 `entity.categoryId`。 |  |
| `mboxDefault` | *`https://www.default.com`* | 如果 `mboxNoRedirect` 參數不存在，則在沒有可用的建議時，`mboxDefault` 應該是將傳回預設內容的絕對 URL。 此 URL 可以是影像或其他靜態內容。<br>如果有 `mboxNoRedirect` 參數，`mboxDefault` 可以是用來指示沒有建議的任何文字，例如 `no_content`。<br>電子郵件提供者必須處理傳回此值的情況，並將預設 HTML 插入電子郵件中。 <br> **安全性最佳做法**：如果不允許列出 `mboxDefault` URL 中使用的網域，則可能會面臨「開啟重新導向弱點」的風險。 為避免第三方未授權使用重導程式連結或 `mboxDefault`，Adobe 建議您使用「已授權的主機」來允許列出預設的重新導向 URL 網域。 Target 會使用主機來允許列出您想要允許重新導向的網域。 如需詳細資訊，請參閱「[建立允許清單，指定在 *Hosts* 中授權傳送 mbox 呼叫至  [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist) 的主機」。 |  |
| `mboxHost` | *mbox_host* | 這是呼叫觸發時新增至預設環境 (主機群組) 的網域。 |  |
| `mboxPC` | 空白 | (使用訪客的設定檔的建議為必要。)<br>如果未提供 &quot;thirdPartyId&quot;，則會產生新的 tntId，並隨著回應傳回。否則會保持空白。<br>**注意**：請務必為每個電子郵件收件人 (即每個 API 呼叫) 提供 `mboxSession` 和 `mboxPC` 的唯一值。如果您沒有為這些欄位提供唯一值，API 回應可能會因為在單一設定檔中產生的大量事件而變得緩慢或失敗。 | 1 &lt; 長度 &lt; 128<br>不能包含超過一個「.」(句點)。<br>允許的唯一一個句點用於設定檔位置字尾。 |

### 選用參數

| 參數 | 值 | 說明 | 驗證 |
|--- |--- |--- |--- |
| `mboxPC`<br>(可選) | *mboxPCId* | Target 訪客 ID。如果您想要追蹤使用者在多次造訪間完全回到您的網站，或使用使用者設定檔參數時，請使用此值。<br>此值必須是使用者的實際 [!DNL Adobe Target] PCID，它會從網站匯出至您的 CRM。 電子郵件提供者會從您的 CRM 或 Data Warehouse 擷取此 ID，並使用它做為此參數的值。<br>當建議屬於 A/B 活動時，`mboxPC` 值對於追蹤多次造訪的訪客網站行為以進行量度追蹤也很實用。<br>**注意**：請務必為每個電子郵件收件人 (即每個 API 呼叫) 提供 `mboxSession` 和 `mboxPC` 的唯一值。如果您沒有為這些欄位提供唯一值，API 回應可能會因為在單一設定檔中產生的大量事件而變得緩慢或失敗。 | 1 &lt; 長度 &lt; 128<br>不能包含超過一個「.」(句點)。<br>允許的唯一一個句點用於設定檔位置字尾。 |
| `mboxNoRedirect`<br>(可選) | 1 | 依預設，在找不到可傳遞的內容時會將呼叫端重新導向。用來停用預設行為。 |  |
| `mbox3rdPartyId` | *xxx* | 如果您有用於設定檔目標定位的自訂訪客 ID，請使用此選項。 |  |

### 可能的 [!DNL Target] 伺服器回應

| 回應 | 說明 |
|--- |--- |
| //錯誤: | 當它無法傳回內容時由負載平衡器產生 |
| 成功 | `mboxNoRedirect` 參數設為 &#39;true&#39;，而伺服器未傳回任何建議 (亦即，沒有 mbox 的相符項目或伺服器快取未初始化)。 |
| bad request | 遺漏 `mbox` 參數。<ul><li>`mboxDefault` 或 `mboxNoRedirect` 參數未指定。</li><li>`mboxTrace` 要求參數已指定但 `mboxNoRedirect` 未指定。</li><li>當 mbox 名稱的結尾是 `-clicked` 尾碼時，`mboxTarget` 參數未指定。</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | 當要求的相符項目不存在時，`mboxDefault` 未指定，並且 `mboxNoRedirect` 參數未指定。 |
| `Invalid mbox name:= MBOX_NAME` | 指出 `mbox` 參數包括無效的字元。 |
| `Mbox name [MBOX_NAME] is too long` | 指出 `mbox` 參數長於 250 個字元。 |

## 方法 3：使用 Recommendations Download API {#download-api}

照常設定建議，但選擇顯示區域中的&#x200B;**僅供下載**，而不是範本和 mbox 組合。然後在 ESP 中，告訴 ESP 您所建立的建議 ID。ESP 透過 API 存取建議資料。該資料顯示應為特定類別或主要項目所建議的項目，例如購物車中放棄的項目。ESP 會儲存資料，以其自身的外觀和感覺連接它，顯示各項目的相關資訊，並透過電子郵件傳送。

使用該選項， Recommendations 伺服器無法直接追蹤建議的效能，或將流量分入多個演算法/範本組合。同時，建議未繫結至訪客設定檔。

如需下載 API 的詳細資訊，請參閱[「舊版 API > 下載」](/help/main/assets/adobe-recommendations-classic.pdf)。
