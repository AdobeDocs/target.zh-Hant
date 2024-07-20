---
keywords: 集合;鎖定目標
description: 瞭解如何在 [!DNL Target Recommendations]中使用產品或專案的集合。
title: 如何在Recommendations活動中使用集合？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: c8bd2bb45ee8ef1a849fd9091554caec77effba0
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 40%

---

# 集合

集合是符合建議資格的一組產品或專案。 集合的定義方式是指定專案必須符合的條件，才能成為其一部分。

集合通常是指一組相似或相關的項目，例如單一產品集合。不過，您可以將任何專案分組到對您的業務有意義的類別中，例如特定價格範圍內的產品，或可能在特定地理區域受到歡迎的顏色或專案。

請使用集合以在邏輯分組中組織產品。例如，如果某些專案在一個區域可用，但在另一個區域不可用，您可以建立排除訪客區域不可用專案的集合。 您也可以使用集合來組織季節性項目，或使用業務上適合的任何其他組織參數。

針對建議內每個條件而產生的[備用建議](/help/main/c-recommendations/c-algorithms/backup-recs.md)也會使用此集合，因此，只有集合中的項目才會納入備用建議中。集合可讓您確保只顯示必須出現在位置中的產品。

每個條件每次執行時皆會重建或更新集合。

您可以將項目分組為目錄，然後為每個集合建立個別的建議。

包含條件的用途類似集合，但必須在您每次建立活動時設定。集合可讓您一次建立一組項目，然後在適當時機派上用場，而不必再次設定。

當您建立或編輯[!DNL Recommendations]活動時，集合名稱會出現在活動圖表的[!UICONTROL Criteria]標籤旁。

>[!NOTE]
>
>使用[!UICONTROL Recently Viewed Items]建議索引鍵時不會套用集合。

## 建立集合 {#task_1256DFF6842141FCAADD9E1428EF7F08}

建立集合來組織您要在建議中顯示的產品或內容。

1. 按一下「**[!UICONTROL Recommendations]** > **[!UICONTROL Collections]**」以顯示現有集合清單。

   ![集合清單](assets/collections_list.png)

   [!UICONTROL Collections]頁面會顯示您現有集合的清單。 您可以按一下[!UICONTROL Create Collection]按鈕來建立新的集合。 您也可以將游標移至所需的集合上，然後按一下所需的圖示，以編輯、複製和刪除現有集合。

   ![暫留圖示：編輯、複製和刪除](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   [!UICONTROL Collections]清單檢視上各集合的「專案數」為設定的預設Recommendations [主機群組](/help/main/administrating-target/hosts.md) （環境）內符合集合規則的產品數。 請參閱[設定](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}以變更預設主機群組。

1. 按一下 **[!UICONTROL Create Collection]**。

1. （依條件）建立（或更新）集合時，從&#x200B;**[!UICONTROL Environment]**&#x200B;篩選器中選擇一個環境，以便預覽該環境中的集合內容。 依照預設，會顯示預設主機群組的結果。

   ![建立集合](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. 輸入集合的&#x200B;**[!UICONTROL Name]**。

   您也可以輸入選擇性的&#x200B;**[!UICONTROL Description]**。

1. 設定用來建立集合的規則。

   例如，您的集合可能根據清單中的產品 ID 或類別、利潤或任何其他參數建立。

   您可以新增規則，以使用多個參數來定義集合。您可使用AND運運算元聯結多個規則。 所有指定的規則必須符合，才會套用集合。

1. 按一下 **[!UICONTROL Save]**。

## 使用進階搜尋建立集合

您也可以使用[目錄搜尋](/help/main/c-recommendations/c-products/catalog-search.md#save-as)頁面上的「進階搜尋」([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search])來建立集合。

![另存為對話方塊](/help/main/c-recommendations/c-products/assets/save-as.png)

例如，使用&quot;id > contains&quot;建立搜尋之後，您就可以按一下[!UICONTROL Save As] > [!UICONTROL Collection]。

>[!IMPORTANT]
>
>「進階搜尋」功能不區分大小寫，不過傳送時傳回的產品會以區分大小寫的搜尋為依據。此不相符的情況可能導致混淆。使用「進階搜尋」功能來根據結果建立集合時，務必注意大小寫。例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您之後建立一個目錄，目的要傳回包含 &quot;holiday&quot; 的產品，則只會傳回包含 &quot;holiday&quot; 的產品。不會傳回包含 &quot;Holiday&quot; 的產品。

## 編輯、複製或刪除集合

將滑鼠懸停在清單中所需的集合上，然後按一下適當的圖示：編輯、複製或刪除。

集合的![暫留圖示](/help/main/c-recommendations/c-products/assets/hover-collections.png)

您可以複製現有收藏集以建立重複的收藏集，然後進行修改。 這可讓您輕鬆建立類似的排除專案。

請注意，集合在整個帳戶中皆可使用。 刪除集合前，請務必考量這一點。 已刪除的集合無法復原。

## 在Recommendations活動中使用集合

1. 使用上述其中一種方法建立集合。

1. 按一下&#x200B;**[!UICONTROL Activities]**&#x200B;和[建立新的Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)活動或編輯現有的活動。

1. 選取條件與設計後，若您選取想要的集合，則會顯示[!UICONTROL Options]頁面。

   ![選擇集合選項](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. （視條件而定）若要變更現有的集合設定，請在&#x200B;**[!UICONTROL Experiences]**&#x200B;頁面（三步驟引導式工作流程的步驟2）上按一下您放置建議的位置，按一下「**[!UICONTROL Change Collection]**」，然後選取所要的集合。

   ![變更集合選項](/help/main/c-recommendations/c-products/assets/change-collection.png)

## 訓練影片：在Recommendations中建立集合和排除專案(7:05) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包含下列資訊:

* 建立集合
* 建立排除項目

>[!VIDEO](https://video.tv.adobe.com/v/27689)
