---
description: 使用最多五個條件的序列來對建議活動中出現的項目執行更好的控制。
keywords: 條件序列;多個條件;演算法;條件;建議條件
seo-description: 使用最多五個條件的序列來對建議活動中出現的項目執行更好的控制。
seo-title: 建立條件序列
solution: Target
title: 建立條件序列
title-outputclass: premium
topic: Premium
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) 建立條件序列{#create-criteria-sequences}

使用最多五個條件的序列來對建議活動中出現的項目執行更好的控制。

>[!NOTE]
>
>條件序列不能搭配在 [!UICONTROL  2016 年 10 月之前版本中建立的 ]Recommendations[!DNL Target Premium] 活動使用。

若要建立條件順序，您必須先建立您要在序列中包括的條件。請參閱[建立條件](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)以取得相關資訊。

透過使用條件序列，您可以在條件未傳回可滿足您的設計的足夠結果時，提供其他鎖定目標的建議，而非使用更一般的備用建議。一般來說，條件序列將從更具體的鎖定目標繼續，這可能會傳回較少的結果，接著再進行更為一般的鎖定目標，這通常會傳回更多結果。

例如，產品頁面條件序列可能會遵循此順序:

1. 根據目前項目，來自相同品牌
1. 根據目前項目，來自所有品牌
1. 根據內容相似度
1. 根據最暢銷商品
1. 根據各網站間檢視次數最多的項目

首頁條件序列可能會遵循此順序:

1. 根據訪客的最近一次的購買
1. 根據訪客最喜愛的項目
1. 根據訪客最喜愛的類別
1. 根據最暢銷商品
1. 根據各網站間檢視次數最多

有多個方式可到達[!UICONTROL 「建立條件順序」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* 建立 [!UICONTROL Recommendations] 活動時，請在[!UICONTROL 「選取條件」]畫面上按一下**[!UICONTROL 「新建]** &gt; **[!UICONTROL 建立條件序列」]**。您將可以選擇儲存您的新條件順序以搭配其他 [!UICONTROL Recommendations] 活動使用。
* 編輯 [!UICONTROL Recommendations] 活動時，請在頁面上的[!UICONTROL 「Recommendations 位置」]方塊中按一下，然後選取**[!UICONTROL 「變更條件」]**。在 [!UICONTROL 選取標準] 畫面上，按一下 **[!UICONTROL 新建]** &gt; **[!UICONTROL 建立標準序列]**。您將可以選擇儲存您的新條件以搭配其他 [!UICONTROL Recommendations] 活動使用。
* 在**[!UICONTROL 「Recommendations**] &gt; **[!UICONTROL 條件」]**資料庫畫面上，按一下**[!UICONTROL 「建立條件]** &gt; **[!UICONTROL 建立條件序列」**]。您在這裡建立的條件會自動可供所有 [!UICONTROL Recommendations] 活動使用。

1. 按一下**[!UICONTROL 「建立條件」]**或**[!UICONTROL 「新建」]**。

   ![建立新標準](/help/c-recommendations/c-algorithms/assets/button_CreateCriteria_new.png)

1. 選取**[!UICONTROL 「建立條件序列」]**。

   ![](assets/CreateCriteriaSequence.png)

1. 輸入序列的**[!UICONTROL 名稱]**。

   這是用來說明該條件順序的「內部」名稱。您的網站的訪客將不會看見此名稱。
1. 如果在序列中使用多個條件填入 [!UICONTROL Recommendations] 設計，請輸入要在頁面上公開顯示的**[!UICONTROL 一般顯示標題]**。

   例如，如果設計可能包括基於一個以上 [!UICONTROL Recommendations] 金鑰的項目，則可以將「檢視這個的客戶也檢視了...」取代為「給您的建議」。
1. 輸入條件序列的簡短**[!UICONTROL 說明]**。

   說明應該能協助您識別條件序列，並且可能包括關於其用途的資訊。
1. 選取**[!UICONTROL 「垂直產業」]**。

   您的預設垂直產業隨即自動顯示。
1. 選取一個**[!UICONTROL 頁面類型]**。

   您可以選取多個頁面類型。

   垂直產業和頁面類型可共同用來分類您儲存的條件順序，讓您可輕鬆對其他 [!UICONTROL Recommendations] 活動重複使用順序。
1. 設定**[!UICONTROL 內容]**規則。

   建立條件順序時，系統會針對組成序列的個別條件，忽略其備用建議和部分設計呈現設定。若要使用備用建議和部分設計呈現，您必須啟用其序列。選取適當的切換。如果您選擇允許備用建議，則也可以選擇是否對備用套用包含規則。
1. 設定序列順序。

1. 按一下**[!UICONTROL 「新增條件」]**。
1. 在「新增條件」畫面上選取條件。
1. 按一下**[!UICONTROL 「新增」]**。

   您可以新增最多五個條件至順序。
1. 按一下**[!UICONTROL 「儲存」]**。

   條件序列會出現在條件清單中。

   ![](assets/CriteriaSequenceCard.png)

   如需關於建議邏輯選項的詳細資訊，請參閱[條件](../../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750)。
