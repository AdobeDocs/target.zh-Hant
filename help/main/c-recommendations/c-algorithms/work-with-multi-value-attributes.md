---
keywords: 多值；屬性；建議；多值；多值
description: 瞭解如何使用特殊的多值運運算元在 [!DNL Target Recommendations] 中處理多值欄位。
title: 我可以在Recommendations中使用多值屬性嗎？
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 9%

---

# 使用多值屬性

有時您可能會想要使用多值欄位。  考量下列範例：

* 您提供影片給使用者。某部電影有多位演員。
* 你賣音樂會的票。給定用戶有多個喜愛的樂隊。
* 你賣衣服。襯衫有多種尺寸。

若要處理這些案例中的建議，您可以將多值資料傳遞至[!DNL Target Recommendations]並使用特殊的多值運運算元。

若要允許[!DNL Recommendations]識別多值資料，應以JSON陣列傳送，如下列程式碼範例所示。

## 在JavaScript中傳遞多值引數

```
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

如需詳細資訊，請參閱&#x200B;*自訂實體屬性*&#x200B;中的[實作多值屬性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14)。

## 在CSV檔案中傳遞多值實體屬性

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

當根據上述格式以多值形式提供實體屬性、設定檔屬性或mbox引數時，[!DNL Recommendations]會自動推斷欄位是多值。

下列運運算元可搭配多值實體、設定檔和mbox屬性使用：

* [!UICONTROL is contained in list]
* [!UICONTROL is not contained in list]

## 在包含規則中使用多值屬性

>[!NOTE]
>
>目前，只有在比較左側的單一值和多值右側時，使用設定檔屬性比對或引數(mbox)屬性比對規則時，才有條件支援動態比對多值屬性。 促銷活動、實體屬性比對或包含規則左側的清單目前不支援多值屬性。

### 範例：排除最近觀看的專案

假設您想要防止推薦使用者最近看過十部影片中的任何影片。 首先，編寫名為`user.lastWatchedMovies`的設定檔指令碼，以JSON陣列形式追蹤最後十部檢視的電影。 然後，您可以使用以下包含規則排除專案：

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
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

假設您只想要向演唱會推薦門票，如果播放的樂隊是使用者最喜愛的樂隊之一。 首先，請確定您有一個名為`profile.favoriteBands`的設定檔變數，其中包含使用者最喜愛的樂隊。 然後，請確定您的目錄包含屬性`entity.artistPerforming`，該屬性包含演唱會中的演出者。 然後，您可以使用以下包含規則：

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
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

使用多值篩選規則的條件（例如所有條件）可透過[!DNL Adobe Target] API建立。 以下提供建立條件的範例API呼叫，其中實體屬性`id`包含在mbox引數清單`favorites`中：

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

這會與頁面上的JavaScript配對以傳入「我的最愛」內容：

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
