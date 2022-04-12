---
keywords: 建議算法；模型訓練；模型服務；內容傳遞；基於項目；基於用戶；基於普遍性；基於購物車；自定義標準
description: 瞭解中使用的算法 [!DNL Target Recommendations]包括模型訓練和模型服務。
title: 我從哪裡可以瞭解塔吉特公司的Recommendations算法背後的科學？
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2839'
ht-degree: 0%

---

# ![高級](/help/main/assets/premium.png) 塔吉特公司推薦算法背後的科學

對中使用的算法的深入描述 [!DNL Adobe Target Recommendations]包括模型訓練的邏輯和數學細節以及模型服務過程。

模型培訓是建議如何由 [!DNL Adobe Target] 學習算法。 模型服務就是 [!DNL Target] 向您的站點訪問者提供建議（也稱為內容交付）。

[!DNL Target] 包括以下廣泛類型的算法 [!DNL Recommendations]:

* **基於項的算法**:包括遵循邏輯的算法「查看/購買此項的人也查看/購買這些項」。 這些算法被歸類到雨傘項 — 項協同過濾中，以及 [!UICONTROL 具有相似屬性的項] 算法。

* **基於用戶的算法**:包括 [!UICONTROL 最近查看] 和 [!UICONTROL 推薦給您] 算法。

* **基於流行度的算法**:包括在整個網站中返回最前查看或最後購買項目、按類別或項目屬性返回最後查看或最後購買項目的算法。

* **基於購物車的算法**:包括基於多項的建議，邏輯為「查看/購買這些物品的人，也查看/購買這些物品」。

* **自定義條件**:包括基於上載到的自定義檔案的建議 [!DNL Target]。

>[!NOTE]
>
>有關每個算法類型和各個算法的更多一般資訊，請參見 [基於建議密鑰的建議](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

上述許多算法都基於一個或多個密鑰的存在。 這些鍵用於在內容交付時（在提出建議時）檢索類似項。 客戶指定的鍵可以包括某人正在查看的當前項目、查看或購買的上一項目、最前查看的項目、當前類別或該訪問者的收藏夾類別。 其他算法（如基於購物車或基於用戶的建議）使用隱式鍵（客戶無法配置）。 有關詳細資訊，請參見 *建議密鑰*, [基於建議密鑰的建議](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys)。 但是，請注意，這些鍵僅與模型服務時間（內容交付）相關。 這些鍵不影響「離線」或模型培訓時間邏輯。

以下各節以與上述算法類型稍有不同的方式對算法進行分組。 以模型訓練邏輯的相似性為基礎進行分組。

## 物料 — 物料協作篩選

算法包括：

* [!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]
* [!UICONTROL 瀏覽過此項目、但購買了其他項目的使用者]
* [!UICONTROL 購買了此項目、也購買了其他項目的使用者]

項目 — 項目協作篩選推薦算法基於這樣一種思想：您應使用許多用戶的行為模式（因此是協作模式）為給定項目提供有用的建議（例如，篩選可能建議的項目的目錄）。 雖然有很多不同的算法都屬於 [協同過濾](https://en.wikipedia.org/wiki/Collaborative_filtering)這些算法普遍使用行為資料源作為輸入。 在 [!DNL Target Recommendations]，這些輸入是用戶對項目的獨特視圖和購買。

對於「查看/購買此項目的人員也查看/購買了這些項目」算法，目標是計算所有對項目之間的相似性s(A,B)。 對於給定項目A，按其相似性s(A,B)排序頂級建議。

相似性的一個示例是項目之間的共現：購買這兩項的用戶數的簡單計數。 雖然直覺，但這種衡量方式過於天真，因為它偏向於推薦流行商品。 例如，如果在雜貨店裡，大多數人都買麵包，麵包與所有商品的共存度就會很高，但這未必是個好建議。 [!DNL Target] 而是使用更複雜的相似度度量，稱為對數似然比(LLR)。 當兩個物料（A和B）的共發概率與它們不共發的概率非常不同時，這個量是大的。 要具體，請考慮 [!UICONTROL 看過這個的人買了] 算法。 當B的購買概率為1時，LLR的相似性大 *不* 無論是否有人看A

例如，若

![查看/購買算法的公式](assets/formula.png)

項目A不推薦項目B。提供了該對數似然比相似性計算的全部細節 [在此PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)。

實際算法實現的邏輯流程如下圖所示：

![已查看/已購買算法的原理圖](assets/diagram1.png)

這些步驟的詳細資訊如下：

* **輸入資料**:行為資料，以在您 [實現目標](/help/main/c-recommendations/plan-implement.md#pass-behavioral) 或 [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md)。

* **模型訓練**:

   * **資料清理和採樣**:對於具有N天回望的算法，首先過濾行為資料以僅包括那些N天的資料。 然後，將應用收集規則和全局排除來刪除任何不應建議的項目。 最後，任何與1000多件物品互動的訪客，其使用資料只採樣到1000件物品。
   * **項目相似性計算**:這是核心計算步驟：計算所有候選項對之間的對數似然比相似性，並通過此相似性得分對項進行排序。
   * **離線篩選**:最後，應用任何進一步適用的動態過濾器（例如，動態類別排除）。 在此步驟之後，預計算的建議被全局快取以便可供服務。

* **模型服務**:Recommendations內容從 [!DNL Target]`s [全局「邊緣」網路](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934)。 在向 [!DNL Target] 並確定應將建議內容交付至該頁，以要求適當 [項鍵](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys) 對於建議算法，從請求中分析或從用戶配置檔案中查找，然後用於檢索在前面步驟中計算的建議。 此時，在適當之前應用更多動態濾波器 [設計](/help/main/c-recommendations/c-design-overview/create-design.md) 。

## 內容相似性

算法包括：

* [!UICONTROL 具有相似屬性的項]

在這類算法中，如果兩個項的名稱和文本描述在語義上相似，則它們被視為相關項。 與必須使用行為資料源的大多數推薦算法不同，內容相似性算法使用產品目錄中的元資料來推導項目之間的相似性。 [!DNL Target] 因此，能夠在所謂的「冷啟動」情形中推動建議，在這種情況下，沒有收集到行為資料(例如，在 [!DNL Target] )。

雖然模型服務和內容交付方面 [!DNL Target]其內容相似性算法與其他基於項的算法相同，模型訓練步驟差別很大，涉及一系列自然語言處理和預處理步驟，如下圖所示。 相似性計算的核心是使用修改的tf-idf向量的余弦相似性來表示目錄中的每個項目。

![顯示內容相似性流程的圖](assets/diagram2.png)

這些步驟的詳細資訊如下：

* **輸入資料**:如前所述，此算法完全基於目錄資料(接收到 [!DNL Target] 通過 [目錄源、實體API或來自頁面更新](/help/main/c-recommendations/plan-implement.md#rec-catalog)。

* **模型訓練**:

   * **屬性提取**:在應用常規靜態過濾器、目錄規則和全局排除後，該算法從實體模式中提取相關文本欄位。 [!DNL Target] 自動使用實體屬性中的名稱、消息和類別欄位，並嘗試從自定義中提取任何字串欄位 [實體屬性](/help/main/c-recommendations/c-products/entity-attributes.md)。 此過程是通過確保該欄位的大多數值不能作為數字、日期或布爾值分析來完成的。
   * **詞塞和詞塞刪除**:為了更精確的文本相似性匹配，請務必刪除非常常見的「停止」字，這些字不會顯著改變項的含義（例如，「was」、「is」、「and」等）。 同樣，詞乾是指在詞根詞上減少帶有不同尾碼的詞的過程，其含義相同(例如，&quot;connect&quot;、&quot;connecting&quot;和&quot;connection&quot;都具有相同的根詞：「連接」)。 [!DNL Target] 用雪球鋼琴。 [!DNL Target] 首先執行自動語言檢測，並可以停止最多50種語言的詞刪除和18種語言的詞乾。
   * **n-gram建立**:在前面的步驟之後，每個字都被視為令牌。 將令牌的連續序列組合成單個令牌的過程稱為n-gram建立。 [!DNL Target]s的算法考慮的最多為2克。
   * **tf-idf計算**:下一步包括建立tf-idf向量以反映項說明中標籤的相對重要性。 對於項目i中的每個令牌/術語t，目錄D中 |D|項，首先計算項頻率TF(t,i)（項在項i中出現的次數）以及文檔頻率DF(t,D)。 實際上，令牌存在的項數。 tf-idf測量隨後

      ![顯示tf-idf度量的公式](assets/formula2.png)

      [!DNL Target] 使用Apache Spark *tf-idf* 特徵實現，在引擎蓋下將每個令牌散列到218個令牌的空間。 在此步驟中，還通過根據在以下步驟中指定的設定調整每個向量中的術語頻率來應用客戶指定的屬性提升和填充 [標準](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)。

   * **項目相似性計算**:最終項目相似度計算使用近似余弦相似度來完成。 對於兩項， *A* 和 *B*，對於向量tA和tB，余弦相似度定義為：

      ![顯示項目相似性計算的公式](assets/formula3.png)

      為避免計算所有N x N項之間的相似性時出現顯著複雜性， *tf-idf* 將截斷向量，以僅包含其最大500個條目，然後使用此截斷向量表示計算項目之間的余弦相似性。 與局部敏感散列等其他近似最近鄰(ANN)方法相比，該方法在稀疏向量相似度計算中具有更強的魯棒性。

   * **模型服務**:此過程與上一節所述的項目 — 項目協作過濾技術相同。

## 多鍵建議

算法包括：

* 基於購物車的建議
* [!UICONTROL 推薦給您]

最近對 [!DNL Target] 一套推薦算法 [!UICONTROL 推薦給您] 以及一系列基於購物車的推薦算法。 這兩種算法都使用協作過濾技術來形成基於項目的建議。 然後，在服務時間，用戶瀏覽歷史記錄中的多個項目( [!UICONTROL 推薦給您])，或用戶的當前購物車（對於基於購物車的建議案）用於檢索這些基於物料的建議案，然後合併這些建議案以形成最終的建議案清單。 請注意，個性化推薦算法有很多種。 選擇多密鑰算法意味著在訪問者具有任何瀏覽歷史記錄並可以更新建議以響應最新的訪問者行為後，建議可以立即獲得。

這些算法基於基於項目的建議部分中描述的基本協作過濾技術，但也包括超參數調整以確定項目之間的最佳相似性度量。 該算法對每個用戶執行按時間順序的行為資料分割，並訓練關於早期資料的推薦模型，同時嘗試預測用戶稍後查看或購買的項目。 生成最佳的相似度量 [平均精度](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)#Mean_average_precision) 頁籤。

模型訓練和評分步驟的邏輯如下圖所示：

![示出模型訓練和評分步驟邏輯的圖](assets/diagram3.png)

這些步驟的詳細資訊如下：

* **輸入資料**:這與項目 — 項目協作過濾(CF)方法相同。 [!UICONTROL 都推薦您] 而基於購物車的算法則使用行為資料，以在您 [實現目標](/help/main/c-recommendations/plan-implement.md#pass-behavioral) 或 [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md)。

* **模型訓練**:

   * **資料清理和採樣**:這同樣與協作篩選方法相同，在協作篩選方法中，應用回望窗口將行為資料篩選到適當的日期範圍，然後應用目錄規則和全局排除。 與1,000多件物品互動的訪客只考慮了他們最近的1,000個用途。
   * **列車test分割**:對每個用戶執行按時間順序劃分的使用實例，將其前80%的使用實例分配給培訓資料，其餘20%分配給test資料。
   * **項目相似性模型訓練**:核心項相似度計算因 [!UICONTROL 推薦給您] 以及基於購物車的算法。 對於 [!UICONTROL 推薦給您]，項目向量具有維NUsers，其中每個條目表示項目的該用戶的隱式評級之和 — 為項目的視圖賦予購買項2x的權重。 對於基於購物車的建議，項目向量包含二進位條目；如果僅考慮會話內行為，則每個會話都有一個新條目。 否則，此項目向量中會為每個訪問者輸入一個條目。

   訓練步驟計算幾種類型的向量相似性：LLR相似性([討論](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf))、余弦相似性（以前定義）和歸一化的L2相似性，定義為：

   ![表示訓練計算的公式](assets/formula4.png)

   * **項目相似性模型評估**:模型評估是採用前一步驟中產生的建議對test資料集進行預測。 通過在test資料集中按時間順序排列每個用戶的項目使用，然後對項目的有序子集提出100個建議，以嘗試預測隨後的視圖和購買，來模擬線上評分階段。 資訊檢索度量， [平均精度](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)#Mean_average_precision)，用於評估這些建議的質量。 此度量考慮了建議的順序，並傾向於建議清單中較高的相關項，這是對系統進行排序的重要屬性。
   * **模型選擇**:離線評估後，將選擇具有最高平均精度的模型，並為其計算所有單個項 — 項建議。
   * **離線篩選**:模型訓練的最後階段是應用任何適用的動態濾波器。 在此步驟之後，預計算的建議被全局快取以便可供服務。


* **模型服務**:與以前的算法不同，在以前的算法中，服務建議涉及指定一個用於檢索的密鑰，然後應用業務規則。 [!UICONTROL 推薦給您] 而基於Cart的算法則採用了一個更複雜的運行時過程。

   * **多密鑰檢索和合併**:對於基於購物車的建議，在購物車中傳遞的最多十個項目被視為檢索的關鍵，而每個項目的建議被平等加權。 對於 [!UICONTROL 推薦給您]最多將前五個唯一查看的項目和最後五個唯一購買的項目視為檢索的關鍵字，從購買的項目中產生的建議的權重是從查看的項目中產生的建議的兩倍。 在合併建議時，如果項目出現在多個單獨的建議清單中，則添加其加權相似性得分。 此階段的建議最終清單隨後是重新加權建議的合併清單，按降序排列。
   * **篩選**:接下來，應用過濾規則，例如刪除以前查看的和/或購買的項目，以及其他動態業務規則。

以下影像說明了這些過程，訪問者已查看項目A和購買的項目B。使用在每個項目標籤下顯示的離線相似性得分來檢索單個建議。 在檢索後，將推薦與加權相似性得分進行合併。 最後，在客戶已指定必須過濾掉以前查看和購買的物料的情形中，篩選步驟會從建議清單中刪除物料A和B。

![示出多鍵算法處理的圖](assets/diagram4.png)

## 基於受歡迎度

算法包括：

* [!UICONTROL 在整個站點上查看的最多]
* [!UICONTROL 按類別查看的最多數]
* [!UICONTROL 按物料屬性查看的最多數]
* [!UICONTROL 網站上的暢銷產品]
* [!UICONTROL 按類別排列的暢銷產品]
* [!UICONTROL 按物料屬性列出的最大銷售者]

[!DNL Target] 為瀏覽次數最多的項目以及網站上銷售量最高的項目提供基於流行度的算法，或按項目屬性或類別細分。 基於流行度的算法根據在給定時間框架內查看或購買該項目的會話數對項目進行排名。

所有這些算法都組合了聚合行為資料，其中查看和購買項目的會話總數以小時和每日解析度記錄。 然後，各個算法會為客戶配置的回望窗口找到查看次數最多或購買次數最多的項目。

具體算法細節如下：

* [!UICONTROL 在整個站點上查看的最多] 和 [!UICONTROL 網站上的暢銷產品] 按分別查看或購買這些項目的會話的合計計數對項目進行排序。 輸出是建議項的單個（無鍵）清單。
* 按類別/物料屬性列出的大多數已查看/最暢銷產品是按查看或採購這些物料的會話的合計計數訂購物料，但按物料類別或特定物料屬性分組的建議。 輸出是建議項的清單，由類別值或項屬性值鍵控。

## 最近查看

「最近查看的」建議算法允許在會話中個性化建議。 該算法不需要離線「模型訓練」。 相反， [!DNL Target] 使用唯一 [訪問者簡介](/help/main/c-target/c-visitor-profile/visitor-profile.md) 以維護在給定會話中已查看的項目的運行清單，並可在建議活動中顯示這些項目。 這允許即時更新建議和下一頁個性化。

## 自定義條件

自定義條件允許客戶 [上傳自己的建議 [!DNL Target]](/help/main/c-recommendations/c-algorithms/recommendations-csv.md)提供重要的靈活性，並允許「自帶模式」功能。 自定義標準替換「離線培訓」部分 [!UICONTROL 基於項] 建議，但在線上內容交付階段的行為與基於項目的建議算法類似，因為使用單個密鑰來檢索建議，然後應用業務規則/過濾器。