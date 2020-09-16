---
keywords: collection;Targeting
description: 集合是 Adobe Target 中符合建議資格的一組產品或項目。
title: Adobe Target 中的集合
feature: entities
uuid: aa1afdcf-e51c-4e44-a229-3c21fc9d0514
translation-type: tm+mt
source-git-commit: 421168f34bffe1f5f90d90f4af9b28940d0b8010
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 69%

---


# ![PREMIUM](/help/assets/premium.png) 集合{#collections}

集合是符合建議資格的一組產品或項目。系列的定義方式是指定項目必須符合的條件，才能成為其一部分。

集合通常是指一組相似或相關的項目，例如單一產品集合。但是，您可以將任何項目群組至對您的業務有意義的類別，例如特定價格範圍的產品或色彩，或在特定地區可能感興趣的項目。

請使用集合以在邏輯分組中組織產品。例如，如果某些項目在某個地區（而非另一個地區）可用，您可以建立一個系列，排除訪客所在地區不可用的項目。 您也可以使用集合來組織季節性項目，或使用業務上適合的任何其他組織參數。

針對建議內每個條件而產生的[備用建議](/help/c-recommendations/c-algorithms/backup-recs.md)也會使用此集合，因此，只有集合中的項目才會納入備用建議中。集合可讓您確保只顯示必須出現在位置中的產品。

每個條件每次執行時皆會重建或更新集合。

您可以將項目分組為目錄，然後為每個集合建立個別的建議。

包含條件的用途類似集合，但必須在您每次建立活動時設定。集合可讓您一次建立一組項目，然後在適當時機派上用場，而不必再次設定。

當您建立或編輯 [!DNL Recommendations] 活動時，集合名稱會出現在活動圖的[!UICONTROL 「條件」]標籤旁。

>[!NOTE]
>
>使用[!UICONTROL 「最近查看的項目」]建議索引鍵時不會套用集合。

## 建立集合 {#task_1256DFF6842141FCAADD9E1428EF7F08}

建立系列以組織您要在建議中顯示的產品或內容。

1. 依序按下&#x200B;**[!UICONTROL 「Recommendations]** > **[!UICONTROL 集合」]**，即可顯示現有集合清單。

   ![集合清單](assets/collections_list.png)

   「系 [!UICONTROL 列] 」頁面會顯示現有系列的清單。 按一下「建立系列」按鈕，即可 [!UICONTROL 建立新的系列] 。 您也可以將滑鼠指標暫留在所要的系列上，然後按一下所要的圖示，以編輯、複製和刪除現有的系列。

   ![暫留圖示：編輯、複製和刪除](/help/c-recommendations/c-products/assets/hover-icons.png)

   [!UICONTROL 「集合」]清單檢視上，每個集合的「項目數量」為設定的預設 Recommendations [主機群組](/help/administrating-target/hosts.md) (環境) 中，符合集合規則的產品數量。請參閱[設定](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)，瞭解如何變更預設主機群組。

1. 按一下&#x200B;**[!UICONTROL 「建立集合」]**。

1. (依條件) 建立 (或更新) 集合時，從&#x200B;**[!UICONTROL 「環境」]**&#x200B;篩選器中選擇一個環境，以便預覽該環境中的集合內容。依照預設，會顯示預設主機群組的結果。

   ![建立集合](/help/c-recommendations/c-products/assets/CreateCollection.png)

1. 輸入集合的&#x200B;**[!UICONTROL 名稱]**。

   您也可以輸入選填的&#x200B;**[!UICONTROL 說明]**。

1. 設定用來建立集合的規則。

   例如，您的集合可能根據清單中的產品 ID 或類別、利潤或任何其他參數建立。

   您可以新增規則，以使用多個參數來定義集合。多個規則會與AND運算子連結。 所有指定的規則必須符合，才會套用集合。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 使用進階搜尋建立集合

您也可以使用[目錄搜尋](/help/c-recommendations/c-products/catalog-search.md#save-as)頁面上的進階搜尋 ([!UICONTROL Recommendations] > [!UICONTROL 目錄搜尋] > [!UICONTROL 進階搜尋])，以建立集合。

![另存為對話框](/help/c-recommendations/c-products/assets/save-as.png)

例如，使用 &quot;id > contains&quot; 建立搜尋之後，您就可以按一下[!UICONTROL 「另存新檔] > [!UICONTROL 集合」]。

>[!IMPORTANT]
>
>「進階搜尋」功能不區分大小寫，不過傳送時傳回的產品會以區分大小寫的搜尋為依據。此不相符的情況可能導致混淆。使用「進階搜尋」功能來根據結果建立集合時，務必注意大小寫。例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您之後建立一個目錄，目的要傳回包含 &quot;holiday&quot; 的產品，則只會傳回包含 &quot;holiday&quot; 的產品。不會傳回包含 &quot;Holiday&quot; 的產品。

## 在Recommendations活動中使用系列

1. 使用上述其中一種方法建立系列。

1. 按一 **[!UICONTROL 下「活]** 動」 [並建立新的Recommendations活動](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md) ，或編輯現有活動。

1. 在「體 **[!UICONTROL 驗]** 」頁面（三部分引導式工作流程的步驟2）上，按一下您放置建議的位置，然後按一下「變更 **[!UICONTROL 系列」]**。

   ![變更系列選項](/help/c-recommendations/c-products/assets/change-collection.png)

1. 在「新增 **[!UICONTROL 系列」頁面]** ，然後選取所要的系列。

## Training video: Create collections and exclusions in Recommendations (7:05) ![Tutorial badge](/help/assets/tutorial.png)

此影片包含下列資訊:

* 建立集合
* 建立排除項目

>[!VIDEO](https://video.tv.adobe.com/v/27689)