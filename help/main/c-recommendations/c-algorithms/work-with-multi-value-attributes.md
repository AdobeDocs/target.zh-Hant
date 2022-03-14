---
keywords: 多值；屬性；建議；多值；多值；多值
description: 瞭解如何在Adobe中使用多值欄位 [!DNL Target] Recommendations使用特殊的多價值運營商，例如在推薦多演員的電影時。
title: 我可以在Recommendations使用多值屬性嗎？
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 8%

---

# 使用多值屬性

有時，您可能希望使用多值欄位。  考量下列範例：

* 您提供影片給使用者。某部電影有多位演員。
* 你賣音樂會的票。給定用戶有多個喜愛的樂隊。
* 你賣衣服。襯衫有多種尺寸。

要處理這些方案中的建議，您可以將多值資料傳遞到 [!DNL Target Recommendations] 使用特殊的多值運算子。

允許 [!DNL Recommendations] 要標識多值資料，應將其作為JSON陣列發送，如下面的代碼示例中所示。

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

有關詳細資訊，請參見 [實現多值屬性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) 在 *自定義實體屬性*。

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

當實體屬性、配置檔案屬性或mbox參數按上述格式提供為多值時， [!DNL Recommendations] 自動推斷欄位是多值。

以下運算子可用於多值實體、配置檔案和mbox屬性：

* [!UICONTROL 清單中包含]
* [!UICONTROL 清單中未包含]

## 在包含規則中使用多值屬性

>[!NOTE]
>
>當將單值左側與多值右側進行比較時，僅在使用配置檔案屬性匹配或參數(mbox)屬性匹配規則時，標準中才提供對多值屬性的動態匹配的支援。 促銷、實體屬性匹配或包含規則左側的清單當前不支援多值屬性。

### 示例：排除最近監視的項目

假設您希望阻止推薦用戶最近10部已觀看影片中的任何影片。 首先，編寫一個名為 `user.lastWatchedMovies` 以JSON陣列形式跟蹤最近10個已查看的影片。 然後，可以使用以下包含規則排除項目：

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

### 示例：推薦用戶收藏夾中的項

假設您只希望在樂隊演奏是用戶最喜愛的樂隊之一時向音樂會推薦票證。 首先，確保您有一個名為 `profile.favoriteBands` 包含用戶最喜愛的頻段。 然後，確保目錄包含屬性 `entity.artistPerforming` 包括音樂會的藝術家。 然後，可以使用以下包含規則：

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

### 示例：API建立從用戶收藏夾推薦項的條件

使用多值篩選規則的條件（與所有條件一樣）可通過Adobe I/OAPI建立。 用於建立實體屬性的標準的示例API調用 `id` 包含在mbox參數清單中 `favorites` 此處提供：

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

這將與頁面上的JavaScript配對，以傳遞收藏夾內容：

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
