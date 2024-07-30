---
keywords: 自訂設計;velocity;小數點;逗號;自訂設計
description: 瞭解如何使用開放原始碼 [!DNL Velocity] 設計語言來自訂 [!DNL Target] Recommendations中的建議設計。
title: 如何使用Velocity自訂設計？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 035d7988-80d8-4080-bb0d-1d0e9f8856d1
source-git-commit: eba9e0b02ce74fea127d2cb2d08d04dcd2da2d76
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 33%

---

# 使用[!DNL Velocity]自訂設計

使用開放原始碼[!DNL Velocity]設計語言來自訂[!DNL Adobe Target Recommendations]中的建議設計。

## [!DNL Velocity]總覽 {#section_C431ACA940BC4210954C7AEFF6D03EA5}

有關[!DNL Velocity]的資訊可在[https://velocity.apache.org](https://velocity.apache.org)中找到。

所有[!DNL Velocity]邏輯、語法等均可用於建議設計。 這表示您可以使用[!DNL Velocity]而非JavaScript來建立&#x200B;*for*&#x200B;回圈、*if*&#x200B;陳述式及其他程式碼。

傳送至`productPage` mbox中的[!DNL Recommendations]或CSV上傳的實體屬性可以在設計中顯示，但「多值」屬性除外。 任何型別的屬性都可以傳送；不過，[!DNL Target]不會傳遞型別「多值」的屬性做為範本可以反複處理的陣列（例如`entityN.categoriesList`）。

這些值以下列語法加以參考:

```
$entityN.variable
```

實體屬性名稱必須遵循[!DNL Velocity]速記符號，由前導的&#x200B;*$*&#x200B;字元組成，後面接著[!DNL Velocity]範本語言(VTL)識別碼。 VTL 識別碼的開頭必須為字母字元 (a-z 或 A-Z)。

Velocity實體屬性名稱僅限於下列字元型別：

* 字母 (a-z、A-Z)
* 數字 (0-9)
* 連字號 ( - )
* 底線 ( _ )

下列屬性可做為[!DNL Velocity]陣列使用。 因此，可透過索引逐一查看或參照。

* `entities`
* `entityN.categoriesList`

例如:

```
#foreach ($category in $entity1.categoriesList) 
<br/>$category 
#end
```

或

```
#if ($entities[0].categoriesList.size() >= 3 ) 
$entities[0].categoriesList[2] 
#end
```

如需[!DNL Velocity]變數（屬性）的詳細資訊，請參閱[https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables)。

如果您在設計中使用設定檔指令碼，指令碼名稱前面的$必須以`\` （反斜線）逸出。 例如：

`\${user.script_name}`

>[!NOTE]
>
>可在設計中參照（硬式編碼或透過回圈）的實體數上限為99。 範本指令碼長度最多可以包含 65,000 個字元。

例如，如果想要讓範本顯示類似下方的內容︰

![velocity_example image](assets/velocity_example.png)

您可使用下列代碼:

```
<table style="border:1px solid #CCCCCC;"> 
<tr> 
<td colspan="3" style="font-size: 130%; border-bottom:1px solid  
#CCCCCC;"> You May Also Like... </td> 
</tr> 
<tr> 
<td style="border-right:1px solid #CCCCCC;"> 
<div class="search_content_inner" style="border-bottom:0px;"> 
<div class="search_title"><a href="$entity1.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity1.id</a></div> 
By $entity1.message <a href="?x14=brand;q14=$entity1.message"> 
(More)</a><br/> 
sku: $entity1.prodId<br/> Price: $$entity1.value 
<br/><br/> 
</div> 
</td> 
<td style="border-right:1px solid #CCCCCC; padding-left:10px;"> 
<div class="search_content_inner" style="border-bottom:0px;">  
<div class="search_title"><a href="$entity2.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity2.id</a></div> 
By $entity2.message <a href="?x14=brand;q14=$entity2.message"> 
(More)</a><br/> 
sku: $entity2.prodId<br/> 
Price: $$entity2.value 
<br/><br/> 
</div> 
</td> 
<td style="padding-left:10px;"> 
<div class="search_content_inner" style="border-bottom:0px;"> 
<div class="search_title"><a href="$entity3.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity3.id</a></div> 
By $entity3.message <a href="?x14=brand;q14=$entity3.message"> 
(More)</a><br/> 
sku: $entity3.prodId<br/> Price: $$entity3.value 
<br/><br/> 
</div> 
</td> 
</tr>  
</table>
```

>[!NOTE]
>
>如果您想要在指出屬性名稱的標籤完成之前，在屬性值之後新增文字，您可以使用正式標籤法將屬性名稱括起來。 例如: `${entity1.thumbnailUrl}.gif`。

您也可以在設計中使用`algorithm.name`和`algorithm.dayCount`作為實體屬性，因此一個設計可用於測試多個條件，而條件名稱可動態地顯示在設計中。 藉此，訪客即知道自己正在看「最暢銷商品」或「看過這件的人也買那件」。您甚至可以使用這些屬性來顯示`dayCount` （條件中使用的資料天數，例如「過去2天最暢銷的商品」等）。

## 使用[!DNL Velocity]範本中的數字

根據預設，[!DNL Velocity]範本會將所有實體屬性視為字串值。 您可能想要將實體屬性視為數值，以便執行數學運算或將其與其他數值進行比較。 若要將實體屬性視為數值，請遵循下列步驟：

1. 宣告虛擬變數並將其初始化為任意整數或雙精度數值。
1. 請確定您要使用的實體屬性不是空白的（[!DNL Target Recommendations]範本剖析器驗證並儲存範本的必要專案）。
1. 將實體屬性傳遞至您在步驟1中建立的虛擬變數上的`parseInt`或`parseDouble`方法，以將字串轉換為整數或雙精度數值。
1. 對新數值執行數學運算或比較。

### 範例：計算折扣價

假設您要將料號的顯示價格降低$0.99以套用折扣。 您可以使用下列方法來取得此結果：

```
#set( $double = 0.1 )

#if( $entity1.get('priceBeforeDiscount') != '' )
    #set( $discountedPrice = $double.parseDouble($entity1.get('priceBeforeDiscount')) - 0.99 )
    Item price: $$discountedPrice
#else
    Item price unavailable
#end
```

### 範例：根據專案的評等選擇星級數

假設您想要根據專案的數值平均客戶評等顯示適當的星級數。 您可以使用下列方法來取得此結果：

```
#set( $double = 0.1 )

#if( $entity1.get('rating') != '' )
    #set( $rating = $double.parseDouble($entity1.get('rating')) )
    #if( $rating >= 4.5 )
        <img src="5_stars.jpg">
    #elseif( $rating >= 3.5 )
        <img src="4_stars.jpg">
    #elseif( $rating >= 2.5 )
        <img src="3_stars.jpg">
    #elseif( $rating >= 1.5 )
        <img src="2_stars.jpg">
    #else
        <img src="1_star.jpg">
    #end
#else
    <img src="no_rating_default.jpg">
#end
```

### 範例：根據專案的長度（分鐘），以小時和分鐘計算時間

假設您以分鐘儲存影片長度，但想要以小時和分鐘顯示長度。 您可以使用下列方法來取得此結果：

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## 顯示含有建議產品的關鍵專案 {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

您可以修改設計來連同其他建議的產品一起顯示主要項目。例如，您可以在建議旁邊顯示目前項目當作參考。

方法是在設計中建立一欄，此欄使用您的建議所依據的 `$key` 屬性，而不是 `$entity` 屬性。例如，主要欄的程式碼可能如下所示:

```
<div class="at-table-column"> 
   <a href="$key.pageURL"> 
      <img src=$key.thumbnailUrl" class="at-thumbnail"/> 
      <br/><h3>$key.name</h3> 
      <br/><p class="at-light">$key.message</p> 
      <br/><p class="at-light">$key.value</p> 
   </a> 
</div>
```

結果會產生如下的設計，其中有一欄顯示主要項目。

![rec_key影像](assets/rec_key.png)

當您建立[!DNL Recommendations]活動時，如果主要專案取自於訪客的設定檔，例如「上次購買的專案」，則[!DNL Target]會在[!UICONTROL Visual Experience Composer] (VEC)中顯示隨機產品。 這是因為當您設計活動時，沒有設定檔可用。訪客檢視頁面時就會看到預期的主要項目。

## 在字串值中執行取代 {#section_01F8C993C79F42978ED00E39956FA8CA}

您可以修改設計，以取代字串中的值。 例如，將美國使用的小數點分隔符號取代為歐洲和其他國家使用的逗號分隔符號。

下面顯示一條件式售價範例的其中一行程式碼:

```
<span class="price">$entity1.value.replace(".", ",") &euro;</span><br>
```

以下程式碼為完整的條件式售價範例:

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") &euro;</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") &euro;<br> #else 
    <span class="price">$entity1.value.replace(".", ",") &euro;</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## 自訂範本大小並檢查空白值 {#default}

使用[!DNL Velocity]指令碼控制實體顯示的動態大小，下列範本可因應1對多結果，以免在[!DNL Recommendations]傳回的相符實體不足時建立空白的HTML元素。 此指令碼最適合備份建議沒有意義且已啟用[!UICONTROL Partial Template Rendering]的情況。

下列 HTML 片段會取代 4x2 預設設計中的現有 HTML 部分 (為了簡潔起見，此處未包含 CSS):

* 如果第五個實體存在，指令碼會插入右 div 標記，並使用 `<div class="at-table-row">` 開啟新的一列。
* 透過 4x2，最多將可顯示八個結果，但您可以修改 `$count <=8`，將此自訂為較小或較大的清單。
* 請注意，邏輯不會平衡多個列上的實體。例如，如果有五個或六個要顯示的實體，並不會動態變成三個在頂端、兩個在底部 (或三個在頂端、三個在底部)。開始第二列之前，頂端列會顯示四個項目。

```
<div class="at-table">
  <div class="at-table-row">
    #set($count=1) 
    #foreach($e in $entities)  
        #if($e.id != "" && $count < $entities.size() && $count <=8) 
            #if($count==5) 
                </div>
                <div class="at-table-row">
            #end
            <div class="at-table-column">
                <a href="$e.pageUrl"><img src="$e.thumbnailUrl" class="at-thumbnail" />
                    <br/>
                    <h3>$e.name</h3>
                    <br/>
                    <p class="at-light">$e.message</p>
                    <br/>
                    <p class="at-light">$$e.value</p>
                </a>
            </div>
            #set($count = $count + 1) 
        #end 
    #end
  </div>
</div>
```
