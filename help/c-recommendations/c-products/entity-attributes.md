---
keywords: 實體;實體屬性;傳遞資訊至 Recommendations;行為資料;資料計數器;定義相對 URL;顯示詳細目錄層級;定義價格;定義利潤;自訂屬性
description: 使用實體屬性將產品或內容資訊傳遞至Adobe Target Recommendations。
title: 實體屬性
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 91%

---


# ![PREMIUM](/help/assets/premium.png) 實體屬性{#entity-attributes}

使用實體屬性來傳遞產品或內容資訊至 [!DNL Adobe Target Recommendations].

[!DNL Recommendations] 會傳送演算法中所用的 `productId` 或 `productPurchasedId` (即程式碼中的 `entity.id`)。

>[!NOTE]
>
>* `entity.id` 必須符合 `productPurchasedId` 傳送至訂單確認頁面和Adobe Analytics產 `productId` 品報表中所使用的項目。
   >
   >
* 提供的實體屬性值會在 61 天後過期。這表示您應確實針對目錄中的每個項目，每個月至少傳送一次每個實體屬性的最新值至 Target Recommendations。


多數預先定義的參數僅接受單一值，以新的值覆寫舊的值。對於包含該產品的每個類別，`categoryId` 參數都能接受值的逗號分隔清單。新的 `categoryId` 值不會覆寫現有值，而是在實體更新期間附加 (250 個字元限制)。

一般而言，如果您使用at.js 1，顯示資訊mbox可能會類似下列範例。** xwith `mboxCreate`。

>[!NOTE]
>
>* 如果您使用at.js 2。*x*, `mboxCreate` （如下例所用）不再受支援。若要使用at.js 2將產品或內容資訊傳遞至Recommendations。*x*，請使 [用targetPageParams](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md)。如需範例，請參閱[計畫並實作Recommendations](/help/c-recommendations/plan-implement.md)。

>



所有實體參數屬性均區分大小寫。

```javascript
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=/help/baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=/help/baseball/giants-tix/giants-136px.gif', 
 
'entity.message=FAMILY SPECIAL', 
 
'entity.value=15.99', 
 
'entity.inventory=1' 
 
); 
 
</script>
```

>[!NOTE]
>
>`pageUrl` 和 `thumbnailUrl` 最好使用相對 URL 而非絕對 URL，因為建議會接收從您網站上所有環境傳出的資料。使用相對 URL 會避免硬式編碼連結至開發用伺服器或程式開發伺服器。

如果 mbox 位於產品頁面，那麼，您可同時包括產品 ID 和類別 ID。所選的演算法決定了顯示方式。產品 ID 用於相關性演算法，類別 ID 用於類別演算法。

## 可用變數

以下清單說明可用的變數。

### entity.id

僅限單一值。

該必需的參數用於識別產品。該英數字元 ID 必須在所有使用的 [!DNL Adobe Experience Cloud] 產品中保持一致 (包括 [!DNL Analytics])，以便各種產品識別項目並共用相關資料。

`entity.id` 值不得包含斜線、&amp; 符號、問號、百分比符號、逗號，或其他在 REST API 呼叫中傳送時需要 URL 編碼的標點符號字元。但可使用連字號和底線。`entity.id`[!DNL Recommendations] 值包含無效標點符號，會造成部分 功能無法使用。

範例: `'entity.id=67833'`

### entity.name

僅限單一值。

建議產品時，網站上顯示的產品名稱。

範例: `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

支援多個值 (以逗號分隔值的清單)。

目前頁面的類別。其中可能包括多個類別，例如子區段的子項 cardigans (即 womens、womens:sweaters、womens:sweaters:cardigans)。多個類別應該以逗號區隔。

`categoryId` 限定為 250 字元以內。

>[!NOTE]
>
>若要根據[!UICONTROL 「類別」]頁面顯示建議，只能將一個 `categoryId` 傳遞至用於顯示該特定建議的 mbox。`categoryId` 的值必須與「產品詳細資料」頁面上傳遞之 `entity.categoryId` 的值完全相符。

範例:

* 產品詳細資料頁面範例: womens, womens:sweaters, womens:sweaters:cardigans
* 類別頁面範例 Sweaters:womens:sweaters
* 類別頁面範例 Cardigans: womens:sweaters:cardigans

若使用類別型建議，請使用逗號來區隔類別值。以逗號區隔的值都會成為類別。您也可以使用不同的分隔符號來定義子類別，例如冒號 (:)，用以區隔類別值中的子類別。

例如，在下列程式碼中，Womens 類別又區分為數個子類別:

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

針對 mbox 傳送，將使用最長的屬性名稱做為索引鍵。如果出現平手狀況，將使用最後一個屬性。在上述範例中，類別索引鍵是 Womens:Outerwear:Jackets:Caban。

### entity.brand

僅限單一值。

顯示項目的品牌名稱。

範例: `'entity.brand=brandxyz'`

### entity.pageUrl

僅限單一值。

定義了可購買項目的頁面的相對 URL。

範例: `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### entity.thumbnailUrl

僅限單一值。

定義了與項目一同顯示的縮圖影像的相對 URL。

範例: `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### entity.message

僅限單一值。

關於建議中所顯示產品的訊息，例如「特價」或「出清」。訊息通常較產品名稱更詳細。用來定義要在範本中隨著產品顯示的其他資訊。

範例: `'entity.message=Family&nbsp;special'`

### entity.inventory

僅限單一值。需要整數或 Long 值。

顯示項目的庫存水平。

範例: `'entity.inventory=1'`

**空庫存屬性處理:** 對於傳送，如果您有包含規則、集合規則，或條件設定 (其中 `entity.inventory` > 0 或 `entity.inventory` = 0)，而且產品未設定庫存，則 [!DNL Target] 會將此評估為 TRUE，且包含未設定庫存的產品。這是在預設情況下完成的，因此具有未設定庫存的產品會顯示在建議結果中。

同樣地，如果您有一個全域排除規則，其中 `entity.inventory` = 0 且未設定 `entity.inventory`，則 [!DNL Target] 會將此規則評估為 TRUE，並排除該產品。

**已知問題:** 產品搜尋與未設定庫存值屬性的傳送不一致。例如，若規則中包含 `entity.inventory` = 0，「產品搜尋」將不會顯示未設定庫存值的產品。

### entity.value

僅限單一值。

定義項目的價格或價值。

範例: `'entity.value=15.99'`

### entity.margin

僅限單一值。

項目的利潤率或其他值。

範例: `'entity.margin=1.00'`

### entity.*custom*

支援多個值 (JSON 陣列)。

定義最多 100 個自訂變數，用以提供項目的額外資訊。您可為各個自訂屬性指定任何未使用的屬性名稱。例如，您可以建立稱為 `entity.genre` 的自訂屬性，以定義書籍或電影。或者，票務公司可就次要參與者的活動地點來建立屬性，包括體育賽事中的客隊或音樂會中的開幕表演。

限制:

* 您無法對自訂實體屬性使用預先定義的實體屬性名稱。
* 屬性 entity.environment 由系統保留，並且無法用於自訂實體屬性。嘗試使用 targetPageParams、摘要或 API 來傳遞 entity.environment 將被忽略。

範例:

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

自訂實體屬性支援多個值。若要瞭解字元和值限制，請參閱[自訂實體屬性](/help/c-recommendations/c-products/custom-entity-attributes.md#limits)。

範例: `'entity.secondary=["band1",&nbsp;"band2"]'`

>[!NOTE]
>
>多值自訂實體屬性需要有效的 JSON 陣列。如需正確語法資訊，請參閱「自訂實體屬性」。

### entity.event.detailsOnly

僅限單一值。

用來防止 mbox 呼叫遞增演算法的行為資料計數器。

範例: `'entity.event.detailsOnly=true'`

在以下範例中，第一個 mbox 呼叫將更新目錄和行為資料。第二個 mbox 呼叫將僅更新目錄。

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

## 相關主題:

* [自訂實體屬性](/help/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
