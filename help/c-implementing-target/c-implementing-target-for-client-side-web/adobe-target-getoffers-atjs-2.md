---
description: '有關適用於 at.js 的 adobe.target.getOffers(options) 函數的資訊。 '
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.getOffers(options) 函數的資訊。
seo-title: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.getOffers(options) 函數的資訊。
solution: Target
subtopic: 快速入門
title: adobe.target.getOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: cc7dc21321816e7f71b67e31abc0855184a285c6

---


# adobe.target.getOffers(options) - at.js 2.x

此函數可讓您透過傳入多個 mbox 來擷取多個選件。此外，還可針對使用中活動內的所有檢視擷取多個選件。

>[!NOTE]
>
>此函數於 at.js 2.x 推出。此函數不適用於 at.js 版本 1。*x* 版本不支援此函數。

| 機碼 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| consumerId | 字串 | 無 | 如果未提供，預設值為用戶端的全域 mbox。此機碼可用來產生用於 A4T 整合的補充資料 ID。 |
| 要求 | 物件 | 是 | 請參閱下方的「要求」表格。 |
| timeout | 數字 | 無 | 請求逾時。如果未指定，則會使用預設的 at.js 逾時。 |

## 請求

| 欄位名稱 | 必要? | 限制 | 說明 |
| --- | --- | --- | --- |
| request &gt; id | 無 |  | `tntId`、`thirdPartyId` 或 `marketingCloudVisitorId` 其中一個是必要項目。 |
| request &gt; id &gt; thirdPartyId | 無 | 大小上限 = 128 |  |  |
| Request&gt; Experience Cloud | 無 |  |  |
| Request&gt; Experience Cloud&gt;分析 | 無 |  | Adobe Analytics整合 |
| 「請求&gt;體驗Cloud&gt;分析&gt;記錄」 | 無 | 下列必須實施於頁面：<ul><li>訪客 ID 服務</li><li>AppMeasurement. js</li></ul> | 支援下列值：<br>**client_ side**：指定後，會將分析裝載傳回回呼叫者，該呼叫者應透過「資料插入API」傳送至Adobe Analytics。<br>**server_ side**：This is the default value where the default value where the Target and Analytics後端will using the SID to stiming the callcom一起for reporting. |
| request &gt; prefetch | 無 |  |  |
| request &gt; prefetch &gt; views | 無 | 計數上限 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 5000<br>名稱不得以「profile」開頭<br>不允許的名稱: 「orderId」、「orderTotal」、「productPurchasedId」 | 傳遞參數以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; profileParameters | 無 | 計數上限 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 5000<br>名稱不得以「profile」開頭 | 傳入設定檔參數以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; product | 無 |  |  |
| request &gt; prefetch &gt; views &gt; product -&gt; id | 無 | 不得空白<br>大小上限 = 128 | 傳入產品 ID 以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; product &gt; categoryId | 無 | 不得空白<br>大小上限 = 128 | 傳入產品類別 ID 以用於擷取活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; order | 無 |  |  |
| request &gt; prefetch &gt; views &gt; order &gt; id | 無 | 長度上限 = 250 | 傳入訂單 ID 以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; order &gt; total | 無 | 總金額 `>=` 0 | 傳入訂單總金額以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; order &gt; purchasedProductIds | 無 | 無空白值<br>每個值的長度上限 50<br>串連並以逗號分隔<br>產品 ID 總長度 `<=` 250 | 傳入已購產品 ID 以用於擷取使用中活動內的相關檢視。 |
| request &gt; execute | 無 |  |  |
| request &gt; execute &gt; pageLoad | 無 |  |  |
| request &gt; execute &gt; pageLoad &gt; parameters | 無 | 計數上限 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 5000<br>名稱不得以「profile」開頭。<br>不允許的名稱: 「orderId」、「orderTotal」、「productPurchasedId」 | 頁面載入時使用指定的參數擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; profileParameters | 無 | 計數上限 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 256<br>名稱不得以「profile」開頭。 | 頁面載入時使用指定的設定檔參數擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; product | 無 |  |  |
| request &gt; execute &gt; pageLoad &gt; product -&gt; id | 無 | 不得空白<br>大小上限 = 128 | 頁面載入時使用指定的產品 ID 擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; product &gt; categoryId | 無 | 不得空白<br>大小上限 = 128 | 頁面載入時使用指定的類別 ID 擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; order | 無 |  |  |
| request &gt; execute &gt; pageLoad &gt; order &gt; id | 無 | 長度上限 = 250 | 頁面載入時使用指定的訂單 ID 擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; order &gt; total | 無 | `>=` 0 | 頁面載入時使用指定的訂單總金額擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; order &gt; purchasedProductIds | 無 | 無空白值<br>每個值的長度上限 50<br>串連並以逗號分隔<br>產品 ID 總長度 `<=` 250 | 頁面載入時使用指定的已購產品 ID 擷取選件。 |
| request &gt; execute &gt; mboxes | 無 | 大小上限  = 50<br>無 null 元素 |  |
| request &gt; execute &gt; mboxes&gt;mbox | 是 | 不得空白<br>無「-clicked」尾碼<br>大小上限  = 250<br>允許的字元: `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | mbox 的名稱。 |
| request &gt; execute &gt; mboxes&gt;mbox&gt;index | 是 | 非 null<br>唯一<br>`>=` 0 | 請注意，索引不代表處理 mbox 的順序。與含有數個區域 mbox 的網頁相同，無法指定處理 mbox 的順序。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; parameters | 無 | 計數上限 = 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 5000<br>名稱不得以「profile」開頭。<br>不允許的名稱: 「orderId」、「orderTotal」、「productPurchasedId」 | 使用指定的參數為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes&gt;mbox&gt;profileParameters | 無 | 計數上限 = 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 256<br>名稱不得以「profile」開頭。 | 使用指定的設定檔參數為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes&gt;mbox &gt; product | 無 |  |  |
| request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; id | 無 | 不得空白<br>大小上限 = 128 | 使用指定的產品 ID 為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; categoryId | 無 | 不得空白<br>大小上限 = 128 | 使用指定的類別 ID 為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; order | 無 |  |  |
| request &gt; execute &gt; mboxes&gt;mbox &gt; order &gt; id | 無 | 長度上限 = 250 | 使用指定的訂單 ID 為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; total | 無 | `>=` 0 | 使用指定的訂單總金額為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; purchasedProductIds | 無 | 無空白值<br>每個值的長度上限 = 50<br>串連並以逗號分隔<br>產品 ID 總長度 `<=` 250 | 使用指定的已購產品 ID 為特定 mbox 擷取選件。 |

## 為所有檢視呼叫 `getOffers()`

```
adobe.target.getOffers({
    prefetch: {
      views: []
    }
  }
});
```

## 呼叫 `getOffers()` 以使用傳入的參數和設定檔參數擷取最新的檢視

```
adobe.target.getOffers({
  request: {
    "prefetch": {
      "views": [
        {
          "parameters": {
            "ad": "1"
          },
          "profileParameters": {
            "age": 23
          }
        }
      ]
    }
  }
});
```

## 呼叫 `getOffers()` 以使用傳入的參數和設定檔參數擷取 mbox。

```
adobe.target.getOffers({
  request: {
    execute: {
      mboxes: [
        {
          index: 0,
          name: "first-mbox"
        },
        {
          index: 1,
          name: "second-mbox",
          parameters: {
            a: 1
          },
          profileParameters: {
            b: 2
          }
        }
      ]
    }
  }
});
```

## 呼叫getOffers()以從用戶端擷取分析裝載

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

**回應**:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

然後，您可以透過 [「資料插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)」轉送裝載至Adobe Analytics。

## 透過 getOffers() and applyOffers() 從多個 mbox 擷取及呈現資料 {#multiple}

at.js 2.x 可讓您透過 `getOffers()` API 擷取多個 mbox。您也可以擷取多個 mbox 的資料，然後使用 `applyOffers()` 在 CSS 選取器所識別的不同位置中呈現資料。

下列範例顯示已實作 at.js 2.x 的單一 HTML 頁面:

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>at.js 2.x, multiple selectors and multiple mboxes</title>
  <script src="at.js"></script>
</head>
<body>
  <div id="container1">Default content 1</div>
  
  <div id="container2">Default content 2</div>

  <div id="container3">Default content 3</div>
</body>
</html>
```

假設您有三個要透過從 [!DNL Target] 收到的內容修改的容器。您可為三個 mbox 建構單一要求，其中每個 mbox 都有要呈現於個別容器中的一些內容。

要求和呈現的程式碼可能如下列範例所示:

```
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "mbox1"
        },
        {
          index: 1,
          name: "mbox2"
        },
        {
          index: 2,
          name: "mbox3"
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;

  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });

    count += 1;
  });
});
```

在 `request > prefetch > mboxes` 區段中，有三個不同的 mbox。如果已成功完成要求，您會從 `response > prefetch > mboxes` 收到每個 mbox 的回應。有了回應和您要用於呈現的位置之後，您可以叫用 `applyOffers()`，呈現從 [!DNL Target] 擷取的內容。在此範例中，我們有下列對應:

* mbox1 &gt; CSS 選取器 #container1
* mbox2 &gt; CSS 選取器 #container2
* mbox3 &gt; CSS 選取器 #container3

此範例使用計數變數來建構 CSS 選取器。在實際情況中，您可以在 CSS 選取器和 mbox 之間使用不同的對應。

請注意，此範例使用 `prefetch > mboxes`，但您也可以使用 `execute > mboxes`。請務必確認，如果您在 `getOffers()` 中使用預先擷取，則在 `applyOffers()` 叫用中也應使用預先擷取。
