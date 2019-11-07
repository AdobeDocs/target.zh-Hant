---
keywords: adobe.target.sendNotifications;sendNotifications;sendnotifications;傳送通知;通知;at.js;函數;函數
description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.sendNotifications(options) 函數的資訊。
title: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.sendNotifications(options) 函數的資訊。
subtopic: 快速入門
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# adobe.target.sendNotifications(options)

此函數會在體驗呈現時傳送通知給 Target Edge，而不需要使用 `adobe.target.applyOffer()` 或 `adobe.target.applyOffers()`。

>[!NOTE]
>
>此函數已在 at.js 2.1.0 中推出，且將適用於 2.1.0 以上的任何版本。

| 機碼 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| consumerId | 字串 | 無 | 如果未提供，預設值為用戶端的全域 mbox。此機碼可用來產生用於 A4T 整合的補充資料 ID。 |
| 請求 | 物件 | 是 | 請參閱下方的「要求」表格。 |
| timeout | 數字 | 無 | 請求逾時。如果未指定，則會使用預設的 at.js 逾時。 |

## 請求

| 欄位名稱 | 類型 | 必要? | 限制 | 說明 |
| --- | --- | --- | --- | --- |
| Request &gt; notifications | 物件陣列 | 是 |  | 顯示內容、點擊選取器及/或已造訪的檢視或 mbox 的通知。 |
| Request &gt; notifications &gt; address | 物件 | 無 |  |  |
| Request &gt; notifications &gt; address &gt; url | 字串 | 無 |  | 觸發通知的來源 URL。 |
| Request &gt; notifications &gt; address &gt; referringUrl | 字串 | 無 |  | 觸發通知的來源引用 URL。 |
| Request &gt; notifications &gt; parameters | 物件 | 無 | 不允許在參數中使用下列名稱:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>考慮以下事項:<ul><li>上限為 50 個參數。</li><li>參數名稱不得空白。</li><li>參數名稱長度上限為 128。</li><li>參數名稱的開頭不得為「設定檔」。</li><li>參數值長度上限為 5000。</li></ul> |  |
| Request &gt; notifications &gt; profileParameters | 物件 | 無 | 不允許在參數中使用下列名稱:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>考慮以下事項:<ul><li>上限為 50 個參數。</li><li>參數名稱不得空白。</li><li>參數名稱長度上限為 128。</li><li>參數名稱的開頭不得為「設定檔」。</li><li>參數值長度上限為 5000。</li></ul> |  |
| Request &gt; notifications &gt; order | 物件 | 無 |  | 說明訂單詳細資料的物件。 |
| Request &gt; notifications &gt; order &gt; id | 字串 | 無 | `<=` 250 個字元。 | 訂購 ID. |
| Request &gt; notifications &gt; order &gt; total | 字串 | 無 | `>=` 0 | 訂購總計. |
| Request &gt; notifications &gt; order &gt; purchasedProductIds | 字串陣列 | 無 | <ul><li>不允許使用任何空白值。</li><li>每個產品 ID 長度上限為 50。</li><li>產品 ID，以逗號分隔並串連，總長度不得超過 250。</li></ul> | 訂購產品 ID。 |
| Request &gt; notifications &gt; product | 物件 | 無 |  |  |
| Request &gt; notifications &gt; product &gt; id | 字串 | 無 | `<=` 128 個字元；不得空白。 | 產品 ID. |
| Request &gt; notifications &gt; product &gt; categoryId | 字串 | 無 | `<=` 128 個字元；不得空白。 | 類別 ID。 |
| Request &gt; notifications &gt; id | 字串 | 是 | `<=` 200 個字元。 | 回應中將傳回通知 ID，且會包含已成功處理的通知。 |
| Request &gt; notifications &gt; impressionId | 字串 | 無 | `<= 128` 個字元。 | Impression ID 可用來拼接 (連結) 目前的通知與先前的通知或執行要求。在兩者彼此相符的情況下，第二個和其他後續要求將不會對活動或體驗產生新曝光次數。 |
| Request &gt; notifications &gt; type | 字串 | 是 | 支援「按一下」或「顯示」。 | 通知類型。 |
| Request &gt; notifications &gt; timestamp | 數字`<int64>` | 是 |  | 自 UNIX 紀元以來經過時間之通知的時間戳記 (以毫秒為單位)。 |
| Request &gt; notifications &gt; tokens | 字串陣列 | 是 |  | 根據通知類型，顯示內容或點擊選取器的 Token 清單。 |
| Request &gt; notifications &gt; mbox | 物件 | 無 |  | mbox 的通知。 |
| Request &gt; notifications &gt; mbox &gt; name | 字串 | 無 | 不允許使用任何空白值。<br>允許的字元: 請參閱此表格後的備註。 | mBox 名稱。 |
| Request &gt; notifications &gt; mbox &gt; state | 字串 | 無 |  | mbox 狀態 Token。 |
| Request &gt; notifications &gt; view | 物件 | 無 |  |  |
| Request &gt; notifications &gt; view &gt; id | 整數 `<int64>` | 無 |  | 檢視 ID。透過檢視 API 建立檢視時，已指派給檢視的 ID。 |
| Request &gt; notifications &gt; view &gt; name | 字串 | 無 | `<= 128` 個字元。 | 檢視的名稱。 |
| Request &gt; notifications &gt; view &gt; key | 字串 | 無 | `<=` 512 個字元。 | 檢視金鑰。已透過 API 使用檢視設定的金鑰。 |
| Request &gt; notifications &gt; view &gt; state | 字串 | 無 |  | 檢視狀態 Token。 |

**注意**: `Request > notifications > mbox > name` 中允許使用下列字元:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## 呈現預先擷取 mbox 後的 sendNotifications() 呼叫

```
function createTokens(options) {
  return options.map(e => e.eventToken);
}

function createNotification(mbox, type, tokens) {
  const id = 11111; // here we should use a random ID like UUID
  const timestamp = Date.now();
  const { name, state, parameters, profileParameters, order, product } = mbox;
  const result = {
    id,
    type,
    timestamp,
    parameters,
    profileParameters,
    order,
    product
  };

  result.mbox = { name, state };
  result.tokens = tokens;

  return result;
}

adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "a1-serverside-ab"
        }
      ]
    }
  }
})
.then(response => {
  const mboxes = response.prefetch.mboxes;
  const notifications = mboxes.map(mbox => {
    const type = "display";
    const tokens = createTokens(mbox.options);

    return createNotification(mbox, type, tokens);
  });
  
  adobe.target.sendNotifications({
    request: { notifications }
  });
})
```

>[!NOTE]
>
>如果您使用 Adobe Analytics、僅具有預先擷取的 `getOffers()` 以及 `sendNotifications()`，必須在執行 `sendNotifications()` 後觸發 Analytics 要求。其目的在於確保 `sendNotifications()` 產生的 SDID 會符合傳送給 Analytics 和 Target 的 SDID。