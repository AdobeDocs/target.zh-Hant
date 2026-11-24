---
keywords: 排除項目
description: 瞭解如何在[!DNL Target Recommendations]中建立排除專案，以防止向訪客建議產品或內容。
title: 如何在[!UICONTROL Recommendations]活動中使用排除專案？
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
TQID: 'https://experienceleague.adobe.com/6-PWkqq5eXAwyLcGGbSqSZmFdJa85yU3x7FPNEt8-2o'
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
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%
---
# 排除項目 {#exclusions}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!DNL Adobe Target Recommendations]中建立和管理排除專案，以防止向訪客建議產品或內容。

>[!ENDSHADEBOX]

排除是不建議給訪客的產品或內容子集。 整個帳戶都可以使用排除專案。 與建立[!DNL Recommendations]活動時為每個體驗選取的集合不同，排除套用至帳戶中的所有活動，且在活動建立期間無法指派排除群組。

排除專案通常用於：

* 已停產的產品。
* 目錄中不再可用的專案。 例如，當只有秋季和冬季目錄應該線上上出現時，夏季目錄中的任何專案都不能購買。
* 可能不適合在大多數頁面或熒幕上推薦的專案（成人產品、NC-17電影等）。
* 中繼資料欄位不完整的產品（遺失縮圖、價格或其他重要中繼資料）。
* 不應建議使用的產品，例如存在於系統中但並非可購買專案的SKU，或QA團隊用來模擬購買而不訂購任何東西的虛假SKU。

>[!IMPORTANT]
>
>排除規則會全域套用至所有[環境](/help/main/administrating-target/environments.md)。
>
>如需靜態和動態排除規則的詳細資訊、範例和使用案例，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules)。

## 建立排除項目

排除規則定義一次，然後套用至帳戶中的每個[!DNL Recommendations]活動。

1. 按一下「**[!UICONTROL 建議]** > **[!UICONTROL 排除專案]**」以顯示現有排除專案的清單。

   >[!NOTE]
   >
   >針對&#x200B;**[!UICONTROL 排除專案]**&#x200B;清單檢視中的每個排除專案所報告的「專案數量」，是設定的預設Recommendations [主機群組](/help/main/administrating-target/hosts.md) （環境）內符合該排除專案規則的產品數量。 如需有關如何變更預設主機群組的資訊，請參閱&#x200B;*Adobe Target開發人員指南*&#x200B;中的[計畫和實作 [!DNL Recommendations]](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/recommendations){target=_blank}。


1. 按一下&#x200B;**[!UICONTROL 顯示篩選器]**&#x200B;圖示（![顯示篩選器圖示](/help/main/assets/icons/Filter.svg)），然後從&#x200B;**[!UICONTROL 環境]**&#x200B;下拉式清單中選擇所需的[環境](/help/main/administrating-target/environments.md)，以預覽該環境中排除專案的內容。 依照預設，會顯示預設主機群組的結果。

   ![排除專案頁面，其中已開啟篩選器面板且環境清單](../assets/exclusions_2.png)

1. 按一下&#x200B;**[!UICONTROL 建立排除專案]**。

   ![包含「建立排除專案」按鈕的「排除專案」頁面](../assets/exclusions_1.png)

1. 輸入排除專案&#x200B;**[!UICONTROL 名稱]**。 您也可以輸入選填的說明。

1. 使用規則產生器來定義排除專案。

   Select是&#x200B;**[!UICONTROL 規則]**&#x200B;清單中的引數，請選取運運算元，然後輸入一或多個值以識別產品。 使用逗號分隔多個值。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

1. 按一下清單中所需排除專案旁的「更多動作」圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg)），然後按一下適當的選項： **[!UICONTROL 編輯]**、**[!UICONTROL 複製]**&#x200B;或&#x200B;**[!UICONTROL 刪除]**。

   ![排除專案清單，[更多動作]功能表已開啟，顯示[編輯]、[複製]和[刪除]](../assets/exclusions_3.png)

<!--
## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded.
-->


## 訓練影片：在Recommendations (7:05) ![教學課程徽章](/help/main/assets/tutorial.png)中建立集合和排除專案

此影片包含下列資訊:

* 建立集合
* 建立排除項目

>[!VIDEO](https://video.tv.adobe.com/v/27689)
