---
keywords: 條件序列；多個條件；演演算法；條件；建議條件；序列；限制傳回的專案數；位置層級控制；位置
description: 瞭解如何設定最多五個條件的順序，以更能掌控建議活動中出現的專案。
title: 如何在Recommendations中建立條件序列？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
TQID: 'https://experienceleague.adobe.com/dxO5cKxesTxgzZyfcvydQUlSq4TAgFN0ztT5VIe1WKU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 8%
---
# 建立條件序列 {#create-criteria-sequence}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何建立條件序列來控制出現在[!DNL Adobe Target Recommendations]活動中的專案。

>[!ENDSHADEBOX]

最多包含五個條件的序列可讓您更深入控制出現在[!DNL Adobe Target] **[!UICONTROL Recommendations]**&#x200B;活動中的專案。 傳回的專案數也可以受到限制（有時稱為「位置層級控制」）。

當條件未傳回足夠的結果以填滿設計時，條件序列會提供其他鎖定目標的建議，而非較一般的備用建議。 通常，條件序列會從更具體的目標定位（可能會傳回較少的結果）進展到更一般的目標定位（通常傳回更多結果）。

>[!NOTE]
>
>條件序列不能搭配在2016年10月發行的[!DNL Target Premium]之前建立的&#x200B;**[!UICONTROL Recommendations]**&#x200B;活動使用。

若要建立條件序列，請先建立要包含在序列中的條件。 如需詳細資訊，請參閱[建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

條件序列的順序會因頁面型別而異，如下列範例所示：

| 頁面類型 | 可能的順序順序 |
| --- | --- |
| 產品頁面 | <ol><li>根據目前專案，來自相同品牌</li><li>根據目前項目，來自所有品牌</li><li>根據內容相似度</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多的項目</li></ol> |
| 首頁 | <ol><li>根據訪客的最近一次的購買 </li><li>根據訪客最喜愛的項目</li><li>根據訪客最喜愛的類別</li><li>根據最暢銷商品</li><li>根據各網站間檢視次數最多</li></ol> |

## 建立條件序列

條件序列是從&#x200B;**[!UICONTROL 建立條件序列]**&#x200B;畫面建立的。 有多種方式可以存取此畫面。 部分熒幕選項會依到達熒幕的方式而有所不同。

* 在&#x200B;**[!UICONTROL 「Recommendations」]**>**[!UICONTROL 「條件」]**&#x200B;資料庫畫面上，按一下&#x200B;**[!UICONTROL 「建立條件」**[!UICONTROL >]**「建立條件順序」]**。 在此建立的條件會自動可供所有&#x200B;**[!UICONTROL Recommendations]**&#x200B;活動使用。
* 建立&#x200B;**[!UICONTROL Recommendations]**&#x200B;活動時，從&#x200B;**[!UICONTROL Select Criteria]**&#x200B;畫面，按一下&#x200B;**[!UICONTROL 新建]** > **[!UICONTROL 建立條件順序]**。 可以儲存新的條件序列以搭配其他&#x200B;**[!UICONTROL Recommendations]**&#x200B;活動使用。
* 編輯&#x200B;**[!UICONTROL Recommendations]**&#x200B;活動時，請按一下頁面上的&#x200B;**[!UICONTROL Recommendations位置]**&#x200B;方塊，然後選取&#x200B;**[!UICONTROL 變更條件]**。 在&#x200B;**[!UICONTROL 「選取條件」]**&#x200B;畫面上，按一下&#x200B;**[!UICONTROL 「新建」]**>**[!UICONTROL 「建立條件順序」]**。 可以儲存新條件以搭配其他&#x200B;**[!UICONTROL Recommendations]**&#x200B;活動使用。

下列步驟假設可從&#x200B;**[!UICONTROL 條件]**&#x200B;功能表存取&#x200B;**[!UICONTROL 建立條件序列]**&#x200B;畫面。

1. 按一下&#x200B;**[!UICONTROL 建議]** > **[!UICONTROL 條件]**。

1. 按一下&#x200B;**[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件順序]**。

   ![在「建立條件」功能表中選取「建立條件序列」選項的條件頁面](../assets/criteria_create_6.png)

1. 在[基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)區段中填入資訊。

1. 在&#x200B;**[!UICONTROL 條件序列]**&#x200B;區段中，按一下加號(+)以新增一或多個條件序列。

   序列順序會定義設計填入的順序。 如果條件1的建議不足以填滿設計，則其餘位置會填滿條件2，依此類推。

   ![建立條件序列對話方塊的條件序列區段，已選取五個條件欄位和條件1的加號](../assets/criteria_create_7.png)

1. 在&#x200B;**[!UICONTROL Select條件]**&#x200B;畫面上，選取條件，然後按一下&#x200B;**[!UICONTROL 儲存]**。

   可以使用&#x200B;**[!UICONTROL 搜尋]**&#x200B;方塊和篩選選項來尋找所需的條件。

1. （選擇性）啟用&#x200B;**[!UICONTROL 限制傳回的專案數]**，然後指定專案數（介於1到50之間）。

   ![條件序列區段已開啟[為您建議作為條件1]和[限制傳回的專案數]選項](../assets/criteria_create_8.png)

   下列使用案例說明&#x200B;**[!UICONTROL 限制傳回的專案數]**&#x200B;選項（有時稱為「位置層級控制」）的值。

   +++ 限制傳回專案數的使用案例

   * **使用案例1**：在單一建議匣中混合不同種類的專案，例如，混合外套（夾克）和上衣（襯衫、T恤）。 若要達成此目的，請使用活動的集合，其中包含可出現在任何設計位置的所有產品型別。 然後以僅包含外套的靜態篩選來設定第一個條件，以僅包含上衣的靜態篩選來設定第二個條件。 最後，將兩個條件新增至條件序列，並將第一個條件限製為2個槽。

     在網站上，建議匣看起來可能像這樣：

     ![精選產品推薦匣](assets/featured-products.png)

   * **使用案例2**：替代專案與補充專案的組合。 設定一個條件，以使用已檢視/已檢視的演演算法和將建議專案限製為目前專案類別的動態篩選器。 設定第二個條件以使用已檢視/已購買的演演算法，以及僅包含不符合目前專案類別的建議專案的動態篩選。 最後，將兩個條件新增至序列，並將第一個條件限製為2個槽。

   +++

1. 繼續將條件新增至序列。 一個序列最多可以新增五個條件。

1. 啟用[備份內容選項](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

條件序列會顯示在&#x200B;**[!UICONTROL 條件]**&#x200B;清單中。

如需有關建議邏輯選項的詳細資訊，請參閱[開始使用條件](/help/main/c-recommendations/c-algorithms/algorithms.md)。
