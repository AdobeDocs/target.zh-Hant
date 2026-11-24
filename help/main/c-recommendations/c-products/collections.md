---
keywords: 集合;鎖定目標
description: 瞭解如何使用[!DNL Target Recommendations]中的產品或專案集合。
title: 如何在Recommendations活動中使用集合？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
TQID: 'https://experienceleague.adobe.com/kdjl2cpjaRWYZRqHFqARHvbTaTuu0iAH7ZWbD2Lrs7o'
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
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 8%
---
# 集合 {#collections}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!DNL Adobe Target Recommendations]中建立、管理及使用專案集合。

>[!ENDSHADEBOX]

集合是符合建議資格的一組產品或項目。 集合是由專案必須符合才能成為其一部分的條件所定義。 專案可以依業務適用的任何方式分組，例如類似或相關的專案、特定價格範圍或顏色的產品，或可能在特定地理區域有趣的專案。

集合將產品組織到邏輯值區中。 例如，如果某些專案在一個區域可用，但在另一個區域不可用，則集合可以排除訪客區域不可用的專案。 集合也可以組織季節性專案，或適用於業務的任何其他組織引數。 專案可以分組到目錄中，然後可以為每個集合建立單獨的建議。

以下幾點說明集合如何與其餘的[!DNL Recommendations]互動：

* 針對每個條件產生的備用建議[&#128279;](/help/main/c-recommendations/c-algorithms/backup-recs.md)也使用集合，因此只有集合中的專案會包含在備用建議中。 因此，只會顯示對某個位置有意義的產品。
* 每個條件每次執行時皆會重建或更新集合。
* 收集規則會套用至執行條件後產生的建議專案。 它們只會影響輸出中的實體建議(ER)，而不會影響索引鍵。
* 使用&#x200B;**[!UICONTROL 最近檢視的專案]**&#x200B;建議索引鍵時不會套用集合。
* 包含條件可產生類似結果，但每次建立活動時都必須設定這些條件。 集合只會建立一次，之後便可以重複使用，無需再次設定。
* 建立或編輯[!DNL Recommendations]活動時，集合名稱會出現在活動圖表的&#x200B;**[!UICONTROL 條件]**&#x200B;標籤旁。

## 建立集合 {#task_1256DFF6842141FCAADD9E1428EF7F08}

集合可在整個帳戶中使用，因此可以在任何[!DNL Recommendations]活動中選取建立一次的集合。 規則是在集合中定義，因此不需要為每個活動再次設定。

1. 按一下&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 集合]**&#x200B;以顯示現有集合清單。

   若要編輯、複製或刪除現有集合，請按一下集合旁的[更多動作]圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下所要的選項。

   >[!NOTE]
   >
   >在&#x200B;**[!UICONTROL 集合]**&#x200B;清單檢視上，每個集合的「專案數量」為設定的預設Recommendations [主機群組](/help/main/administrating-target/hosts.md) （環境）中，符合集合規則的產品數量。 請參閱[設定](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=zh-Hant){target=_blank}，瞭解如何變更預設主機群組。

1. 按一下&#x200B;**[!UICONTROL 建立集合]**。

   具有[建立集合]按鈕的![集合頁面](../assets/collection_1.png)

1. 輸入集合的&#x200B;**[!UICONTROL 名稱]**。 也可以輸入選用的&#x200B;**[!UICONTROL 描述]**。

1. （視條件而定）從&#x200B;**[!UICONTROL 環境]**&#x200B;篩選器中選擇[環境](/help/main/administrating-target/environments.md)以預覽該環境中的集合內容。 依照預設，會顯示預設主機群組的結果。

1. 設定用來建立集合的規則。

   您可以根據產品ID或類別、利潤或清單中的任何其他引數來建立集合。 新增規則以使用多個引數來定義集合。 您可使用AND運運算元聯結多個規則，因此所有指定的規則都必須相符，才會套用集合。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

1. 建立集合後，按一下「更多動作」圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ）並選取適當的選項： **[!UICONTROL 編輯]**、**[!UICONTROL 複製]**&#x200B;或&#x200B;**[!UICONTROL 刪除]**。

   ![已開啟[更多動作]功能表的[集合]清單，顯示[編輯]、[複製]和[刪除]](../assets/collection_2.png)

<!--
## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned.
-->

## 在活動中使用集合

已針對[!DNL Recommendations]活動的每個體驗選取集合。 集合會決定哪些專案符合出現在該體驗的建議中的資格。

1. [建立集合](#task_1256DFF6842141FCAADD9E1428EF7F08)。

   ![使用集合詳細資料和規則區段來建立集合畫面](../assets/collection_3.png)

1. 按一下&#x200B;**[!UICONTROL 活動]**&#x200B;和[建立新的Recommendations活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)或編輯現有的活動。

   在「建立活動」功能表中選取建議的![所有活動頁面](../assets/collection_4.png)

1. 選取條件與設計後，請在&#x200B;**[!UICONTROL 選項]**&#x200B;頁面上選取所需的集合。

1. （視條件而定）若要變更現有活動的集合，請按一下&#x200B;**[!UICONTROL 體驗]**&#x200B;頁面上的建議位置，按一下&#x200B;**[!UICONTROL 變更集合]**，然後選取所要的集合。
