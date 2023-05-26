---
keywords: 包含規則;包含條件;建議;建立新條件;促銷活動;動態篩選;動態;空白值;忽略篩選規則;靜態篩選;按值篩選;實體屬性比對;設定檔屬性比對;參數比對;靜態篩選
description: 瞭解如何在Adobe中建立包含規則 [!DNL Target] Recommendations以取得條件和促銷活動。 若要取得更好的結果，請新增更多動態或靜態篩選規則。
title: 如何在Recommendations中使用動態和靜態包含規則？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '2093'
ht-degree: 16%

---

# 使用動態和靜態包含規則

有關在中建立條件和促銷活動的包含規則的資訊 [!DNL Adobe Target] 和新增動態或靜態篩選規則，以便為您的建議取得更好的結果。

對於條件和促銷活動，建立和使用包含規則的過程很相似，就如同使用案例和範例很相似一樣。本節將說明條件和促銷活動以及包含規則的使用。

## 將篩選規則新增至條件 {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[建立條件時](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)，請按一下&#x200B;**[!UICONTROL 「包含規則」]**&#x200B;下的&#x200B;**[!UICONTROL 「新增篩選規則」]**。

![inclusion_options_new圖片](assets/inclusion_options_new.png)

可用的選項依選取的行業別和建議金鑰而不同。

## 將篩選規則新增至促銷活動 {#section_D59AFB62E2EE423086281CF5D18B1076}

[建立促銷活動](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)時，請選取&#x200B;**[!UICONTROL 「依屬性促銷」]**，然後按一下&#x200B;**[!UICONTROL 「新增篩選規則」]**。

![inclusion_options圖片](assets/inclusion_options.png)

## 篩選類型 {#section_0125F1ED10A84C0EB45325122460EBCD}

以下小節列出篩選選項的型別 [!UICONTROL 動態篩選] 和 [!UICONTROL 按值篩選] 對於條件和促銷：

### 動態篩選

動態包含規則比靜態包含規則功能更強大，且產生更好的結果和參與。 考慮以下事項：

* 動態包含規則會透過比對使用者設定檔引數或mbox呼叫中的屬性來傳送建議。

   例如，您可以建立「最受歡迎的條件」建議。 從傳回的建議集中，您可以針對使用者存取顯示建議的頁面時傳遞的屬性來（即時）篩選掉任何建議。

* 使用靜態規則來限制建議中包含的專案（而不是使用集合）。

* 您可以視需要建立儘可能多的動態包含規則。 包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

下列選項適用於動態篩選：

| 動態篩選選項 | 詳細資料 |
| --- | --- |
| [實體屬性比對](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | 比較一批潛在的建議專案與使用者已互動的特定專案，以動態篩選。<br>使用 [!UICONTROL 實體屬性比對] 當您想要顯示最有可能吸引訪客的建議時，例如訪客最喜愛的品牌。 |
| [設定檔屬性比對](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | 比較專案（實體）與使用者設定檔中的值，以動態篩選。<br>使用 [!UICONTROL 設定檔屬性比對] 當您想要顯示符合訪客設定檔中儲存之值（例如大小或最喜愛的品牌）的建議。 |
| [參數比對](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | 比較專案（實體）與請求（API或mbox）中的值，以動態篩選。<br>使用 [!UICONTROL 引數比對] 以建議符合頁面引數或訪客引數（例如裝置維度或地理位置）的內容。 |

### 按值篩選

下列選項可依值篩選：

| 依值選項篩選 | 詳細資料 |
| --- | --- |
| [靜態篩選器](/help/main/c-recommendations/c-algorithms/static-value.md) | 手動輸入一或多個要篩選的靜態值。 |

## 可用的運運算元 {#operators}

動態條件和促銷活動比靜態條件和促銷活動強大得多，並可產生更好的結果和參與。

下列範例提供如何在行銷工作中使用動態促銷和排除專案的一般概念：

| 運算子 | 範例 |
| --- | --- |
| 等於<br>（適用於實體屬性比對、設定檔屬性比對、引數比對和靜態篩選。） | 如果在動態促銷活動中使用「等於」運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以促銷下列來源的其他專案：<ul><li>相同品牌</li><li>相同類別</li><li>來自自家品牌的相同類別和</li><li>相同商店</li></ul> |
| 不等於<br>（適用於實體屬性比對、設定檔屬性比對、引數比對和靜態篩選。） | 如果在動態促銷活動中使用「不等於」運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以促銷下列來源的其他專案：<ul><li>另一部電視劇</li><li>不同的型別</li><li>不同的產品系列</li><li>不同的樣式ID</li></ul> |
| 不包含子字串<br>（適用於實體屬性比對、設定檔屬性比對、引數比對和靜態篩選。） | 使用「不包含子字串」運運算元時，當訪客檢視您網站上的專案時（例如產品），您可以促銷符合以下條件的其他專案：<ul><li>標題不包含髒字</li></ul> |
| 開頭為<br>（適用於實體屬性比對、設定檔屬性比對、引數比對和靜態篩選。） | 使用「開頭為」運運算元時，當訪客檢視您網站上的專案時（例如產品），您可以促銷符合以下條件的其他專案：<ul><li>產品名稱以iPhone開頭</li></ul> |
| 結尾為<br>（適用於實體屬性比對、設定檔屬性比對、引數比對和靜態篩選。） | 使用「結尾為」運運算元時，當訪客檢視您網站上的專案時（例如產品），您可以促銷符合以下條件的其他專案：<ul><li>內容結尾是EN，表示英文</li></ul> |
| 大於或等於<br>（適用於實體屬性比對、設定檔屬性比對、引數比對和靜態篩選。） | 使用「大於或等於」運運算元時，當訪客檢視您網站上的專案時（例如產品），您可以促銷符合以下條件的其他專案：<ul><li>成本相同或更高</li></ul> |
| 小於或等於<br>（適用於實體屬性比對、設定檔屬性比對、引數比對和靜態篩選。） | 使用「小於或等於」運運算元時，當訪客檢視您網站上的專案時（例如產品），您可以促銷符合以下條件的其他專案：<ul><li>成本相同或較便宜</li><li>排除較便宜的專案</li></ul> |
| 介於<br>（適用於實體屬性比對、設定檔屬性比對和引數比對。） | 如果在動態促銷活動中使用「介於」運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以促銷如下的其他專案：<ul><li>更貴</li><li>更便宜</li><li>成本加減30%</li><li>同一季的稍後集數</li><li>系列中先前的書籍</li></ul> |
| 包含在清單中<br>（適用於設定檔屬性比對和引數比對。） | 在設定檔屬性比對中使用「包含在清單中」運運算元時，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以促銷如下的其他專案：<ul><li>可在訪客的地理位置中使用</li></ul>**範例**：您只要建議訪客所在地理區域內可用的專案。<br>您的篩選規則可能如下所示：<br>`availableGeographies list contains an item in user.currentGeography`<br>**注意**：使用此運運算元時，清單應位於 [右側](#caveats) 規則的。 |
| 不包含在清單中<br>（適用於設定檔屬性比對和引數比對。） | 若在設定檔屬性比對中使用「不在清單中」運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以排除其他專案，包括：<ul><li>在訪客已檢視的最後10個專案清單中</li></ul></ul>**範例**：您不想促銷訪客最近檢視過且沒有興趣的專案。<br>您的篩選規則可能如下所示：<br>`id is not contained in list user.lastViewedItems`<br>**注意**：使用此運運算元時，清單應位於 [右側](#caveats) 規則的。 |
| 清單中包含一個專案<br>（適用於實體屬性比對、設定檔屬性比對和引數比對。） | 在設定檔屬性比對中使用「清單中包含專案」運運算元，當訪客檢視您網站上的專案時（例如體育賽事或音樂會），您可以促銷如下的其他專案：<ul><li>與訪客其中一個最喜愛的團隊相關聯</li></ul>**範例**：您想要建議與訪客最喜愛的團隊之一相關聯的遊戲。<br>您的篩選規則可能如下所示：<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**注意**：使用此運運算元時，清單應位於 [雙面](#caveats) 規則的。 |
| 清單中不包含某個專案<br>（適用於實體屬性比對、設定檔屬性比對和引數比對。） | 在引數屬性比對中使用「list does not contain an item in」運運算元時，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以排除下列其他專案：<ul><li>包含在禁止型別清單中</li></ul>**範例**：您想要排除成人訪客可用的專案，例如菸草和酒精。<br>您的篩選規則可能如下所示：<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**注意**：使用此運運算元時，清單應位於 [雙面](#caveats) 規則的。 |
| 清單包含所有專案<br>（適用於實體屬性比對、設定檔屬性比對和引數比對。） | 在設定檔屬性比對中使用「清單包含所有專案」運運算元，當訪客檢視您網站上的專案時（例如工作發佈或配方），您可以促銷具有以下特性的其他專案：<ul><li>包含一組技能</li><li>包含一組必要要素</li></ul>**範例1**：假設訪客有一組技能(Java、C++和HTML)。 目錄中的專案是具有所需技能(Java和HTML)的工作。 在向訪客建議工作之前，您希望確保訪客的設定檔包含所有必要的技能。<br>您的篩選規則可能如下所示：<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**範例2**：假設使用者有一份食品櫃成分的清單。 配方包含所需成分的清單。 在向訪客建議配方之前，您希望確保訪客的設定檔包含所有必要的組成部分。<br>您的篩選規則可能如下所示：<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**注意**：使用此運運算元時，清單應位於 [雙面](#caveats) 規則的。 |
| 清單中不包含所有專案<br>（適用於實體屬性比對、設定檔屬性比對和引數比對。） | 在實體屬性比對中使用「清單不包含中的所有專案」運運算元，當訪客檢視您網站上的專案時（例如體育賽事或音樂會），您可以促銷其他符合以下條件的專案：<ul><li>不要包含一組團隊</li></ul>**範例**：假設一個體育賽事包含兩支球隊。 訪客的設定檔指出該訪客不想檢視這些團隊的遊戲。 您希望確保在這些團隊在比賽時不建議遊戲。<br>您的篩選規則可能如下所示：<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**注意**：使用此運運算元時，清單應位於 [雙面](#caveats) 規則的。 |

## 依實體屬性比對、設定檔屬性比對和引數比對來篩選時，處理空白值 {#section_7D30E04116DB47BEA6FF840A3424A4C8}

您可以選擇多個選項，在篩選時處理空白值，方法是 [!UICONTROL 實體屬性比對]， [!UICONTROL 設定檔屬性比對]、和 [!UICONTROL 引數比對] 退出條件和促銷活動的相關資訊。

以前，如果值空白，則不會傳回結果。如果條件有空白值，則「如果 *x* 為空白」下拉式清單可讓您選擇適當的動作來執行，如下圖所示:

![empty_value圖片](assets/empty_value.png)

若要選取所需的動作，請將滑鼠指標暫留在齒輪圖示上(![icon_gear影像](assets/icon_gear.png))，然後選擇所需的動作：

| Action | 可用於 | 詳細資料 |
|--- |--- |--- |
| [!UICONTROL 忽略此篩選規則] | [!UICONTROL 設定檔屬性比對] 和 [!UICONTROL 引數比對] | 此動作為的預設值 [!UICONTROL 設定檔屬性比對] 和 [!UICONTROL 引數比對].<br>此選項會指定忽略規則。例如，假設有三個篩選規則，而第三個規則未傳遞任何值，為了避免不傳回任何結果，您可以直接用空白值忽略第三個規則。 |
| [!UICONTROL 不顯示此條件的任何結果]<br>（僅限條件） | [!UICONTROL 實體屬性比對]， [!UICONTROL 設定檔屬性比對]、和 [!UICONTROL 引數比對] | 此動作為的預設值 [!UICONTROL 實體屬性比對].<br>此動作是如何 [!DNL Target] 在新增此選項之前處理空白值：不顯示此條件的結果。 |
| [!UICONTROL 不促銷任何專案<br>（僅限促銷活動）] | [!UICONTROL 實體屬性比對]， [!UICONTROL 設定檔屬性比對]、和 [!UICONTROL 引數比對] | 此動作為的預設值 [!UICONTROL 實體屬性比對].<br>此動作是如何 [!DNL Target] 在新增此選項之前處理空白值：不顯示此條件的結果。 |
| [!UICONTROL 使用靜態值] | [!UICONTROL 實體屬性比對]， [!UICONTROL 設定檔屬性比對]、和 [!UICONTROL 引數比對] | 如果值為空白，您可以選擇使用靜態值。 |

## 注意事項 {#caveats}

>[!IMPORTANT]
>
>使用「等於」和「不等於」運算子時，在執行階段，動態條件或促銷活動中的不同資料類型可能不相容。使用 [!UICONTROL 值]， [!UICONTROL 利潤]， [!UICONTROL 詳細目錄]、和 [!UICONTROL 環境] 如果左側有預先定義的屬性或自訂屬性，則右側值會很明智。

![left_right影像](assets/left_right.png)

下表顯示有效規則，以及在執行階段可能不相容的規則:

| 相容規則 | 可能不相容的規則 |
|--- |--- |
| value - 介於 - 目前項目的 90% 和 110% - salesValue | salesValue - 介於 - 目前項目的 90% 和 110% - value |
| value - 介於 - 目前項目的 90% 和 110% - value | clearancePrice - 介於 - 目前項目的 90% 和 110% - margin |
| margin - 介於 - 目前項目的 90% 和 110% - margin | storeInventory - 等於 - 目前項目的 - inventory |
| inventory - 等於 - 目前項目的 - inventory |  |
