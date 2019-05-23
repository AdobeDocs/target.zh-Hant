---
description: 'at. js的adobe. target. getOffers(選項)函數相關資訊。 '
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: Adobe Target at. js JavaScript程式庫的adobe. target. getOffers(選項)函數的相關資訊。
seo-title: Adobe Target at. js JavaScript程式庫的adobe. target. getOffers(選項)函數的相關資訊。
solution: Target
subtopic: 快速入門
title: adobe.target.getOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: e5ac81441b7bf1c57b1bf62f49100e98673ac65c

---


# adobe. target. getOffers(選項)- at. js2.x

此函數可讓您透過傳入多個 mbox 來擷取多個選件。此外，還可針對使用中活動內的所有檢視擷取多個選件。

>[!NOTE]
>
>此函數是以. js2.x導入。此函數不適用於. js第版。*x* 版本不支援此函數。

| 機碼 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| consumerId | 字串 | 無 | 如果未提供，預設值為用戶端的全域 mbox。此機碼可用來產生用於 A4T 整合的補充資料 ID。 |
| 要求 | 物件 | 是 | 請參閱下方的「要求」表格。 |
| timeout | 數字 | 無 | 請求逾時。如果未指定，則會使用預設的 at.js 逾時。 |

## 請求

| 欄位名稱 | 必要? | 限制 | 說明 |
| --- | --- | --- | --- |
| request &gt; id | 無 | `tntId`、`thirdPartyId` 或 `marketingCloudVisitorId` 其中一個是必要項目。 |
| request &gt; id &gt; thirdPartyId | 無 | 大小上限 = 128 |
| request &gt; prefetch | 無 |
| request &gt; prefetch &gt; views | 無 | 計數上限 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 5000<br>名稱不得以「profile」開頭<br>不允許的名稱: 「orderId」、「orderTotal」、「productPurchasedId」 | 傳遞參數以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; profileParameters | 無 | 計數上限 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 5000<br>名稱不得以「profile」開頭 | 傳入設定檔參數以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; product | 無 |
| request &gt; prefetch &gt; views &gt; product -&gt; id | 無 | 不得空白<br>大小上限 = 128 | 傳入產品 ID 以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; product &gt; categoryId | 無 | 不得空白<br>大小上限 = 128 | 傳入產品類別 ID 以用於擷取活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; order | 無 |
| request &gt; prefetch &gt; views &gt; order &gt; id | 無 | 長度上限 = 250 | 傳入訂單 ID 以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; order &gt; total | 無 | 總金額 `>=` 0 | 傳入訂單總金額以用於擷取使用中活動內的相關檢視。 |
| request &gt; prefetch &gt; views &gt; order &gt; purchasedProductIds | 無 | 無空白值<br>每個值的長度上限 50<br>串連並以逗號分隔<br>產品 ID 總長度 `<=` 250 | 傳入已購產品 ID 以用於擷取使用中活動內的相關檢視。 |
| request &gt; execute | 無 |
| request &gt; execute &gt; pageLoad | 無 |
| request &gt; execute &gt; pageLoad &gt; parameters | 無 | 計數上限 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 5000<br>名稱不得以「profile」開頭。<br>不允許的名稱: 「orderId」、「orderTotal」、「productPurchasedId」 | 頁面載入時使用指定的參數擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; profileParameters | 無 | 計數上限 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 256<br>名稱不得以「profile」開頭。 | 頁面載入時使用指定的設定檔參數擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; product | 無 |
| request &gt; execute &gt; pageLoad &gt; product -&gt; id | 無 | 不得空白<br>大小上限 = 128 | 頁面載入時使用指定的產品 ID 擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; product &gt; categoryId | 無 | 不得空白<br>大小上限 = 128 | 頁面載入時使用指定的類別 ID 擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; order | 無 |
| request &gt; execute &gt; pageLoad &gt; order &gt; id | 無 | 長度上限 = 250 | 頁面載入時使用指定的訂單 ID 擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; order &gt; total | 無 | `>=` 0 | 頁面載入時使用指定的訂單總金額擷取選件。 |
| request &gt; execute &gt; pageLoad &gt; order &gt; purchasedProductIds | 無 | 無空白值<br>每個值的長度上限 50<br>串連並以逗號分隔<br>產品 ID 總長度 `<=` 250 | 頁面載入時使用指定的已購產品 ID 擷取選件。 |
| request &gt; execute &gt; mboxes | 無 | 大小上限  = 50<br>無 null 元素 |
| request &gt; execute &gt; mboxes&gt;mbox | 是 | 不得空白<br>無「-clicked」尾碼<br>大小上限  = 250<br>允許的字元: `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | mbox 的名稱。 |
| request &gt; execute &gt; mboxes&gt;mbox&gt;index | 是 | 非 null<br>唯一<br>`>=` 0 | 請注意，索引不代表處理 mbox 的順序。與含有數個區域 mbox 的網頁相同，無法指定處理 mbox 的順序。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; parameters | 無 | 計數上限 = 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 5000<br>名稱不得以「profile」開頭。<br>不允許的名稱: 「orderId」、「orderTotal」、「productPurchasedId」 | 使用指定的參數為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes&gt;mbox&gt;profileParameters | 無 | 計數上限 = 50<br>名稱不得空白<br>名稱長度 `<=` 128<br>值長度 `<=` 256<br>名稱不得以「profile」開頭。 | 使用指定的設定檔參數為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes&gt;mbox &gt; product | 無 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; id | 無 | 不得空白<br>大小上限 = 128 | 使用指定的產品 ID 為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; categoryId | 無 | 不得空白<br>大小上限 = 128 | 使用指定的類別 ID 為特定 mbox 擷取選件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; order | 無 |
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

## 透過GeoOffers()和applyOffers()，從多個mbox擷取和演算資料() {#multiple}

at. js2.x可讓您透過 `getOffers()` API擷取多個mbox。您也可以擷取多個mbox的資料，然後用來 `applyOffers()` 在CSS選擇器所識別的不同位置中演算資料。

下列範例顯示已實施. js2.x的簡單HTML頁面：

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

假設您有三個容器要透過接收到 [!DNL Target]的內容進行修改。您可以建構三個mbox的單一請求，其中每個mbox都有要演算至個別容器的內容。

請求和轉換程式碼看起來可能類似下列範例：

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

在 `request > prefetch > mboxes` 區段中，有三個不同的mbox。如果請求成功完成，您會收到每個mbox的回應 `response > prefetch > mboxes`。您有回應和想要用於演算的位置後，可以叫用 `applyOffers()` 來轉譯從 [!DNL Target]中擷取的內容。在此範例中，我們有下列對應：

* mbox&gt; CSS選擇器#容器1
* mbox2&gt; CSS選擇器#容器2
* mbox3&gt; CSS選擇器#容器3

此範例使用計數變數來建構CSS選擇器。在現實生活中，您可以在CSS選擇器和mbox之間使用不同的對應。

請注意，此範例使用 `prefetch > mboxes`，但您也可以使用 `execute > mboxes`。確定您在使用預先擷取時 `getOffers()`，也應在 `applyOffers()` 觸發中使用預先擷取。