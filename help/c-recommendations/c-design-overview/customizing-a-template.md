---
keywords: custom design;velocity;decimal;comma;customize design
description: 使用開放原始碼Velocity設計語言，在Adobe Target Recommendations中自訂建議設計。
title: 使用 Velocity 自訂設計
feature: designs
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 61%

---


# ![PREMIUM](/help/assets/premium.png) 使用 Velocity 自訂設計{#customize-a-design-using-velocity}

使用開放原始碼Velocity設計語言，在[!DNL Adobe Target Recommendations]中自訂建議設計。

## Velocity 概述 {#section_C431ACA940BC4210954C7AEFF6D03EA5}

有關 Velocity 的資訊，請參閱 [](https://velocity.apache.org)https://velocity.apache.org。

所有 Velocity 邏輯、語法等，均可用於建議設計。即是說，您可使用 Velocity 取代 JavaScript 來建立 *for* 迴圈、*if* 陳述式及其他程式碼。

[!DNL Recommendations] mbox 或 CSV 上傳項目中任何傳送至 `productPage` 的變數均可在設計中顯示。這些值以下列語法加以參考:

```
$entityN.variable
```

變數名稱必須遵循 Velocity 縮寫標記法，亦即包含前置 *$* 字元，後接 Velocity 範本語言 (VTL) 識別碼。VTL 識別碼的開頭必須為字母字元 (a-z 或 A-Z)。

Velocity 變數名稱僅限於下列字元類型:

* 字母 (a-z、A-Z)
* 數字 (0-9)
* 連字號 ( - )
* 底線 ( _ )

下列變數可當成 Velocity 陣列使用。因此，可透過索引逐一查看或參照。

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

如需 Velocity 變數的詳細資訊，請參閱 [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables)。

如果您在設計中使用設定檔指令碼，指令碼名稱前面的 $ 必須以 \ 來轉譯。例如, `\${user.script_name}`。

>[!NOTE]
>
>在設計中可參考的實體（硬式編碼或透過循環）數目上限為99。 範本指令碼長度最多可以包含 65,000 個字元。

例如，如果想要讓範本顯示類似下方的內容︰

![](assets/velocity_example.png)

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
>如果要在表示變數名稱已完成的標籤之前，在變數值之後添加文本，則可使用正式符號括住變數名稱。 例如: `${entity1.thumbnailUrl}.gif`。

您亦可在範本中使用 `algorithm.name` 和 `algorithm.dayCount` 當作變數，因此，一個設計便可用於測試多個條件，而條件名稱可動態地在設計中顯示。藉此，訪客即知道自己正在看「最暢銷商品」或「看過這件的人也買那件」。甚至，您可以使用這些變數來顯示 `dayCount` (條件中使用的資料天數，例如「過去 2 天最暢銷的商品」等)。

## 在Velocity範本中使用數字

預設情況下，Velocity模板將所有實體屬性視為字串值。 您可能想要將實體屬性視為數值，以便執行數學運算或將其與其他數值比較。 要將實體屬性視為數值，請執行以下步驟：

1. 宣告虛擬變數，並將其初始化為任意整數或雙重值。
1. 請確定您要使用的實體屬性不是空白（Target Recommendations的範本剖析器驗證並儲存範本時需要）。
1. 在步驟1中建立的虛擬變數上，將entity屬性傳遞至`parseInt`或`parseDouble`方法，將字串轉換為整數或雙重值。
1. 對新數值執行數學運算或比較。

### 範例：計算折扣價格

假設您想要將項目的顯示價格降低$0.99以套用折扣。 您可以使用下列方法來達成此結果：

```
#set( $Double = 0.1 )

#if( $entity1.get('priceBeforeDiscount') != '' )
    #set( $discountedPrice = $Double.parseDouble($entity1.get('priceBeforeDiscount')) - 0.99 )
    Item price: $$discountedPrice
#else
    Item price unavailable
#end
```

### 範例：根據項目的評分選擇要顯示的星數

假設您想根據項目的數值平均客戶評分顯示適當的星數。 您可以使用下列方法來達成此結果：

```
#set( $Double = 0.1 )

#if( $entity1.get('rating') != '' )
    #set( $rating = $Double.parseDouble($entity1.get('rating')) )
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

### 範例：根據項目長度（以分鐘為單位）計算時間（以小時和分鐘為單位）

假設您以分鐘儲存影片長度，但想以小時和分鐘來顯示長度。 您可以使用下列方法來達成此結果：

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## 顯示包含建議產品{#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}的關鍵項目

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

![](assets/rec_key.png)

當您建立 [!DNL Recommendations] 活動時，如果主要項目取自於訪客的設定檔，例如「上次購買的項目」，則 [!DNL Target] 會在[!UICONTROL 可視化體驗撰寫器] (VEC) 中顯示隨機產品。這是因為當您設計活動時，沒有設定檔可用。訪客檢視頁面時就會看到預期的主要項目。

## 在字串值{#section_01F8C993C79F42978ED00E39956FA8CA}中執行替換

您可以修改設計以取代字串中的值。 例如，以歐洲和其他國家使用的逗號分隔字元取代美國使用的小數點分隔字元。

下面顯示一條件式售價範例的其中一行程式碼:

```
<span class="price">$entity1.value.replace(".", ",") €</span><br>
```

以下程式碼為完整的條件式售價範例:

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") €</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") €<br> #else 
    <span class="price">$entity1.value.replace(".", ",") €</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## 自訂範本大小並檢查空白值{#default}

透過 Velocity 指令碼控制實體顯示的動態大小，下列範本可因應 1 對多結果，以免在 [!DNL Recommendations] 傳回的相符實體不足時建立空白的 HTML 元素。最適合使用此指令碼的情況是，備份建議不具有合理意義且已啟用[!UICONTROL 局部範本轉譯]。

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
