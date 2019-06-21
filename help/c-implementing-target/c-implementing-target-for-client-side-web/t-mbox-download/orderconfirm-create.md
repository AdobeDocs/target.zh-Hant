---
description: 訂購確認 mbox 會記錄關於您的網站上訂單的詳細資料，並允許根據收入和訂單報告。訂購確認 mbox 也可以促進建議演算法，例如「購買了產品 x、也購買了產品 y 的使用者」
keywords: 訂購確認;orderConfirmPage
seo-description: 訂購確認 mbox 會記錄關於您的網站上訂單的詳細資料，並允許根據收入和訂單報告。訂購確認 mbox 也可以促進建議演算法，例如「購買了產品 x、也購買了產品 y 的使用者」
seo-title: 建立訂購確認 mbox - mbox.js
solution: Target
subtopic: 快速入門
title: 建立訂購確認 mbox - mbox.js
uuid: 001da2bd-2ccf-490b-ba84-ac9b9a2a5451
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 建立訂購確認 mbox - mbox.js{#create-an-order-confirmation-mbox-mbox-js}

訂購確認 mbox 會記錄關於您的網站上訂單的詳細資料，並允許根據收入和訂單報告。訂購確認 mbox 也可以促進建議演算法，例如「購買了產品 x、也購買了產品 y 的使用者」

>[!NOTE]
>
>如果使用者在您的網站上進行購買，建議您實作訂購確認 mbox，即便您對報表使用 Analytics for Target (A4T) 亦然。

>[!NOTE]
>
>您也可以使用相同的方法為 at.js 建立「訂購確認」mbox，不過 [!DNL at.js] 是推薦方法。如需詳細資訊，請參閱[追蹤轉換](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)。

1. 在訂單詳細資料頁面中，請依照下方的模式插入 mbox 指令檔。
1. 使用目錄中的動態或靜態值來取代大寫的字母。

   >[!NOTE]
   >
   >請使用逗號來隔開多個產品 ID。

   **提示:** 您也可以在任何 mbox 中傳遞訂單資訊 (名稱不需是 `orderConfirmPage`)。您也可以將訂單資訊傳遞至同一個促銷活動中的多個 mbox。

   ```
   <div class="mboxDefault"> 
      <!-- CONTENT TO SHOW IF NO OFFERS AVAILABLE. --> 
   </div> 
   <script type="text/javascript">    
      mboxCreate('orderConfirmPage', 
      'productPurchasedId=PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3', 
      'orderTotal=ORDER TOTAL FROM YOUR ORDER PAGE', 
      'orderId=ORDER ID FROM YOUR ORDER PAGE'); 
   </script> 
   ```

「訂購確認」mbox 會使用下列參數:

| 參數 | 說明 |
|--- |--- |
| `orderId` | 要進行轉換計算之訂單的唯一識別值。<br>`orderId` 必須是唯一的。報表中會忽略重複的訂單。 |
| `orderTotal` | 購買貨幣值。<br>請勿加上貨幣符號。請使用小數點 (而非逗點) 表示小數值。 |
| `productPurchasedId` (可選) | 訂單中購買之產品 ID 的逗點分隔清單。<br>這些產品 ID 會顯示在稽核報表中，以支援其他報表分析。 |