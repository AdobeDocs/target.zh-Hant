---
keywords: 建議索引鍵；建議邏輯；目前類別；自訂屬性；上次購買的專案；上次檢視的專案；檢視次數最多的專案；最愛的專案；熱門度；最近檢視的專案；上次購買；上次檢視；最愛；最近檢視
description: 瞭解如何根據索引鍵使用建議，這些索引鍵使用訪客行為內容來顯示[!UICONTROL Recommendations]活動中的相關結果。
title: 如何以[!UICONTROL Recommendation]為[!UICONTROL Recommendation Key]的基礎？
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '3463'
ht-degree: 27%

---

# 使推薦以推薦索引鍵為依據

以演演算法為基礎的建議會使用訪客行為內容來顯示[!DNL Adobe Target] [!DNL Recommendations]活動中的相關結果。

每個演演算法型別會提供適合其型別的不同演演算法，如下表所示：

| 演演算法型別 | 何時使用/可用的演演算法 |
| --- | --- |
| [!UICONTROL Cart-Based] | 根據使用者的購物車內容提供建議。<ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
| [!UICONTROL Popularity-Based] | 根據您網站上的專案整體人氣或使用者最喜愛或檢視次數最多的類別、品牌、型別等內的專案人氣提供建議。 <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | 根據找到使用者目前正在檢視或最近檢視之專案的類似專案提供建議。 <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | 根據使用者的行為提供建議。 <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | 根據您上傳的自訂檔案提出建議。 <ul><li>自訂演演算法</li></ul> |

各條件均在自己的標籤中定義。流量平均分入不同的條件測試中。換句話說，如果您有兩個條件，流量會在它們之間平均分配。如果您有兩個條件和兩個設計，流量會在四個組合中平均分割。您也可指定可看到預設內容的訪客比例，以進行比較。在這種情況下，指定的訪客百分比會看到預設內容，其餘則會平分給您的條件和設計組合。

如需建立條件以及定義其演演算法型別與演演算法的詳細資訊，請參閱[建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

不同的建議演演算法會將自身借出，以放置在不同型別的頁面上。 請參閱下列各節，以取得關於每個演演算法型別及其可用演演算法的詳細資訊。

## 購物車型 {#cart-based}

[!UICONTROL Cart-Based]演演算法型別允許根據訪客目前購物車的內容來建議專案。 建議金鑰是透過[mbox引數`cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}以逗號分隔的值提供。 僅考慮前 10 個值。

購物車型建議邏輯類似於&quot;[!UICONTROL Recommended For You]&quot;使用者型演演算法，以及&quot;[!UICONTROL People Who Viewed These, Bought Those]&quot;和&quot;[!UICONTROL People Who Bought These, Bought Those]&quot;專案型演演算法。

[!DNL Target]會使用合作篩選技術來判斷訪客購物車中每個專案的相似性，然後結合每個專案的這些行為相似性，以取得合併清單。

[!DNL Target]也可讓行銷人員選擇檢視單一工作階段或多個工作階段中的訪客行為：

* **[!UICONTROL Single Session]**：根據其他訪客在單一工作階段中的行為。

  當產品根據使用、場合或事件強烈地「配合」在一起時，檢視單一工作階段中的行為可能是合理的。 例如，訪客正在購買印表機，可能還需要墨水及紙張。 或者，訪客正在購買花生醬，可能還需要麵包和果凍。

* **[!UICONTROL Across Sessions]**：根據其他訪客在多個工作階段所做的動作。

  當產品根據訪客偏好或品味強烈「配合」時，檢視多個工作階段的行為可能有意義。 例如，訪客喜歡《星際大戰》，可能也喜歡《印地安納瓊斯》，即使訪客不一定想同時觀看兩部電影。 或者，訪客喜歡桌遊遊戲「Codenames」，並且可能也喜歡桌遊遊戲「Avalon」，即使訪客無法同時玩兩個遊戲。

[!DNL Target]會根據每位訪客目前購物車中的專案提供建議，無論您是檢視單一工作階段內的訪客行為，還是檢視多個工作階段的訪客行為。

下列演演算法可用於[!UICONTROL Cart-Based]演演算法型別：

### [!UICONTROL People Who Viewed This, Also Viewed]

建議在檢視所指定項目的相同工作階段中，最常檢視的項目。

此邏輯會傳回使用者檢視此產品後所檢視的其他產品。 指定的產品未包含在結果集中。

此邏輯可讓您藉由推薦其他檢視過專案的訪客也檢視過的專案，來建立其他轉換機會。 例如，在您網站上檢視公路腳踏車的訪客也可能檢視腳踏車頭盔、腳踏車套件、車鎖等。 您可以使用此邏輯建立建議，以建議其他產品可協助您增加收入。

如果您選取此演演算法，可以選取下列建議索引鍵：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Also Bought]

建議在檢視指定專案的相同工作階段中最常購買的專案。

此邏輯會傳回使用者檢視此產品後購買的其他產品。 指定的產品未包含在結果集中。

此邏輯可讓您藉由在產品頁面上顯示建議（例如，顯示其他檢視過所購買專案的訪客）來增加交叉銷售機會。 例如，如果訪客正在檢視釣竿，建議會顯示其他訪客購買的其他專案，例如釣竿盒、魚竿和釣魚誘餌。 當訪客瀏覽您的網站時，您會提供他們額外的購買建議。

如果您選取此演演算法，可以選取下列建議索引鍵：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Also Bought]

建議當客戶購買所指定項目的同時，最常購買的項目。

此邏輯會傳回使用者購買此產品後購買的其他產品。 指定的產品未包含在結果集中。

此邏輯可讓您藉由在購物車摘要頁面上顯示建議（例如，顯示其他買家也購買的專案），以增加交叉銷售機會。 例如，如果訪客正在購買西裝，建議可顯示其他訪客隨同西裝一起購買的其他專案，例如領帶、正裝鞋和袖扣。 當訪客檢閱其購買專案時，您會提供他們額外的建議。

如果您選取此演演算法，可以選取下列建議索引鍵：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## [!UICONTROL Popularity-Based]

[!UICONTROL Popularity-Based]演演算法型別可讓您根據整個網站中專案的整體人氣或根據使用者最喜愛或檢視次數最多的類別、品牌、型別等內的專案人氣提供建議。

下列演演算法可用於[!UICONTROL Popularity-Based]演演算法型別：

### [!UICONTROL Most Viewed Across the Site] {#most-viewed}

建議由檢視次數最多的專案決定。 這由最新/頻率條件判斷，方式如下:

* 第一個產品檢視 10 點
* 每個後續檢視 5 點
* 作業結束時，所有值除以 2

例如，在一個工作階段中檢視衝浪板A然後檢視衝浪板B會導致A：10、B：5。 作業結束時，您有A：5、B：2.5。如果您在下一個作業階段中檢視相同的專案，值會變更為A： 15 B： 7.5。

在一般頁面（例如首頁或登陸頁面及站外廣告）上使用此演演算法。

### [!UICONTROL Most Viewed by Category] {#most-viewed-category}

建議由接收最多活動的類別確定，而使用的方法與「檢視次數最多的項目」的相同，只不過是以類別計分，而並非產品。

這由最新/頻率條件判斷，方式如下:

* 第一個類別檢視 10 點
* 每個後續檢視 5 點

第一次造訪的類別會獲得 10 點。後續對相同類別的造訪會獲得 5 點。隨著每次造訪，之前已檢視的非目前類別會減少 1。

例如，在一個工作階段中檢視類別A接著檢視類別B會導致A：9、B：10。 如果您在下次作業時檢視相同項目，值會變更為 A: 20 B: 9。

在一般頁面（例如首頁或登陸頁面及站外廣告）上使用此演演算法。

如果您選取「依類別檢視次數最多」演演算法，可以選取下列Recommendations索引鍵：

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Most Viewed by Item Attribute]

推薦與您網站上檢視次數最多的專案或媒體類似的專案或媒體。

此演演算法可讓您選取建議要根據的專案屬性，例如「名稱」或「品牌」。

接著，您需選取訪客的設定檔中儲存哪些設定檔屬性要符合，例如「最喜愛的品牌」、「加入購物車的最後一個專案」或「最常檢視的節目」。

### [!UICONTROL Top Sellers Across the Site] {#top-sellers}

顯示整個網站中，已完成最多訂單所包含的料號。 單一訂單中相同項目的多個單位視為一份訂單。

此演演算法可讓您為網站上的最暢銷專案建立建議，以提高轉換率和收入。 此邏輯尤其適合初次造訪您網站的訪客。

### [!UICONTROL Top Sellers by Category]

依類別顯示最已完成訂單中包含的料號。 單一訂單中相同項目的多個單位視為一份訂單。

此演演算法可讓您根據類別，建立網站上最暢銷商品的建議，以提高轉換率和收入。 此邏輯尤其適合初次造訪您網站的訪客。

如果您選取[!UICONTROL Most Viewed by Category]演演算法，則可以選取下列[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Top Sellers by Item Attribute]

推薦與您網站上最常購買的專案或媒體類似的專案或媒體。

此演演算法可讓您選取建議要根據的專案屬性，例如「名稱」或「品牌」。

接著，您需選取訪客的設定檔中儲存哪些設定檔屬性要符合，例如「最喜愛的品牌」、「加入購物車的最後一個專案」或「最常檢視的節目」。

### [!UICONTROL Top by Analytics Metric]

顯示&#x200B;*x*&#x200B;為任意[!DNL Analytics]量度的「前x個」。 使用來自mbox的行為資料時，您可以使用[!UICONTROL Top Sold]或[!UICONTROL Top Viewed] （x = &quot;Sold&quot;或x = &quot;Viewed&quot;）。 如果您是使用[!DNL Adobe Analytics]的行為資料，您可以使用x = &quot;Cart Adds&quot;或其他[!DNL Analytics]個量度。

## [!UICONTROL Item-Based]

[!UICONTROL Item-Based]建議型別可讓您根據使用者目前檢視或最近檢視之專案的類似專案來提出建議。

下列演演算法可用於[!UICONTROL Item-Based]演演算法型別：

### [!UICONTROL People Who Viewed This, Viewed That] {#viewed-viewed}

建議在檢視所指定項目的相同工作階段中，最常檢視的項目。

此邏輯會傳回檢視此邏輯後所檢視的其他產品；指定的產品不會包含在結果集中。

此邏輯可讓您藉由推薦其他檢視過專案的訪客也檢視過的專案，來建立其他轉換機會。 例如，在您網站上檢視公路腳踏車的訪客也可能檢視腳踏車頭盔、腳踏車套件、車鎖等。 您可以使用此邏輯建立建議，以建議其他產品可協助您增加收入。

如果您選取此演演算法，則可以選取下列[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Bought That] {#viewed-bought}

建議在檢視所指定項目的相同工作階段中，最常購買的項目。此條件傳回在檢視這個產品之後購買的其他產品，而指定的產品未包含在結果集合中。

此邏輯會傳回檢視此邏輯後購買的其他產品；指定的產品不包含於結果集中。

此邏輯可讓您藉由在產品頁面上顯示建議（例如，顯示其他檢視過所購買專案的訪客）來增加交叉銷售機會。 例如，如果訪客正在檢視釣竿，建議會顯示其他訪客購買的其他專案，例如釣竿盒、魚竿和釣魚誘餌。 當訪客瀏覽您的網站時，您會提供他們額外的購買建議。

如果您選取此演演算法，則可以選取下列[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Bought That] {#bought-bought}

建議當客戶購買所指定項目的同時，最常購買的項目。

此邏輯會傳回使用者購買此產品後購買的其他產品。 指定的產品未包含在結果集中。

此邏輯可讓您藉由在購物車摘要頁面上顯示建議（例如，顯示其他買家也購買的專案），以增加交叉銷售機會。 例如，如果訪客正在購買西裝，建議可顯示其他訪客隨同西裝一起購買的其他專案，例如領帶、正裝鞋和袖扣。 當訪客檢閱其購買專案時，您會提供他們額外的建議。

如果您選取此演演算法，則可以選取下列[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL Items with Similar Attributes] {#similar-attributes}

根據目前頁面活動或訪客的過去行為，建議相似的項目或媒體。

如果您選取[!UICONTROL Items with Similar Attributes]或[!UICONTROL Media with Similar Attributes]，便可選擇設定內容相似度規則。

使用內容相似度來產生建議，對於使用[!UICONTROL People Who Viewed This]、[!UICONTROL Viewed That]和其他根據過去行為的邏輯，不太可能在建議中顯示的新專案特別有效。 您也可以使用內容相似度，為沒有過去的購買或其他歷史資料的新訪客產生實用的建議。

如果您選取此演演算法，則可以選取下列[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

如需詳細資訊，請參閱[內容相似度](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)。

## [!UICONTROL User-Based]

[!UICONTROL User-Based]演演算法型別可讓您根據使用者的行為提供建議。

下列演演算法可用於[!UICONTROL User-Based]演演算法型別：

### [!UICONTROL Recently Viewed Items] {#recently-viewed}

根據設計中的位置數量，使用訪客的歷史 (跨工作階段) 以呈現訪客已檢視的前 *x* 個項目。

[!UICONTROL Recently Viewed Items]演演算法傳回指定[環境](/help/main/administrating-target/hosts.md)的特定結果。 如果兩個網站分屬於不同環境，當訪客在這兩個網站之間進行切換時，每個網站都只會顯示適用網站最近檢視過的項目。如果兩個網站屬於同一環境，當訪客在這兩個網站之間進行切換時，訪客會看到兩個網站同樣最近檢視過的專案。

>[!NOTE]
>
>您無法將[!UICONTROL Recently Viewed Items]條件用於備份建議。

可以篩選[!UICONTROL Recently Viewed Items]或[!UICONTROL Recently Viewed Media]，以便只顯示具有特定屬性的專案。

* [!UICONTROL Recently Viewed]條件可設定，就像建議中的其他條件一樣。
* 您可以使用與任何其他條件相同的方式使用[集合](/help/main/c-recommendations/c-products/collections.md)、[排除專案](/help/main/c-recommendations/c-products/exclusions.md)和[包含專案](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) （包括價格與存貨的特殊規則）。

可能的使用案例包括，擁有多個企業的跨國公司可能有跨多個數位資產的訪客檢視專案。 在此情況下，您可以將最近查看的項目限制在僅顯示檢視其所在位置的各自屬性。這可防止最近檢視的專案顯示在其他數位屬性的網站上。

在一般頁面（例如首頁或登陸頁面及站外廣告）上使用此演演算法。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items]會尊重排除全域設定和針對活動選取的集合設定。 如果全域排除排除了某個專案，或所選集合中未包含某個專案，則不會顯示該專案。 因此，在使用[!UICONTROL Recently Viewed Items]條件時，通常應使用「所有集合」設定。

### [!UICONTROL Recommended for You] {#recommended-for-you}

根據每位訪客的瀏覽、檢視和購買記錄來建議專案。

此演演算法可讓您為新訪客和回訪訪客提供個人化內容和體驗。 建議清單會針對訪客的最近活動加權，並會在工作階段中更新，當使用者瀏覽您的網站時，推薦清單會變得更個人化。

檢視和購買都會用來決定建議專案。 指定的建議金鑰（例如[!UICONTROL Current Item]）可用來套用您選取的任何包含規則篩選器。

例如，您可以:

* 排除不符合特定條件的專案（無庫存、30天前發表的文章、分級為R的影片等）。
* 將內含專案限製為單一類別或目前類別。

如果您選取此演演算法，可以選取下列篩選索引鍵：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## 自訂條件 {#custom}

[!UICONTROL Custom Criteria]演演算法型別可讓您根據上傳的自訂檔案提出建議。

Recommendation 由儲存在訪客輪廓中的項目決定，並使用user.*x* 或輪廓。*x* 屬性。

選取此選項時，輪廓屬性中必須呈現 `entity.id` 值。

根據自訂屬性來建議時，您必須選取自訂屬性，然後選取建議類型。

對於您自己的自訂條件輸出，您可以執行即時篩選。例如，您可以將建議的項目限制在來自訪客最喜愛的類別或品牌的內容。此功能可讓您結合離線計算與即時篩選。

此功能表示您可以在離線計算的建議或自訂策展清單上，使用[!DNL Target]新增個人化。 這結合資料科學家的本領和研究，與 Adobe 的實測可靠傳送、執行階段篩選、A/B 測試、鎖定目標、報表、整合及其他。

連同在[!UICONTROL Custom Criteria]上新增包含規則，這還可以根據訪客的興趣，將原本靜態的建議轉換成動態建議。

* 就像建議中的其他條件一樣，自訂條件也可設定。
* 您可以使用與任何其他條件相同的方式使用[集合](/help/main/c-recommendations/c-products/collections.md)、[排除專案](/help/main/c-recommendations/c-products/exclusions.md)和[包含專案](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) （包括價格與存貨的特殊規則）。

可能的使用案例包括:

* 您想從自訂策展清單中建議電影，但僅限於訪客還沒看過。
* 您想要執行離線演演算法，並使用結果來支援建議，但您必須確保永遠不建議使用無庫存的專案。
* 您想只包含此訪客最喜愛的類別中的項目。

## 建議索引鍵 {#keys}

下列建議索引鍵可從[!UICONTROL Recommendation Key]下拉式清單中取得：

### [!UICONTROL Current Item] {#current-item}

建議由訪客正在檢視的項目確定。

推薦會顯示對指定項目感興趣的訪客的其他項目。

選取此選項時，必須將 `entity.id` 值作為顯示 mbox 的參數傳遞。

可與下列演演算法搭配使用：

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

使用您網站上的[!UICONTROL Current Item]建議金鑰：

* 單一項目頁面，例如產品頁面。
* 請勿在 null 搜尋結果頁面上使用。

### [!UICONTROL Last Purchased Item] {#last-purchased}

建議由每位獨特訪客上次購買的項目確定。系統會自動擷取此值，因此頁面上不會傳遞任何值。

可與下列演演算法搭配使用：

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

使用您網站上的[!UICONTROL Last Purchased Item]建議金鑰：

* 首頁、我的帳戶頁面、離站廣告。
* 請勿在產品頁面或與購買相關的頁面上使用。

#### 自訂建議索引鍵

您可以讓建議以自訂輪廓屬性的值為依據。例如，假設您要根據訪客最近新增至佇列的影片顯示建議影片。

1. 從&#x200B;**[!UICONTROL Recommendation Key]**&#x200B;下拉式清單（例如&quot;[!UICONTROL Last Show Added to Watchlist]&quot;）中選取自訂設定檔屬性。
1. 然後選取您的&#x200B;**[!UICONTROL Recommendation Logic]** （例如&quot;[!UICONTROL People Who Viewed This, Viewed That]&quot;）。

如果自訂輪廓屬性未直接比對至單一實體 ID，則需要向 [!DNL Recommendations] 解說您希望實體的比對如何發生。例如，假設您要顯示訪客最喜愛品牌的最暢銷商品專案。

1. 從&#x200B;**[!UICONTROL Recommendation Key]**&#x200B;下拉式清單（例如「最喜愛的品牌」）中選取自訂設定檔屬性。

1. 然後選取您要與此金鑰搭配使用的&#x200B;**[!UICONTROL Recommendation Logic]** （例如&quot;[!UICONTROL Top Sellers]&quot;）。

   [!UICONTROL Group By Unique Value Of]選項隨即顯示。

1. 選取符合所選索引鍵的實體屬性。 在此案例中，&quot;[!UICONTROL Favorite Brand]&quot;符合`entity.brand`。

   [!DNL Recommendations]現在會產生每個品牌的「[!UICONTROL Top Sellers]」清單，並根據訪客的[!UICONTROL Top Sellers]設定檔屬性中儲存的值，向訪客顯示適當的「[!UICONTROL Favorite Brand]」清單。

### [!UICONTROL Last Viewed Item] {#last-viewed}

建議由每位獨特訪客上次檢視的項目確定。系統會自動擷取此值，因此頁面上不會傳遞任何值。

可與下列演演算法搭配使用：

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

使用您網站上的[!UICONTROL Last Viewed Item]建議金鑰：

* 首頁、我的帳戶頁面、離站廣告。
* 請勿在產品頁面或與購買相關的頁面上使用。

### [!UICONTROL Most Viewed Item] {#most-viewed-logic}

顯示網站上檢視次數最多的專案或媒體。

此邏輯可讓您根據網站上檢視次數最多的專案顯示建議，以提高其他專案的轉換率。 例如，媒體網站可在其首頁上顯示檢視次數最多影片的建議，以鼓勵訪客觀看其他影片。

此建議金鑰可與下列演演算法搭配使用：

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

### [!UICONTROL Current Category] {#current-category}

建議由訪客正在檢視的產品類別確定。

推薦會將項目顯示在指定的產品類別中。

選取此選項時，必須將 `entity.categoryId` 值作為參數傳入顯示 mbox。

此建議金鑰可與下列演演算法搭配使用：

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

使用您網站上的[!UICONTROL Current Category]建議金鑰：

* 單一類別頁面。
* 請勿在 null 搜尋結果頁面上使用。

### [!UICONTROL Favorite Category] {#favorite-category}

建議由訪客最喜愛的產品類別決定。

推薦會將項目顯示在指定的產品類別中。

選取此選項時，必須將 `entity.categoryId` 值作為參數傳入顯示 mbox。

此建議金鑰可與下列演演算法搭配使用：

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

使用您網站上的[!UICONTROL Current Category]建議金鑰：

* 單一類別頁面。
* 請勿在 null 搜尋結果頁面上使用。

### [!UICONTROL Site Affinity] {#site-affinity}

根據項目之間關係的必然性來建議項目。您可以設定此條件，以決定使用[!UICONTROL Inclusion Rules]滑桿顯示建議之前需要多少資料。 例如，如果您選取「非常強」，則會建議符合確定性最強的產品。

例如，如果您設定非常強的相關性，且您的設計包含五個項目，其中三個符合連線強度臨界值，則不符合最低強度需求的兩個項目不會出現在建議中，而會由您定義的備用項目取代。具有最強相關性的項目會先顯示。

例如，線上retailer可在後續的造訪中，建議訪客在過去工作階段中感興趣的專案。 系統會擷取每個訪客工作階段的活動，以根據造訪間隔和頻率模型計算相似性。 當此訪客返回您的網站時，會使用網站相似性來根據您網站上先前的動作顯示建議。

某些客戶具有相異產品集合和相異網站行為，如果他們設定弱網站相關性，可能會獲得最佳結果。

此邏輯可與下列建議索引鍵搭配使用：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]
