---
keywords: 實作;mbox.js non javascript;重新導向程式;每次點擊成本;每次點擊收入
description: 瞭解如何在電子郵件實作中使用重新導向程式，就像您在Adobe Target活動中使用mbox的方式一樣。
title: 如何與重新導向程式搭配使用？
feature: Implement Email
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 66%

---


# 使用重新導向程式{#work-with-redirectors}

使用「重新導向程式」的方式和您在測試中使用 mbox 類似。

重新導向程式是使用特殊的「重新導向 URL」所建立的程式，此 URL 會載入一個「重新導向 mbox (重新導向程式)」到您的 帳戶。使用此「重新導向程式」的方式和您在測試中使用 mbox 類似。將「重新導向 URL」提交到您的廣告網路以作為廣告的目的地連結。

使用「重新導向程式」執行下列動作:

* 追蹤從您的顯示廣告進入您網站的點按次數
* 建立單一集中式報表來追蹤多個廣告網路上顯示廣告的點按次數
* 變化顯示廣告目的地

   例如，將相同的橫幅廣告分別放在您的首頁、分類頁面及產品頁面上。

* 找到達成最多轉換的著陸頁面

如需有關決定正確設定的說明，請參閱[非 JavaScript 型實作](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)。

## 建立重新導向程式{#redirector}

您必須先建立重新導向程式才能加以使用。

1. 決定廣告目的地的變數，包括預設目的地。
1. 建立重新導向程式 URL。

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * 其中 `yourclientcode` 代表貴公司的用戶端代碼。您的公司用戶端代碼為全部小寫並且不帶特殊字元。

      您的客戶端代碼位於[!DNL Target]介面的[!UICONTROL 管理>實施]頁面頂部。

   * `redirectorlink_456` 代表重新導向程式 mbox 的名稱，會顯示在您用於促銷活動和測試的帳戶中。

      重新導向程式的功能與其他 mbox 不同，但外觀就如同您帳戶中的其他 mbox 一樣。請為重新導向程式命名，以便容易區別它們和您帳戶中其他標準類型的 mbox。作為最佳作法，請從名稱為 &#39;redirectorlink&#39; 的 mbox 開始。

   * 其中 `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` 是預設目的地。

      此網址必須經過 URL 編碼，且必須為絕對參照。您可以使用[HTML URL編碼參考](https://www.w3schools.com/tags/ref_urlencode.asp)快速編碼URL。

      >[!IMPORTANT]
      >
      >請注意，使用重新導向程式時，您可能會面臨「開啟重新導向」弱點的風險。 為避免第三方未經授權使用重新導向程式連結，我們建議您使用「授權主機」來允許列出預設的重新導向URL網域。 Target使用主機來允許列出您要允許重新導向的網域。 如需詳細資訊，請參閱[建立允許清單，指定在&#x200B;*Hosts*&#x200B;中授權傳送mbox呼叫至Target](/help/administrating-target/hosts.md#allowlist)的主機。

1. 驗證重新導向程式。
   1. *安全性最佳實務*:請確定允許列出重新導向程式中使用的網域，如上所述。如果您使用未允許列出的網域，Adobe會封鎖對該網域的任何呼叫，以防止惡意使用者使用「重新導向程式」重新導向至可能有惡意的網域。
   1. 請將「重新導向程式 URL」插入到瀏覽器中，然後重新整理。
   1. 登入您的帳戶，重新整理您的 mbox 清單，然後確認新的「重新導向程式」是否已列為 mbox。
1. 如果要測試某個廣告的不同目的地，請分別為每個版本建立[重新導向選件](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。
1. 建立促銷活動。

   請參閱[非 JavaScript 型實作](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)，以瞭解符合您目標的正確設定。
1. 完成促銷活動上的品質保證。

   以包含重新導向程式 URL 的 `<a href>` 建立一個虛擬頁面。範例:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. 請確認對所有的環境來說，所有的體驗、預設內容與報表都如預期般在所有瀏覽器類型上運作。

   >[!NOTE]
   >
   >* mbox 的「選件預覽」或「瀏覽」不支援重新導向程式。直接在瀏覽器中預覽體驗。
   >* `mboxDebug` 不能用於重新導向程式。


1. 將完整的重新導向程式 URL 作為廣告目的地，提交到您的顯示廣告網路。

## 使用重新導向程式來傳遞每次點按成本和每次點按收入{#concept_3078EF48E9C44B34992D62AAB9628853}

關於對每次點擊成本和每次點擊收入使用重新導向程式的資訊。

### 傳遞每次點擊的成本 {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

使用重新導向程式來傳遞每次點按成本。

>[!NOTE]
>
>最佳實務是使用&#x200B;**每次瀏覽分數**&#x200B;參與度量來判斷成本值。

將 `&mboxPageValue=-value` 新增至 URL 中。請注意負值。

範例: 若每次點按成本為 0.1 分美元:

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### 傳遞每次點擊的收入  {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

使用重新導向程式來傳遞每次點按收入。

>[!NOTE]
>
>最佳實務是使用&#x200B;**每次瀏覽分數**&#x200B;參與度量來判斷收入值。

將 `&mboxPageValue=value` 新增至 URL 中。

範例: 若每次點按收入為 0.1 分美元。

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
