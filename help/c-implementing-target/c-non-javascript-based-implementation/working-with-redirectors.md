---
description: 使用「重新導向程式」的方式和您在測試中使用 mbox 類似。
keywords: 實作;mbox.js non javascript;重新導向程式;每次點擊成本;每次點擊收入
seo-description: 使用「重新導向程式」的方式和您在測試中使用 mbox 類似。
seo-title: 使用重新導向程式
solution: Target
subtopic: 快速入門
title: 使用重新導向程式
topic: Standard
uuid: 79d7caf6-5693-4bb3-9131-8d1ae420fa5e
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

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

如需有關決定正確設定的說明，請參閱[非 JavaScript 型實作](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)。

## 建立重新導向程式 {#task_76608B0F73FC45C4A9F125B894DCF821}

您必須先建立重新導向程式才能加以使用。

1. 決定廣告目的地的變數，包括預設目的地。
1. 建立重新導向程式 URL。

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * 您 `yourclientcode` 公司的客戶代碼。您的公司用戶端代碼為全部小寫並且不帶特殊字元。

      * **at.js:** 您的用戶端代碼可在 [!UICONTROL  介面的]「設定 &gt; 實作 &gt; 編輯 at.js 設定」[!DNL Target]頁面最上方取得。

      * **mbox.js:** 您的用戶端代碼可在[!UICONTROL 「設定 &gt; 實作 &gt; 編輯 Mbox.js 設定」]頁面最上方取得。
   * `redirectorlink_456` 代表重新導向程式 mbox 的名稱，會顯示在您用於促銷活動和測試的帳戶中。

      重新導向程式的功能與其他 mbox 不同，但外觀就如同您帳戶中的其他 mbox 一樣。請為重新導向程式命名，以便容易區別它們和您帳戶中其他標準類型的 mbox。作為最佳作法，請從名稱為 &#39;redirectorlink&#39; 的 mbox 開始。

   * 預設 `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` 目的地。

      此網址必須經過 URL 編碼，且必須為絕對參照。您可以使用 [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) 來快速編碼您的URL。|



1. 驗證重新導向程式。
   1. 請將「重新導向程式 URL」插入到瀏覽器中，然後重新整理。
   1. 登入您的帳戶，重新整理您的 mbox 清單，然後確認新的「重新導向程式」是否已列為 mbox。
1. 如果要測試某個廣告的不同目的地，請分別為每個版本建立[重新導向選件](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。
1. 建立促銷活動。

   請參閱[非 JavaScript 型實作](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)，以瞭解符合您目標的正確設定。
1. 完成促銷活動上的品質保證。

   以包含重新導向程式 URL 的 `<a href>` 建立一個虛擬頁面。範例:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. 請確認對所有的環境來說，所有的體驗、預設內容與報表都如預期般在所有瀏覽器類型上運作。

   >[!NOTE] {class=&quot;- topic/note &quot;}
   >
   >* mbox 的「選件預覽」或「瀏覽」不支援重新導向程式。直接在瀏覽器中預覽體驗。
   >* `mboxDebug` 不能用於重新導向程式。


1. 將完整的重新導向程式 URL 作為廣告目的地，提交到您的顯示廣告網路。

## 對每次點擊成本和每次點擊收入使用重新導向程式 {#concept_3078EF48E9C44B34992D62AAB9628853}

關於對每次點擊成本和每次點擊收入使用重新導向程式的資訊。

### 傳遞每次點擊的成本 {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

使用重新導向程式來傳遞每次點按成本。

>[!NOTE]
>
>最佳實務是使用每次瀏覽 **分數** 參與度量判斷成本值， [如參與所述](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html)。

將 `&mboxPageValue=-value` 新增至 URL 中。請注意負值。

範例: 若每次點按成本為 0.1 分美元:

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### 傳遞每次點擊的收入 {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

使用重新導向程式來傳遞每次點按收入。

>[!NOTE]
>
>最佳實務是使用每次瀏覽 **分數** 參與度量判斷收入值， [如參與所述](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html)。

將 `&mboxPageValue=value` 新增至 URL 中。

範例: 若每次點按收入為 0.1 分美元。

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
