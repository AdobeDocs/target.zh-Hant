---
keywords: 集合;鎖定目標
description: 瞭解如何在Adobe中使用集合 [!DNL Target] Recommendations。 集合是符合建議資格的一組產品或項目。
title: 如何在Recommendations活動中使用收藏？
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 59%

---

# ![PREMIUM](/help/main/assets/premium.png) 集合

集合是符合建議資格的一組產品或項目。通過指定要成為集合一部分的項目必須滿足的條件來定義集合。

集合通常是指一組相似或相關的項目，例如單一產品集合。但是，您可以將任何對您的業務有意義的項目分組到類別中，例如特定價格範圍的產品或顏色或在特定地理區域可能感興趣的項目。

請使用集合以在邏輯分組中組織產品。例如，如果某些項目在一個區域中可用，但在另一個區域中不可用，則可以建立一個集合來排除訪問者區域中不可用的項目。 您也可以使用集合來組織季節性項目，或使用業務上適合的任何其他組織參數。

針對建議內每個條件而產生的[備用建議](/help/main/c-recommendations/c-algorithms/backup-recs.md)也會使用此集合，因此，只有集合中的項目才會納入備用建議中。集合可讓您確保只顯示必須出現在位置中的產品。

每個條件每次執行時皆會重建或更新集合。

您可以將項目分組為目錄，然後為每個集合建立個別的建議。

包含條件的用途類似集合，但必須在您每次建立活動時設定。集合可讓您一次建立一組項目，然後在適當時機派上用場，而不必再次設定。

當您建立或編輯 [!DNL Recommendations] 活動時，集合名稱會出現在活動圖的[!UICONTROL 「條件」]標籤旁。

>[!NOTE]
>
>使用[!UICONTROL 「最近查看的項目」]建議索引鍵時不會套用集合。

## 建立集合 {#task_1256DFF6842141FCAADD9E1428EF7F08}

建立一個集合，以組織要在建議書中顯示的產品或內容。

1. 依序按下&#x200B;**[!UICONTROL 「Recommendations]** > **[!UICONTROL 集合」]**，即可顯示現有集合清單。

   ![集合清單](assets/collections_list.png)

   的 [!UICONTROL 集合] 頁面顯示現有集合的清單。 通過按一下 [!UICONTROL 建立集合] 按鈕 也可以通過懸停在所需集合上並按一下所需表徵圖來編輯、複製和刪除現有集合。

   ![懸停錶徵圖：編輯、複製和刪除](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   [!UICONTROL 「集合」]清單檢視上，每個集合的「項目數量」為設定的預設 Recommendations [主機群組](/help/main/administrating-target/hosts.md) (環境) 中，符合集合規則的產品數量。請參閱 [設定](https://developer.adobe.com/target/implement/recommendations/){target=_blank}以更改預設主機組。

1. 按一下&#x200B;**[!UICONTROL 「建立集合」]**。

1. (依條件) 建立 (或更新) 集合時，從&#x200B;**[!UICONTROL 「環境」]**&#x200B;篩選器中選擇一個環境，以便預覽該環境中的集合內容。依照預設，會顯示預設主機群組的結果。

   ![建立集合](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. 輸入集合的&#x200B;**[!UICONTROL 名稱]**。

   您也可以輸入選填的&#x200B;**[!UICONTROL 說明]**。

1. 設定用來建立集合的規則。

   例如，您的集合可能根據清單中的產品 ID 或類別、利潤或任何其他參數建立。

   您可以新增規則，以使用多個參數來定義集合。多個規則與AND運算子相聯。 所有指定的規則必須符合，才會套用集合。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 使用進階搜尋建立集合

您也可以使用[目錄搜尋](/help/main/c-recommendations/c-products/catalog-search.md#save-as)頁面上的進階搜尋 ([!UICONTROL Recommendations] > [!UICONTROL 目錄搜尋] > [!UICONTROL 進階搜尋])，以建立集合。

![另存為對話框](/help/main/c-recommendations/c-products/assets/save-as.png)

例如，使用 &quot;id > contains&quot; 建立搜尋之後，您就可以按一下[!UICONTROL 「另存新檔] > [!UICONTROL 集合」]。

>[!IMPORTANT]
>
>「進階搜尋」功能不區分大小寫，不過傳送時傳回的產品會以區分大小寫的搜尋為依據。此不相符的情況可能導致混淆。使用「進階搜尋」功能來根據結果建立集合時，務必注意大小寫。例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您之後建立一個目錄，目的要傳回包含 &quot;holiday&quot; 的產品，則只會傳回包含 &quot;holiday&quot; 的產品。不會傳回包含 &quot;Holiday&quot; 的產品。

## 編輯、複製或刪除集合

將滑鼠懸停在清單中所需的集合上，然後按一下相應的表徵圖：編輯、複製或刪除。

![收藏的懸停錶徵圖](/help/main/c-recommendations/c-products/assets/hover-collections.png)

您可以複製現有集合以建立重複的集合，然後可以修改該集合。 這樣，您就可以以較少的工作量建立類似的排除。

請注意，整個帳戶都有收帳。 請確保在刪除集合之前考慮此問題。 無法恢復已刪除的集合。

## 在Recommendations活動中使用集合

1. 使用上述方法之一建立集合。

1. 按一下 **[!UICONTROL 活動]** 和 [建立了新的Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) 或編輯現有活動。

1. 在選取標準和設計後， [!UICONTROL 選項] 頁面。

   ![選擇集合選項](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. （條件）要更改現有集合設定，請在 **[!UICONTROL 體驗]** 頁面（三部分指導工作流的步驟2），按一下放置建議的位置，按一下 **[!UICONTROL 更改集合]**，然後選擇所需的集合。

   ![「更改集合」選項](/help/main/c-recommendations/c-products/assets/change-collection.png)

## 培訓視頻：在Recommendations建立收藏和排除(7:05) ![教程徽章](/help/main/assets/tutorial.png)

此影片包含下列資訊:

* 建立集合
* 建立排除項目

>[!VIDEO](https://video.tv.adobe.com/v/27689)
