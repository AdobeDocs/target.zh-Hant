---
keywords: 集合;鎖定目標
description: 瞭解如何在 [!DNL Target Recommendations]中使用產品或專案的集合。
title: 如何在Recommendations活動中使用集合？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: be9cb6da17f125c127d64ed8f9002987188fdf3d
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 25%

---

# 集合

集合是符合建議資格的一組產品或專案。 集合的定義方式是指定專案必須符合的條件，才能成為其一部分。

集合通常是指一組相似或相關的項目，例如單一產品集合。不過，您可以將任何專案分組到對您的業務有意義的類別中，例如特定價格範圍內的產品，或可能在特定地理區域受到歡迎的顏色或專案。

請使用集合以在邏輯分組中組織產品。例如，如果某些專案在一個區域可用，但在另一個區域不可用，您可以建立排除訪客區域不可用專案的集合。 您也可以使用集合來組織季節性項目，或使用業務上適合的任何其他組織參數。

[針對建議內每個條件產生的備用建議](/help/main/c-recommendations/c-algorithms/backup-recs.md)也會使用此集合，因此只有集合中的專案會包含在備用建議中。 集合可讓您確保只顯示必須出現在位置中的產品。

每個條件每次執行時皆會重建或更新集合。

您可以將項目分組為目錄，然後為每個集合建立個別的建議。

包含條件的用途類似集合，但必須在您每次建立活動時設定。集合可讓您一次建立一組專案，然後可視需要隨時使用它，而無需重新設定。

當您建立或編輯[!DNL Recommendations]活動時，集合名稱會出現在活動圖表的[!UICONTROL Criteria]標籤旁。

>[!NOTE]
>
>* 收集規則會套用至執行條件後產生的建議專案。 它們只會影響輸出中的實體建議(ER)，而不會影響索引鍵。
>
>* 使用[!UICONTROL Recently Viewed Items]建議索引鍵時不會套用集合。

## 建立集合 {#task_1256DFF6842141FCAADD9E1428EF7F08}

建立集合來組織您要在建議中顯示的產品或內容。

1. 按一下「**[!UICONTROL Recommendations]** > **[!UICONTROL Collections]**」以顯示現有集合清單。

   [!UICONTROL Collections]頁面會顯示您現有集合的清單。 您可以按一下[!UICONTROL Create Collection]按鈕來建立新的集合。 您也可以編輯、複製和刪除現有集合，方法是按一下所要集合旁的「更多動作」圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下所要的選項。

   [!UICONTROL Collections]清單檢視上每個集合報告的「專案數」為設定的預設Recommendations [主機群組](/help/main/administrating-target/hosts.md) （環境）內符合集合規則的產品數。 請參閱[設定](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}以變更預設主機群組。

1. 按一下 **[!UICONTROL Create Collection]**。

1. 輸入集合的&#x200B;**[!UICONTROL Name]**。

   您也可以輸入選擇性的&#x200B;**[!UICONTROL Description]**。

1. （視條件而定）建立（或更新）集合時，從&#x200B;**[!UICONTROL Environment]**&#x200B;篩選器中選擇[環境](/help/main/administrating-target/environments.md)，以預覽該環境中的集合內容。 依照預設，會顯示預設主機群組的結果。

1. 設定用來建立集合的規則。

   例如，您的集合可能根據清單中的產品 ID 或類別、利潤或任何其他參數建立。

   您可以新增規則，以使用多個參數來定義集合。您可使用AND運運算元聯結多個規則。 所有指定的規則必須符合，才會套用集合。

1. 按一下 **[!UICONTROL Create]**。

<!-- ## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. -->

## 編輯、複製或刪除集合

按一下清單中所需集合旁的（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下適當的圖示： [!UICONTROL Edit]、[!UICONTROL Copy]或[!DNL Delete]。

您可以複製現有收藏集以建立重複的收藏集，然後進行修改。 這可讓您輕鬆建立類似的系列。

請注意，集合在整個帳戶中皆可使用。 刪除集合前，請務必考量這一點。 已刪除的集合無法復原。

## 在[!DNL Recommendations]活動中使用集合

1. 使用上述其中一種方法建立集合。

1. 按一下&#x200B;**[!UICONTROL Activities]**&#x200B;和[建立新的Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)活動或編輯現有的活動。

1. 選取條件和設計後，[!UICONTROL Options]頁面會隨即顯示，您可在其中選取所要的集合。

1. （視條件而定）若要變更現有的集合設定，請在&#x200B;**[!UICONTROL Experiences]**&#x200B;頁面（三步驟引導式工作流程的步驟1）上按一下您放置建議的位置，按一下「**[!UICONTROL Change Collection]**」，然後選取所要的集合。
