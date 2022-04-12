---
keywords: 實體;實體屬性;傳遞資訊至 Recommendations;行為資料;資料計數器;定義相對 URL;顯示詳細目錄層級;定義價格;定義利潤;自訂屬性
description: 瞭解如何使用實體屬性將產品或內容資訊傳遞給 [!DNL Target] Recommendations。
title: 如何使用實體屬性？
feature: Recommendations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 55%

---

# ![PREMIUM](/help/main/assets/premium.png) 實體屬性

使用實體屬性來傳遞產品或內容資訊至 [!DNL Adobe Target Recommendations].

實體會參考您要建議的項目。實體可以包括產品、內容（文章、幻燈片、影像、電影和電視節目）、工作清單、餐廳等。

[!DNL Recommendations] 會傳送演算法中所用的 `productId` 或 `productPurchasedId` (即程式碼中的 `entity.id`)。

考慮以下事項:

* `entity.id` 必須匹配 `productPurchasedId` 發送到訂單確認頁和 `productId` 用於 [!DNL Adobe Analytics] 產品報告。
* 傳遞給的實體屬性值 [!DNL Recommendations] 61天後過期。 Adobe建議將每個實體屬性的最新值傳遞給 [!DNL Recommendations] 每月至少為目錄中的每個項目一次。

大多數預定義參數只接受單個值，新值覆蓋舊值。 對於包含該產品的每個類別，`categoryId` 參數都能接受值的逗號分隔清單。新的 `categoryId` 值不會覆寫現有值，而是在實體更新期間附加 (250 個字元限制)。

通常，如果您使用at.js 1，則顯示資訊框與以下示例類似。*x* 與 `mboxCreate`。 所有實體參數屬性都區分大小寫。

>[!NOTE]
>
>如果您使用at.js 2。*x*。 `mboxCreate` （如下例所用）不再受支援。 將產品或內容資訊傳遞到 [!DNL Recommendations] 使用at.js 2。*x*。 [targetPageParams](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md)。 有關示例，請參見 [規劃和實施Recommendations](/help/main/c-recommendations/plan-implement.md)。

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

的 `entity.id` 值 *不* 包含斜槓、和號、問號、百分比符號、逗號或其他標點字元，在REST API調用中傳遞時需要URL編碼。 允許使用連字元和下划線。 `entity.id`[!DNL Recommendations] 值包含無效標點符號，會造成部分 功能無法使用。

範例: `'entity.id=67833'`

### entity.name

僅限單一值。

建議產品時，網站上顯示的產品名稱。

範例: `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

支援多個值 (以逗號分隔值的清單)。

目前頁面的類別。entity.categoryID可以包括多個類別，如羊毛衫子子子小節(例如，女人、女人：毛衣、女人:sweaters:羊毛衫)。 多個類別必須用逗號分隔。

的 `categoryId` 值限制為250個字元。

>[!NOTE]
>
>若要根據[!UICONTROL 「類別」]頁面顯示建議，只能將一個 `categoryId` 傳遞至用於顯示該特定建議的 mbox。`categoryId` 的值必須與「產品詳細資料」頁面上傳遞之 `entity.categoryId` 的值完全相符。

範例:

* 「產品詳細資訊」頁示例：女人，女人：毛衣，女人:sweaters:羊毛衫
* 類別頁面範例 Sweaters:womens:sweaters
* 示例類別頁開襟羊毛衫：女性:sweaters:羊毛衫

對於基於類別的建議，用逗號分隔類別值。 以逗號區隔的值都會成為類別。您也可以使用不同的分隔符號來定義子類別，例如冒號 (:)，用以區隔類別值中的子類別。

例如，在以下代碼中，婦女類別分為幾個子類別：

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

針對 mbox 傳送，將使用最長的屬性名稱做為索引鍵。如果出現平手狀況，將使用最後一個屬性。在上例中，類別鍵為Womens:Outerwear:夾克：卡班。

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

關於建議中所顯示產品的訊息，例如「特價」或「出清」。訊息通常較產品名稱更詳細。使用entity.message定義要與模板中的產品一起顯示的附加資訊。

範例: `'entity.message=Family&nbsp;special'`

### entity.inventory

僅限單一值。需要整數或 Long 值。

顯示項目的庫存水平。

範例: `'entity.inventory=1'`

**空庫存屬性處理：** 對於交貨，如果您具有包含規則、收集規則或條件設定 `entity.inventory` > 0或 `entity.inventory` = 0，產品未設定庫存， [!DNL Target] 將此值評估為TRUE，並包括未設定庫存的產品。 因此，未設定庫存的產品將顯示在建議結果中。

同樣地，如果您有一個全域排除規則，其中 `entity.inventory` = 0 且未設定 `entity.inventory`，則 [!DNL Target] 會將此規則評估為 TRUE，並排除該產品。

**已知問題：** 產品搜索與未設定的庫存值屬性的交貨不一致。 例如，對於具有 `entity.inventory` = 0，「產品搜索」不顯示未設定庫存值的產品。

### entity.value

僅限單一值。

定義項目的價格或價值。

範例: `'entity.value=15.99'`

entity.value僅支援小數格式（例如15.99）。 不支援逗號格式(15,99)。

### entity.margin

僅限單一值。

項目的利潤率或其他值。

範例: `'entity.margin=1.00'`

### entity.*custom*

支援多個值 (JSON 陣列)。

定義最多 100 個自訂變數，用以提供項目的額外資訊。您可為各個自訂屬性指定任何未使用的屬性名稱。例如，可以建立名為 `entity.genre` 定義書籍或電影。 票證供應商可以為輔助表演者的活動場所建立屬性，例如體育賽事中的訪問團隊或音樂會的開幕活動。

限制:

* 您無法對自訂實體屬性使用預先定義的實體屬性名稱。
* 屬性 entity.environment 由系統保留，並且無法用於自訂實體屬性。忽略使用targetPageParams、feed或API傳遞entity.environment的嘗試。

範例:

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

自訂實體屬性支援多個值。若要瞭解字元和值限制，請參閱[自訂實體屬性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#limits)。

範例: `'entity.secondary=["band1",&nbsp;"band2"]'`

多值自訂實體屬性需要有效的 JSON 陣列。有關正確的語法資訊，請參見 [自定義實體屬性](/help/main/c-recommendations/c-products/custom-entity-attributes.md)。

### entity.event.detailsOnly

僅限單一值。

用來防止 mbox 呼叫遞增演算法的行為資料計數器。

範例: `'entity.event.detailsOnly=true'`

在下面的示例中，第一個框調用更新目錄和行為資料。 第二個框調用僅更新目錄。

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

>[!MORELIKETHIS]
>
>* [自訂實體屬性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
