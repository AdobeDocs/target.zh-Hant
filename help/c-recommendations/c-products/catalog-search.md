---
description: 目錄搜尋可協助您在目錄中尋找產品或內容。
keywords: 目錄;搜尋
seo-description: Adobe Target中的目錄搜尋可協助您在目錄中找到產品或內容。
seo-title: Adobe Target中的目錄搜尋
solution: Target
title: 目錄搜尋
title-outputclass: premium
topic: Premium
uuid: e0876963-5905-4850-a615-953e435f26e9
badge: premium
translation-type: tm+mt
source-git-commit: afb87e3e23b44133982e55fdc7650250e6bf8b3a

---


# ![PREMIUM](/help/assets/premium.png) 目錄搜尋{#catalog-search}

目錄搜尋可協助您在目錄中尋找產品或內容。

若要存取目錄搜尋，請按一下 **[!UICONTROL 「建議]** &gt; **[!UICONTROL 目錄搜尋]**」。

您可以從選項功能表中 (按一下搜尋欄位的向下箭頭時出現) 選取搜尋選項，以精簡搜尋。

![](assets/searchproductsmenu.png)

搜尋選項包括：

* ALL
* 名稱
* 品牌
* 類別
* ID
* 訊息

**[!UICONTROL 全部]**&#x200B;會使用 OR 邏輯，涵蓋其他所有搜尋條件來搜尋。

In the search results, you click the **[!UICONTROL Environment]** filter to specify the production [host group environment](/help/administrating-target/hosts.md) whose catalog you are displaying. 您也可以捲動瀏覽搜尋結果中的項目，以檢視縮圖和其他產品資訊。

「產品」旁顯示的數字代表在所指定環境中可用的總數之中，符合搜尋詞語的產品數量。

透過動態消息、API或mbox更新收到更新時，目錄會自動重新整理。更新通常在一小時內完成。如果更新正在進行中，則會顯示最近更新的時間。如果未進行更新，則會顯示最新更新開始和完成的時間。

## 根據進階搜尋建立系列或排除

You can create [collections](/help/c-recommendations/c-products/collections.md) or [exclusions](/help/c-recommendations/c-products/exclusions.md) using Advanced Search on the Catalog Search page ([!UICONTROL Recommendations] &gt; [!UICONTROL Catalog Search] &gt; [!UICONTROL Advanced Search]).

![另存新檔](/help/c-recommendations/c-products/assets/save-as.png)

例如，使用 "id &gt; contains" 建立搜尋之後，您就可以按一下[!UICONTROL 「另存新檔] &gt; [!UICONTROL 集合或排除項目」]。

>[!IMPORTANT]
>
>「進階搜尋」功能不區分大小寫，不過傳送時傳回的產品會以區分大小寫的搜尋為依據。此不相符的情況可能導致混淆。使用「進階搜尋」功能來根據結果建立集合或排除項目時，務必注意大小寫。例如，如果您執行 "Holiday" 的搜尋，初始的搜尋清單結果會包含 "Holiday" 和 "holiday"。如果您之後建立一個目錄，目的要傳回包含 "holiday" 的產品，則只會傳回包含 "holiday" 的產品。不會傳回包含 "Holiday" 的產品。排除項目也是以類似的方式處理。
