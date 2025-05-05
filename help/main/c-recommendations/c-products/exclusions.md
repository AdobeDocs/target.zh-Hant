---
keywords: 排除項目
description: 瞭解如何在 [!DNL Target Recommendations] 中建立排除專案，以防止向訪客建議產品或內容。
title: 如何在[!UICONTROL Recommendations]活動中使用排除專案？
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 14%

---

# 排除項目

在[!DNL Adobe Target Recommendations]中建立排除專案，以防止向訪客建議產品或內容。 排除是不建議給訪客的產品或內容子集。

整個帳戶都可以使用排除專案。 集合是當您建立[!UICONTROL Recommendations]活動時，為每個體驗指定特定的集合，與此不同，排除適用於整個帳戶的所有活動。 活動建立期間沒有指派排除群組的選項。

您使用排除專案的次數範例包括：

* 已停產的產品。
* 秋冬目錄現在是唯一應該線上上顯示的目錄。 Summer目錄中的任何專案都不再提供購買。
* 可能不適合在大多數頁面或熒幕上推薦的專案（成人產品、NC-17電影等）。
* 中繼資料欄位不完整的產品（遺失縮圖、價格或其他重要中繼資料）。
* 不應建議使用的產品（可能系統中已有某專案的SKU，但並非可購買的專案）。 或許QA團隊模擬購買而不實際訂購東西可能是虛假SKU)。

>[!IMPORTANT]
>
>排除規則會全域套用至所有[環境](/help/main/administrating-target/environments.md)。
>
>靜態和動態排除規是可協助您從事行銷活動的強大功能。如需詳細資訊、範例和使用案例，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)。

## 建立排除項目

1. 按一下「**[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]**」以顯示現有排除專案的清單。

   [!UICONTROL Exclusions]清單檢視上各排除專案所報告的「專案數」，為預設Recommendations [主機群組](/help/main/administrating-target/hosts.md) （環境）內符合該排除專案規則的產品數。 如需有關如何變更預設主機群組的資訊，請參閱&#x200B;*Adobe Target開發人員指南*&#x200B;中的[計畫和實作 [!DNL Recommendations]](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/recommendations){target=_blank}。

1. （視條件而定）按一下&#x200B;**[!UICONTROL Show Filters]**&#x200B;圖示（![顯示篩選器圖示](/help/main/assets/icons/Filter.svg) ），然後在建立（或更新）排除專案時，從&#x200B;**[!UICONTROL Environment]**&#x200B;下拉式清單中選擇所需的[環境](/help/main/administrating-target/environments.md)，以預覽該環境中的排除專案內容。 依照預設，會顯示預設主機群組的結果。

1. 按一下 **[!UICONTROL Create Exclusion]**。

1. 輸入排除專案&#x200B;**[!UICONTROL Name]**&#x200B;並輸入選擇性說明。

1. 使用規則產生器來建立排除項目。

   在[!UICONTROL Rules]清單中選取引數、選取運運算元，然後輸入一或多個值以識別產品。 使用逗號分隔多個值。

1. 按一下 **[!UICONTROL Create]**。

<!-- ## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded. -->

## 編輯、複製或刪除排除專案

按一下清單中所需排除專案旁的「更多動作」圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下適當的圖示： [!UICONTROL Edit]、[!UICONTROL Copy]或[!UICONTROL Delete]。

您可以複製現有的排除專案，以建立重複的排除專案，然後進行修改。 此選項可讓您輕鬆建立類似的排除專案。

請注意，整個帳戶都可以使用排除專案。 刪除排除專案前，請務必考量此注意事項。 已刪除的排除專案無法復原。

## 訓練影片：在Recommendations中建立集合和排除專案(7:05) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包含下列資訊:

* 建立集合
* 建立排除項目

>[!VIDEO](https://video.tv.adobe.com/v/27689)
