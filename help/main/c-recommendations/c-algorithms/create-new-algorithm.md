---
keywords: 標準；算法；行業垂直；頁面類型；建議邏輯；邏輯；資料範圍；回望窗口；行為資料源；部分設計；包含規則；屬性權重；當前類別；自定義屬性；最後購買的物料；最後查看的物料；最後查看的物料；最後查看的；最後查看的；
description: 瞭解如何建立控制您的Adobe Recommendations活動內容的標準，以顯示最適合您活動的建議。
title: 如何在Recommendations建立標準？
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: 81cd39140eb21d2718f3899ed6b28217023bd680
workflow-type: tm+mt
source-wordcount: '2835'
ht-degree: 53%

---

# ![PREMIUM](/help/main/assets/premium.png) 建立條件

中的標準 [!UICONTROL Adobe Target] [!UICONTROL Recommendations] 控制您的 [!UICONTROL Recommendations] 活動。 建立條件以顯示最適合您的活動的建議。這些條件使用訪問者的操作來確定要顯示哪些內容或產品。

以下各節說明如何建立新條件。

## 訪問「建立新條件」螢幕

有多個方式可進入[!UICONTROL 「建立新條件」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在 **[!UICONTROL Recommendations]** > **[!UICONTROL 標準]** 庫螢幕，按一下 **[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**。 您在這裡建立的條件會自動可供所有 [!DNL Recommendations] 活動使用。
* 建立 [!DNL Recommendations] 活動 [!UICONTROL 視覺體驗作曲家] (VEC)，您將立即轉到 [!UICONTROL 選擇條件] 在頁面上選擇元素並按一下 [!UICONTROL 更換為Recommendations]。 [!UICONTROL 在前面插入Recommendations]或 [!UICONTROL 在後面插入Recommendations]。 然後可以選擇可用標準，或按一下 **[!UICONTROL 建立條件]**。 如果建立新標準，則可以選擇保存標準以便與其他標準一起使用 [!DNL Recommendations] 活動。 有關詳細資訊，請參見 [建立Recommendations活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。
* 編輯 [!DNL Recommendations] 活動時，請在頁面上的[!UICONTROL 「Recommendations 位置」]方塊中按一下，然後選取&#x200B;**[!UICONTROL 「變更條件」]**。在 [!UICONTROL 選擇條件] 螢幕，按一下 **[!UICONTROL 建立條件]**。 您將可以選擇儲存您的新條件以搭配其他 [!DNL Recommendations] 活動使用。

以下步驟假定您訪問 [!UICONTROL 建立新條件] 使用第一種方法進行螢幕顯示：這樣 **[!UICONTROL Recommendations]** > **[!UICONTROL 標準]** 庫螢幕。

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 標準]**。

1. 按一下 **[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**。

   ![建立新條件](assets/CreateNewCriteria_full-new.png)

1. 在以下各節中配置資訊。

## [!UICONTROL 基本資訊] {#info}

1. 輸入&#x200B;**[!UICONTROL 條件名稱]**。

   這是用來說明該條件的「內部」名稱。例如，您可能想要將您的條件稱為「利潤最高的產品」，但您不想要將該標題公開顯示。請參閱下一個步驟來設定公開顯示的標題。

   ![基本資訊部分](assets/basic-information.png)

1. 輸入公開顯示的&#x200B;**[!UICONTROL 顯示標題]**，以在使用此條件的任何 Recommendations 頁面上顯示。

   例如，使用此條件來顯示建議時，您可能想要顯示「瀏覽過此項目、也瀏覽了其他項目的使用者」或「類似產品」。

1. 輸入條件的簡短&#x200B;**[!UICONTROL 說明]**。

   說明應幫助您確定標準，並可能包括有關標準用途的資訊。

1. 根據建議活動的目標選擇行業垂直型。

   | 垂直產業 | 目標 |
   |--- |--- |
   | 零售/電子商務 | 轉換帶動購買 |
   | 潛在客戶開發/B2B/金融服務 | 轉換但未購買 |
   | 媒體/出版 | 參與 |

   其他條件選項將根據您選取的垂直產業而變更。

1. 選取一個&#x200B;**[!UICONTROL 頁面類型]**。

   您可以選取多個頁面類型。

   產業垂直和頁面類型可共同用來分類您儲存的條件，讓您可輕鬆對其他 [!DNL Recommendations] 活動重複使用條件。

## [!UICONTROL Recommendations算法] {#rec-algo}

1. 選擇 **[!UICONTROL 算法類型]** 和 **[!UICONTROL 算法]**:

   ![「推薦算法」部分](assets/recommended-algorithm.png)

   | 算法類型 | 何時使用 | 可用算法 |
   | --- | --- | --- |
   | [!UICONTROL 基於購物車] | 根據用戶的購物車內容提出建議。 | <ul><li>看過這些的人</li><li>看過這些的人，買了那些</li><li>買這些，買那些的人</li></ul> |
   | [!UICONTROL 基於受歡迎度] | 根據項目在整個站點的總體受歡迎程度或用戶最喜愛或查看次數最多的類別、品牌、流派等中項目的受歡迎程度來提出建議。 | <ul><li>在整個站點上查看的最多</li><li>按類別查看的最多數</li><li>按物料屬性查看的最多數</li><li>網站上的暢銷產品</li><li>按類別排列的暢銷產品</li><li>按物料屬性列出的最大銷售者</li><li>按分析度量排在前面</li></ul> |
   | [!UICONTROL 基於項] | 根據查找與用戶當前正在查看或最近已查看的項目類似的項目來提出建議。 | <ul><li>檢視過此項目、也檢視了其他項目的使用者</li><li>瀏覽過此項目、但購買了其他項目的使用者</li><li>購買了此項目、也購買了其他項目的使用者</li><li>具有相似屬性的項</li></ul> |
   | [!UICONTROL 基於用戶] | 根據用戶的行為提出建議。 | <ul><li>最近查看的項目</li><li>推薦給您</li></ul> |
   | [!UICONTROL 自定義條件] | 根據您上載的自定義檔案提出建議。 | <ul><li>自定義算法</li></ul> |

   >[!NOTE]
   >
   >如果選擇 **[!UICONTROL 項目]**/ **[!UICONTROL 具有相似屬性的媒體]**，您將可以 [內容相似性規則](#similarity)。

1. 根據需要，選擇 **物料屬性** 和 **要匹配的配置檔案屬性**&#x200B;的 **建議密鑰**。 **篩選鍵**，和 **分析度量** 來配置算法。

其餘算法配置選項因所選算法而異。 要完成算法配置，請選擇 [!UICONTROL 建議密鑰]。 [!UICONTROL 篩選鍵]。 [!UICONTROL 共現基準]。 [!UICONTROL 分析度量]，和 [!UICONTROL 物料屬性] 和 [!UICONTROL 要匹配的配置檔案屬性]。

有關選擇的詳細資訊 [!UICONTROL 建議密鑰]，請參閱 [基於建議密鑰的建議](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

## [!UICONTROL 資料來源] {#data-source}

1. 選擇所需 **[!UICONTROL 行為資料源]**: [!UICONTROL Adobe Target] 或 [!UICONTROL 分析]。

   >[!NOTE]
   >
   >的 [!UICONTROL 行為資料源] 只有在實施使用 [目標分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。

   ![「行為資料源」部分](assets/data-source.png)

   如果您選擇 [!UICONTROL Analytics]，請選取需要的報表套裝。

   如果條件使用 [!DNL Adobe Analytics] 作為行為資料源，一旦建立，條件可用性的時間取決於所選報告套件和回望窗口是否已用於任何其他條件，如下所述：

   * **一次性報表套裝設定**: 報表套裝第一次搭配指定資料範圍回顧期間使用時，[!DNL Target Recommendations] 可能需要二到七天才能從 [!DNL Analytics] 完全下載所選報表套裝的行為資料。此時間框取決於 [!DNL Analytics] 系統負載。
   * **使用已可取得之報表套裝的全新或已編輯的條件**: 建立新條件或編輯現有條件時，如果所選報表套裝已搭配 [!DNL Target Recommendations] 使用，且資料範圍小於或等於所選資料範圍，資料即可立即使用且不需要一次性設定。在此情況下，或是在未修改所選報表套裝或資料範圍時已編輯演算法的設定，演算法會在 12 小時內執行或重新執行。
   * **現有演算法執行**: 資料會每天從 [!DNL Analytics] 流動到 [!DNL Target Recommendations]。例如，針對[!UICONTROL 已檢視的相關性]建議，當使用者檢視某個產品時，產品檢視追蹤呼叫會以近乎即時的速度傳送到 [!DNL Analytics]。[!DNL Analytics] 資料會在隔天很早推送到 [!DNL Target]，且 [!DNL Target] 會在 12 小時內執行演算法。

   有關詳細資訊，請參見 [將Adobe Analytics與目標Recommendations](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md)。

1. 設定 **[!UICONTROL 回望窗口]** 確定在確定要顯示的建議時要使用的可用歷史用戶行為資料的時間範圍。 此選項適用於除具有相似屬性的項和自定義算法外的所有算法。

   ![回望窗口滑塊](assets/data-range.png)

   如果您的網站經常有大量流量和行為變更，請選擇較短的資料時段。較短的時段可讓 [!DNL Recommendations] 對於市場和您的業務中的變更更具回應力。例如，較短的時段表示 [!DNL Recommendations] 將在您的訪客開始季節性購物 (例如開學購物或聖誕節) 時偵測訪客行為中的變更，並將對這些購物季建議適當的項目。

   如果您沒有許多資料，或訪客行為不會經常變更，則可以選取較長的時段。但是，對於許多網站，較短的窗口會產生更高質量的建議。

   可用的資料範圍為:

   | 回望窗口選項 | 更新的頻率（懸停時顯示） | 支援的alogrims |
   | --- | --- | --- |
   | 六小時 | 算法每3-6小時運行一次 | [!UICONTROL 基於受歡迎度] 選中時的算法 [!UICONTROL 行為資料源] 是 [!DNL Adobe Target] |
   | 有一天 | 算法每12-24小時運行一次 | [!UICONTROL 基於受歡迎度] 算法 |
   | 兩天 | 算法每12-24小時運行一次 | <ul><li>[!UICONTROL 基於受歡迎度] 算法</li><li>[!UICONTROL 基於項] 算法</li><li>[!UICONTROL 基於用戶] 算法</li><li>[!UICONTROL 基於購物車] 算法</li></ul> |
   | 一週 | 算法每24-48小時運行一次 | <ul><li>[!UICONTROL 基於受歡迎度] 算法</li><li>[!UICONTROL 基於項] 算法</li><li>[!UICONTROL 基於用戶] 算法</li><li>[!UICONTROL 基於購物車] 算法</li></ul> |
   | 兩週 | 算法每24-48小時運行一次 | <ul><li>[!UICONTROL 基於受歡迎度] 算法</li><li>[!UICONTROL 基於項] 算法</li><li>全部 [!UICONTROL 基於用戶] 算法</li><li>[!UICONTROL 基於購物車] 算法</li></ul> |
   | 一個月（30天） | 算法每24-48小時運行一次 | <ul><li>[!UICONTROL 基於受歡迎度] 算法</li><li>[!UICONTROL 基於項] 算法</li><li>[!UICONTROL 基於用戶] 算法</li><li>[!UICONTROL 基於購物車] 算法</li></ul> |
   | 兩個月（61天） | 算法每24-48小時運行一次 | <ul><li>[!UICONTROL 基於受歡迎度] 算法</li><li>[!UICONTROL 基於項] 算法</li><li>[!UICONTROL 基於用戶] 算法</li><li>[!UICONTROL 基於購物車] 算法</li></ul> |

## [!UICONTROL 備份內容] {#content}

[!UICONTROL 備份內容] 規則確定如果建議的項目數未滿足您 [建議設計](/help/main/c-recommendations/c-design-overview/design-overview.md)。 [!DNL Recommendations] 條件可能傳回較您的設計所需更少的建議。例如，如果您的設計有四個插槽，但您的條件只建議兩個，則可以保留其餘的插槽為空，可以使用備份建議來填充額外的插槽，或者選擇不顯示建議。

![內容部分](assets/content.png)

1. （可選）滑動 **[!UICONTROL 部分設計渲染]** 切換到「開啟」位置。

   將填充盡可能多的插槽，但設計模板可能包含剩餘插槽的空白空間。 如果禁用此選項，並且沒有足夠的內容來填充所有可用插槽，則不會提供建議，而會顯示預設內容。

   如果希望建議與空插槽一起使用，請啟用此選項。 如果希望根據您的條件在建議插槽中填充內容，而空插槽中填充了來自您站點的類似或熱門內容，請使用備份建議，如下一步所述。

1. （可選）滑動 **[!UICONTROL 顯示備份內容]** 切換到「開啟」位置。

   在設計中的所有剩餘空插槽中，隨機選擇您站點內查看最多的產品。

   使用備份建議可確保您的建議設計能夠填滿所有可用插槽。 假設您有4 x 1設計，如下所示：

   ![4 x 1設計](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   假設您的條件僅建議兩個項目。 如果啟用 [!UICONTROL 部分設計渲染] 選項，前兩個插槽已填充，但其餘兩個插槽仍為空。 但是，如果啟用 [!UICONTROL 顯示備份Recommendations] 選項，前兩個插槽將根據您的指定條件填充，其餘兩個插槽將根據您的備份建議填充。

   以下矩陣顯示使用 [!UICONTROL 部分設計渲染] 和 [!UICONTROL 備份內容] 選項：

   | 部分設計呈現 | 備份內容 | 結果 |
   |--- |--- |--- |
   | 已停用 | 已停用 | 如果傳回的建議少於設計呼叫的數目，則會以預設內容取代建議設計，並且不顯示建議。 |
   | 已啟用 | 已停用 | 系統會轉譯設計，但如果傳回的建議少於設計呼叫的數目，則可能包含空格。 |
   | 已啟用 | 已啟用 | 備用建議會填滿可用的設計「槽」，以完整呈現設計。<br>如果因套用包含規則至備用建議而限制了合格備用建議的數量，以致設計無法填滿，則會轉譯部分設計。<br>如果條件未傳回任何建議，並且包含規則將備用建議限制為零，則會以預設內容來取代設計。 |
   | 已停用 | 已啟用 | 備用建議會填滿可用的設計「槽」，以完整呈現設計。<br>如果因套用包含規則至備用建議而限制了合格備用建議的數量，以致設計無法填滿，則會以預設內容取代設計，並且不顯示建議。 |

   有關詳細資訊，請參見 [使用備份建議](/help/main/c-recommendations/c-algorithms/backup-recs.md)。

1. （條件）如果選擇 **[!UICONTROL 顯示備份內容]** 在上一步中，您可以 **[!UICONTROL 將包含規則應用於備份建議]**。

   包含規則確定建議中包含哪些項。 可用的選項取決於您的垂直產業。

   如需更多詳細資料，請參閱 [指定包含規則](#inclusion) 下。

## 內容相似度 {#similarity}

使用[!UICONTROL 內容相似度]規則根據項目或媒體屬性來提出建議。

>[!NOTE]
>
>如果已選擇 **[!UICONTROL 基於項]**/ **[!UICONTROL 具有相似屬性的媒體]** 作為「算法類型」和「算法」，您可以選擇設定內容相似性規則。

內容相似度會比較項目屬性關鍵字並根據不同項目有多少共通的關鍵字進行建議。根據內容相似度的建議不需要過去的資料即可傳送強大的結果。

使用內容相似度來產生建議對於新項目來說尤其有效，它不太可能在使用&#x200B;*瀏覽過此項目、也瀏覽了其他項目的使用者*&#x200B;和根據過去行為之其他邏輯的建議中顯示。您也可以使用內容相似度，為沒有過去的購買或其他歷史資料的新訪客產生實用的建議。

選擇時 **[!UICONTROL 基於項]**/ **[!UICONTROL 具有相似屬性的媒體]**，您可以選擇建立規則來增加或減少特定物料屬性在確定建議時的重要性。 對於書籍之類的項目，您可能想要增強&#x200B;*風格*、*作者*、*系列*&#x200B;之類屬性的重要性，以建議類似的書籍。

![](assets/ContentSimilarity.png)

因為內容相似度使用關鍵字來比較項目，有些屬性，例如&#x200B;*訊息*&#x200B;或&#x200B;*說明*&#x200B;可能會對比較產生「雜訊」。您可以建立規則來忽略這些屬性。

依預設，所有屬性會設為&#x200B;*「基線」*。除非您要變更此設定，否則您不需建立規則。

>[!NOTE]
>
>內容相似性算法可能採用隨機抽樣計算項目之間的相似度。 因此，在算法運行之間，項目之間的相似性等級可能會有所不同。

## 包含規則 {#inclusion}

有數個選項可以協助您縮減在建議中顯示的項目。您可以在建立條件或促銷活動時使用包含規則。

![包含規則](/help/main/c-recommendations/c-algorithms/assets/inclusion-rules.png)

包含規則屬於可選; 不過，設定這些詳細資料可讓您對於建議中出現的項目擁有更多控制。您設定的每個詳細資訊都會進一步縮小顯示條件。

例如，您可以選擇只顯示存貨超過 50 雙且價格介於 $25 和 $45 之間的女鞋。您也可以加權每個屬性，讓對於您業務更為重要的項目可以更常顯示。

另一個範例是，您可以選擇對造訪您的網站、僅來自特定城市且擁有所需大學學位的訪客顯示職缺。

包含規則選項可能因垂直產業而不同。依預設，包含規則會套用至備用建議。

>[!IMPORTANT]
>
>您應該謹慎使用包含規則。例如，如果您的組織具有規則，要求在顯示某個品牌時不建議其他品牌，則這些選項很有用。不過，此功能有機會成本。將活動條件通常會顯示的某些項目限制為不要顯示時，您可能會遺失提升度百分比。

利用 AND 聯合包含規則。必須符合所有規則，才能在建議中納入某個項目。

如先前所提及，若要建立簡單的包含規則，僅顯示存貨大於 50 且價格介於 $25 與 $45 之間的女鞋，請執行下列步驟:

1. （條件）滑動 **[!UICONTROL 是否允許推薦最近購買的項目？]** 切換到「開啟」位置。

   此設定是根據 `productPurchasedId`。預設行為是不推薦先前購買的項目。大多數情況下，您不會想推銷客戶最近已購買的項目。如果您銷售的是客戶一般只會購買一次的項目，例如獨木舟，則此相當實用。如果您銷售的是人們反複回來購買的產品，如洗髮水或其他個人產品，則應啟用此選項。

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

有關詳細資訊，請參見 [使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)。

## 屬性加權 {#weighting}

您可以添加多個規則，根據有關內容目錄的重要資訊或元資料來「微移」算法，以便更有可能顯示某些項目。

例如，您可以對在售項目套用較高的加權，以便在建議中更頻繁地顯示它們。不完全排除非售項目，但它們的顯示頻率較低。多種加權屬性皆可套用至相同的演算法，並能依據建議中的拆分流量測試加權屬性。

1. 選擇值。

   根據數個可用條件中的一個，值會決定較可能顯示的項目類型。

1. 選擇一個求值器。

1. 輸入關鍵字以完成規則屬性。

   例如，完整規則可能是「Category contains substring shoes（類別包含子字串鞋）」。

   ![](assets/Recs_AttributeWeighting.png)

1. 選取要指派至規則的加權。

   選項範圍從 0 到 100 (增量為 25)。

1. 如有需要，可新增其他規則。

完成時，按一下&#x200B;**[!UICONTROL 「儲存」]**。

如果您要建立新的 [!UICONTROL Recommendations] 活動或編輯現有的活動，依預設會選取&#x200B;**[!UICONTROL 「儲存條件以供稍後使用」]**&#x200B;核取方塊。如果您不想在其他活動中使用條件，請在儲存之前清除核取方塊。

## 培訓視頻：在Recommendations建立標準(12:33) ![教程徽章](/help/main/assets/tutorial.png)

此影片包含下列資訊:

* 建立條件
* 建立條件序列
* 上傳自訂條件

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
