---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: 透過比較項目（實體）與使用者設定檔中的值，在Adobe Target Recommendations中動態篩選。
title: 在Adobe Target Recommendations中動態包含規則中依描述檔屬性比對篩選
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 5%

---


# ![PREMIUM](/help/assets/premium.png) Profile屬性匹配

透過比較 [!DNL Adobe Target] 項目(實 [!DNL Recommendations] 體)與使用者設定檔中的值，動態篩選。

當您  想要顯示符合訪客描述檔中儲存之值（例如大小或我的最愛品牌）的建議時，請使用描述檔屬性符合。

下列案例說明如何使用描述檔 [!UICONTROL 屬性符合]:

* 一家銷售眼鏡的公司把遊客喜愛的畫格顏色儲存為「胡桃木」。 針對該特定訪客，建議設定為僅傳回符合彩色「胡桃」的眼鏡影格。
* 描述檔參數可定義為訪客瀏覽公司網站時的服裝尺寸（例如，「小」、「中」或「大」）。 建議可設定為符合該描述檔參數，並傳回僅針對使用者偏好服裝尺寸的特定產品。

## 描述檔屬性比對範例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 「描述檔屬性符合] 」可讓您僅建議符合訪客描述檔中屬性的項目，如下列範例所示。

### 從使用者最愛的品牌推薦項目

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. 透過此規則，如果訪客在查看特定品牌的慢跑短褲，則只有符合使用者最喜愛品牌 (訪客設定檔中 `profile.favoritebrand` 內儲存的值) 的建議才會出現。

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 將工作與求職者相匹配

假設你試圖把工作與求職者匹配。 您只想推薦與求職者位於同一城市的工作。

您可以使用包含規則，將求職者的位置從訪客的個人檔案比對至工作清單，如下列範例所示：

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 推薦符合訪客大小的衣服

讓我們來看一個範例，建議符合訪客描述檔中設定之服裝大小的服裝。

產品頁面在 `entity.size` mbox呼叫中傳送（下圖中的紅色箭頭）。

您可以建立描 [述檔指令碼](/help/c-target/c-visitor-profile/profile-parameters.md) ，從訪客瀏覽的最後一頁擷取訪客的描述檔屬性和值。

例如，

```
if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'small')) { return 'small';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'medium')) { return 'medium';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'large')) { return 'large';
}
```

描述檔指令碼會從名 `entity.size` 為mbox擷取值， `target-global-mbox` 並將它傳回為名為描述檔屬 `user.size` 性（下圖中的藍色箭頭）。

![大小mbox呼叫](/help/c-recommendations/c-algorithms/assets/size.png)

建立建議准則時，按一下「新 [!UICONTROL 增篩選規則]」，然後選 [!UICONTROL 取「描述檔屬性符合」]。

![描述檔屬性比對圖例](/help/c-recommendations/c-algorithms/assets/profile-attribute-matching.png)

如果您 `user.size` 的描述檔已載入 [!DNL Target]，當您設定規則以符合mbox呼叫(`size`)中傳入的值至描述檔指令碼名稱(`user.size`)時，該描述檔會顯示在下拉式清單中以進行比對。

然後，您可以選取「size」「equals」（等於）儲存在「user.size」中的值／文字，以便設定檔屬性符合。

建立描述檔屬性規則後，這些規則會篩選出所有具有不符合訪客儲存的描述檔屬性的建議。

### 根據大小推薦項目

如需描述檔屬性比對如何影響建議的視覺化範例，請考慮銷售粉絲的網站。

當訪客點按此網站上的粉絲影像時，每個頁面會根據影像中的粉絲大小 `entity.size` ，來設定參數值。

假設您已建立描述檔指令碼，以追蹤並計算其值設定為小 `entity.size` 或大的次數。

如果訪客接著返回首頁，他或她會根據是否點按了更多小粉絲或大粉絲，看到篩選的建議。

根據在網站上檢視更多小粉絲的建議：

![小粉絲建議](/help/c-recommendations/c-algorithms/assets/small-fans.png)

根據在網站上檢視更多大型粉絲的建議：

![大型粉絲建議](/help/c-recommendations/c-algorithms/assets/large-fans.png)