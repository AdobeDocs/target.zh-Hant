---
keywords: dynamic data;assets;data;offers;personalized offers;personal offers;token replace
description: 您可以直接在 HTML 或 JSON 選件上顯示設定檔值和活動資訊。
title: 將動態資料傳遞至選件
feature: offers
translation-type: tm+mt
source-git-commit: 431ccc937a3ad4aaf735b31b4790ead43a6fc4d9
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 94%

---


# 將動態資料傳遞至選件{#pass-dynamic-data-into-offers}

您可以動態地顯示儲存在 Target 設定檔中的訪客資訊。同樣地，活動資訊 (例如活動名稱或體驗名稱) 也能用來根據訪客興趣、過去行為和整體設定檔，建立動態地傳回個人化內容的單一選件。

**業務案例**

* 促銷折扣選件以「重新裝滿」或「補充」最後一個購買的產品。與其為您目錄中的每個項目建立個別選件，您可以建立含有動態文字的選件，從設定檔讀取「最後一個購買的產品」並在選件中顯示連結。
* 訪客使用 `keyword=world` `cup` 到達您的登陸頁面。您在選件中顯示字詞 *World cup*。
* 使用資訊個人化建議標籤，例如 (1) 最後一個新增至訪客購物車的項目 (Nike Air Max 1000s)、(2) 訪客的顏色偏好 (黑色) 和 (3) 訪客最喜愛的非鞋類別 (連帽上衣)。範例:「運用這些酷炫的黑色『連帽上衣』裝飾您的『Nike Air Max 1000s』!」


**技術優勢**

由於使用者的特定偏好、行為、狀態等項目可儲存在使用者的設定檔中，您可以在其後續造訪中重複此訊息。動態選件可讓您在活動中設定單一選件，為所有訪客顯示個人化訊息，以支援更大的規模。當訪客的意向有所變更，您的網站內容會自動反映這些變更。

**範例**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* HTML 選件代碼: `Get your ${profile.keyword} information here!`
* 使用者看見: 在這裡取得您的世界盃資訊!

下面的值可以是「取代的代號」:

| 值 | 範例 |
|--- |--- |
| In-mbox 描述檔參數 | `${profile.age}` |
| 指令碼描述檔參數 | `${user.lifetimeSpend}` |
| mbox 參數 | `${mbox.favoriteColor}` |
| 促銷活動資訊 | `${campaign.name}`, `${campaign.recipe.name}`, `${campaign.id}`, `${campaign.recipe.id}`, 和 `${campaign.recipe.trafficType}` |
| 唯一的訪客 ID | `${user.pcId}` |
| 唯一工作階段 ID | `${user.sessionId}` |
| 訪客的第一個作業 (true 或 false) | `${user.isFirstSession}` |
| 過去行為 | `${user.endpoint.lastPurchasedEntity}`, `${user.endpoint.lastViewedEntity}`, `${user.endpoint.mostViewedEntity}`, `${user.endpoint.categoryAffinity}` |

在主控台中記錄用於偵錯用途的資訊，例如 `${campaign.name}`, `${campaign.id}`, `${campaign.recipe.name}`, `${campaign.recipe.id}`, `${offer.name}`, `${offer.id}`, `${campaign.name}`

有關 Recommendations 設計，請參閱[設計概覽](/help/c-recommendations/c-design-overview/design-overview.md)中的其他範例。

**實施**

若為傳入 mbox 的設定檔參數，請使用語法: `${profile.parameter}` 若為以設定檔指令碼建立的設定檔參數，請使用語法:

`${user.parameter}`

在Recommendations設計中使用動態屬性時，您必須在貨幣符號($)前插入反斜線(\)，才能正確呈現動態值：`\${user.endpoint.lastViewedEntity}`

這些變數會在伺服器端取代為值，所以不需要引號或其他 JavaScript 即可正確顯示。

也可為您想開放給選件的值指定預設值。語法如下:

`${user.testAttribute default="All Items!"}`

當 `testAttribute` 不存在或為空白時，會寫出「All Items!」。如果空白屬性值有效，並且您要將它寫出而非顯示預設，則可以使用:

`${user.testAttribute default="All Items!" show_blank="true"}`

您也可以逸出和取消逸出要顯示的值。如果值有縮寫符號，您可能想要逸出值，如此就不會在頁面上中斷 JavaScript。(選件以 JavaScript 撰寫，因此容易混淆單一縮寫符號與引號。)例如:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`