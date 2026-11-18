---
keywords: 優先順序; 體驗建立; 體驗; 客群; 切換體驗; 可視化體驗撰寫器
description: 瞭解訪客如何隨著其設定檔的演化，在[!DNL Adobe Target] [!UICONTROL 體驗鎖定目標] (XT)活動中的體驗之間切換。
title: 訪客可以在[!UICONTROL 體驗鎖定目標]活動中切換體驗嗎？
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
TQID: 'https://experienceleague.adobe.com/4bBukCristluFUClhewMcSsNMTPjLjXEqM1QyyropKU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: b6f5758b-84f7-4943-8b05-1297a046943c
    internal-label: Experience target
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aaa094f4f36b6088ca180637d8054b6d5ff59d60
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 20%
---
# 在[!UICONTROL 體驗鎖定目標]中切換體驗 {#switching-experiences}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解優先順序在&#x200B;**[!UICONTROL 體驗鎖定目標]**&#x200B;活動中如何運作，以及訪客如何隨著其設定檔的演化，在體驗之間切換。

>[!ENDSHADEBOX]

透過&#x200B;**[!UICONTROL 體驗鎖定目標]**，您可以控制訪客在其設定檔演化時看到的體驗。 訪客的設定檔可能以數種方式變更，而您可能會想要根據這些變更呈現不同的內容。 下表列出一些範例：

| 藍本 | 詳細資料 |
|--- |--- |
| 地理位置 | 隨著訪客因商業或休閒目的周遊，他們可能會從不同地理位置檢視您的網站或行動應用程式。 |
| 客戶狀態 | 訪客在建立帳戶或購買產品之前，可能會被視為潛在商機。 |
| 類別相關性 | [!DNL Target]中的[類別相關性](/help/main/c-target/c-visitor-profile/category-affinity.md)功能會自動擷取訪客檢視的類別，然後針對鎖定目標目的計算每個類別的訪客相關性。 例如，在您網站上檢視數篇關於特定主題的文章的訪客，會看到與該主題相關的內容。 |
| 星期 | 隨著週末到來，您可能要對訪客顯示關於電影、餐飲或其他娛樂形式的內容。 |

若要在[!DNL Target]中使用這些功能，在處理&#x200B;**[!UICONTROL 體驗鎖定目標]**&#x200B;活動時，請務必瞭解下列資訊。

## 如何提供訪客 {#how-visitors-are-served}

[!DNL Target] UI中體驗的順序（從上到下）會控制其優先順序，因此請在較廣的體驗之前定義目標更明確的體驗。 下表總結了訪客在每個情況下看到的內容。

| 情況 | 訪客看到的內容 |
|--- |--- |
| 訪客符合一個以上對象的資格。 | 優先順序較高的體驗內容。 |
| 訪客開始符合較高優先順序體驗對象的資格。 | 訪客會切換至較高優先順序的體驗。 |
| 訪客不再符合目前對象的資格，但開始符合較低優先順序體驗的資格。 | 訪客會切換至優先順序較低的體驗。 |
| 訪客停止符合目前體驗的資格，且不符合其他體驗的資格。 | 預設內容。 |
| 訪客未符合任何其他體驗的資格，且上一個體驗已鎖定為「所有訪客」。 | 「所有訪客」體驗。 此體驗「捕捉」未符合任何其他體驗資格的訪客。 |
| 鎖定在「所有訪客」的體驗不是順序中的最後一個。 | 系統仍會評估列出低於「所有訪客」體驗的目標體驗。 |
| 活動具有單一體驗，且訪客不再符合其對象的資格。 | 訪客會留在體驗中。 |

## 範例 {#examples}

以下範例說明這些情況。

### 優先順序：紐約和美國

如果您有兩個體驗，一個鎖定在「美國」，另一個鎖定在「紐約」，則位於紐約的訪客同時符合兩個對象的資格。 因此，您必須在[!DNL Target] UI中先定義「New York」體驗，然後再定義「United States」體驗。 此作法可確保目標較明確的「紐約」體驗有較高的優先順序，如下列範例所示：

![優先順序紐約 > 美國](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-refresh.png)

### 切換至較高優先順序的體驗：美國至德國

在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至德國並第二次造訪您的網站。 在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。 從德國檢視您的網站之後，此訪客切換到體驗 B (德國訪客)。

![優先順序美國 > 德國](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

### 離開對象：美國到法國

在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至法國並第二次造訪您的網站。 在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。 從法國檢視您的網站之後，此訪客會保留原始體驗。

![優先順序美國>德國，來自法國的訪客](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

### 鎖定所有訪客的體驗

在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至德國並第二次造訪您的網站。 在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。 從德國檢視您的網站之後，此訪客仍會留在體驗A （美國訪客）。

![優先順序美國 > 所有訪客](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-refresh.png)

如果這不是您預期的行為，您可以建立新客群，明確定義為您鎖定客群的相片，如下列範例所示:

![優先順序美國 > 非美國](/help/main/c-activities/t-experience-target/t-xt-create/assets/not-us.png)

### 單一體驗活動

使用單一體驗&#x200B;**[!UICONTROL 體驗鎖定目標]**&#x200B;活動，即使訪客不再符合將其放在該體驗中對象的資格，訪客仍會停留在體驗中。 如果這不是您預期的行為，您可以建立另一個體驗，鎖定在相反的對象（例如，與「美國」相對的「非美國」）。 作為另一個選項，您可以建立&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動，以100%流量分配鎖定在您需要的對象，如下列範例所示：

![優先順序一體驗](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-refresh.png)
