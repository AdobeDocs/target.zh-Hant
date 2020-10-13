---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: 有關在Adobe Target Recommendations中建立標準和促銷包含規則，以及新增其他動態或靜態篩選規則以取得更佳結果的資訊。
title: 在Adobe Target Recommendations中使用動態和靜態包含規則
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: 55860d360cf69415ad41807144a3cbe4657eedad
workflow-type: tm+mt
source-wordcount: '2100'
ht-degree: 35%

---


# ![PREMIUM](/help/assets/premium.png) 使用動態和靜態包含規則{#use-dynamic-and-static-inclusion-rules}

有關在Adobe Target中建立標準和促銷的包含規則，以及新增其他動態或靜態篩選規則以為您的建議取得更佳結果的資訊。

對於條件和促銷活動，建立和使用包含規則的過程很相似，就如同使用案例和範例很相似一樣。本主題涵蓋條件和促銷活動及如何使用包含規則。

## 將篩選規則新增至條件 {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[建立條件時](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)，請按一下&#x200B;**[!UICONTROL 「包含規則」]**&#x200B;下的&#x200B;**[!UICONTROL 「新增篩選規則」]**。

![](assets/inclusion_options_new.png)

可用的選項依選取的行業別和建議金鑰而不同。

## 將篩選規則新增至促銷活動 {#section_D59AFB62E2EE423086281CF5D18B1076}

[建立促銷活動](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)時，請選取&#x200B;**[!UICONTROL 「依屬性促銷」]**，然後按一下&#x200B;**[!UICONTROL 「新增篩選規則」]**。

![](assets/inclusion_options.png)

## 篩選類型 {#section_0125F1ED10A84C0EB45325122460EBCD}

下表列出條件和促銷活動的篩選選項類型:

### 動態篩選

動態包含規則比靜態包含規則更強大，而且可產生更佳的結果和參與度。 考慮以下事項:

* 動態包含規則會比對使用者描述檔參數或mbox呼叫中的屬性，以提供建議。

   例如，您可以建立「最受歡迎的准則建議」，然後針對傳回的建議集，針對使用者存取顯示建議之頁面時傳遞的屬性即時篩選任何建議。

* 使用靜態規則來限制建議中包含的項目（而非系列）。

* 您可以視需要建立任意數量的動態包含規則。 包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

動態篩選可使用下列選項：

#### 實體屬性比對

透過比較潛在建議項目群組與使用者已互動的特定項目，動態篩選。

例如，只建議符合目前項目品牌的項目，如下列範例所示：

如果「品牌著陸頁面」上的mbox傳 `entity.brand=Nike`回，則僅會傳回Nike產品並顯示在該頁面上。 同樣地，在阿迪達斯的品牌登陸頁面上，只會傳回阿迪達斯產品。 使用這種類型的動態包含規則時，使用者只需指定一個建議規則，即可在所有品牌頁面傳回相關品牌結果，而不需指定系列或靜態篩選以符合每個品牌名稱。

#### 設定檔屬性比對

透過比較項目（實體）與使用者描述檔中的值，動態篩選。

當您  想要顯示符合訪客描述檔中儲存之值（例如大小或我的最愛品牌）的建議時，請使用描述檔屬性符合。

下列範例說明如何使用描述檔 [!UICONTROL 屬性符合]:

* 一家銷售眼鏡的公司把遊客喜愛的畫格顏色儲存為「胡桃木」。 針對該特定訪客，建議設定為僅傳回符合彩色「胡桃」的眼鏡影格。
* 描述檔參數可定義為訪客瀏覽公司網站時的服裝尺寸（例如，「小」、「中」或「大」）。 建議可設定為符合該描述檔參數，並傳回僅針對使用者偏好服裝尺寸的特定產品。

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

如需描述檔屬性比對如何影響建議的視覺化範例，請考慮銷售粉絲的網站。

當訪客點按此網站上的粉絲影像時，每個頁面會根據影像中的粉絲大小 `entity.size` ，來設定參數值。

假設您已建立描述檔指令碼，以追蹤並計算其值設定為小 `entity.size` 或大的次數。

如果訪客接著返回首頁，他或她會根據是否點按了更多小粉絲或大粉絲，看到篩選的建議。

根據在網站上檢視更多小粉絲的建議：

![小粉絲建議](/help/c-recommendations/c-algorithms/assets/small-fans.png)

根據在網站上檢視更多大型粉絲的建議：

![大型粉絲建議](/help/c-recommendations/c-algorithms/assets/large-fans.png)

#### 參數比對

透過比較項目（實體）與請求中的值（API或mbox），動態篩選。

例如，只建議符合「產業」頁面參數或其他參數的內容，例如裝置尺寸或地理位置，如下列範例所示。

* 螢幕寬度和高度的Mbox參數可用來定位行動訪客，並僅建議行動裝置和附件。
* 區域地理位置參數可用來在冬季傳回工具建議。 在下雪的地區，遊客可以建議使用吹雪機和其他降雪工具，但在沒有下雪的地區，不建議使用。

>[!NOTE]
>
>如果活動是在2016年10月31日之前建立，則其傳送會失敗（如果其使用「參數符合」篩選）。 若想暫時解決此問題，請:
>
>* 建立新活動，並在其中新增條件。
>* 使用不包含「參數比對」篩選的條件。
>* 從條件中移除「參數比對」篩選。


可用運算子：

* 等於
* 不等於
* 包含
* 不包含
* 開始於
* 終止於
* 大於或等於
* 小於或等於
* 介於

### 按值篩選

動態篩選可使用下列選項：

#### 靜態濾鏡

手動輸入一或多個靜態值以進行篩選。

例如，僅建議 MPAA 評等為 &quot;G&quot; 或 &quot;PG&quot; 的內容。

可用運算子：

* 等於
* 不等於
* 包含
* 不包含
* 開始於
* 終止於
* 值存在
* 值不存在
* 大於或等於
* 小於或等於

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版 (2017 年 6 月) 之前包含規則的設定方式，您將注意到一些選項和運算子已變更。只會顯示適用於所選取選項的那些運算子，而一些運算子已重新命名 (「符合」現在是「等於」)，以便更為一致且直覺。在此版本之前建立的所有現有排除規則皆已自動移轉至新結構。您不需要重新處理結構。

您可以視需要建立許多包含規則。包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

## 動態准則和促銷範例

動態條件搭配促銷活動比靜態條件搭配促銷活動更強大，結果和參與度也更佳。

下列範例可讓您構想如何在市場行銷工作中使用動態促銷活動:

### 等於

在動態促銷中使用「等於」運算子，當訪客在您的網站上檢視項目（例如產品、文章或影片）時，您可從以下網站促銷其他項目：

* 相同品牌
* 相同種類
* 相同類別 AND 來自於自主品牌
* 相同商店

### 不等於

在動態促銷中使用「不等於」運算子，當訪客在您的網站上檢視項目（例如產品、文章或影片）時，您可以從以下位置促銷其他項目：

* 不同影集
* 不同內容類型
* 不同產品系列
* 不同樣式 ID

### 介於

在動態促銷中使用「介於」運算子，當訪客在您的網站上檢視項目（例如產品、文章或影片）時，您可以促銷其他項目：

* 較貴
* 較便宜
* 成本加或減 30%
* 同一季的最後幾集
* 同一套書的前幾本

## Handling empty values when filtering by Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching {#section_7D30E04116DB47BEA6FF840A3424A4C8}

You can choose several options to handle empty values when filtering by [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching] for exit criteria and promotions.

以前，如果值空白，則不會傳回結果。如果條件有空白值，則「如果 *x* 為空白」下拉式清單可讓您選擇適當的動作來執行，如下圖所示:

![](assets/empty_value.png)

若要選取所需的動作，請將游標停留在齒輪圖示上 (![](assets/icon_gear.png))，然後選擇所需的動作:

| Action | 可用於 | 詳細資料 |
|--- |--- |--- |
| 忽略此篩選規則 | 設定檔屬性比對<br>參數比對 | 這是設定檔屬性比對和參數比對的預設動作。<br>此選項會指定忽略規則。例如，假設有三個篩選規則，而第三個規則未傳遞任何值，為了避免不傳回任何結果，您可以直接用空白值忽略第三個規則。 |
| 不促銷任何項目 | 實體屬性匹<br>配配置檔案屬<br>性匹配參數匹配 | 這是實體屬性比對的預設動作。<br>[!DNL Target]在新增此選項的值之前，此動作代表 處理空白值的方式，也就是不顯示此條件的任何結果。 |
| 使用靜態值 | 實體屬性比對<br>設定檔屬性比對<br>參數比對 | 如果值為空白，您可以選擇使用靜態值。 |

## 描述檔屬性比對範例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 「描述檔屬性符合] 」可讓您僅建議符合訪客描述檔中屬性的項目，如下列範例所示。

### 範例1:從使用者最愛的品牌推薦項目

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. 透過此規則，如果訪客在查看特定品牌的慢跑短褲，則只有符合使用者最喜愛品牌 (訪客設定檔中 `profile.favoritebrand` 內儲存的值) 的建議才會出現。

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 範例2:將工作與求職者相匹配

假設你試圖把工作與求職者匹配。 您只想推薦與求職者位於同一城市的工作。

您可以使用包含規則，將求職者的位置從訪客的個人檔案比對至工作清單，如下列範例所示：

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

## 實體屬性匹配示例

[!UICONTROL 「實體屬性符合] 」可讓您只建議符合使用者目前檢視之項目中屬性的項目、使用者最近檢視的項目、使用者最近購買的項目、使用者最常檢視的項目，或訪客描述檔中自訂屬性中儲存的項目，如下列範例所示。

### 範例3:升級銷售更昂貴的產品

假設您是服裝零售商，並想鼓勵使用者考慮更高的價格，因此獲利更多的商品。 您可以使用「等於」和「介於」運算子來促銷來自相同類別和相同品牌的更昂貴項目。 例如，鞋類零售商可以推廣更貴的跑鞋，以向上銷售看跑鞋的訪客。

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### 範例4:推廣私有標籤產品

您可以混合動態和靜態篩選來促銷私用標籤產品。 例如，辦公室供應公司可以推廣公司房屋品牌的碳粉盒，以促使查看碳粉的訪客進行更有利可圖的銷售，並推廣公司房屋品牌的鋼筆，以促使查看碳粉的訪客進行更有利可圖的銷售。

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

## 注意事項 {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>使用「等於」和「不等於」運算子時，在執行階段，動態條件或促銷活動中的不同資料類型可能不相容。You should use [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory], and [!UICONTROL Environment] values wisely on the right hand side if the left hand side has predefined attributes or custom attributes.

![](assets/left_right.png)

下表顯示有效規則，以及在執行階段可能不相容的規則:

| 相容規則 | 可能不相容的規則 |
|--- |--- |
| value - 介於 - 目前項目的 90% 和 110% - salesValue | salesValue - 介於 - 目前項目的 90% 和 110% - value |
| value - 介於 - 目前項目的 90% 和 110% - value | clearancePrice - 介於 - 目前項目的 90% 和 110% - margin |
| margin - 介於 - 目前項目的 90% 和 110% - margin | storeInventory - 等於 - 目前項目的 - inventory |
| inventory - 等於 - 目前項目的 - inventory |  |
