---
keywords: 排除項目
description: 瞭解如何在Adobe中建立排除專案 [!DNL Target] Recommendations可防止向訪客建議產品或內容。
title: 如何在Recommendations活動中使用排除專案？
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 34%

---

# 排除項目

在中建立排除專案 [!DNL Adobe Target Recommendations] 以防止將產品或內容推薦給訪客。 排除是不建議給訪客的產品或內容子集。

整個帳戶都可以使用排除專案。 不像集合，當您建立時，為每個體驗指定特定的集合 [!UICONTROL Recommendations] 活動、排除適用於該帳戶的所有活動。 活動建立期間沒有指派排除群組的選項。

您使用排除專案的次數範例包括：

* 已停產的產品
* 秋冬目錄現在是唯一應該線上上顯示的目錄。 Summer目錄中的任何專案都不再提供購買。
* 可能不宜在大多數頁面/熒幕上推薦的專案（成人產品、NC-17電影等）
* 中繼資料欄位不完整的產品（遺失縮圖、價格或其他重要中繼資料）
* 絕不應該建議使用的產品（可能是系統中某樣東西存在SKU，但並非可購買的專案，或可能是QA團隊模擬購買而不實際訂購某樣東西的虛假SKU等）

>[!IMPORTANT]
>
>排除規則會全域套用至所有環境。
>
>靜態和動態排除規是可協助您從事行銷活動的強大功能。如需詳細資訊、範例和使用案例，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)。

## 建立排除項目

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 排除專案]** 以顯示現有排除專案的清單。

   ![exclusions_list圖片](assets/exclusions_list.png)

   [!UICONTROL 「排除項目」]清單檢視上各排除項目顯示的「項目數量」，為預設 Recommendations [主機群組](/help/main/administrating-target/hosts.md) (環境) 內符合該排除項目規則的產品數量。另請參閱 [設定](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} 變更預設主機群組。

1. 按一下 **[!UICONTROL 建立排除專案]**.

1. （視條件而定）從 **[!UICONTROL 環境]** 在建立（或更新）排除專案時進行篩選，以便預覽該環境中的排除專案內容。 依照預設，會顯示預設主機群組的結果。

   ![建立排除項目](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. 輸入排除專案 **[!UICONTROL 名稱]** 並輸入選擇性說明。

1. 使用規則產生器來建立排除項目。

   在「規則」清單中選取參數，選取運算子，然後輸入一或多個值以辨別產品。使用逗號分隔多個值。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 使用進階搜尋建立排除項目

您也可以使用下列專案來建立排除專案： [!UICONTROL 進階搜尋] 於 [目錄搜尋](/help/main/c-recommendations/c-products/catalog-search.md#save-as) 頁面( [!UICONTROL Recommendations] > [!UICONTROL 目錄搜尋] > [!UICONTROL 進階搜尋])。

![另存新檔對話方塊](/help/main/c-recommendations/c-products/assets/save-as.png)

例如，使用「id > contains」建立搜尋之後，您就可以按一下[!UICONTROL 「另存新檔] > [!UICONTROL 排除項目」]。

>[!IMPORTANT]
>
>此 [!UICONTROL 進階搜尋] 功能不區分大小寫，不過傳送時傳回的產品會以區分大小寫的搜尋為依據。 此不相符的情況可能導致混淆。使用「進階搜尋」功能來根據結果建立排除項目時，務必注意大小寫。例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您接著建立排除項目而希望排除含有 &quot;holiday&quot; 的產品，則只會排除含有 &quot;holiday&quot; 的產品。不會排除含有 &quot;Holiday&quot; 的產品。

## 編輯、複製或刪除排除專案

將游標停留在清單中所需的排除專案上，然後按一下適當的圖示：「編輯」、「複製」或「刪除」。

![排除專案的暫留圖示](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

您可以複製現有的排除專案，以建立重複的排除專案，然後進行修改。 這可讓您輕鬆建立類似的排除專案。

請注意，整個帳戶都可以使用排除專案。 刪除排除專案前，請務必先考量此事項。 已刪除的排除專案無法復原。

## 訓練影片：在Recommendations中建立集合和排除專案(7:05) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包含下列資訊:

* 建立集合
* 建立排除項目

>[!VIDEO](https://video.tv.adobe.com/v/27689)
