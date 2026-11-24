---
keywords: 多值；屬性；建議；多值；多值
description: 瞭解如何使用特殊的多值運運算元在[!DNL Target Recommendations]中使用多值欄位。
title: 使用多值屬性
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
TQID: 'https://experienceleague.adobe.com/FrjVxvYfGh2o-qomXRbVh6WS6f65Mja41gBMhejEPlE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 2%
---
# 使用多值屬性 {#multi-value-attributes}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何傳送多值資料給[!DNL Adobe Target Recommendations]，以及如何在多值運運算元的包含規則中使用資料。

>[!ENDSHADEBOX]

多值欄位會保留相同專案或訪客的多個值。 例如：

* 提供給使用者的電影：指定電影有多位演員。
* 演唱會門票已售：特定使用者有多個最喜愛的樂隊。
* 已售出衣服：襯衫有多種尺寸。

若要處理這些案例中的建議，可將多值資料傳遞至[!DNL Target Recommendations]並搭配特殊的多值運運算元使用。

## 傳送多值資料 {#send}

若要允許[!DNL Recommendations]識別多值資料，應以JSON陣列傳送。

若為JavaScript (`targetPageParams`)中的多值引數，請參閱&#x200B;*自訂實體屬性*&#x200B;中的[實作多值屬性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14)。

在CSV檔案中，多值實體屬性會在屬性的儲存格中以JSON陣列形式傳送，如以下範例所示。

+++ 具有多值屬性的範例CSV檔案

```
## RECSRecommendations Upload File,,,,,,,,,,,,,,,,,,,
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines.,,,,,,,,,,,,,,,,,,,
## RECS,,,,,,,,,,,,,,,,,,,
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left.,,,,,,,,,,,,,,,,,,,
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'.,,,,,,,,,,,,,,,,,,,
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations.,,,,,,,,,,,,,,,,,,,
## RECSentity.id ,entity.name,entity. categoryId ,entity. message ,entity.thumbnailUrl ,entity.value ,entity.pageUrl ,entity.inventory ,entity.margin ,entity.custom1 ,entity.custom2 ,entity.custom3 ,entity.custom4,entity.custom5,entity.custom6,entity.custom7,entity.custom8,entity.custom9,entity.custom10,
1,Sample Product 1,category1,Save 10%,http://sample.store/products/images/product1_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=1,1000,48,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
2,Sample Product 2,category1,Save 10%,http://sample.store/products/images/product2_th.jpg,369,http://sample.store/products/product_detail.jsp?productId=2,1000,52,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
3,Sample Product 3,category1,Save 10%,http://sample.store/products/images/product3_th.jpg,479,http://sample.store/products/product_detail.jsp?productId=3,1000,78,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
4,Sample Product 4,category1,Save 10%,http://sample.store/products/images/product4_th.jpg,409,http://sample.store/products/product_detail.jsp?productId=4,1000,66,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
5,Sample Product 5,category1,Save 10%,http://sample.store/products/images/product5_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=5,1000,45,a,"[ ""v1"", ""v2"" ]",,,,,,,,, 
```

+++

在此格式中提供實體屬性、設定檔屬性或mbox引數為多值時，[!DNL Recommendations]會自動推斷欄位是多值。

## 在包含規則中使用多值屬性 {#multi-value-inclusion-rules}

下列運運算元可搭配多值實體、設定檔和mbox屬性使用：

* **[!UICONTROL 包含在清單]**&#x200B;中
* **[!UICONTROL 不在清單]**&#x200B;中

>[!NOTE]
>
>目前，只有使用設定檔屬性比對或引數(mbox)屬性比對規則（將左側的單一值與右側的多個值比較）的條件，才支援動態比對多值屬性。 促銷活動、實體屬性比對或包含規則左側的清單目前不支援多值屬性。

### 範例：排除最近觀看的專案

若要避免建議使用者觀看的最後10部影片中的任何影片，請先撰寫名為`user.lastWatchedMovies`的設定檔指令碼，以JSON陣列形式追蹤最後10部檢視的影片。 然後可以使用以下包含規則排除專案：

```
Profile Attribute Matching
id - is not contained in list - user.lastWatchedMovies
```

包含規則的JSON API表示法：

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": "user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### 範例：從使用者的最愛中建議專案

只有當樂團演奏是使用者最喜愛的樂團之一時，才建議音樂會票證，需要兩個專案：名為`profile.favoriteBands`的設定檔變數包含使用者最喜愛的樂隊，以及目錄中的屬性`entity.artistPerforming`，包含音樂會中演奏的藝人。 然後可以使用以下包含規則：

```
Profile Attribute Matching
artistPerforming - is contained in list - profile.favoriteBands
```

包含規則的JSON API表示法：

```
{
    "attribute": "artistPerforming",
    "operation": "isContainedInList",
    "source": {
        "name": "profile.favoriteBands",
        "type": "PROFILE"
    }
}
```

### 範例：API建立條件，從使用者的最愛中建議專案

使用多值篩選規則的條件可以透過[!DNL Adobe Target] API建立，例如所有條件。 下列範例API呼叫會建立條件，其中實體屬性`id`包含在mbox引數清單`favorites`中：

```
curl -X POST \
  https://<serverhost>/api/recs/<client>/criteria/item \
  -H 'Accept: application/vnd.adobe.target.v1+json' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: <from API client>' \
  -H 'X-Target-user-email: <email address>' \
  -H 'cache-control: no-cache' \
  -d '{
    "name": "viewed criteria",
    "criteriaTitle": "test title",
    "type": "VIEWED_CF",
    "key": "CURRENT",
    "daysCount": "TWO_WEEKS",
    "aggregation": "NONE",
    "backupDisabled": false,
    "partialDesignAllowed": true,
    "configuration": {
        "inclusionRules": [
            {
                "attribute": "id",
                "operation": "isContainedInList",
                "source": {
                    "name": "mbox.favorites",
                    "type": "MBOX"
                }
            }
        ]
    }
}'
```

此呼叫會與傳入我的最愛內容之頁面上的JavaScript配對：

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
