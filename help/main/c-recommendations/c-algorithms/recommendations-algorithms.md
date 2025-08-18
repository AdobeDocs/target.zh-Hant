---
keywords: 建議演演算法；模型訓練；模型服務；內容傳送；專案型；使用者型；人氣型；購物車型；自訂條件
description: 瞭解 [!DNL Target Recommendations]中使用的演演算法，包括模型訓練和模型服務。
title: 我可以在何處瞭解Target建議演演算法背後的科學？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '2739'
ht-degree: 0%

---

# Target 推薦演算法背後的科學

[!DNL Adobe Target Recommendations]中所使用演演算法的深入說明，包括模型訓練的邏輯和數學細節，以及模型服務的程式。

模型訓練是[!DNL Adobe Target]學習演演算法產生建議的程式。 模型服務是[!DNL Target]如何提供建議給您的網站訪客（也稱為內容傳遞）。

[!DNL Target]在[!DNL Recommendations]中包含下列廣泛的演演算法型別：

* **以專案為基礎的演演算法**：包含遵循下列邏輯的演演算法：「檢視/購買過此專案的人員也檢視/購買了這些專案」。 這些演演算法會分組在傘狀字詞「專案 — 專案協同篩選」以及[!UICONTROL Items with Similar Attributes]演演算法下。

* **以使用者為基礎的演演算法**：包含[!UICONTROL Recently Viewed]和[!UICONTROL Recommended for You]演演算法。

* **以熱門程度為基礎的演演算法**：包含會傳回網站中檢視次數最多或購買次數最多的專案，或依類別或專案屬性檢視次數最多或購買次數最多的專案的演演算法。

* **購物車型演演算法**：包含多專案型建議，其邏輯為「已檢視/購買這些專案的使用者，也已檢視/購買這些專案」。

* **自訂條件**：包含以上傳至[!DNL Target]的自訂檔案為基礎的建議。

>[!NOTE]
>
>如需每個演演算法型別和個別演演算法的詳細一般資訊，請參閱[讓建議以建議索引鍵為依據](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

以上列出的許多演演算法都是以一或多個索引鍵的存在為前提。 這些索引鍵會在內容傳送時（產生建議時）用來擷取類似專案。 客戶指定的索引鍵可包含某人正在檢視的目前專案、最後一個已檢視或購買的專案、最常檢視的專案、目前類別，或該訪客最喜愛的類別。 其他演演算法（例如購物車型或使用者型建議）則使用隱含索引鍵（客戶無法設定）。 如需詳細資訊，請參閱&#x200B;*讓建議以建議金鑰為依據*&#x200B;中的[建議金鑰](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys)。 但是請注意，這些鍵值僅在模型服務時間（內容傳送）中相關。 這些索引鍵不會影響「離線」或模型訓練時間邏輯。

以下各節會以與上述演演算法型別稍微不同的方式將演演算法分組。 以下分組是根據模型訓練邏輯的相似性。

## 料號 — 料號協同篩選

演演算法包括：

* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

料號 — 料號協同篩選建議演演算法所根據的理念是，您應使用許多使用者的行為模式（因此是協同合作），為指定料號提供有用的建議（例如，篩選可能要建議的料號目錄）。 雖然有許多不同的演演算法屬於[協同篩選](https://en.wikipedia.org/wiki/Collaborative_filtering)的一般傘狀結構，但這些演演算法通常都會使用行為資料來源作為輸入。 在[!DNL Target Recommendations]中，這些輸入是使用者對專案的唯一檢視和購買。

針對「檢視/購買此專案的使用者也檢視/購買這些專案」演演算法，目標是計算所有專案配對之間的相似度(A，B)。 接著，系統會針對指定專案A，依其相似度s(A，B)排序排名最前的建議。

這種相似性的一個範例是專案之間的共同發生：購買兩個專案的使用者人數的簡單計數。 雖然此量度直覺式偏好，但偏向於推薦熱門專案，因此這種量度並不實際。 例如，如果在retailer的雜貨店大多數人購買麵包，則麵包會與所有專案具有高度的共生性，但這不一定是好的建議。 [!DNL Target]改為使用更複雜的相似性量度，稱為對數似然比(LLR)。 如果兩個專案（A和B）同時發生的機率與其不同時發生的機率非常不同，則此數量會很大。 如需具體資訊，請考慮[!UICONTROL People Who Viewed This, Bought That]演演算法的情況。 購買B的可能性為&#x200B;*not*&#x200B;時，LLR相似度會很高，這和某人是否檢視A無關。

例如，若

已檢視/已購買演演算法的![公式](assets/formula.png)

那麼專案B不應與專案A一起建議。此PDF[中提供了此對數似然比相似度計算的完整詳細資料](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)。

實際演演算法實施的邏輯流程如下圖所示：

已檢視/已購買演演算法的![示意圖](assets/diagram1.png)

這些步驟的詳細資訊如下：

* **輸入資料**：行為資料，其形式為當您[實作Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}或從[Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}收集的訪客檢視和購買。

* **模型訓練**：

   * **資料清理和取樣**：對於具有N天回顧的演演算法，會先篩選行為資料以僅包含這N天的資料。 收集規則和全域排除會套用，以移除任何不應建議使用的專案。 最後，任何與1,000個以上專案互動的訪客，其使用資料取樣為僅1,000個專案。
   * **專案相似度計算**：這是核心計算步驟：計算所有候選專案配對之間的對數似然比相似度，並依此相似度分數將專案配對排名。
   * **離線篩選**：最後，會套用任何進一步適用的動態篩選（例如，動態類別排除）。 在此步驟後，預先計算的建議會快取至全域，以便提供。

* **模型服務**：建議內容是從[!DNL Target]的[全域「Edge」網路](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934)傳遞。 當向[!DNL Target]發出mbox要求，並判定建議內容應傳送至頁面時，會從要求中剖析建議演演算法的適當[專案索引鍵](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys)要求，或從使用者設定檔中查詢，然後用來擷取在先前步驟中計算的建議。 此時在呈現適當的[設計](/help/main/c-recommendations/c-design-overview/create-design.md)之前，會套用其他動態篩選器。

## 內容相似度

包含的演演算法：

* [!UICONTROL Items with Similar Attributes]

在此型別的演演算法中，如果兩個專案的名稱和文字說明在語義上相似，則會將其視為相關。 與大多數必須使用行為資料來源的Recommendations演演算法不同，內容相似度演演算法使用產品目錄中的中繼資料來匯出專案之間的相似度。 因此，[!DNL Target]能夠在所謂的「冷啟動」情境中推動建議，其中未收集任何行為資料（例如，在[!DNL Target]活動開始時）。

雖然[!DNL Target]的內容相似度演演算法的模型服務和內容傳遞方面與其他專案型演演算法相同，但模型訓練步驟卻大不相同，而且涉及一系列自然語言處理和前置處理步驟，如下圖所示。 相似度計算的核心是使用已修改的tf-idf向量餘弦相似度，這些向量代表目錄中的每個專案。

![顯示內容相似度程式流程的圖表](assets/diagram2.png)

這些步驟的詳細資訊如下：

* **輸入資料**：如前所述，此演演算法完全以目錄資料為基礎(透過[!DNL Target]目錄摘要、實體API或頁面上的更新擷取至[。](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}

* **模型訓練**：

   * **屬性擷取**：在應用一般靜態篩選器、目錄規則和全域排除之後，此演演算法會從實體結構描述中擷取相關的文字欄位。 [!DNL Target]會自動使用來自實體屬性的名稱、訊息和類別欄位，並嘗試從自訂[實體屬性](/help/main/c-recommendations/c-products/entity-attributes.md)擷取任何字串欄位。 此程式可透過確保該欄位的大多數值都不可剖析為數字、日期或布林值來完成。
   * **刪除詞幹與停用詞**：若要更精確的文字相似度比對，請謹慎移除不會大幅改變專案含義的非常常見的「停用詞」（例如，「was」、「is」、「and」等）。 同樣地，詞幹是指將尾碼不同的字詞還原為根字詞的過程，根字詞具有相同的含義（例如，「connect」、「connecting」和「connection」都擁有相同的根字詞：「connect」）。 [!DNL Target]使用Snowball字乾器。 [!DNL Target]會先執行自動語言偵測，最多可以移除50種語言的stop單字，並為18種語言撰寫字根。
   * **n字元建立**：在前面的步驟之後，每個字都會被視為語彙基元。 將權杖的連續序列組合成單一權杖的過程稱為n字元組建立。 [!DNL Target]的演演算法最多可考慮2克。
   * **tf-idf計算**：下一個步驟涉及建立tf-idf向量，以反映專案描述中權杖的相對重要性。 對於專案i中的每個Token/詞語t，在目錄D中使用 |D| 專案，會先計算字詞頻率TF(t， i) （字詞出現在專案i中的次數），以及檔案頻率DF(t， D)。 實質上，代號存在的專案數。 則tf-idf測量為

     ![顯示tf-idf量值的公式](assets/formula2.png)

     [!DNL Target]使用Apache Spark的&#x200B;*tf-idf*&#x200B;功能化實作，這種實作會將每個權杖雜湊至218個權杖的空間。 在此步驟中，也會套用客戶指定的屬性提升與埋藏，方法是根據[條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)中指定的設定，調整每個向量中的字詞頻率。

   * **專案相似度計算**：使用近似餘弦相似度完成最終專案相似度計算。 對於具有向量tA和tB的兩個專案&#x200B;*A*&#x200B;和&#x200B;*B*，餘弦相似度定義為：

     ![顯示專案相似度計算的公式](assets/formula3.png)

     為了避免計算所有N x N專案之間相似性的重大複雜性，*tf-idf*&#x200B;向量會被截斷，以僅包含其最大的500個專案，然後使用此截斷向量表示來計算專案之間的餘弦相似度。 與其他近似最近鄰(ANN)技術（例如區域性敏感雜湊技術）相比，此方法對於稀疏向量相似度計算更具穩健性。

   * **模型服務**：此程式與上一節中說明的專案 — 專案協同篩選技術相同。

## 多鍵建議

演演算法包括：

* 購物車型建議
* [!UICONTROL Recommended For You]

[!DNL Target]套裝建議演演算法的最新新增專案為[!UICONTROL Recommended For You]和一系列購物車型建議演演算法。 這兩種演演算法都使用合作篩選技術來形成個別專案型建議。 接著，在服務時間，使用者的瀏覽記錄（針對[!UICONTROL Recommended For You]）或使用者目前的購物車（針對購物車式建議）中的多個專案會用來擷取這些專案式建議，然後合併以形成最終建議清單。 請注意，存在許多風格個人化推薦演演算法。 多鍵演演算法的選擇表示訪客擁有任何瀏覽歷程記錄後，即可立即使用建議，而建議可以更新，以回應最新的訪客行為。

這些演演算法以「以專案為基礎的建議」區段中說明的基本共同篩選技術為基礎，但也合併超引數調整以確定專案之間的最佳相似度量度。 演演算法會依時間順序對每個使用者的行為資料執行分割，並在較早的資料上訓練建議模型，同時嘗試預測使用者稍後會檢視或購買的專案。 產生最佳[平均平均精確度] (https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval))的相似性量度。

模型訓練和評分步驟的邏輯如下圖所示：

![顯示模型訓練和評分步驟邏輯的圖表](assets/diagram3.png)

這些步驟的詳細資訊如下：

* **輸入資料**：這與專案 — 專案協同篩選(CF)方法相同。 [!UICONTROL Both Recommended For You]和購物車型演演算法使用行為資料，其形式為當您[實作Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}或從[Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}收集的使用者檢視和購買。

* **模型訓練**：

   * **資料清理和取樣**：這再次與合作篩選方法相同，後者會套用回顧視窗，將行為資料篩選至適當的日期範圍，然後套用目錄規則和全域排除。 與超過1,000個專案互動的訪客只會考慮其最近的1,000個使用例項。
   * **訓練測試分割**：對每個使用者執行使用量按時間順序分割，將其使用量的前80%配置給訓練資料，其餘20%配置給測試資料。
   * **專案相似度模型訓練**：核心專案相似度計算對於[!UICONTROL Recommended For You]和購物車型演演算法而言在建構候選專案向量方式上有所不同。 對於[!UICONTROL Recommended For You]，專案向量具有維度NUsers，其中每個專案都代表該專案使用者的隱含評等總和，購買專案的權重是專案檢視的2倍。 對於購物車型建議，專案向量具有二進位專案；如果只考慮工作階段內的行為，則每個工作階段都會有新專案。 否則，此專案向量中會有每個訪客的專案。

  訓練步驟會計算數種向量相似度： LLR相似度（[在此討論](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)）、餘弦相似度（先前定義）以及標準化的L2相似度，定義如下：

  ![顯示訓練計算的公式](assets/formula4.png)

   * **專案相似度模型評估**：模型評估是透過採用先前步驟中產生的建議並對測試資料集進行預測來完成。 模擬線上評分階段的方法是，在測試資料集中依時間順序排序每個使用者的專案使用情形，然後對排序的專案子集提出100個建議，以嘗試預測後續的檢視和購買。 資訊擷取量度[平均平均精確度]&#x200B;(https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval))可用來評估這些建議的品質。 此量度會考量建議的順序，並偏向建議清單中排名較高的相關專案，這是排名系統的重要屬性。
   * **模型選擇**：離線評估之後，會選取具有最高平均精確度的模型，並為其計算所有個別專案建議。
   * **離線篩選**：模型訓練的最後階段是套用任何適用的動態篩選。 在此步驟後，預先計算的建議會快取至全域，以便提供。

* **模型服務**：與先前提供建議的演演算法不同，在提供建議時，先要指定單一索引鍵進行擷取，接著再套用商業規則，[!UICONTROL Recommended for You]和Cart-Based演演算法會採用更複雜的執行階段程式。

   * **多重金鑰擷取與合併**：對於購物車式建議，最多會將購物車中傳遞的10個專案視為擷取的金鑰，且每個專案的建議會平均加權。 對於[!UICONTROL Recommended for You]，最多會將最近五個不重複檢視的專案和最近五個不重複購買的專案視為擷取的索引鍵，其中來自購買專案的建議權重是來自檢視專案的建議的兩倍。 合併建議時，如果某個專案出現在多個個別建議清單中，則會新增其加權相似度分數。 此階段的最終建議清單是重新加權的合併建議清單，依遞減順序排列。
   * **篩選**：接著，套用篩選規則，例如移除先前檢視和/或購買的專案，以及其他動態商業規則。

下圖說明這些程式，其中訪客已檢視專案A並購買專案B。系統會使用每個專案標籤下方顯示的離線相似度分數來擷取個別建議。 擷取後，建議會與加權相似度分數彙總合併。 最後，在客戶已指定必須篩選掉先前檢視和購買專案的情境中，篩選步驟會從建議清單中移除專案A和B。

![顯示多重金鑰演演算法處理的圖表](assets/diagram4.png)

## 基於人氣

演演算法包括：

* [!UICONTROL Most Viewed Across the Site]
* [!UICONTROL Most Viewed by Category]
* [!UICONTROL Most Viewed by Item Attribute]
* [!UICONTROL Top Sellers Across the Site]
* [!UICONTROL Top Sellers by Category]
* [!UICONTROL Top Sellers by Item Attribute]

[!DNL Target]針對檢視次數最多的專案，以及整個網站或依專案屬性或類別劃分的最暢銷專案，提供人氣型演演算法。 基於人氣的演演算法會根據在指定時間範圍內檢視或購買該專案的工作階段數來排名專案。

所有這些演演算法都會結合彙總的行為資料，也就是以每小時和每日解析度來記錄檢視和購買專案的工作階段總數。 接著，個別演演算法會針對客戶設定的回顧期間，尋找檢視次數最多或購買次數最多的專案。

個別演演算法的細微差別如下：

* [!UICONTROL Most Viewed Across the Site]和[!UICONTROL Top Sellers Across the Site]會依已檢視或購買這些專案的工作階段彙總計數來排名專案。 輸出是建議專案的單一（無索引鍵）清單。
* 依類別/專案屬性檢視次數最多/最暢銷商品是建議，其中專案會依檢視或購買這些專案的工作階段彙總計數排序，但會依專案類別或特定專案屬性分組。 輸出是建議專案清單，以類別值或專案屬性值作為索引鍵。

## 最近檢視的專案

「最近檢視的」建議演演算法允許在工作階段中個人化建議。 此演演算法不需要離線「模型訓練」。 相反，[!DNL Target]會使用唯一的[訪客設定檔](/help/main/c-target/c-visitor-profile/visitor-profile.md)來維護在指定工作階段中檢視過的專案執行中清單，並且可以在建議活動中呈現這些專案。 如此可讓您即時更新推薦內容並取得下一頁個人化。

## 自訂條件

自訂條件可讓客戶[將自己的建議 [!DNL Target]](/help/main/c-recommendations/c-algorithms/recommendations-csv.md)上傳至，提供重要的彈性並允許「自備模型」功能。 自訂條件取代了[!UICONTROL Item-Based]個建議的「離線訓練」部分，但線上上內容傳遞階段中的行為類似於「專案式」建議演演算法，也就是使用單一索引鍵來擷取建議，然後套用商業規則/篩選器。
