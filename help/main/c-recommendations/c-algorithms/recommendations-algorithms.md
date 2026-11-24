---
keywords: 建議演演算法；模型訓練；模型服務；內容傳送；專案型；使用者型；人氣型；購物車型；自訂條件
description: 瞭解[!DNL Target Recommendations]中使用的演演算法，包括模型訓練和模型服務。
title: Target 推薦演算法背後的科學
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
TQID: 'https://experienceleague.adobe.com/goYsorjFUweT4Aw0XvzQSeiqON7orDcLntZaJliqGl4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '2755'
ht-degree: 0%
---
# Target 推薦演算法背後的科學 {#recommendations-algorithms}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解[!DNL Adobe Target Recommendations]中的演演算法如何運作，包括模型訓練和模型服務的邏輯和數學細節。

>[!ENDSHADEBOX]

模型訓練是[!DNL Adobe Target]學習演演算法產生建議的程式。 模型服務（也稱為內容傳送）是[!DNL Target]將這些建議傳送給網站訪客的方式。

[!DNL Target]在[!DNL Recommendations]中提供下列型別的演演算法：

* **以專案為基礎的演演算法**：遵循邏輯「檢視/購買此專案的人員也檢視/購買這些專案」。 這些演演算法會分組在字詞「專案 — 專案」協同篩選下。 此型別也包含具有類似屬性的&#x200B;**[!UICONTROL 專案]**&#x200B;演演算法。

* **以使用者為基礎的演演算法**：包含&#x200B;**[!UICONTROL 最近檢視的專案]**&#x200B;和&#x200B;**[!UICONTROL 為您推薦的演演算法]**。

* **基於人氣的演演算法**：傳回整個網站中檢視次數最多或購買次數最多的專案，或依類別或專案屬性傳回。

* **購物車型演演算法**：使用邏輯「已檢視/購買這些專案的人也已檢視/購買這些專案」提供多專案建議。

* **自訂條件**：使用上載至[!DNL Target]的自訂檔案作為建議的來源。

如需每個演演算法型別及其演演算法的詳細資訊，請參閱[讓建議以建議索引鍵為依據](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

許多演演算法依賴一或多個索引鍵，[!DNL Target]在內容傳遞時（產生建議時）使用這些索引鍵來擷取類似專案。 客戶指定的索引鍵可以是訪客正在檢視的目前專案、最後檢視或購買的專案、檢視次數最多的專案、目前類別，或訪客最喜愛的類別。 其他演演算法（例如購物車演演算法和以使用者為基礎的演演算法）則使用客戶無法設定的隱含索引鍵。 如需詳細資訊，請參閱[建議金鑰](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys)。

金鑰僅適用於模型服務時間（內容傳送）。 它們不會影響離線模型訓練邏輯。

以下部分會依照其模型訓練邏輯的相似性來分組演演算法，因此這些群組與上述型別稍有不同。

## 料號 — 料號協同篩選

演演算法包括：

* **[!UICONTROL 瀏覽過此專案、也瀏覽了其他專案的使用者]**
* **[!UICONTROL 瀏覽過此專案、但購買了其他專案的使用者]**
* **[!UICONTROL 購買了此專案、也購買了其他專案的使用者]**

料號 — 料號協同篩選演演算法會使用許多使用者的行為模式（因此是協同合作），來建議與指定料號相關的料號，這會篩選可能料號的目錄。 許多不同的演演算法屬於共同篩選的一般傘狀結構，而且所有演演算法都使用行為資料作為輸入。 在[!DNL Target Recommendations]中，這些輸入是使用者對專案的唯一檢視和購買。

針對「檢視/購買此專案的人員也檢視/購買這些專案」演演算法，目標是計算所有專案配對之間的相似度(A，B)。 對於指定的專案A，排名最前的建議是依相似度s(A，B)排序的專案。

專案之間的共同發生是類似性的一個範例：購買兩個專案的使用者計數。 此量度直覺式但天真，因為偏向於推薦熱門專案。 例如，在大多數人購買麵包的retailer雜貨店，麵包與所有專案的高共現率，但不一定是好的建議。 [!DNL Target]改為使用對數似然比(LLR)。 當兩個專案（A和B）同時發生的機率與其不同時發生的機率非常不同時，此數量就會很大。 例如，使用&#x200B;**[!UICONTROL 瀏覽過此專案、也購買了那]**&#x200B;個演演算法的使用者，當某人購買B的可能性是&#x200B;*而非*&#x200B;時，LLR相似度就會很高，這與其是否瀏覽過A無關。

若有下列保留，則不建議將料號B與料號A搭配使用：

已檢視/已購買演演算法的![公式](/help/main/c-recommendations/c-algorithms/assets/formula.png)

如需對數似然比相似度計算的完整詳細資料，請參閱[此PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)。

下列示意圖顯示演演算法實施的邏輯流程：

![已檢視/已購買演演算法的示意圖](/help/main/c-recommendations/c-algorithms/assets/diagram1.png)

步驟如下：

* **輸入資料**：當您[實作Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}或從[Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}收集之訪客檢視和購買形式的行為資料。

* **模型訓練**：

  * **資料清理和取樣**：對於具有N天回顧的演演算法，會先篩選行為資料以僅包含這N天的資料。 收集規則和全域排除會套用，以移除任何不應建議使用的專案。 最後，任何與1,000多個專案互動的訪客的使用情況資料會取樣至1,000個專案。
  * **專案相似度計算**：核心計算步驟。 [!DNL Target]會計算所有候選專案配對之間的對數似然比相似度，並依據此分數排名配對。
  * **離線篩選**：套用任何進一步適用的動態篩選（例如，動態類別排除）。 接著，預先計算的建議會快取至全域，以便伺服。

* **模型服務**：建議是從[!DNL Target]的[全域「Edge」網路](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934)傳遞。 向[!DNL Target]發出mbox要求並判定建議內容應傳送至頁面時，會從要求中剖析演演算法所需的[專案索引鍵](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys)，或從訪客設定檔中查詢。 [!DNL Target]使用此索引鍵來擷取先前步驟中計算的建議、套用進一步的動態篩選器，然後轉譯適當的[設計](/help/main/c-recommendations/c-design-overview/create-design.md)。

## 內容相似度

包含的演演算法：

* **[!UICONTROL 具有類似屬性的專案]**

使用此演演算法時，如果兩個專案的名稱和文字說明在語義上類似，則會將兩個專案相關聯。 與大多數需要行為資料的建議演演算法不同，內容相似度演演算法從產品目錄中繼資料中衍生出專案之間的相似度。 因此，[!DNL Target]可以在所謂的「冷啟動」情境中提出建議，其中尚未收集行為資料（例如，[!DNL Target]活動開始時）。

內容相似度演演算法的模型服務和內容傳遞與其他基於專案的演演算法相同。 模型訓練非常不同：它包含一系列自然語言處理和前置處理步驟，如下圖所示。 相似度計算的核心是修改過的tf-idf向量餘弦相似度，這些向量代表目錄中的每個專案。

![顯示內容相似度程式流程的圖表](/help/main/c-recommendations/c-algorithms/assets/diagram2.png)

步驟如下：

* **輸入資料**：此演演算法僅使用目錄資料，透過[目錄摘要、實體API或頁面上的更新擷取到[!DNL Target]。](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}

* **模型訓練**：

  * **屬性擷取**：套用靜態篩選、目錄規則和全域排除後，演演算法會從實體結構描述中擷取相關的文字欄位。 [!DNL Target]會自動使用實體屬性的名稱、訊息和類別欄位。 它也會嘗試從自訂[實體屬性](/help/main/c-recommendations/c-products/entity-attributes.md)擷取任何字串欄位。 當欄位的大部分值無法剖析為數字、日期或布林值時，該欄位會被視為字串欄位。
  * **刪除詞幹和停用詞**：為了讓文字相似度比對更準確，[!DNL Target]會移除不會大幅改變專案含義的非常常見的「停用詞」（例如，「was」、「is」和「and」）。 詞幹會將尾碼不同的字詞減少為根字，其含義相同（例如，「connect」、「connecting」和「connection」都使用根字「connect」）。 [!DNL Target]使用Snowball字乾器。 它首先執行自動語言偵測，最多可以移除50種語言的停用詞，並為18種語言執行字乾處理。
  * **n字元建立**：在前面的步驟之後，每個字都會被視為語彙基元。 將權杖的連續序列組合成單一權杖稱為n字元組建立。 [!DNL Target]最多考慮2克。
  * **tf-idf計算**：下一個步驟會建立tf-idf向量，以反映專案描述中權杖的相對重要性。 對於專案i中的每個Token或詞語t，在目錄D中使用 |D|個專案，[!DNL Target]首先計算專案頻率TF(t， i)，這是專案出現在專案i中的次數，以及檔案頻率DF(t， D)，這是語彙基元存在的專案數。 然後tf-idf測量為：

    ![顯示tf-idf量值的公式](/help/main/c-recommendations/c-algorithms/assets/formula2.png)

    [!DNL Target]使用Apache Spark的&#x200B;*tf-idf*&#x200B;功能化實作，將每個權杖雜湊至2<sup>18</sup>個權杖的空間。 在此步驟中，也會套用[條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)中指定的屬性boosting和burying，方法是調整每個向量中的字詞頻率。

  * **專案相似度計算**：最終專案相似度是以近似餘弦相似度計算。 對於具有向量tA和tB的兩個專案&#x200B;*A*&#x200B;和&#x200B;*B*，餘弦相似度定義為：

    ![顯示專案相似度計算的公式](/help/main/c-recommendations/c-algorithms/assets/formula3.png)

    為了避免計算所有N x N專案之間相似度的複雜度很高，*tf-idf*&#x200B;向量會截斷為最大的500個專案，而專案之間的餘弦相似度會從此截斷表示法計算。 與其他近似最近鄰(ANN)技術（例如區域性敏感雜湊技術）相比，此方法在稀疏向量相似度計算上更穩健。

* **模型服務**：此程式與上一節中說明的料號專案協同篩選程式相同。

## 多鍵建議

演演算法包括：

* 購物車型建議
* **[!UICONTROL 為您推薦]**

**[!UICONTROL 為您推薦]**，購物車型演演算法使用協同篩選技術來形成個別專案型推薦。 在服務時間，多個專案會當作索引鍵來擷取這些專案型建議：訪客的瀏覽歷程記錄中的專案（針對&#x200B;**[!UICONTROL 已為您推薦]**）或訪客目前的購物車中的專案（針對購物車型建議）。 擷取的建議會合併成最終清單。 使用多鍵演演算法時，只要訪客有任何瀏覽記錄，建議就會可供使用，並會更新以反映最新的訪客行為。

這些演演算法以專案型建議區段中所述的合作篩選技術為基礎，也使用超引數調整來確定專案之間的最佳相似度量度。 演演算法會依時間順序分割每個使用者的行為資料，並在較早的資料上訓練建議模型，同時嘗試預測使用者稍後會檢視或購買的專案。 然後選擇具有最佳平均平均精確度的相似性量度。

下圖顯示模型訓練和評分步驟的邏輯：

![顯示模型訓練和評分步驟邏輯的圖表](/help/main/c-recommendations/c-algorithms/assets/diagram3.png)

步驟如下：

* **輸入資料**：與專案 — 專案協同篩選(CF)方法相同。 **[!UICONTROL 為您推薦的]**&#x200B;和購物車型演演算法都使用使用者檢視和購買形式的行為資料，這些資料是在您[實作Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}時或從[Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}收集的。

* **模型訓練**：

  * **資料清理和取樣**：與協同合作篩選方法相同。 回顧期間會將行為資料篩選至適當的日期範圍，然後套用目錄規則和全域排除。 如果訪客與1,000個以上的專案互動，則只會考量最近1,000個使用情況。
  * **訓練測試分割**：每個使用者的使用方式按時間順序分割。 前80%會分配給訓練資料，其餘20%則分配給測試資料。
  * **專案相似度模型訓練**：核心專案相似度計算在建構候選專案向量的方式上，在&#x200B;**[!UICONTROL 建議您]**&#x200B;和Cart-Based之間有所不同。 對於&#x200B;**[!UICONTROL Recommended for You]**，專案向量具有維度NUsers，每個專案都是使用者提供給專案的隱含評等總和。 購買的權重是檢視的2倍。 對於購物車型建議，專案向量會有二進位專案。 如果只考量工作階段內的行為，則每個工作階段都會有一個專案。 否則，每個訪客都會有一個專案。

    訓練步驟會計算數種型別的向量相似度： LLR相似度（[請參閱PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)）、餘弦相似度（先前定義）以及標準化的L2相似度，定義如下：

    ![顯示訓練計算的公式](/help/main/c-recommendations/c-algorithms/assets/formula4.png)

  * **專案相似度模型評估**：在上一步驟中產生的建議會透過在測試資料集上進行預測來進行評估。 透過按時間順序訂購測試資料集中每個使用者的專案使用情況，然後為訂購的專案子集提出100個建議以預測後續的檢視和購買，來模擬線上評分階段。 這些建議的品質是以「平均精確度」來評估，這是一種資訊擷取量度。 此量度會考量建議的順序，並偏向於清單中排名較高的相關專案，這是排名系統的重要屬性。
  * **模型選擇**：離線評估之後，會選取平均平均精確度最高的模型，並為其計算所有個別專案建議。
  * **離線篩選**：模型訓練的最後階段會套用任何適用的動態篩選。 接著，預先計算的建議會快取至全域，以便伺服。

* **模型服務**：不同於先前指定單一索引鍵進行擷取，然後套用商業規則的演演算法，**[!UICONTROL 建議您]**&#x200B;和Cart-Based使用更複雜的執行階段程式：

  * **多重金鑰擷取與合併**：對於購物車式建議，最多會將購物車中傳入的10個專案當作要擷取的金鑰，而每個金鑰中的建議會平均加權。 針對「**[!UICONTROL 給您的建議」]**，使用最近五個不重複檢視的專案和最近五個不重複購買的專案作為索引鍵，而且購買專案的建議權重是檢視專案的兩倍。 合併建議時，系統會新增出現在數個清單中的專案加權相似度分數。 結果會是重新加權的建議合併清單，依遞減順序排名。
  * **篩選**：接著會套用篩選規則，例如移除先前檢視或購買的專案，以及其他動態商業規則。

下圖說明檢視專案A及購買專案B的訪客的這些程式。系統會使用每個專案標籤下方顯示的離線相似度分數來擷取個別建議，然後與加權的相似度分數彙總在一起。 最後，當客戶已指定必須篩選掉先前檢視和購買的專案，則篩選步驟會從建議清單中移除專案A和B。

![顯示多重金鑰演演算法處理的圖表](/help/main/c-recommendations/c-algorithms/assets/diagram4.png)

## 基於人氣

演演算法包括：

* 整個網站檢視次數最多&#x200B;**&#x200B;**
* 依類別檢視次數最多&#x200B;**&#x200B;**
* **[!UICONTROL 檢視次數最多的專案屬性]**
* **[!UICONTROL 依輪廓屬性的檢視次數最多項目]**
* 整個網站&#x200B;**[!UICONTROL 最暢銷商品]**
* **[!UICONTROL 依類別排名的最暢銷商品]**
* **[!UICONTROL 依專案屬性的最暢銷商品]**
* **[!UICONTROL 依個人檔案屬性的最暢銷商品]**

[!DNL Target]為整個網站或依專案屬性或類別劃分的「檢視次數最多」的專案和「最暢銷」專案提供人氣型演演算法。 這些演演算法會根據在指定時間範圍內檢視或購買專案的工作階段數來排名專案。

所有這些演演算法都會結合彙總的行為資料，以每小時和每日解析度記錄檢視和購買專案的工作階段總數。 接著，每個演演算法會針對客戶設定的回顧期間，找出檢視次數最多或購買次數最多的專案。

演演算法的差異如下：

* **[!UICONTROL 整個網站檢視次數最多]**&#x200B;和整個網站最暢銷商品&#x200B;**[!UICONTROL 依工作階段總數（分別檢視或購買專案）排名專案]**。 輸出是建議專案的單一（無索引鍵）清單。
* 依類別或專案屬性檢視次數最多和最暢銷商品也會依彙總工作階段計數來訂購專案，但會依專案類別或特定專案屬性來分組專案。 輸出是建議專案清單，以類別或專案屬性的值作為索引鍵。
* **[!UICONTROL 依設定檔屬性檢視次數最多]**&#x200B;及&#x200B;**[!UICONTROL 依設定檔屬性最暢銷商品]**&#x200B;也會依彙總檢視或購買計數來排名專案，但會依訪客設定檔屬性（例如國家/地區、或會員層級）分組，而非專案屬性。 每個工作階段的計數會歸因於訪客在互動時持有的設定檔值，而不是歸因於專案的任何屬性。 結果是一組以該設定檔屬性的不同值作為關鍵字的建議清單。

## 最近檢視的專案

「最近檢視」的演演算法提供工作階段內個人化的建議。 它不需要離線模型訓練。 相反，[!DNL Target]會使用唯一的[訪客設定檔](/help/main/c-target/c-visitor-profile/visitor-profile.md)來維護工作階段中檢視之專案的執行中清單，並可在Recommendations活動中呈現這些專案。 如此可讓您即時更新推薦內容並取得下一頁個人化。

## 自訂條件

自訂條件可讓客戶[將自己的建議](/help/main/c-recommendations/c-algorithms/recommendations-csv.md)上傳至Target，以提供彈性並允許「自備模型」功能。 自訂條件取代了&#x200B;**[!UICONTROL 以專案為基礎的]**&#x200B;建議的離線訓練部分。 線上上內容傳遞期間，其行為就像以專案為基礎的演演算法：使用單一索引鍵來擷取建議，然後套用商業規則和篩選器。
