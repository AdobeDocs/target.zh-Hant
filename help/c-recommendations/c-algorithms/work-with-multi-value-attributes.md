---
keywords: multi-value;attributes;recommendations;multi value;multivalue;multi-value
description: 有關使用特殊多值運算子在Adobe Target Recommendations中處理多值欄位的資訊。
title: 在Adobe Target Recommendations中使用多值屬性
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---


# 使用多值屬性

有時您可能想要使用多值欄位。 考量下列範例:

* 您提供影片給使用者。 某部電影有多位演員。
* 你賣音樂會的票。 給定用戶有多個喜愛的樂隊。
* 你賣衣服。 T恤衫有多種尺寸。

若要處理這些案例中的建議，您可將多值資料傳遞至[!DNL Target Recommendations]，並使用特殊的多值運算子。

若要允許[!DNL Recommendations]識別多值資料，應以JSON陣列傳送，如下列程式碼範例所示。

## 在JavaScript中傳遞多值參數

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

如需詳細資訊，請參閱&#x200B;*自訂實體屬性*&#x200B;中的[實作多值屬性](/help/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14)。

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

當根據上述格式將實體屬性、描述檔屬性或mbox參數提供為多值時，[!DNL Recommendations]會自動推斷欄位為多值。

以下運算子可用於多值實體、描述檔和mbox屬性：

* [!UICONTROL 包含在清單中]
* [!UICONTROL 未包含在清單中]

## 在包含規則中使用多值屬性

>[!NOTE]
>
>當將單一值左側與多值右側比較時，目前只有在使用描述檔屬性比對或參數(mbox)屬性比對規則時，標準才支援動態比對多值屬性。 促銷活動、實體屬性比對或包含規則左側的清單目前不支援多值屬性。

### 範例：排除最近監看的項目

假設您想要防止建議使用者最近10部已觀看影片中的任何影片。 首先，撰寫名為`user.lastWatchedMovies`的描述檔指令碼，以追蹤最後10個檢視的影片為JSON陣列。 然後，您可以使用下列包含規則來排除項目：

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

### 範例：建議使用者最愛的項目

假設您只想在演奏樂隊是使用者最愛的樂隊之一時，將票證推薦給音樂會。 首先，請確定您有名為`profile.favoriteBands`的描述檔變數，其中包含使用者最愛的節區。 然後，請確定您的目錄包含屬性`entity.artistPerforming`，其中包含演唱會中的藝術家。 然後，您可以使用下列包含規則：

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

### 範例：API建立從使用者最愛的項目推薦標準

使用多值篩選規則的准則（如所有准則）可透過Adobe I/O API建立。 此處提供範例API呼叫，以建立實體屬性`id`包含在mbox參數清單`favorites`中的准則：

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

這會與頁面上的JavaScript配對，以傳入我的最愛內容：

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
