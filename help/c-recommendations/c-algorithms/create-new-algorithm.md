---
keywords: criteria;algorithm;industry vertical;page type;recommendation key;recommendation logic;logic;data range;behavior data source;partial design;backup recommendations;inclusion rules;attribute weighting
description: 條件可控制 Adobe Recommendations 活動的內容。建立條件以顯示最適合您的活動的建議。
title: 建立條件
feature: criteria
uuid: 603d4b02-cdb6-40aa-9654-0086c23b0c8e
translation-type: tm+mt
source-git-commit: 35bd6358f1deaaccbf3f272c0f3ff53ed39fb332
workflow-type: tm+mt
source-wordcount: '3609'
ht-degree: 85%

---


# ![PREMIUM](/help/assets/premium.png) 建立條件{#create-criteria}

條件可控制 [!UICONTROL Recommendations] 活動的內容。建立條件以顯示最適合您的活動的建議。

## 建立新條件

以下各節說明如何建立新標準。

### 存取「建立新准則」畫面

有多個方式可進入[!UICONTROL 「建立新條件」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. 您在這裡建立的條件會自動可供所有 [!DNL Recommendations] 活動使用。
* When you are creating a [!DNL Recommendations] activity, click **[!UICONTROL Create Criteria]** on the [!UICONTROL Select Criteria] screen. 您將可以選擇儲存您的新條件以搭配其他 [!DNL Recommendations] 活動使用。
* 編輯 [!DNL Recommendations] 活動時，請在頁面上的[!UICONTROL 「Recommendations 位置」]方塊中按一下，然後選取&#x200B;**[!UICONTROL 「變更條件」]**。On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. 您將可以選擇儲存您的新條件以搭配其他 [!DNL Recommendations] 活動使用。

以下步驟假定您使用第一 [!UICONTROL 種方法訪問「建立新標準] 」螢幕：「建 **[!UICONTROL 議]** > **[!UICONTROL 准則]** 」程式庫畫面。

1. 按一 **[!UICONTROL 下「建議]** > **[!UICONTROL 准則]**」。

1. 按一 **[!UICONTROL 下「建立條件]** > **[!UICONTROL 建立條件]**」。

   ![建立新條件](/help/c-recommendations/c-algorithms/assets/CreateNewCriteria_full-new.png)

### 填寫「基本資訊」區段 {#info}

1. 輸入&#x200B;**[!UICONTROL 條件名稱]**。

   這是用來說明該條件的「內部」名稱。例如，您可能想要將您的條件稱為「利潤最高的產品」，但您不想要將該標題公開顯示。請參閱下一個步驟來設定公開顯示的標題。

   ![「基本資訊」部分](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. 輸入公開顯示的&#x200B;**[!UICONTROL 顯示標題]**，以在使用此條件的任何 Recommendations 頁面上顯示。

   例如，使用此條件來顯示建議時，您可能想要顯示「瀏覽過此項目、也瀏覽了其他項目的使用者」或「類似產品」。

1. 輸入條件的簡短&#x200B;**[!UICONTROL 說明]**。

   說明應協助您識別標準，並可能包含標準用途的相關資訊。

1. 選取&#x200B;**[!UICONTROL 垂直產業]**:

   * [!UICONTROL 零售/電子商務]
   * [!UICONTROL 潛在客戶開發/B2B/金融服務]
   * [!UICONTROL 媒體/出版]

   其他條件選項將根據您選取的垂直產業而變更。

1. 選取一個&#x200B;**[!UICONTROL 頁面類型]**。

   您可以選取多個頁面類型。

   產業垂直和頁面類型可共同用來分類您儲存的條件，讓您可輕鬆對其他 [!DNL Recommendations] 活動重複使用條件。

1. 選取一個&#x200B;**[!UICONTROL 建議索引鍵]**。

   如需依據索引鍵的條件之相關詳細資訊，請參閱[讓建議以建議索引鍵為依據](#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B)。

1. 選取&#x200B;**[!UICONTROL 「建議邏輯」]**。

   如需關於建議邏輯選項的詳細資訊，請參閱[條件](../../c-recommendations/c-algorithms/algorithms.md)。

   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](#similarity).

### 指定您的資料來源選項

1. 設定&#x200B;**[!UICONTROL 資料範圍]**，以便在決定要顯示哪些建議時，限定要使用的可用歷史使用者行為資料的時間範圍。

   ![資料範圍滑桿](/help/c-recommendations/c-algorithms/assets/data-range.png)

   如果您的網站經常有大量流量和行為變更，請選擇較短的資料時段。較短的時段可讓 [!DNL Recommendations] 對於市場和您的業務中的變更更具回應力。例如，較短的時段表示 [!DNL Recommendations] 將在您的訪客開始季節性購物 (例如開學購物或聖誕節) 時偵測訪客行為中的變更，並將對這些購物季建議適當的項目。

   如果您沒有許多資料，或訪客行為不會經常變更，則可以選取較長的時段。不過，對許多網站來說，較短的時段會造成較好的建議。

   可用的資料範圍為:

   * 兩天
   * 一週
   * 兩週
   * 一個月
   * 兩個月

1. (Conditional) Select the desired **[!UICONTROL Behavioral Data Source]**: [!UICONTROL mboxes] or [!UICONTROL Analytics].

   >[!NOTE]
   >
   >只有當 [!UICONTROL 您的實作使用Analytics for Target][](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)時，才會顯示「行為資料來源」區段。

   ![「行為資料源」部分](/help/c-recommendations/c-algorithms/assets/behavioural-data-source.png)

   如果您選擇 [!UICONTROL Analytics]，請選取需要的報表套裝。

   If the criteria uses [!DNL Adobe Analytics] as the behavioral data source, once created, the time for criteria availability depends on whether the selected report suite and lookback window has been used for any other criteria, as explained below:

   * **一次性報表套裝設定**: 報表套裝第一次搭配指定資料範圍回顧期間使用時，[!DNL Target Recommendations] 可能需要二到七天才能從 [!DNL Analytics] 完全下載所選報表套裝的行為資料。This time frame is dependent on the [!DNL Analytics] system load.
   * **使用已可取得之報表套裝的全新或已編輯的條件**: 建立新條件或編輯現有條件時，如果所選報表套裝已搭配 [!DNL Target Recommendations] 使用，且資料範圍小於或等於所選資料範圍，資料即可立即使用且不需要一次性設定。在此情況下，或是在未修改所選報表套裝或資料範圍時已編輯演算法的設定，演算法會在 12 小時內執行或重新執行。
   * **現有演算法執行**: 資料會每天從 [!DNL Analytics] 流動到 [!DNL Target Recommendations]。例如，針對[!UICONTROL 已檢視的相關性]建議，當使用者檢視某個產品時，產品檢視追蹤呼叫會以近乎即時的速度傳送到 [!DNL Analytics]。[!DNL Analytics] 資料會在隔天很早推送到 [!DNL Target]，且 [!DNL Target] 會在 12 小時內執行演算法。

   如需詳細資訊，請參 [閱「搭配使用Adobe Analytics與Target Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md)」。

### 指定內容設定 {#content}

內容規則會決定如果建議的項目數量無法滿足您設計時所要發生的情況。Recommendations 條件可能傳回較您的設計所需更少的建議。例如，如果您的設計有5個項目的空間，但您的准則只會建議3個項目，您可以保留空余空間，或使用備份建議來填滿額外空間。

![內容區段](/help/c-recommendations/c-algorithms/assets/content.png)

1. （可選）將「部 **[!UICONTROL 分設計演算]** 」切換至「開啟」位置。

   將會填入盡可能多的槽，但設計範本可能包含剩餘槽的空白空間。

1. （可選）將「顯 **[!UICONTROL 示備份建議]** 」切換至「開啟」位置。

   從您的網站上隨機選擇檢視次數最多的產品，以填入設計中剩餘的空白位置。

   如需詳細資訊，請參 [閱使用備份建議](/help/c-recommendations/c-algorithms/backup-recs.md)。

1. （條件性）如果您在上 **[!UICONTROL 一步驟中選取「顯示備份建議]** 」，則可以啟用「套 **[!UICONTROL 用包含規則至備份建議」]**。

   包含規則可決定將在您的建議中包括哪些項目。可用的選項取決於您的垂直產業。

   如需更多詳細資料，請參閱 [請在下方指定包含規則](#inclusion) 。

1. （可選）投影片「 **[!UICONTROL 建議先前購買的項目]** 」會切換至「開啟」位置。

   此設定是根據 `productPurchasedId`。預設行為是不推薦先前購買的項目。大多數情況下，您不會想推銷客戶最近已購買的項目。如果您銷售的是客戶一般只會購買一次的項目，例如獨木舟，則此相當實用。如果您銷售的是人們反複回來購買的物品，例如洗髮水或其他個人物品，您應啟用此選項。

下列矩陣顯示使用「部分設計演算」和「備 [!UICONTROL 份建議」選項時][!UICONTROL 將觀察的結果] :

| 部分設計呈現 | 備份 Recommendations | 結果 |
|--- |--- |--- |
| 已停用 | 已停用 | 如果傳回的建議少於設計呼叫的數目，則會以預設內容取代建議設計，並且不顯示建議。 |
| 已啟用 | 已停用 | 系統會轉譯設計，但如果傳回的建議少於設計呼叫的數目，則可能包含空格。 |
| 已啟用 | 已啟用 | 備用建議會填滿可用的設計「槽」，以完整呈現設計。<br>如果因套用包含規則至備用建議而限制了合格備用建議的數量，以致設計無法填滿，則會轉譯部分設計。<br>如果條件未傳回任何建議，並且包含規則將備用建議限制為零，則會以預設內容來取代設計。 |
| 已停用 | 已啟用 | 備用建議會填滿可用的設計「槽」，以完整呈現設計。<br>如果因套用包含規則至備用建議而限制了合格備用建議的數量，以致設計無法填滿，則會以預設內容取代設計，並且不顯示建議。 |

### Specify content similarity rules {#similarity}

使用[!UICONTROL 內容相似度]規則根據項目或媒體屬性來提出建議。

>[!NOTE]
>
>If you selected **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]** as your [recommendation logic](#info), you will have the option to set content similarity rules.

內容相似度會比較項目屬性關鍵字並根據不同項目有多少共通的關鍵字進行建議。根據內容相似度的建議不需要過去的資料即可傳送強大的結果。

使用內容相似度來產生建議對於新項目來說尤其有效，它不太可能在使用&#x200B;*瀏覽過此項目、也瀏覽了其他項目的使用者*&#x200B;和根據過去行為之其他邏輯的建議中顯示。您也可以使用內容相似度，為沒有過去的購買或其他歷史資料的新訪客產生實用的建議。

選取&#x200B;**[!UICONTROL 「項目」]**/**[!UICONTROL 「具有類似屬性的媒體」]**&#x200B;時，您有選項可建立規則，以增加或減少在決定建議時特定項目屬性的重要性。對於書籍之類的項目，您可能想要增強&#x200B;*風格*、*作者*、*系列*&#x200B;之類屬性的重要性，以建議類似的書籍。

![](assets/ContentSimilarity.png)

因為內容相似度使用關鍵字來比較項目，有些屬性，例如&#x200B;*訊息*&#x200B;或&#x200B;*說明*&#x200B;可能會對比較產生「雜訊」。您可以建立規則來忽略這些屬性。

依預設，所有屬性會設為&#x200B;*「基線」*。除非您要變更此設定，否則您不需建立規則。

>[!NOTE]
>
>內容相似度算法可以利用隨機抽樣來計算項目之間的相似度。 因此，項目之間的相似性分級可能會因演算法執行而異。

### 指定包含規則 {#inclusion}

![包含規則](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

有數個選項可以協助您縮減在建議中顯示的項目。您可以在建立條件或促銷活動時使用包含規則。

包含規則屬於可選; 不過，設定這些詳細資料可讓您對於建議中出現的項目擁有更多控制。您設定的每個詳細資訊都會進一步縮小顯示條件。

例如，您可以選擇只顯示存貨超過 50 雙且價格介於 $25 和 $45 之間的女鞋。您也可以加權每個屬性，讓對於您業務更為重要的項目可以更常顯示。

另一個範例是，您可以選擇對造訪您的網站、僅來自特定城市且擁有所需大學學位的訪客顯示職缺。

包含規則選項可能因垂直產業而不同。依預設，包含規則會套用至備用建議。

>[!IMPORTANT]
>
>您應該謹慎使用包含規則。例如，如果您的組織具有規則，要求在顯示某個品牌時不建議其他品牌，則這些選項很有用。不過，此功能有機會成本。將活動條件通常會顯示的某些項目限制為不要顯示時，您可能會遺失提升度百分比。

利用 AND 聯合包含規則。必須符合所有規則，才能在建議中納入某個項目。

如先前所提及，若要建立簡單的包含規則，僅顯示存貨大於 50 且價格介於 $25 與 $45 之間的女鞋，請執行下列步驟:

1. 設定您要建議之產品的價格範圍。
1. 設定您要建議之產品的存貨量下限。
1. 設定建議只在項目符合您的特定條件時才顯示。

   ![](assets/Recs_InclusionRules.png)

   您可以指定僅在符合清單中的其中一項屬性，或不符合一項或多項指定的條件時，才包括項目。

   可用的評估工具取決於您在第一個下拉式清單中選擇的值。您可以列出多個項目。這些項目會使用 OR 來評估。

   多個規則會使用 AND 來結合。

   >[!NOTE]
   >
   >此選項會限制建議中所顯示的項目。不會限制在哪些頁面中顯示建議。若要限制建議顯示的位置，請在體驗撰寫器中選取頁面。

For more information, see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

### 指定屬性加權

您可以新增多個規則，以根據內容目錄的重要說明或中繼資料來「微調」演算法，以便更有可能顯示某些項目。

例如，您可以對在售項目套用較高的加權，以便在建議中更頻繁地顯示它們。不完全排除非售項目，但它們的顯示頻率較低。多種加權屬性皆可套用至相同的演算法，並能依據建議中的拆分流量測試加權屬性。

1. 選擇值。

   根據數個可用條件中的一個，值會決定較可能顯示的項目類型。

1. 選擇一個求值器。

1. 輸入關鍵字以完成規則屬性。

   例如，完整規則可能是&quot;Category contains substring shoes&quot;。

   ![](assets/Recs_AttributeWeighting.png)

1. 選取要指派至規則的加權。

   選項範圍從 0 到 100 (增量為 25)。

1. 如有需要，可新增其他規則。

完成時，按一下&#x200B;**[!UICONTROL 「儲存」]**。

如果您要建立新的 [!UICONTROL Recommendations] 活動或編輯現有的活動，依預設會選取&#x200B;**[!UICONTROL 「儲存條件以供稍後使用」]**&#x200B;核取方塊。如果您不想在其他活動中使用條件，請在儲存之前清除核取方塊。

## 讓建議以建議索引鍵為依據 {#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B}

基於機碼的 Recommendations 會利用訪客行為環境來顯示相關結果。

有兩種類型的建議: 

* **人氣:** 根據「檢視次數最多」、「銷售最高」和「排名最前的量度」列出項目。人氣條件的金鑰為空白。
* **以金鑰為依據:** 組成條件的其餘部分。Recommendations 提供與金鑰類型相關的多種設定選擇。選項範圍從「目前項目」到「設定檔參數」，這允許您以程式設計方式設定要建議的值金鑰。您可以讓每個條件以不同金鑰為基礎，對彼此測試多個條件。

各條件均在自己的標籤中定義。流量平均分入不同的條件測試中。換句話說，如果您有兩個條件，流量會在它們之間平均分配。如果您有兩個條件和兩個設計，流量會在四個組合中平均分割。您也可指定可看到預設內容的訪客比例，以進行比較。這種情況下，指定比例的訪客看到預設內容，其餘的分入條件和設計組合之間。

1. 建立新建議，或選取現有的建議，然後按一下&#x200B;**[!UICONTROL 「編輯」]**。
1. 若要變更建議索引鍵，請從[!UICONTROL 「建議索引鍵」]下拉式清單中選取新索引鍵，然後按一下&#x200B;**[!UICONTROL 「儲存」]**。

   因為不同邏輯會對應至不同建議金鑰，而不同建議會將自身借出，以放置在不同類型的頁面上。請參閱下文章節，瞭解有關每個索引鍵的詳細資訊。

### 目前項目

建議由訪客正在檢視的項目確定。

Recommendations 會顯示對指定項目感興趣的訪客的其他項目。

選取此選項時，必須將 `entity.id` 值作為顯示 mbox 的參數傳遞。

#### 邏輯 (條件)

* [!UICONTROL 具有類似屬性的項目]
* [!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]
* [!UICONTROL 瀏覽過此項目、但購買了其他項目的使用者]
* [!UICONTROL 購買了此項目、也購買了其他項目的使用者]
* [!UICONTROL 網站相關性]

#### 使用您網站上的哪個位置

單一項目頁面，例如產品頁面。

請勿在 null 搜尋結果頁面上使用。

### 目前類別

建議由訪客正在檢視的產品類別確定。

Recommendations 會將項目顯示在指定的產品類別中。

選取此選項時，必須將 `entity.categoryId` 值作為參數傳入顯示 mbox。

#### 邏輯 (條件)

* 最暢銷商品
* 檢視次數最多

#### 使用您網站上的哪個位置

單一類別頁面。

請勿在 null 搜尋結果頁面上使用。

### 自訂屬性 {#custom}

Recommendation 由儲存在訪客設定檔中的項目決定，並使用user.*x* 或設定檔。*x* 屬性。

選取此選項時，設定檔屬性中必須呈現 `entity.id` 值。

#### 邏輯 (條件)

* [!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]
* [!UICONTROL 瀏覽過此項目、但購買了其他項目的使用者]
* [!UICONTROL 購買了此項目、也購買了其他項目的使用者]
* [!UICONTROL 整體行為]
* [!UICONTROL 檢視次數最多]
* [!UICONTROL 最暢銷商品]

如果金鑰為自訂設定檔屬性，而演算法類型為「檢視次數最多」或「最暢銷商品」，則系統會顯示稱為「依下列唯一值分組:」的新下拉式清單，其中有已知實體屬性 (除了 ID、類別、利潤、值、存貨和環境) 的清單。此為必填欄位。

#### 使用您網站上的哪個位置

可以在任何頁面上使用。

#### 使用自訂建議索引鍵

您可以讓建議以自訂設定檔屬性的值為依據。例如，假設您要依據訪客最近新增至其佇列中的電影顯示推薦電影。

1. 從&#x200B;**[!UICONTROL 建議索引鍵]**&#x200B;下拉式清單 (例如「最近新增到觀看清單的節目」) 中選取自訂設定檔屬性。
1. 接著，選取&#x200B;**[!UICONTROL 建議邏輯]** (例如「瀏覽過此項目、也瀏覽了其他項目的使用者」)。

   ![建立新條件對話方塊](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

如果自訂設定檔屬性未直接比對至單一實體 ID，則需要向 [!DNL Recommendations] 解說您希望實體的比對如何發生。例如，假設您要顯示訪客最喜愛品牌的最暢銷商品項目。

1. 從&#x200B;**[!UICONTROL 建議索引鍵]**&#x200B;下拉式清單 (例如「最喜愛的品牌」) 選取自訂設定檔屬性。

1. 接著，選取您要用於此索引鍵的&#x200B;**[!UICONTROL 建議邏輯]** (例如「最暢銷商品」)。

   [!UICONTROL 依下列唯一值分組]選項隨即顯示。

1. 選取比對至您已選擇之索引鍵的實體屬性。在此範例中，「最喜愛的品牌」比對至 `entity.brand`。

   [!DNL Recommendations] 現在會產生每個品牌的「最暢銷商品」清單，並依據訪客最喜愛的品牌設定檔屬性中儲存的值，向訪客顯示相關的「最暢銷商品」清單。

   ![建立新條件對話方塊 2](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### 上次購買的項目

建議由每位獨特訪客上次購買的項目確定。這會自動擷取，因此無需向頁面傳遞任何值。

#### 邏輯 (條件)

* [!UICONTROL 具有類似屬性的項目]
* [!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]
* [!UICONTROL 瀏覽過此項目、但購買了其他項目的使用者]
* [!UICONTROL 購買了此項目、也購買了其他項目的使用者]
* [!UICONTROL 網站相關性]

#### 使用您網站上的哪個位置

首頁、我的帳戶頁面、離站廣告。

請勿在產品頁面或與購買相關的頁面上使用。

### 上次檢視的項目

建議由每位獨特訪客上次檢視的項目確定。這會自動擷取，因此無需向頁面傳遞任何值。

#### 邏輯 (條件)

* [!UICONTROL 具有類似屬性的項目]
* [!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]
* [!UICONTROL 瀏覽過此項目、但購買了其他項目的使用者]
* [!UICONTROL 購買了此項目、也購買了其他項目的使用者]
* [!UICONTROL 網站相關性]

#### 使用您網站上的哪個位置

首頁、我的帳戶頁面、離站廣告。

請勿在產品頁面或與購買相關的頁面上使用。

### 檢視次數最多的項目

建議由檢視次數最多的項目確定，而使用的方法與最喜愛類別的相同。

這由最新/頻率條件判斷，方式如下:

* 第一個產品檢視 10 點
* 每個後續檢視 5 點
* 作業結束時，所有值除以 2

例如，在一次作業中先後檢視 surfboardA 和 surfboardB，結果為 A: 10、B: 5。作業結束之後，結果為 A: 5、B: 2.5。如果您在下次作業時檢視相同項目，值會變更為 A: 15、B: 7.5。

#### 邏輯 (條件)

* [!UICONTROL 具有類似屬性的項目]
* [!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]
* [!UICONTROL 瀏覽過此項目、但購買了其他項目的使用者]
* [!UICONTROL 購買了此項目、也購買了其他項目的使用者]
* [!UICONTROL 網站相關性]

#### 使用您網站上的哪個位置

一般頁面，例如首頁或登陸頁面及離站廣告。

### 最喜愛的類別

建議由接收最多活動的類別確定，而使用的方法與「檢視次數最多的項目」的相同，只不過是以類別計分，而並非產品。

這由最新/頻率條件判斷，方式如下:

* 第一個類別檢視 10 點
* 每個後續檢視 5 點

第一次造訪的類別會獲得 10 點。後續對相同類別的造訪會獲得 5 點。隨著每次造訪，之前已檢視的非目前類別會減少 1。

例如，在一次作業中先後檢視 categoryA 和 categoryB，結果為 A: 9、B: 10。如果您在下次作業時檢視相同項目，值會變更為 A: 20 B: 9。

#### 邏輯 (條件)

* [!UICONTROL 最暢銷商品]
* [!UICONTROL 檢視次數最多]

#### 使用您網站上的哪個位置

一般頁面，例如首頁或登陸頁面及離站廣告。

### 人氣

建議由網站上的項目人氣確定。人氣包括依據 mbox 資料的最暢銷商品和檢視次數最多的產品，如果使用 Adobe Analytics，則還依據產品報表中的所有可用量度。項目的排名是根據您選取的建議邏輯。

#### 邏輯 (條件)

* [!UICONTROL 最暢銷商品]
* [!UICONTROL 檢視次數最多]
* 產品報表量度 (如果您使用 Adobe Analytics)

#### 使用您網站上的哪個位置

一般頁面，例如首頁或登陸頁面及離站廣告。

### 最近查看的項目 {#recently-viewed}

根據設計中的位置數量，使用訪客的歷史 (跨工作階段) 以呈現訪客已檢視的前 *x* 個項目。

現在，「最近檢視的項目」條件會傳回指定[環境](/help/administrating-target/hosts.md)的特定結果。如果兩個網站分屬於不同環境，當訪客在這兩個網站之間進行切換時，每個網站都只會顯示適用網站最近檢視過的項目。如果兩個網站屬於同一環境，當訪客在這兩個網站之間進行切換時，訪客會看到兩個網站同樣最近檢視過的項目。

#### 使用您網站上的哪個位置

一般頁面，例如首頁或登陸頁面及離站廣告。

>[!NOTE]
>
>最近查看的項目會尊重排除全域設定和針對活動所選的收集設定。如果全域排除排除了某個項目，或所選收集中未包含某個項目，則不會顯示該項目；因此，使用最近查看的項目條件時，通常應使用「所有收集」設定。

## Training video: Create criteria in Recommendations (12:33) ![Tutorial badge](/help/assets/tutorial.png)

此影片包含下列資訊:

* 建立條件
* 建立條件序列
* 上傳自訂條件

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
