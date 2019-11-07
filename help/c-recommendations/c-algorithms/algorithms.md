---
keywords: recommendations;recommendations活動；准則；算法；建議鍵；自訂鍵；行業垂直；零售；eccommerce;lead generation;b2b；金融服務；媒體；發佈
description: Adobe Target Recommendations中的准則是規則，可根據一組預先設定的訪客行為來決定要推薦哪些產品。
title: Adobe Target Recommendations中的條件
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) 條件{#criteria}

條件即為一種規則，用來根據預先決定的一組訪客行為決定要建議的產品。

條件決定什麼動作會產生什麼建議。您可以新增多個條件，將多個建議類型彼此測試。

## 垂直產業 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

您需要根據建議活動的目標，選取垂直產業。

| 垂直產業 | 目標 |
|--- |--- |
| 零售/電子商務 | 轉換帶動購買 |
| 潛在客戶開發/B2B/金融服務 | 轉換但未購買 |
| 媒體/出版 | 參與 |

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

您選取的建議金鑰決定條件類型。提供幾個條件類型，當您設定 [!DNL Recommendations] 活動時會以條件卡呈現。

| 條件類型 | 密鑰 |
|--- |--- |
| 目前頁面活動 | 根據使用者在目前頁面上的行為來建議項目。例如，訪客在檢視特定文章時，可能想看同類型的其他文章。<ul><li>目前項目</li><li>目前類別</li></ul> |
| 自訂 | 根據自訂屬性來建議項目。<ul><li>自訂屬性</li></ul>根據自訂屬性來建議時，您必須選取自訂屬性，然後選取建議類型。<br>對於您自己的自訂條件輸出，您可以執行即時篩選。例如，您可以將建議的項目限制在來自訪客最喜愛的類別或品牌的內容。此功能可讓您結合離線計算與即時篩選。<br>此功能表示對於離線計算的建議或自訂策展清單，您可以使用 Target 來新增個人化。這結合資料科學家的本領和研究，與 Adobe 的實測可靠傳送、執行階段篩選、A/B 測試、鎖定目標、報表、整合及其他。<br>連同在自訂條件上增加包含規則，這還可以根據訪客的興趣，將原本靜態的建議轉換成動態建議。<ul><li>就像建議中的其他條件一樣，自訂條件也可設定。</li><li>您可以使用[收集](/help/c-recommendations/c-products/collections.md)、[排除](/help/c-recommendations/c-products/exclusions.md)和[包含](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (包括用於價格和存貨的特殊規則) 的方式與任何其他條件相同。</li></ul>可能的使用案例包括:<ul><li>您想從自訂策展清單中建議電影，但僅限於訪客還沒看過。</li><li>您想執行離線演算法，並利用結果來強化建議，但您需要確定絕不會建議沒有庫存的項目。</li><li>您想只包含此訪客最喜愛的類別中的項目。</li></ul> |
| 過去行為 | 根據訪客以往如何回應項目來建議項目。例如，購買特定牌品的人很可能購買相同牌品的其他項目。<ul><li>上次購買的項目</li><li>上次檢視的項目</li><li>檢視次數最多的項目</li><li>最喜愛的類別</li></ul> |
| 人氣 | 建議最熱門項目，例如相關類別中最熱門的影片，或您網站上最常被看到的產品。<ul><li>人氣</li></ul> |
| 最近查看的項目 | 建議訪客最近看過的項目，例如訪客上次造訪網站時查看的項目，或此刻最夯的文章。<br>「最近查看的項目」演算法會傳回某個[環境](/help/administrating-target/hosts.md)中特定訪客活動的結果。如果兩個網站分屬不同環境，且訪客在兩個網站之間切換，演算法僅會傳回相應網站的最近查看項目。<br>此條件類型不受限於集合。<ul><li>最近查看的項目</li></ul>**注意:** 您無法對備用建議使用「最近查看的項目」條件。<br>您可以篩選「最近查看的項目/媒體」，以便僅顯示具有特定屬性的項目。<ul><li>如同建議中的其他條件一樣，「最近查看」條件也可設定。</li><li>您可以使用[收集](/help/c-recommendations/c-products/collections.md)、[排除](/help/c-recommendations/c-products/exclusions.md)和[包含](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (包括用於價格和存貨的特殊規則) 的方式與任何其他條件相同。</li></ul>可能的使用案例包括:<ul><li>經營多種業務的跨國公司可能讓訪客看到遍及多種數位屬性的項目。在此情況下，您可以將最近查看的項目限制在僅顯示檢視其所在位置的各自屬性。這會防止在另一個數位屬性的網站上顯示「最近查看的項目」。</li></ul> |

## 使用自訂建議金鑰 {#custom-key}

您也可以根據自訂描述檔屬性的值來建議。

>[!NOTE]
>
>自訂描述檔參數可透過JavaScript、API或整合傳遞至Target。 如需自訂描述檔屬性的詳細資訊，請參閱「訪客 [描述檔」](/help/c-target/c-visitor-profile/visitor-profile.md)。

例如，假設您想根據使用者最近新增至佇列的影片來顯示建議的影片。

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Last Show Added to Watchlist]).

1. Select your [!UICONTROL Recommendation Logic] (for example, [!UICONTROL People Who Viewed This, Viewed That]).

   ![「建立新標準」對話框](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

If your custom profile attribute does not directly match to a single entity ID, it is necessary to explain to [!DNL Recommendations] how you want the match to an entity to occur.

例如，假設您想要顯示來自使用者最愛品牌的暢銷商品。

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Favorite Brand]).

1. Select the [!UICONTROL Recommendation Logic] you want to use with this key (for example, [!UICONTROL Top Sellers]).

   [!UICONTROL 依下列唯一值分組]選項隨即顯示。

1. 選取比對至您已選擇之索引鍵的實體屬性。In this case [!UICONTROL Favorite Brand] matches to `entity.brand`.

   [!DNL Recommendations] 現在會針對每個品牌產生「最暢銷商品」清單，並根據「最愛品牌」描述檔屬性中儲存的值，向使用者顯示適當的「最暢銷商品  」清單。

   ![「最暢銷商品」屬性](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Criteria/algorithms {#criteria-algorithms}

[!DNL Target Recommendations] 採用複雜的演算法，用於判斷訪客的動作何時符合活動中設定的條件。建議金鑰決定可用的建議邏輯選項。

| 標準 | 說明 |
|--- |--- |
| 具有類似屬性的項目/媒體 | 根據目前頁面活動或訪客的過去行為，建議相似的項目或媒體。<br>**注意:** 如果您選取「具有類似屬性的項目/媒體」，便可選擇設定內容相似度規則。 |
| 瀏覽過此項目、也瀏覽了其他項目的使用者 | 建議在檢視所指定項目的相同工作階段中，最常檢視的項目。 |
| 瀏覽過此項目、但購買了其他項目的使用者 | 建議在檢視所指定項目的相同工作階段中，最常購買的項目。此條件傳回在檢視這個產品之後購買的其他產品，而指定的產品未包含在結果集合中。 |
| 購買了此項目、也購買了其他項目的使用者 | 建議當客戶購買所指定項目的同時，最常購買的項目。 |
| 網站相關性 | 根據項目之間關係的必然性來建議項目。您可以使用「包含規則」滑桿來設定此條件，以決定呈現建議之前需要多少資料。例如，如果選擇「非常強」，則會建議符合確定性最強的產品。<br>例如，如果您設定非常強的相關性，且您的設計包含五個項目，其中三個符合連線強度臨界值，則不符合最低強度需求的兩個項目不會出現在建議中，而會由您定義的備用項目取代。具有最強相關性的項目會先顯示。<br>某些客戶具有相異產品集合和相異網站行為，如果他們設定弱網站相關性，可能會獲得最佳結果。 |
| 最暢銷商品 | 多數完成的訂單中包含的項目。單一訂單中相同項目的多個單位視為一份訂單。 |
| 檢視次數最多 | 最常檢視的項目或媒體。 |
| 最近查看的項目/媒體 | 訪客最近檢視的項目。使用此條件時，您應更新 Target 設計來處理先前檢視的項目數不足以顯示而出現空白建議的情況。 |
| 使用者建議 | 根據每位訪客的瀏覽、檢視和購買記錄來建議項目。 這些項目通常稱為「為您推薦」。<br>此准則可讓您為新訪客和舊訪客提供個人化內容和體驗。 建議清單會針對訪客的最近活動加權，並會在工作階段中更新，當使用者瀏覽您的網站時，建議清單會變得更個人化。<br>檢視和購買都可用來決定建議的項目。 指定的建議金鑰（例如目前項目）可用來套用您選取的任何包含規則篩選。 例如，您可以:<ul><li>排除不符合特定條件的項目（產品無存貨、30天前發佈的文章、評為R的影片等）</li><li>將包含的項目限制為單一類別或目前類別</li></ul> |

>[!NOTE] {class="- topic/note "}
>
>如果執行建議時變更其條件，將會失去報表資料。

您也可以使用訪客的其他已知資訊來增強建議。

所有一天條件每日執行兩次。所有一週及更久條件每日執行一次。網站相關性條件每日執行一次。備用條件每日執行兩次。

## Viewing criteria information {#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以將游標移至卡片上並按一下卡片上的「資訊」圖示，這樣無需開啟條件，即可在快顯卡上查看條件詳情。

![條件卡暫留](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

按一下&#x200B;**[!UICONTROL 「演算法資訊」]索引標籤，即可查看選取條件的一般資訊，包括名稱、說明、垂直產業、頁面類型、建議金鑰、建議邏輯和演算法 ID。**

![演算法資訊索引標籤](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

按一下&#x200B;**[!UICONTROL 「演算法使用情形」]索引標籤，即可查看參照選取條件的活動清單。**&#x200B;卡片會列出使用中和非使用中的活動。按一下「已上線活動」或「非使用中活動」下拉式清單，即可查看參照該條件的完整活動清單。您可以按一下活動連結以開啟活動並編輯。

![條件使用情形索引標籤](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

