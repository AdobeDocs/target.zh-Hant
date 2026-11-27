---
keywords: 電子郵件;ESP;電子郵件服務提供者;rawbox;傳送 API;僅供下載的範本;電子郵件範本;批次處理;建置時間電子郵件
description: 瞭解如何將電子郵件與Adobe [!DNL Target Recommendations]整合，包括使用[!DNL Target]傳遞API、rawbox範本及僅供下載的範本。
title: 如何將推薦與電子郵件整合？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
TQID: 'https://experienceleague.adobe.com/ZyeOl6ysM03a0mMiNgHuicOLPfgpXnrdqXJE1gHRRvE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 26%
---
# 將[!DNL Recommendations]與電子郵件整合 {#integrate-recs-email}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何將[!DNL Target Recommendations]與電子郵件服務提供者(ESP)整合，以在電子郵件中個人化建議的傳送時間。

>[!ENDSHADEBOX]

[!DNL Adobe Target] 支援電子郵件中推薦的傳送時間個人化。 不支援推薦的開放時間個人化。

三種方法可用來整合[!DNL Target Recommendations]與ESP。 ESP的功能會決定要使用的方法，而客戶經理或顧問可以協助選擇最佳選項。

| 方法 | 詳細資料 |
| --- | --- |
| [方法 1： [!DNL Adobe Target Delivery API]](#delivery-api) (偏好設定) | 使用[!DNL Adobe Target Delivery API]針對每位客戶、每封電子郵件提出推薦請求。 |
| [方法 2： [!DNL Adobe Rawbox API]](#rawbox) | 使用[!DNL Adobe Target Rawbox API]針對每位客戶、每封電子郵件提出推薦請求。 |
| [方法 3： [!DNL Recommendations Download API]](#download-api) | 使用[!DNL Recommendations Download API]來要求產品或類別清單（CSV格式）的大量建議。 |

方法1和2要求ESP根據每位客戶、每封電子郵件對外部API進行呼叫，並等待傳回內容。 並非所有ESP都支援這些方法，因此必須聯絡ESP以判斷其是否與此整合模式相容。

方法3要求ESP依產品ID或類別ID將推薦清單聯結至電子郵件清單。 此加入可以是根據屬性，例如上次檢視的產品、上次購買的產品或客戶檢視次數最多的類別。 ESP必須在其客戶設定檔中擁有此資料的存取權才能執行聯結，因此必須聯絡ESP以判斷其是否擁有此資料的存取權，以及是否與此整合模式相容。

>[!IMPORTANT]
>
>下列容量指南適用於傳送API和rawbox電子郵件範本方法（方法1和2）：
>
>* 要求的速率應該限製為每秒1,000個要求或每日尖峰流量的25倍，以較低者為準。
>* 流量應該以每分鐘200個要求的步驟進行遞增。
>
>若要使用較高的速率限制，請聯絡客戶經理。

## 方法1：使用傳送API （偏好設定） {#delivery-api}

傳送API是與建置時間電子郵件搭配使用的POST請求。 此選項是用於建置時間電子郵件偏好的方法。

大部分電子郵件使用者端不允許POST要求，因此不建議針對開放時間使用案例使用此API。 有些電子郵件使用者端（例如Gmail或Outlook）可能會快取內容或封鎖影像，並要求收件者主動允許影像呈現。

預設內容無法與傳送API一併傳回。

下列程式碼為範例API傳遞要求，其中`clientcode`為[!DNL Target]使用者端程式碼：

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

>[!NOTE]
>
>為每個電子郵件收件者（每個API呼叫）的`sessionId`及`tntId`或`thirdPartyId`兩者之一，提供唯一值。 如果沒有這些欄位的唯一值，API回應可能會因為在單一設定檔中產生的許多事件而變得緩慢或失敗。

如需詳細資訊，請參閱[傳送API檔案](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html){target=_blank}。

## 方法 2：使用 rawbox 電子郵件範本 {#rawbox}

rawbox類似於mbox要求，但適用於非Web環境，例如電子郵件服務提供者(ESP)。 [!DNL Adobe Experience Platform Web SDK]和[!DNL at.js]不適用於rawbox要求，因此必須手動建立要求。 以下範例說明如何在電子郵件中使用rawbox請求。

此方法可讓您追蹤電子郵件中建議的效能、以正常方式測試建議與建議，並繼續網站上的追蹤。

>[!NOTE]
>
>使用 rawbox 和 [!DNL Target] 時，請參閱「[建立允許清單，指定授權傳送 mbox 呼叫至  [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist) 的主機」底下的重要安全性注意事項。

1. 使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)選項，在[!DNL Target]中設定[!DNL Recommendations]活動。

1. 對於位置，選取在來自ESP的rawbox請求中使用的mbox名稱。

1. Select的設計，具備電子郵件所需的外觀與風格。

在電子郵件建置時，ESP 會對每個要產生的電子郵件中的每個 Rawbox 對 [!DNL Target] 伺服器進行呼叫。 ESP必須有一個方式可在傳送的電子郵件中包含傳回的HTML。

電子郵件系統必須能夠處理以下案例。

### 收到有效回應，但沒有建議

* 回應是在`mboxDefault`引數中設定的值。 請參閱必要參數列中此引數的說明。
* 電子郵件提供者應該具有預設的建議 HTML 區塊，以在此情況下使用。

### [!DNL Target] 伺服器逾時，且未傳回任何資料

* [!DNL Target]伺服器傳回下列內容：

  `//ERROR: application server timeout`

* 電子郵件應用程式應該搜尋該文字，而且必須能夠處理錯誤。 電子郵件提供者有多個選項可用於處理此情況:

  * 立即嘗試另一個伺服器呼叫 (建議，也許可以使用嘗試計數器)。
  * 捨棄該特定電子郵件，並繼續處理下一個電子郵件。
  * 將該特定電子郵件加入佇列，並在初始執行結束時，以批次形式重新執行失敗的電子郵件。

### 樣本請求 URL

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### 必要的參數 {#reqparams}

>[!NOTE]
>
>若要在電子郵件中使用[!DNL Recommendations]，rawbox呼叫通常必須包含`entity.id`或`entity.categoryId`，或同時包含兩者，視建議條件的型別而定。 以上的樣本呼叫包括這兩者。

| 參數 | 值 | 說明 | 驗證 |
|--- |--- |--- |--- |
| `client_code` | *client_code* | [!DNL Recommendations]中使用的使用者端代碼。 Adobe顧問可提供此值。 |  |
| `mbox` | *mboxName* | 用於鎖定目標的 mbox 名稱。 | 與所有mbox呼叫相同的驗證。<br>250個字元限制。<br>不能包含下列任一個字元：`', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | 已停用 | 防止回應在非 Web 環境中設定 Cookie。 |  |
| `entity.id`<br> (對某些類型的標準為必要：檢視/檢視、檢視/購買、購買/購買) | *entity_id* | 建議所根據的產品ID，例如購物車中放棄的產品或之前的購買。<br>如果條件要求，rawbox 呼叫必須包括 `entity.id`。 |  |
| `entity.event.detailsOnly` | true | 如果傳遞了`entity.id`，強烈建議您傳遞此引數，以防止要求為了不要扭曲產品檢視式的演演算法，而遞增專為某專案調整的頁面檢視數量。 |  |
| `entity.categoryId`<br> (對某些類型的標準為必要：檢視次數最多類別和最暢銷商品類別) | *category_id* | 建議所依據的類別，例如類別中的最暢銷商品。<br>如果條件要求，rawbox 呼叫必須包括 `entity.categoryId`。 |  |
| `mboxDefault` | *`https://www.default.com`* | 如果 `mboxNoRedirect` 參數不存在，則在沒有可用的建議時，`mboxDefault` 應該是將傳回預設內容的絕對 URL。 此 URL 可以是影像或其他靜態內容。<br>如果`mboxNoRedirect`引數存在，`mboxDefault`可以是任何文字，指出沒有任何建議，例如`no_content`。<br>電子郵件提供者必須處理傳回此值的情況，並將預設HTML插入電子郵件中。<br>請參閱表格下方的安全性最佳實務。 |  |
| `mboxHost` | *mbox_host* | 這是呼叫觸發時新增至預設環境 (主機群組) 的網域。 |  |
| `mboxPC` | 空白 | （使用訪客設定檔的建議為必要。）<br>如果未提供&quot;thirdPartyId&quot;，則會產生新的tntId，並隨著回應傳回。 否則，值會維持空白。<br>請參閱表格下方關於唯一值的備註。 | 1 &lt; 長度 &lt; 128<br>不能包含超過一個「.」 （點）。<br>僅允許在設定檔位置字尾中使用點。 |

### 選用參數

| 參數 | 值 | 說明 | 驗證 |
|--- |--- |--- |--- |
| `mboxPC`<br>(可選) | *mboxPCId* | [!DNL Target]訪客識別碼。 此值可用於追蹤多次造訪或使用使用者設定檔引數時，使用者以整圈回訪網站。<br>此值必須是使用者的實際[!DNL Adobe Target] PCID，它會從網站匯出至CRM。 電子郵件提供者會從CRM或資料倉儲擷取此ID，並使用它做為此引數的值。<br>當建議屬於A/B活動時，`mboxPC`值對於追蹤多次造訪間的度量追蹤的訪客網站行為也很實用。<br>請參閱表格下方關於唯一值的備註。 | 1 &lt; 長度 &lt; 128<br>不能包含超過一個「.」 （點）。<br>僅允許在設定檔位置字尾中使用點。 |
| `mboxNoRedirect`<br>(可選) | 1 | 依預設，在找不到可傳遞的內容時會將呼叫端重新導向。 使用此引數可停用預設行為。 |  |
| `mbox3rdPartyId` | *xxx* | 使用此選項來指定設定檔目標定位的自訂訪客ID。 |  |

針對`mboxSession`和`mboxPC`，為每個電子郵件收件者（每個API呼叫）提供唯一值。 如果沒有這些欄位的唯一值，API回應可能會因為在單一設定檔中產生的大量事件，導致變慢或失敗。

根據`mboxDefault`的安全性最佳實務，請使用授權的主機來允許列出預設的重新導向URL網域。 如果`mboxDefault` URL中使用的網域未被加入允許清單，可能會出現「開啟重新導向弱點」的風險。 授權主機可避免第三方未經授權使用重新導向程式連結或`mboxDefault`。 [!DNL Target]使用主機來允許列出允許重新導向的網域。 如需詳細資訊，請參閱本區段開頭的安全性注意事項。

### 可能的 [!DNL Target] 伺服器回應

| 回應 | 說明 |
|--- |--- |
| //錯誤: | 當它無法傳回內容時由負載平衡器產生。 |
| 成功 | `mboxNoRedirect`引數設為&#39;true&#39;，而伺服器未傳回任何建議（mbox沒有相符專案，或是伺服器快取未初始化）。 |
| bad request | 遺漏 `mbox` 參數。<ul><li>`mboxDefault` 或 `mboxNoRedirect` 參數未指定。</li><li>已指定`mboxTrace`要求引數，但未指定`mboxNoRedirect`。</li><li>當mbox名稱的結尾是`-clicked`尾碼時，未指定`mboxTarget`引數。</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | 當要求的相符專案不存在時，未指定`mboxDefault`，且未指定`mboxNoRedirect`引數。 |
| `Invalid mbox name:= MBOX_NAME` | `mbox`引數包含無效的字元。 |
| `Mbox name [MBOX_NAME] is too long` | `mbox`引數長度超過250個字元。 |

## 方法 3：使用推薦 Download API {#download-api}

照常設定建議，但選擇顯示區域中的&#x200B;**僅供下載**，而不是範本和 mbox 組合。 然後為ESP提供已建立之建議的ID。 ESP透過API存取建議資料。 該資料顯示應為特定類別或主要項目所建議的項目，例如購物車中放棄的項目。 ESP會儲存這些資料、將其與自己的外觀和感覺連線、顯示每個專案的相關資訊，並在電子郵件中傳送。

有了此選項，建議伺服器就無法直接追蹤建議的效能，也無法跨多個演演算法和範本組合分割流量。 同時，建議未繫結至訪客設定檔。

如需下載 API 的詳細資訊，請參閱[「舊版 API > 下載」](/help/main/assets/adobe-recommendations-classic.pdf)。
