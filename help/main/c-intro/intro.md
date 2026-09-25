---
keywords: Target Standard;推薦;Target Premium;Automated Personalization;自動鎖定目標;自動鎖定目標;權限;什麼是adobe target;
description: 了解 Adobe [!DNL Target] Standard 和 Adobe [!DNL Target] Premium 的基本概念。[!DNL Target] Premium 包含標準產品中不提供的進階功能。
landing-page-description: 實現個人化的客戶體驗，協助您在網站和行動網站、應用程式、社交媒體和其他數位頻道上獲得最大收入。
short-description: 實現個人化的客戶體驗，協助您在網站和行動網站、應用程式、社交媒體和其他數位頻道上獲得最大收入。
title: 什麼是 Target？
feature: Overview
exl-id: 0e729c71-618b-4ab8-93a3-d37e73ec2740
TQID: https://experienceleague.adobe.com/Mr8fwY1FNfJShSezC50YX1QeBagmuovUySsQUO8jPqo
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: 2cecb1f8ae52fd6c47e543710bb14e00503c06ef
workflow-type: tm+mt
source-wordcount: '1644'
ht-degree: 70%
---
# [!DNL Target]簡介


>[!CONTEXTUALHELP]
>id="target_sample_size_ab_daily_traffic"
>title="每日流量"
>abstract="每天有多少使用者進入您的實驗。 如果您不知道自己的每日流量，請選擇上方的「流量」，計算機將根據您的其他輸入進行計算。"

>[!CONTEXTUALHELP]
>id="target_sample_size_setup"
>title="設定測試"
>abstract="這些欄位會定義您的 A/B 測試、您預期看到的內容，以及您對結果所需的信賴度。 與您上方所選內容繫結的欄位將會自動計算。 其餘欄位請填入您預期的值。"

>[!CONTEXTUALHELP]
>id="target_sample_size_number_experiences"
>title="體驗數量"
>abstract="實驗中變體的數量，包括控制組。 A/B 測試包含 2 個組。 五個變體加上一個控制組，共 6 組。 組數越多，維持統計檢定力所需的流量就越大。"

>[!CONTEXTUALHELP]
>id="target_sample_size_duration"
>title="A/B 測試持續時間"
>abstract="您的實驗將執行多少天。 較長的持續時間可使實驗有更多的時間來收集資料，讓您能可靠地檢測較小的效應。 較短的持續時間需要較大的效應或較多的每日流量，才能獲得可靠的結果。"

>[!CONTEXTUALHELP]
>id="target_sample_size_minimum_detectable_effect"
>title="最小可檢測效應"
>abstract="值得檢測的最小改進，即您會採取行動的量度的最小變化量。 這是提升度的大小 (以百分點為單位)，而非相對於基準線的百分比變化。 例如，如果您的基準線是 5%，而提升 1 個百分點很重要，請輸入 1。"

>[!CONTEXTUALHELP]
>id="target_sample_size_expected_improvement"
>title="預期的改進"
>abstract="您預期實驗將產生的改進。"

>[!CONTEXTUALHELP]
>id="target_sample_size_variance"
>title="變異數"
>abstract="您的量度值的分佈方式 (而非其平均值)。 點按率之類的量度 (大多為 0 和 1) 具有低變異數，而每位使用者的收入之類的量度 (少數高支出者，眾多低支出者) 則可能具有較高的變異數。 如果您不確定，請保留預設值 1。"

>[!CONTEXTUALHELP]
>id="target_sample_size_confidence_level"
>title="信賴水準"
>abstract="在將某個結果稱為真實結果之前，您需要有多大的自信才能確定其非隨機巧合，這就是統計顯著性的臨界值。 95% 信賴水準表示最多有 5% 的機率是誤判。 較高的值可降低誤判率，但需要較多的資料。"

>[!CONTEXTUALHELP]
>id="target_sample_size_statistical_power"
>title="統計檢定力"
>abstract="檢測到效應的機率 (如果效應確實存在)，即實驗的靈敏度。 80% 的檢定力意味著有 80% 的機率可以檢測到真實效應。 較高的檢定力可降低誤判率，但需要較多的流量或較長的執行時間。"

>[!CONTEXTUALHELP]
>id="target_sample_size_traffic_mode"
>title="流量模式"
>abstract="使用者如何進入您的實驗。 持續：使用者在實驗期間每天進入。 流量會在結果產生時自動轉向績效較佳的變體。"

>[!CONTEXTUALHELP]
>id="target_sample_size_metric_type"
>title="量度類型"
>abstract="您在衡量的量度類型。 百分比：請將此用於點按或轉換等二進位結果，其中每位使用者要麼有執行動作，要麼沒有執行動作。 數字：請將此用於收入或頁面檢視數等量度，其中的值可能會因使用者而有很大的變化。"

>[!CONTEXTUALHELP]
>id="target_sample_size_auto_daily_traffic"
>title="每日流量"
>abstract="每天有多少使用者進入您的實驗。 用於執行多天的持續實驗，流量會在結果產生時自動轉向績效較佳的變體。"

>[!CONTEXTUALHELP]
>id="target_sample_size_baseline_metric_rate"
>title="基準線量度比率"
>abstract="您在實驗開始前的目前績效，即控制組平均值。 始終為必要項。 對於百分比量度，請輸入百分比：如果 5% 的訪客點按「今日購買」，請輸入 5。 對於計數量度，請輸入原始小數值。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_primary_metric"
>title="主要量度"
>abstract="主要量度會自動從報告設定中提取。 若要進行變更，請在「目標和設定」下方修改目標量度。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_hypothesis"
>title="假設"
>abstract="假設是您定義的陳述，用來說明實驗的預期結果。 包括說明要變更的內容及位置，然後指出您預期變更的量度以及變更方式。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_insights"
>title="洞察"
>abstract="實驗洞察是當實驗資料達到統計顯著性時，AI 所獲得的學習成果。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_opportunities"
>title="機會"
>abstract="實驗機會是根據在您的實驗螢幕擷圖和結果中所發現的模式，AI 所建議的處理想法。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_treatment_details"
>title="處理詳細資料"
>abstract="處理詳細資料會顯示當使用者符合處理資格時處理外觀的影像。 您可以為所有實驗檢閱這些影像。 有些實驗可能會要求您確認影像或在需要時進行取代。"

[!DNL Adobe Target] （屬於[!DNL Adobe Experience Cloud]的一部分）提供全方位的工具，可跨網站、行動網站、應用程式、社群媒體和其他數位頻道個人化客戶體驗。

[!DNL Target]有助於最大化收入，並且可以授權為[!DNL Target Standard]或[!DNL Target Premium]。

## [!UICONTROL Target Standard] {#section_ACD5EFF17AAB4E979CBEFA0145CCD905}

[!DNL Target Standard]是[!DNL Adobe Target]的前端，可讓您以視覺化方式建立和管理A/B測試及規則型鎖定目標活動。 [!DNL Target]支援在[[!UICONTROL 視覺化體驗撰寫器]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)工作流程內外插入自訂程式碼。 [!DNL Target Standard]為您的數位財產提供簡化的實作策略，每個頁面上有一行程式碼管理您的網站與[!DNL Target]之間的所有通訊。

已將業界最佳實務整合至[!DNL Target Standard]，使其同時適用於新手和有經驗的使用者。 您可以使用[!DNL Adobe Experience Cloud]輕鬆與團隊成員共用資料、結果和共同作業。

## [!DNL Target Premium] {#premium}

[!BADGE 進階版]{type=Positive}

[!DNL Target Premium]是進階產品，需要授權才能將進階功能加入[!DNL Target Standard]。 [!DNL Target]指南中的所有[!DNL Target Premium]篇文章都會在每個頁面頂端或受影響文字附近的內嵌包含[!UICONTROL Premium]徽章。 [!UICONTROL Premium]徽章可點按並連結至此區段。

**[!DNL Target Premium]包含下列功能：**

### [!UICONTROL 自動個人化]

[[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) (AP)使用進階的機器學習演演算法來提供個人化的體驗，並改善數位互動的轉換率。

AP會記錄訪客活動、建立設定檔以將內容鎖定在類似的訪客上。 AP會追蹤個人和母體對內容的回應，使用複雜的模型，根據每位訪客的所有已知資訊自動鎖定目標。

AP完全自動化，以最少的人工分析持續學習。 它會建立模型，判斷訪客可能對哪些產品感興趣，並收集資訊並儲存在訪客設定檔中。 多種演演算法可確保為您的系統提供最佳模型。

### [!UICONTROL 自動鎖定目標]

[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)使用進階機器學習，以識別高效能行銷人員定義的體驗。 接著，它會根據個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗。 [!UICONTROL 自動鎖定目標]有助於個人化內容並推動轉換。

### 推薦

[推薦](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) 活動可依據先前的使用者行為，自動顯示可能使客戶感興趣的產品或內容。 [!UICONTROL Recommendations]可協助引導客戶至他們可能不知道的相關專案。

建議會判斷向客戶建議產品的方式，取決於客戶在網站上的行為。 例如:

* 鼓勵購買背包的使用者考慮購買登山鞋和登山杖。

  使用「購買了此項目、也購買了其他項目的使用者」條件，建立顯示經常一起購買項目的建議。

* 根據訪客目前觀賞的影片來建議類似的影片內容，以吸引訪客在您的媒體網站上停留更久。

  使用「瀏覽過此項目、也瀏覽了其他項目的使用者」條件，建立建議其他影片的建議。

* 建議檢視了關於在您的銀行存款計劃的客戶也閱讀關於 IRA 帳戶的資訊。

  使用「瀏覽過此項目、但購買了其他項目的使用者」條件，顯示人員在檢視一個產品而沒有顯示建議中第一個產品之後購買的其他產品。

### 推薦作為產品建議

[Recommendations作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)可讓您在[!UICONTROL A/B測試]、[!UICONTROL 自動分配]、[!UICONTROL 自動鎖定目標]和[!UICONTROL 體驗鎖定目標] (XT)活動中包含建議。

這項功能開啟了全新功能，例如:

* 在同一個活動內測試及鎖定建議與非建議內容。
* 輕鬆試驗建議在頁面中的放置方法，包括多個建議的排列順序。
* 使用[!UICONTROL 自動分配]自動將流量推送到績效最佳的建議體驗。
* 使用[!UICONTROL 自動鎖定目標]，根據個別設定檔，以動態方式為訪客指派自訂建議體驗。

### 企業使用者權限

[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838)功能可讓您建立不同的專案 (在 [!DNL Adobe Admin Console for Enterprise] 中稱為「產品設定檔」)。 [!UICONTROL 企業使用者許可權]可讓您為單一使用者指派不同許可權，以指定該使用者存取每個專案的許可權。 這些獨特的專案可與 [!DNL Adobe Analytics] 中報表套裝的運作方式比較。 每個專案可以有特定的使用者具有適用一組屬性的特定角色。 結果，客戶可限制其使用者的檢視、編輯、核准和發佈存取權。 您可以根據地區、環境（開發／舞台/prod）、頻道或其他自訂准則來限制使用者。

## Beta功能 {#beta}

[!BADGE Beta]{type=Informative}

[!DNL Adobe Target]團隊經常為特定客戶啟用新功能，以進行測試和提供意見回饋。 在測試期間完成後，這些功能會在未來[!DNL Target Standard/Premium]版本中針對所有客戶啟用，並在發行說明中宣佈。

在說明Beta功能的[!DNL Target]指南中，文章會在每個頁面的頂端或受影響文字附近的內嵌包含Beta標誌。 Beta徽章可點按，並包含本區段的連結。

## 推薦經典版 {#section_9554068100054D2DBDB298CBE5A0E413}

>[!IMPORTANT]
>
>[!DNL Recommendations Classic] 是舊版產品，不再授權給新客戶。 為獲得最佳的 [!DNL Recommendations] 體驗，請升級至 [!DNL Adobe Target Premium] 中的 [!DNL Recommendations] ，如上所述。

[!DNL Recommendations Classic] 會依據網站上先前的使用者行為，自動顯示可能吸引客戶的產品或內容。 推薦有助於將客戶導向他們原本可能不知道的項目，提升網站產生的銷售額。

如需詳細資訊，請參閱[推薦經典版說明文件](/help/main/assets/adobe-recommendations-classic.pdf)。

## Experience League： Adobe [!DNL Target]歡迎套件 {#kit}

使用此歡迎套件，在 [!DNL Adobe Target] 上建立最佳化和個人化方案。 此歡迎套件包含重要資訊、工具和資源，可協助您準備並啟動第一個 [!DNL Target] 活動。 此套件包含短期快速贏取和長期最佳化策略的概念。

[Adobe Target歡迎套件](/help/main/c-intro/target-welcome-kit.md)

## 訓練影片：活動型別(9:03) ![Overview badge](/help/main/assets/overview.png)

下列影片說明 [!DNL Target Standard/Premium] 中可用的活動類型，以及 [!DNL Target] 的三步驟引導式工作流程如何協助您達成網站目標。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)


