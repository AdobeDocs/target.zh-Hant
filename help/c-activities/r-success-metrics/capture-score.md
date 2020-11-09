---
keywords: capture score;score
description: 「擷取分數」參與度量會根據指派給網站上瀏覽之頁面的值，從訪客首次看到促銷活動的第一個顯示「目標請求」開始計算匯總分數。
title: 擷取分數
feature: success metrics
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 51%

---


# 擷取分數{#capture-score}

The Capture Score engagement metric calculates an aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the campaign&#39;s first display [!DNL Target] request.

下列範例會說明如何計算促銷活動中的分數參與，這個促銷活動會測試兩種體驗，一種包含貓的圖片，另一種則包含狗的圖片。

![](assets/example_score.png)

在本範例中，第一位訪客會看到貓的圖片。Assume that a global [!DNL Target] request passes in a page score based on the value of the page. If the marketer has captured page count engagement on a success metric associated with `**any Target request**`, the visit score accumulates for any request seen after the display request around the cat image.

第一頁將分數加 1，第二頁加 0.25，第三頁加 0.10，第四頁加 0.10，總共是 1.45。這可以解讀為貨幣或點數。在個別的瀏覽中，訪客會看到「狗」的圖片，雖然訪客檢視的頁面較少，但由於訪客檢視的重要頁面較多，因此仍會獲得高於其他瀏覽的 2.10 分數。

您可以考慮透過傳遞 adbox 和重新導向程式，來採用贏取成本和附屬單位連結收入，如以下的頁面流程中所述。Notice that, in this example, both [!DNL Target] requests on the article page pass a score, possibly representing a known CPM.

![](assets/example_score2.png)

**指定頁面分數**

您可以根據頁面的價值，在網站上為任何頁面指定一個值。例如，烹飪網站在精選文章頁面銷售廣告所賺取的金錢，可能會比在體驗區段更多。因此，精選文章的價值會高於體驗區段。頁面分數可讓您開發瀏覽的整體「值」，因此閱讀越多精選文章的使用者較僅瀏覽體驗的使用者獲得更多「點數」。

指定頁面分數共有以下兩種方法:

* 在請求 [!DNL Target] 中，建立名為的參數 `mboxPageValue`。

   範例: `('global_mbox', 'mboxPageValue=10');`

   The specified value is added to the score every time the page with that [!DNL Target] request is viewed. 如果頁面上的多個請求包含分數值，則頁面的分數是所有請求值的總和。 `mboxPageValue` 是保留的參數，用於傳遞Target請求中的值以擷取參與分數。 可傳入正值和負值。每位訪客造訪後會計算總和，以計算該次造訪的總分數。

* 在頁面 URL 中傳入 `?mboxPageValue=n` 參數。

   範例: `https://www.mydomain.com?mboxPageValue=5`

   Using this method, the specified value is added to the score for each [!DNL Target] request on the page. For example, if you pass the parameter `?mboxPageValue=10`and there are three [!DNL Target] requests on the page, the score for the page is 30.

>[!NOTE]
>
>位於活動第一個顯示請求上方的 [!DNL Target] 定位請求將不會包含在分數中。

Best practice is to assign values in the [!DNL Target] request. 這可讓您根據每個請求的內容，精確測量值。

>[!NOTE]
>
>為了便於維護，您可以在 [!DNL at.js] 或 [!DNL mbox.js] 檔案中，運用某些條件式 JavaScript 邏輯來設定網站的頁面分數值指派。這樣便無須在頁面中新增更多程式碼。請連絡您的帳戶顧問以取得協助。

您可以併用兩種方法，但可能會導致分數高於預期值。For example, if you assign a value of 10 to each of three [!DNL Target] requests and no score to a fourth request, then pass the URL parameter `?mboxPageValue=5`, your page score will be 50, 30 for the three requests with assigned values, and then 5 for each of the four requests on the page.

計數器以第一個顯示請求開始，而非輸入請求。 例如，如果您在沒有顯示請求的首頁上輸入活動，然後連結至包含顯示請求的目錄頁面，則計數器會在您移至目錄頁面時開始計算。

您也可以針對需要花費金錢或不適合訪客瀏覽的特定頁面，來傳遞負值。負值也會影響整體分數。您可以在訪客透過廣告到達的頁面上使用此方法，以瞭解 CPC 的價格。或者舉例來說，此方法可用於支援或連絡頁面，而您可以從中瞭解訪客可能透過此頁面呼叫或要求協助。
