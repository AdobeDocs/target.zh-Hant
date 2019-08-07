---
description: 'at. js的adobe. target. sendNotifications(選項)函數相關資訊。 '
keywords: adobe. target. sendNotifications；SendNotifications；sendnotifications；傳送通知；通知；at. js；函數；函數
seo-description: Adobe Target at. js JavaScript程式庫的adobe. target. sendNotifications(選項)函數的相關資訊。
seo-title: Adobe Target at. js JavaScript程式庫的adobe. target. sendNotifications(選項)函數的相關資訊。
solution: Target
subtopic: 快速入門
title: adobe. target. sendNotifications(選項)
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# adobe. target. sendNotifications(選項)

此函數會在不使用 `adobe.target.applyOffer()` 或 `adobe.target.applyOffers()`使用體驗時，將通知傳送至Target邊緣。

>[!NOTE]
>
>此函數已於at. js2.1.0中推出，適用於2.1.0以上的任何版本。

| 機碼 | 類型 | 必要? | 說明 |
| --- | --- | --- | --- |
| consumerId | 字串 | 無 | 如果未提供，預設值為用戶端的全域 mbox。此機碼可用來產生用於 A4T 整合的補充資料 ID。 |
| 請求 | 物件 | 是 | 請參閱下方的「要求」表格。 |
| timeout | 數字 | 無 | 要求逾時. 如果未指定，則會使用預設的 at.js 逾時。 |

## 請求

| 欄位名稱 | 類型 | 必要? | 限制 | 說明 |
| --- | --- | --- | --- | --- |
| 請求&gt;通知 | 物件陣列 | 是 |  | 顯示內容、點選的選擇器及/或已造訪檢視或mbox的通知。 |
| 「請求&gt;通知&gt;地址」 | 物件 | 無 |  |  |
| 「請求&gt;通知&gt;地址&gt; url」 | 字串 | 無 |  | 通知所在的URL。 |
| 「請求&gt;通知&gt;地址&gt;反向連結URL」 | 字串 | 無 |  | 通知所從的反向連結URL。 |
| 「請求&gt;通知&gt;參數」 | 物件 | 無 | 參數不允許使用下列名稱：<ul><li>orderId</li><li>orderTotal</li><li>productPurchaseVidds</li></ul>考慮以下事項:<ul><li>上限50個參數限制。</li><li>參數名稱不應空白。</li><li>參數名稱max長度128。</li><li>參數名稱不應以「profile」開頭。</li><li>參數值長度上限5000。</li></ul> |  |
| 「請求&gt;通知&gt; profileParameters」 | 物件 | 無 | 參數不允許使用下列名稱：<ul><li>orderId</li><li>orderTotal</li><li>productPurchaseVidds</li></ul>考慮以下事項:<ul><li>上限50個參數限制。</li><li>參數名稱不應空白。</li><li>參數名稱max長度128。</li><li>參數名稱不應以「profile」開頭。</li><li>參數值長度上限5000。</li></ul> |  |
| 「請求&gt;通知&gt;順序」 | 物件 | 無 |  | 說明訂購詳細資訊的物件。 |
| 「請求&gt;通知&gt;順序&gt; id」 | 字串 | 無 | `<=` 250 個字元. | 訂購 ID. |
| 「請求&gt;通知&gt;順序&gt;總計」 | 字串 | 無 | `>=` 0 | 訂購總計. |
| 「請求&gt;通知&gt;訂購&gt; purchasedProductIDs」 | 字串陣列 | 無 | <ul><li>不允許空白值。</li><li>每個產品ID最大長度50。</li><li>產品ID，以逗號分隔並串連，總長度不得超過250個。</li></ul> | 訂購產品ID。 |
| 「請求&gt;通知&gt;產品」 | 物件 | 無 |  |  |
| 「請求&gt;通知&gt;產品&gt; id」 | 字串 | 無 | `<=` 128個字元；不能空白。 | 產品 ID. |
| 「請求&gt;通知&gt; product&gt; categoryId」 | 字串 | 無 | `<=` 128個字元；不能空白。 | 類別ID。 |
| 「請求&gt;通知&gt; id」 | 字串 | 是 | `<=` 200個字元。 | 通知ID會傳回回應，並指出通知已成功處理。 |
| 「請求&gt;通知&gt; impressionID」 | 字串 | 無 | `<= 128` 個字元. | 曝光ID用於將目前通知與先前通知或執行要求接合(連結)。如果兩者兩者相符，則第二個和其他後續請求不會對活動或體驗產生新曝光。 |
| 「請求&gt;通知&gt;類型」 | 字串 | 是 | 「按一下」或「顯示」受到支援。 | 通知類型。 |
| 「請求&gt;通知&gt;時間戳記」 | 數字`<int64>` | 是 |  | 自UNIX週年起，通知的時間戳記。 |
| 「請求&gt;通知&gt; token」 | 字串陣列 | 是 |  | 根據通知類型，顯示顯示內容或按下選擇器的代號清單。 |
| 「請求&gt;通知&gt; mbox」 | 物件 | 無 |  | mbox的通知。 |
| 「請求&gt;通知&gt; mbox&gt;名稱」 | 字串 | 無 | 不允許空白值。<br>允許的字元：請參閱此表格後的附註。 | mBox 名稱. |
| 「請求&gt;通知&gt; mbox&gt;狀態」 | 字串 | 無 |  | mbox狀態Token。 |
| 「請求&gt;通知&gt;檢視」 | 物件 | 無 |  |  |
| 「請求&gt;通知&gt;檢視&gt; id」 | 整數 `<int64>` | 無 |  | 檢視ID。透過檢視API建立檢視時，指派給檢視的ID。 |
| 「請求&gt;通知&gt;檢視&gt;名稱」 | 字串 | 無 | `<= 128` 個字元. | 檢視名稱。 |
| 「請求&gt;通知&gt;檢視&gt;索引鍵」 | 字串 | 無 | `<=` 512個字元。 | 檢視金鑰。經由API與檢視設定的索引鍵。 |
| 「請求&gt;通知&gt;檢視&gt;狀態」 | 字串 | 無 |  | 檢視狀態Token。 |

**注意**：下列字元可 `Request > notifications > mbox > name`用於：

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## 在轉譯預先擷取的mbox後呼叫sendNotifications()呼叫

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
>如果您使用Adobe Analytics，且 `getOffers()` 僅使用預先擷取， `sendNotifications()`則必須在執行後觸發Analytics `sendNotifications()` 請求。其目的在於確保所產生的SDID符合 `sendNotifications()` 傳送至Analytics和Target的SDID。