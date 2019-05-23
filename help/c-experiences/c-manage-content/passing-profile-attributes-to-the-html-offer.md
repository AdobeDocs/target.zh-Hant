---
description: 您可以直接在HTML或JSON選件中顯示描述檔值和活動資訊。
keywords: 動態資料；資產；資料；優惠；個人化優惠；個人化優惠；代號取代
seo-description: 您可以直接在HTML或JSON選件中顯示描述檔值和活動資訊。
seo-title: 將動態資料傳遞至選件
solution: Target
title: 將動態資料傳遞至選件
topic: Premium
uuid: 1910a7f5-e4bd-413a-9875-e0b005407f50
translation-type: tm+mt
source-git-commit: f792c0b995e0f4445d3c3849a431d64b6bd60324

---


# 將動態資料傳遞至選件{#pass-dynamic-data-into-offers}

您可以動態顯示儲存在Target描述檔中的訪客資訊。同樣地，活動資訊(例如活動名稱或體驗名稱)也可以用來建立單一選件，根據訪客的興趣、過去行為和整體描述檔動態傳回個人化內容。

**業務案例**

* 促銷折扣選件以「調整」或「補充」最後購買的產品。您不需為目錄中每個項目建立個別選件，而可以使用動態文字建立選件，以便讀取描述檔中所購買的「最後一個產品」，並在選件中顯示連結。
* 訪客使用 `keyword=world` `cup` 到達您的登陸頁面。您在選件中顯示字詞 *World cup*。
* 使用資訊個人化建議標籤，例如(1)將最後一個項目新增至訪客的購物車(Nike Air Max1000s)、(2)訪客的色彩偏好設定(黑色)和(3)訪客最喜愛的非鞋類類別(hoop)。範例：「使用這些酷炫的&#39;black&#39;whootes&#39;讓您的Nike Air Max1000s變得令人驚艷！」


**技術優勢**

因為使用者專屬的偏好、行為、狀態等，可儲存在使用者的個人檔案中，您可以在訪客下次造訪時重復此訊息。動態選件可讓您在活動中設定單一選件，以便在所有訪客的個人化訊息中設定單一選件。當訪客的意圖變更時，您的網站內容會自動反映這些變更。

**範例**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* HTML 選件代碼: `Get your ${profile.keyword} information here!`
* 使用者看見: 在這裡取得您的世界盃資訊！

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
| 過去行為 | `{$user.endpoint.lastPurchasedEntity}`, `{$user.endpoint.lastViewedEntity}`, `{$user.endpoint.mostViewedEntity}`, `{$user.endpoint.categoryAffinity}` |

在主控台中記錄資訊以進行除錯，例如 `${campaign.name}`， `${campaign.id}``${campaign.recipe.name}``${campaign.recipe.id}``${offer.name}``${offer.id}`、 `${campaign.name}`

如需Recommendations設計，請參閱 [設計概述](/help/c-recommendations/c-design-overview/design-overview.md)中的其他範例。

**實施**

對於傳遞至mbox的描述檔參數，請使用語法： `${profile.parameter}` 對於描述檔指令碼中建立的描述檔參數，請使用語法：

`${user.parameter}`

在Recommendations設計中使用動態屬性時，您必須在$符號(&#39;$&#39;)之前插入反斜線(&#39;\&#39;)，以便動態值正確轉換： `\${user.endpoint.lastViewedEntity}`

這些變數會在伺服器端取代為值，所以不需要引號或其他 JavaScript 即可正確顯示。

也可為您想開放給選件的值指定預設值。語法如下:

`${user.testAttribute default="All Items!"}`

當 `testAttribute` 不存在或為空白時，會寫出「All Items!」。如果空白屬性值有效，並且您要將它寫出而非顯示預設，則可以使用:

`${user.testAttribute default="All Items!" show_blank="true"}`

您也可以逸出和取消逸出要顯示的值。如果值有縮寫符號，您可能想要逸出值，如此就不會在頁面上中斷 JavaScript。(選件以 JavaScript 撰寫，因此容易混淆單一縮寫符號與引號。)例如:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`