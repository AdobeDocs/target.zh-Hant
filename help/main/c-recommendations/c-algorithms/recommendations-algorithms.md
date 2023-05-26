---
keywords: Recommendations演演算法；模型訓練；模型服務；內容傳送；專案型；使用者型；熱門程度；購物車型；自訂條件
description: 瞭解中使用的演演算法 [!DNL Target Recommendations]，包括模型訓練和模型服務。
title: 我可以在何處瞭解Target Recommendations演演算法背後的科學？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
source-git-commit: 2a25fdb42ce4470f9126b7e0e7f6fd9e60c350e5
workflow-type: tm+mt
source-wordcount: '2842'
ht-degree: 1%

---

# Target 推薦演算法背後的科學

中使用的演演算法的深入說明 [!DNL Adobe Target Recommendations]包括模型訓練的邏輯和數學細節，以及模型服務的流程。

模型訓練是產生建議的程式 [!DNL Adobe Target] 學習演演算法。 模型服務是如何 [!DNL Target] 會向網站訪客提供建議（也稱為內容傳送）。

[!DNL Target] 包含下列各種型別的演演算法： [!DNL Recommendations]：

* **以專案為基礎的演演算法**：包括遵循「已檢視/購買此專案的人也已檢視/購買這些專案」邏輯的演演算法。 這些演演算法會分組在傘狀字詞「專案 — 專案協同篩選」下，以及 [!UICONTROL 具有類似屬性的專案] 演演算法。

* **基於使用者的演演算法**：包含 [!UICONTROL 最近檢視的專案] 和 [!UICONTROL 為您推薦] 演演算法。

* **基於熱門程度的演演算法**：包含可傳回網站中「最常檢視」或「最常購買」專案，或依類別或專案屬性傳回「最常檢視」或「最常購買」專案的演演算法。

* **購物車型演演算法**：使用邏輯「已檢視/購買這些專案的人也已檢視/購買這些專案」包含以多專案為基礎的建議。

* **自訂條件**：包括根據上傳到的自訂檔案的建議 [!DNL Target].

>[!NOTE]
>
>如需每個演演算法型別和個別演演算法的詳細一般資訊，請參閱 [讓建議以建議索引鍵為依據](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

以上列出的許多演演算法都是以存在一或多個索引鍵為前提。 這些索引鍵是用來在內容傳送時（提出建議時）擷取類似專案。 客戶指定的索引鍵可包含某人正在檢視的目前專案、上次檢視或購買的專案、最常檢視的專案、目前類別，或該訪客最喜愛的類別。 其他演演算法（例如購物車或使用者型建議）會使用隱含索引鍵（客戶無法設定）。 如需詳細資訊，請參閱 *建議索引鍵*，在 [讓建議以建議索引鍵為依據](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys). 但請注意，這些鍵值僅與模型服務時間（內容傳送）相關。 這些索引鍵不會影響「離線」或模型訓練時間邏輯。

以下各節會以與上述演演算法型別稍微不同的方式將演演算法分組。 以下分組是根據模型訓練邏輯的相似性。

## 料號 — 料號協同篩選

演演算法包括：

* [!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]
* [!UICONTROL 瀏覽過此項目、但購買了其他項目的使用者]
* [!UICONTROL 購買了此項目、也購買了其他項目的使用者]

料號 — 料號協同篩選建議演演算法所根據的理念是，您應使用許多使用者的行為模式（因此是協同合作），為指定料號提供有用的建議（例如，篩選可能要建議之料號的目錄）。 雖然有許多不同的演演算法屬於的一般範圍， [協同篩選](https://en.wikipedia.org/wiki/Collaborative_filtering)，這些演演算法會普遍使用行為資料來源作為輸入。 在 [!DNL Target Recommendations]，這些輸入為使用者對專案的不重複檢視和購買。

針對「已檢視/購買此專案的使用者也檢視/購買了這些專案」演演算法，目標是計算所有專案配對之間的相似度(A，B)。 對於指定的專案A，排名最前的建議會依其相似度s(A，B)排序。

專案之間的共現即為此類相似性的一個範例：購買兩個專案的使用者人數的簡單計數。 雖然此量度直覺式但太過天真，因為它偏向於推薦熱門專案。 例如，如果大多數人在雜貨店購買麵包，則麵包會與所有專案有很高的共現率，但不一定是好的建議。 [!DNL Target] 而是使用更複雜的相似性量度，稱為對數似然比(LLR)。 當A和B兩個專案同時發生的機率與其不同時發生的機率差異很大時，此數量會很大。 如需具體資訊，請考慮 [!UICONTROL 瀏覽過此專案、但購買了其他專案的使用者] 演演算法。 購買B的可能性為時，LLR相似性會很大 *not* 無論是否有人檢視A。

例如，若

![已檢視/已購買演演算法的公式](assets/formula.png)

則專案B不應與專案A一起建議。已提供此對數似然比相似度計算的完整詳細資料 [在此PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf).

實際演演算法實施的邏輯流程如下圖所示：

![已檢視/已購買演演算法的示意圖](assets/diagram1.png)

這些步驟的詳細資訊如下：

* **輸入資料**：行為資料，形式為當您執行以下動作時收集的訪客檢視和購買 [實作Target](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} or from [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **模型訓練**：

   * **資料清理和取樣**：針對具有N天回顧的演演算法，會先篩選行為資料，以僅包含這N天的資料。 然後會套用收集規則和全域排除，以移除任何不應建議使用的專案。 最後，任何與1,000個以上專案互動的訪客，其使用資料取樣為僅1,000個專案。
   * **專案相似度計算**：此為核心計算步驟：計算所有候選專案配對之間的對數似然比相似度，並依此相似度分數排名專案配對。
   * **離線篩選**：最後，套用任何進一步適用的動態篩選器（例如動態類別排除）。 在此步驟後，預先計算的建議會快取至全域以供提供。

* **模型服務**：Recommendations內容傳送自 [!DNL Target]的 [全域「邊緣」網路](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934). 向發出mbox請求時 [!DNL Target] 而且我們已決定應將Recommendations內容傳送至頁面，提供適當的要求 [專案索引鍵](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys) 針對recommendations演演算法，會從請求中剖析，或從使用者設定檔中查詢，然後用於擷取在先前步驟中運算的建議。 此時會在適當的時間之前，套用其他動態篩選器 [設計](/help/main/c-recommendations/c-design-overview/create-design.md) 已呈現。

## 內容相似度

包含的演演算法：

* [!UICONTROL 具有類似屬性的專案]

在此型別的演演算法中，如果兩個專案的名稱和文字說明在語義上相似，則會視為相關。 與大多數必須使用行為資料來源的建議演演算法不同，內容相似度演演算法會使用產品目錄中的中繼資料來衍生專案之間的相似度。 [!DNL Target] 因此，能夠在所謂的「冷啟動」情境中推動建議，這種情境中未收集到任何行為資料(例如，在 [!DNL Target] 活動)。

雖然模型服務與內容傳遞方面屬於 [!DNL Target]的內容相似度演演算法與其他基於專案的演演算法相同，模型訓練步驟截然不同，並涉及一系列自然語言處理和預先處理步驟，如下圖所示。 相似度計算的核心是使用修改過的tf-idf向量的餘弦相似度，這些向量代表目錄中的每個專案。

![顯示內容相似度程式流程的圖表](assets/diagram2.png)

這些步驟的詳細資訊如下：

* **輸入資料**：如先前所述，此演演算法完全根據目錄資料(擷取至 [!DNL Target] 透過 [目錄摘要、實體API或來自頁面上的更新](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}.

* **模型訓練**：

   * **屬性擷取**：套用一般靜態篩選器、目錄規則和全域排除後，此演演算法會從實體結構中擷取相關文字欄位。 [!DNL Target] 自動使用實體屬性中的名稱、訊息和類別欄位，並嘗試從自訂擷取任何字串欄位 [實體屬性](/help/main/c-recommendations/c-products/entity-attributes.md). 此程式可透過確保該欄位的大多數值都不可剖析為數字、日期或布林值來完成。
   * **詞幹和停用字移除**：如需更精確的文字相似度比對，請謹慎移除不會明顯改變專案含義（例如「was」、「is」、「and」等）的非常常見的「stop」字詞。 同樣地，詞幹是指將尾碼不同的字詞減少到其根字詞的過程，根字詞具有相同的含義（例如，「connect」、「connecting」和「connection」都擁有相同的根字詞：「connect」）。 [!DNL Target] 使用Snowball詞幹分析器。 [!DNL Target] 首先執行自動語言偵測，最多可以刪除50種語言和18種語言的詞幹。
   * **n元語法建立**：在先前步驟後，每個字詞都會被視為代號。 將權杖的連續序列組合成單一權杖的過程稱為n元語法建立。 [!DNL Target]的演演算法最多可考慮2克。
   * **tf-idf計算**：下一個步驟涉及建立tf-idf向量，以反映專案說明中權杖的相對重要性。 對於專案i中的每個Token/詞語t，在目錄D中使用 |D|個專案，會先計算字詞頻率TF(t， i) （字詞出現在專案i中的次數），以及檔案頻率DF(t， D)。 實質上，代號存在的專案數量。 則tf-idf測量為

      ![顯示tf-idf測量值的公式](assets/formula2.png)

      [!DNL Target] 使用Apache Spark的 *tf-idf* 功能化實作，在幕後將每個權杖雜湊至一個218個權杖的空間。 在此步驟中，也會套用客戶指定的屬性增加和埋葬，方法是根據 [條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

   * **專案相似度計算**：最終的專案相似度計算會使用近似的餘弦相似度來完成。 針對兩個專案， *A* 和 *B*，使用向量tA和tB，餘弦相似度的定義如下：

      ![顯示專案相似度計算的公式](assets/formula3.png)

      為避免所有N x N個專案之間的計算相似度過於複雜， *tf-idf* 向量被截斷以僅包含其最大的500個專案，然後使用此截斷的向量表示來計算專案之間的餘弦相似度。 與其他近似最近鄰(ANN)技術（例如區域性敏感雜湊技術）相比，這種方法對於稀疏向量相似度計算更具魯棒性。

   * **模型服務**：此程式與上一節所述的專案 — 專案共同篩選技術相同。

## 多索引鍵建議

演演算法包括：

* 購物車型建議
* [!UICONTROL 為您推薦]

最近新增至 [!DNL Target] 建議演演算法套件包括 [!UICONTROL 為您推薦] 以及一系列購物車型建議演演算法。 這兩種演演算法都使用協同篩選技術來形成個別專案型建議。 然後，在服務時間，使用者的瀏覽歷史記錄中有多個專案(例如 [!UICONTROL 為您推薦])，或使用者的目前購物車（適用於購物車型建議）來擷取這些專案型建議，然後合併以形成建議的最終清單。 請注意，存在多種個人化推薦演演算法。 選擇多索引鍵演演算法意味著，訪客擁有任何瀏覽記錄後，即可立即使用建議，而建議可以更新，以回應最新的訪客行為。

這些演演算法以「以專案為基礎的建議」區段中說明的基本共同篩選技術為基礎，但也包含超引數調整，以確定專案之間的最佳相似性量度。 演演算法會依時間順序分割每個使用者的行為資料，並在嘗試預測使用者稍後會檢視或購買的專案時，針對較早的資料培訓推薦模型。 產生最佳化的相似性量度 [平均平均精確度](然後選擇https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)。

模型訓練和評分步驟的邏輯如下圖所示：

![顯示模型訓練和評分步驟邏輯的圖表](assets/diagram3.png)

這些步驟的詳細資訊如下：

* **輸入資料**：這等同於專案 — 專案協同篩選(CF)方法。 [!UICONTROL 兩者都為您推薦] 和購物車型演演算法會使用行為資料，其形式為當您執行以下動作時收集的使用者檢視和購買 [實作Target](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} or from [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **模型訓練**：

   * **資料清理和取樣**：這再次與合作篩選方法相同，後者會套用回顧期間將行為資料篩選至適當的日期範圍，然後套用目錄規則和全域排除。 與1,000多個專案互動的訪客只會考量其最近1,000個使用量。
   * **訓練測試分割**：對每個使用者的使用量執行時間順序分割，將其使用量的前80%分配給訓練資料，其餘20%分配給測試資料。
   * **專案相似度模型訓練**：核心專案相似度計算針對以下專案而有所不同： [!UICONTROL 為您推薦] 和購物車型演演算法（以建構候選專案向量的方式）。 對象 [!UICONTROL 為您推薦]，專案向量具有維度NUsers，其中每個專案都代表該使用者對該專案的隱含評等總和 — 購買專案的權重為該專案檢視次數的2倍。 對於Cart-Based Recommendations，專案向量具有二進位專案；如果只考慮工作階段內的行為，則每個工作階段都會有一個新專案。 否則，此專案向量中會有每個訪客的專案。

   訓練步驟會計算數種型別的向量相似度： LLR相似度([在此討論](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf))、餘弦相似度（先前定義）和標準化的L2相似度(定義為：

   ![顯示訓練計算的公式](assets/formula4.png)

   * **專案相似度模型評估**：模型評估是透過採用上一步驟中產生的建議並對測試資料集做出預測來完成。 透過在測試資料集中依時間順序排序每個使用者的專案使用情況，然後針對排序的專案子集提出100個建議，以嘗試預測後續的檢視和購買，來模擬線上評分階段。 資訊擷取量度， [平均平均精確度](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval))可用來評估這些建議的品質。 此量度會考量建議的順序，並偏向建議清單中排名較高的相關專案，這是排名系統的重要屬性。
   * **模型選擇**：離線評估後，會選取具有最高平均平均精確度的模型，並為其計算所有個別專案建議。
   * **離線篩選**：模型訓練的最後階段是應用任何適用的動態篩選器。 在此步驟後，預先計算的建議會快取至全域以供提供。


* **模型服務**：與先前提供建議的演演算法不同，這類演演算法涉及指定要擷取的單一索引鍵，然後套用商業規則， [!UICONTROL 為您推薦] 和Cart型演演算法會採用更複雜的執行階段程式。

   * **多索引鍵擷取和合併**：針對購物車型建議，購物車中傳遞的最多10個專案會視為擷取的索引鍵，而來自每個專案的建議會平均加權。 對象 [!UICONTROL 為您推薦]，最多前五個不重複檢視的專案和前五個不重複購買的專案會視為擷取的索引鍵，而來自購買專案的建議權重會比來自已檢視專案的建議權重兩倍。 合併建議時，如果某個專案出現在多個個別建議清單中，則會新增其加權相似度分數。 此階段的最終建議清單是重新加權的合併建議清單，依遞減順序排列。
   * **篩選**：接下來，會套用篩選規則（例如移除先前檢視和/或購買的專案）以及其他動態商業規則。

下圖說明這些程式，其中訪客已檢視專案A並購買專案B。系統會使用每個專案標籤下方顯示的離線相似度分數來擷取個別建議。 擷取後，建議會與加權相似度分數相加。 最後，在客戶已指定必須篩選掉先前檢視和購買專案的案例中，篩選步驟會從建議清單中移除專案A和B。

![顯示多鍵演演算法處理程式的圖表](assets/diagram4.png)

## 基於人氣

演演算法包括：

* [!UICONTROL 整個網站檢視次數最多]
* [!UICONTROL 依類別檢視次數最多]
* [!UICONTROL 依專案屬性檢視次數最多]
* [!UICONTROL 全網站最暢銷商品]
* [!UICONTROL 依類別排名的最暢銷商品]
* [!UICONTROL 依專案屬性排名的最暢銷商品]

[!DNL Target] 針對網站中檢視次數最多的專案以及最暢銷的專案，或依專案屬性或類別劃分的專案，提供人氣型演演算法。 基於人氣的演演算法會根據在指定時間範圍內檢視或購買該專案的工作階段數量來排名專案。

所有這些演演算法都會結合彙總的行為資料，也就是以每小時和每日解析度來記錄檢視和購買專案的工作階段總數。 然後，個別演演算法會針對客戶設定的回顧期間，尋找檢視次數最多或購買次數最多的專案。

個別演演算法的細微差別如下：

* [!UICONTROL 整個網站檢視次數最多] 和 [!UICONTROL 全網站最暢銷商品] 依已檢視或購買這些專案的工作階段彙總計數排名專案。 輸出是建議專案的單一（無索引鍵）清單。
* 依類別/專案屬性檢視次數最多/最暢銷商品是建議，其中專案會依檢視或購買這些專案的工作階段彙總計數排序，但會依專案類別或特定專案屬性分組。 輸出是建議專案清單，以類別值或專案屬性值作為索引鍵。

## 最近檢視的專案

「最近檢視的」建議演演算法允許在工作階段中個人化建議。 此演演算法不需要離線「模型訓練」。 而是 [!DNL Target] 使用唯一 [訪客設定檔](/help/main/c-target/c-visitor-profile/visitor-profile.md) 維護在指定工作階段中檢視過且可在Recommendations活動中顯示這些專案的執行中專案清單。 如此可讓您即時更新推薦和下一頁個人化。

## 自訂條件

自訂條件允許客戶 [上傳自己的建議至 [!DNL Target]](/help/main/c-recommendations/c-algorithms/recommendations-csv.md)，提供重要的彈性，並允許「自攜」功能。 自訂條件會取代的「離線訓練」部分 [!UICONTROL 基於專案] recommendations，但其行為類似於線上內容傳送階段中的專案型建議演演算法，也就是使用單一索引鍵來擷取建議，然後套用商業規則/篩選器。
