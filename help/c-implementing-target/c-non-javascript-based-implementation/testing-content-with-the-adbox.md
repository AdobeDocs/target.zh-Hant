---
keywords: 實作;mbox.js 非 javascript;mbox;adbox
description: 使用AdBox，在使用Adobe Target的非現場實作中提供影像。 AdBox就像mbox，但是由URL而非JavaScript控制。
title: 如何建立影像的Adbox?
feature: 實作電子郵件
role: Developer
exl-id: c66cfbc2-633a-46f2-8d9f-dbd18f7e880e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 73%

---

# 為影像建立 Adbox

使用AdBox，在使用Adobe Target的非現場實作中提供影像。

AdBox 類似 mbox，不過它是由 URL 來控制，而非 JavaScript。AdBox 是使用特殊的「AdBox URL」建立，此 URL 會將「廣告」mbox (或 AdBox) 載入到您的 Adobe 帳戶。請在您的活動中使用此 AdBox 取代 mbox。請在電子郵件或其他非 JavaScript 實施中使用 AdBox URL 而非直接影像參考。

如需關於選擇正確設定的說明，請參閱 [非 JavaScript 型實作](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)。

1. 建立 AdBox URL:

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200&
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * 其中 `myClientCode` 代表貴公司的用戶端代碼。您的公司用戶端代碼為全部小寫並且不帶特殊字元。

      您的用戶端程式碼位於[!DNL Target]介面的[!UICONTROL 管理>實作]頁面頂端。

   * 其中 `image` 是呼叫類型。在此範例中，它是一個影像。

   * 其中 `emailHeroImage123_320x200` 是 AdBox 的名稱。

   * 其中 `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` 是 mbox 的預設內容。這必須為影像。

      此網址必須經過 URL 編碼，且必須為絕對參照。您可以使用[HTML URL編碼參考](https://www.w3schools.com/tags/ref_urlencode.asp)快速編碼URL。

1. 為每個替代影像建立[重新導向選件](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)。

   >[!NOTE]
   >
   >AdBox 必須以「重新導向選件」或是預設的內容選件載入。其他選件類型將無法運作。因為 AdBox 是 URL，它只能顯示所收到的 URL，所以只有「重新導向選件」可以運作。

1. 建立活動。

   請參閱[非 JavaScript 型實作](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)，以瞭解符合您目標的正確設定。
1. 完成活動上的品質保證。

   作為最佳作法，請建立一份虛擬頁面，然後確認對您所有的環境來說，所有的體驗、預設內容與報表都如預期般在所有瀏覽器類型上運作。

1. 啟動活動。
