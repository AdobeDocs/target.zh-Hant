---
keywords: order confirmation;orderConfirmPage
description: 訂購確認 mbox 會記錄關於您的網站上訂單的詳細資料，並允許根據收入和訂單報告。訂購確認 mbox 也可以促進建議演算法，例如「購買了產品 x、也購買了產品 y 的使用者」
title: 建立訂購確認 mbox - mbox.js
feature: null
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 69%

---


# 建立訂購確認 mbox - mbox.js

訂購確認 mbox 會記錄關於您的網站上訂單的詳細資料，並允許根據收入和訂單報告。訂購確認 mbox 也可以促進建議演算法，例如「購買了產品 x、也購買了產品 y 的使用者」

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 將不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

>[!NOTE]
>
>* 如果使用者在您的網站上進行購買，建議您實作訂購確認 mbox，即便您對報表使用 Analytics for Target (A4T) 亦然。
   >
   >
* 您也可以為at.js 1建立訂單確認mbox。*使* 用相同方法；但是，方 [!DNL at.js] 法是優選的。如需詳細資訊，請參閱[追蹤轉換](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)。
   >
   >
* 如果您使用at.js 2。*x*, `mboxCreate` 不再支援。如需使用at.js 2的訂購確認。*x*，請使用下列追蹤相關API: [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 和 [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)。


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