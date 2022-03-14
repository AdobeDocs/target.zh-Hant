---
keywords: 包含規則;包含條件;建議;建立新條件;促銷活動;動態篩選;動態;空白值;忽略篩選規則;靜態篩選;按值篩選;實體屬性比對;設定檔屬性比對;參數比對;靜態篩選
description: 瞭解如何在Adobe中建立包含規則 [!DNL Target] Recommendations提供標準和促銷。 為獲得更好的效果，添加更多動態或靜態過濾規則。
title: 如何在Recommendations使用動態和靜態包含規則？
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2078'
ht-degree: 17%

---

# ![PREMIUM](/help/main/assets/premium.png) 使用動態和靜態包含規則

有關在中為標準和促銷建立包含規則的資訊 [!DNL Adobe Target] 並添加動態或靜態篩選規則，以獲得更好的建議結果。

對於條件和促銷活動，建立和使用包含規則的過程很相似，就如同使用案例和範例很相似一樣。本節包括標準和促銷以及包含規則的使用。

## 將篩選規則新增至條件 {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[建立條件時](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)，請按一下&#x200B;**[!UICONTROL 「包含規則」]**&#x200B;下的&#x200B;**[!UICONTROL 「新增篩選規則」]**。

![](assets/inclusion_options_new.png)

可用的選項依選取的行業別和建議金鑰而不同。

## 將篩選規則新增至促銷活動 {#section_D59AFB62E2EE423086281CF5D18B1076}

[建立促銷活動](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)時，請選取&#x200B;**[!UICONTROL 「依屬性促銷」]**，然後按一下&#x200B;**[!UICONTROL 「新增篩選規則」]**。

![](assets/inclusion_options.png)

## 篩選類型 {#section_0125F1ED10A84C0EB45325122460EBCD}

以下各節列出的篩選選項類型 [!UICONTROL 動態篩選] 和 [!UICONTROL 按值篩選] 對於標準和促銷：

### 動態篩選

動態包含規則比靜態包含規則更強大，並且能產生更好的結果和參與。 考慮以下事項:

* 動態包含規則通過匹配用戶配置檔案參數或框調用中的屬性來傳遞建議。

   例如，您可以建立「最常用標準」建議。 從返回的建議集中，您可以根據用戶訪問顯示建議的頁面時傳遞的屬性過濾出任何建議（即時）。

* 使用靜態規則限制建議書中包含的項（而不是使用集合）。

* 您可以根據需要建立盡可能多的動態包含規則。 包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

以下選項可用於動態篩選：

| 動態篩選選項 | 詳細資料 |
| --- | --- |
| [實體屬性比對](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | 通過將潛在建議項池與用戶已交互的特定項進行比較來動態篩選。<br>使用 [!UICONTROL 實體屬性匹配] 當您希望顯示最有可能吸引訪客的推薦時，例如訪客最喜愛的品牌。 |
| [設定檔屬性比對](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | 通過將項目（實體）與用戶配置檔案中的值進行比較來動態篩選。<br>使用 [!UICONTROL 配置檔案屬性匹配] 當要顯示與訪問者配置檔案中儲存的值匹配的建議時，例如大小或收藏夾品牌。 |
| [參數比對](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | 通過將項（實體）與請求（API或mbox）中的值進行比較來動態篩選。<br>使用 [!UICONTROL 參數匹配] 建議與頁面參數或訪問者參數匹配的內容，如設備尺寸或地理位置。 |

### 按值篩選

以下選項可用於按值篩選：

| 按值篩選選項 | 詳細資料 |
| --- | --- |
| [靜態篩選器](/help/main/c-recommendations/c-algorithms/static-value.md) | 手動輸入一個或多個要篩選的靜態值。 |

## 可用運算子 {#operators}

動態標準和促銷比靜態標準和促銷功能強大得多，並能產生更好的結果和參與。

以下示例提供了關於如何在營銷工作中使用動態促銷和排除的一般說明：

| 運算元 | 範例 |
| --- | --- |
| 等於<br>（可用於實體屬性匹配、配置檔案屬性匹配、參數匹配和靜態篩選器。） | 在動態促銷中使用「等於」運算子，當訪問者在您的網站上查看某個項目（如產品、文章或電影）時，您可以從以下站點升級其他項目：<ul><li>同一品牌</li><li>同一類別</li><li>同一類別AND來自品牌</li><li>同一家商店</li></ul> |
| 不等於<br>（可用於實體屬性匹配、配置檔案屬性匹配、參數匹配和靜態篩選器。） | 在動態促銷中使用「不等於」運算子，當訪問者在您的網站上查看某個項目（如產品、文章或電影）時，您可以從以下位置促銷其他項目：<ul><li>另一部電視劇</li><li>另一種類型</li><li>不同的產品系列</li><li>不同樣式ID</li></ul> |
| 不包含子字串<br>（可用於實體屬性匹配、配置檔案屬性匹配、參數匹配和靜態篩選器。） | 使用「不包含子字串」運算子，當訪問者在您的網站（如產品）上查看項目時，您可以升級其他項目：<ul><li>標題不包含粗體字</li></ul> |
| 開頭為<br>（可用於實體屬性匹配、配置檔案屬性匹配、參數匹配和靜態篩選器。） | 使用「開頭為」運算子，當訪問者在您的網站（如產品）上查看項目時，您可以升級其他項目：<ul><li>產品名稱以iPhone開頭</li></ul> |
| 結尾為<br>（可用於實體屬性匹配、配置檔案屬性匹配、參數匹配和靜態篩選器。） | 使用「結尾為」運算子，當訪問者在您的網站（如產品）上查看項目時，您可以升級其他項目：<ul><li>內容以EN結尾，表示英語</li></ul> |
| 大於或等於<br>（可用於實體屬性匹配、配置檔案屬性匹配、參數匹配和靜態篩選器。） | 使用「大於或等於」運算子，當訪問者在您的網站上查看項目（如產品）時，您可以升級其他項目：<ul><li>成本相同或更貴</li></ul> |
| 小於或等於<br>（可用於實體屬性匹配、配置檔案屬性匹配、參數匹配和靜態篩選器。） | 使用「小於或等於」運算子，當訪問者在您的網站（如產品）上查看項目時，您可以升級其他項目：<ul><li>成本相同或成本更低</li><li>排除較便宜的項目</li></ul> |
| 介於<br>（可用於實體屬性匹配、配置檔案屬性匹配和參數匹配。） | 在動態促銷中使用「介於」運算子，當訪問者在您的網站上查看某個項目（如產品、文章或電影）時，您可以促銷以下項目：<ul><li>更貴</li><li>更便宜</li><li>成本加負三成</li><li>同一季的後續劇集</li><li>系列中的前期書籍</li></ul> |
| 包含在清單中<br>（可用於配置檔案屬性匹配和參數匹配。） | 在配置檔案屬性匹配中使用「is contained in list」運算子，當訪問者在您的網站上查看項目（如產品、文章或電影）時，您可以升級其他項目，這些項目包括：<ul><li>可在訪問者的地理位置獲得</li></ul>**示例**:您只想推薦訪問者地理區域中可用的項目。<br>篩選器規則可能如下所示：<br>`availableGeographies list contains an item in user.currentGeography`<br>**注釋**:使用此運算子時，在 [右側](#caveats) 規則。 |
| 未包含在清單中<br>（可用於配置檔案屬性匹配和參數匹配。） | 在配置檔案屬性匹配中使用「is not incontained in list」運算子，當訪問者在您的網站上查看項目（如產品、文章或電影）時，您可以排除其他項目：<ul><li>在訪問者查看的最後十項清單中</li></ul></ul>**示例**:您不想升級訪問者最近查看的、並且對此不感興趣的項目。<br>篩選規則可能如下所示：<br>`id is not contained in list user.lastViewedItems`<br>**注釋**:使用此運算子時，在 [右側](#caveats) 規則。 |
| 清單包含中的項<br>（可用於實體屬性匹配、配置檔案屬性匹配和參數匹配。） | 在配置檔案屬性匹配中使用「清單包含項目在」運算子，當訪問者在您的網站上查看項目（如體育賽事或音樂會）時，您可以升級以下項目：<ul><li>與訪客最喜愛的團隊之一關聯</li></ul>**示例**:您希望推薦與訪問者最喜愛的團隊之一關聯的遊戲。<br>篩選規則可能如下所示：<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**注釋**:使用此運算子時，在 [雙方](#caveats) 規則。 |
| 清單中不包含項<br>（可用於實體屬性匹配、配置檔案屬性匹配和參數匹配。） | 在參數屬性匹配中使用「list不包含項目」運算子，當訪問者在您的網站上查看項目（如產品、文章或電影）時，您可以排除其他項目：<ul><li>包含在禁止類型清單中</li></ul>**示例**:您希望排除成人遊客可使用的物品，如煙草和酒精。<br>篩選規則可能如下所示：<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**注釋**:使用此運算子時，在 [雙方](#caveats) 規則。 |
| 清單包含中的所有項<br>（可用於實體屬性匹配、配置檔案屬性匹配和參數匹配。） | 在配置檔案屬性匹配中使用「清單包含所有物料」運算子，當訪問者在您的網站上查看物料（如職務過帳或處方）時，您可以升級其它物料：<ul><li>包括一組技能</li><li>包括一組必需的配料</li></ul>**示例1**:假設訪問者具有一組技能(Java、C++和HTML)。 目錄中的項目是具有所需技能(Java和HTML)的作業。 在向訪問者推薦該工作之前，您需要確保訪問者的個人資料包含所有必需的技能。<br>篩選規則可能如下所示：<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**示例2**:假設用戶有一個食品配料清單。 該處方有一份所需配料的清單。 在向訪問者推薦食譜之前，您需要確保訪問者的個人資料包含所有必需的配料。<br>篩選規則可能如下所示：<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**注釋**:使用此運算子時，在 [雙方](#caveats) 規則。 |
| 清單中不包含所有項<br>（可用於實體屬性匹配、配置檔案屬性匹配和參數匹配。） | 在實體屬性匹配中使用「list does not cand all items in」運算子，當訪問者在您的網站上查看項目（如體育賽事或音樂會）時，您可以升級以下其他項目：<ul><li>不包括一組團隊</li></ul>**示例**:假設一個體育賽事包括兩個隊。 訪問者的個人資料表明此訪問者不想查看這些團隊的遊戲。 如果這些團隊在進行遊戲，您需要確保不推薦遊戲。<br>篩選規則可能如下所示：<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**注釋**:使用此運算子時，在 [雙方](#caveats) 規則。 |

## 按實體屬性匹配、配置檔案屬性匹配和參數匹配篩選時處理空值 {#section_7D30E04116DB47BEA6FF840A3424A4C8}

可以選擇幾個選項來處理篩選時的空值 [!UICONTROL 實體屬性匹配]。 [!UICONTROL 配置檔案屬性匹配], [!UICONTROL 參數匹配] 退出條件和促銷。

以前，如果值空白，則不會傳回結果。如果條件有空白值，則「如果 *x* 為空白」下拉式清單可讓您選擇適當的動作來執行，如下圖所示:

![](assets/empty_value.png)

若要選取所需的動作，請將游標停留在齒輪圖示上 (![](assets/icon_gear.png))，然後選擇所需的動作:

| Action | 可用於 | 詳細資料 |
|--- |--- |--- |
| [!UICONTROL 忽略此篩選規則] | [!UICONTROL 配置檔案屬性匹配] 和 [!UICONTROL 參數匹配] | 此操作是 [!UICONTROL 配置檔案屬性匹配] 和 [!UICONTROL 參數匹配]。<br>此選項會指定忽略規則。例如，假設有三個篩選規則，而第三個規則未傳遞任何值，為了避免不傳回任何結果，您可以直接用空白值忽略第三個規則。 |
| [!UICONTROL 不顯示此條件的任何結果]<br>（僅限條件） | [!UICONTROL 實體屬性匹配]。 [!UICONTROL 配置檔案屬性匹配], [!UICONTROL 參數匹配] | 此操作是 [!UICONTROL 實體屬性匹配]。<br>此操作是 [!DNL Target] 添加此選項前已處理空值：沒有顯示此條件的結果。 |
| [!UICONTROL 不提升任何項目<br>（僅限促銷）] | [!UICONTROL 實體屬性匹配]。 [!UICONTROL 配置檔案屬性匹配], [!UICONTROL 參數匹配] | 此操作是 [!UICONTROL 實體屬性匹配]。<br>此操作是 [!DNL Target] 添加此選項前已處理空值：沒有顯示此條件的結果。 |
| [!UICONTROL 使用靜態值] | [!UICONTROL 實體屬性匹配]。 [!UICONTROL 配置檔案屬性匹配], [!UICONTROL 參數匹配] | 如果值為空白，您可以選擇使用靜態值。 |

## 注意事項 {#caveats}

>[!IMPORTANT]
>
>使用「等於」和「不等於」運算子時，在執行階段，動態條件或促銷活動中的不同資料類型可能不相容。使用 [!UICONTROL 值]。 [!UICONTROL 邊距]。 [!UICONTROL 庫存], [!UICONTROL 環境] 如果左側具有預定義的屬性或自定義屬性，則右側的值將明智。

![](assets/left_right.png)

下表顯示有效規則，以及在執行階段可能不相容的規則:

| 相容規則 | 可能不相容的規則 |
|--- |--- |
| value - 介於 - 目前項目的 90% 和 110% - salesValue | salesValue - 介於 - 目前項目的 90% 和 110% - value |
| value - 介於 - 目前項目的 90% 和 110% - value | clearancePrice - 介於 - 目前項目的 90% 和 110% - margin |
| margin - 介於 - 目前項目的 90% 和 110% - margin | storeInventory - 等於 - 目前項目的 - inventory |
| inventory - 等於 - 目前項目的 - inventory |  |
