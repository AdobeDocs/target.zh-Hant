---
keywords: 排除項目
description: 瞭解如何在Adobe Target Recommendations中建立排除，以防止建議訪客使用產品或內容。
title: 如何在Recommendations活動中使用排除？
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 44%

---


# 排除項目{#exclusions}。

在[!DNL Adobe Target Recommendations]中建立排除，以防止建議訪客使用產品或內容。 排除是不應建議給訪客的產品或內容子集。

整個帳戶都可使用排除。 不同於在建立[!UICONTROL Recommendations]活動時為每個體驗指定特定系列的系列，排除項目會套用至帳戶中的所有活動。 在建立活動期間，沒有指定排除群組的選項。

您使用排除的一些範例包括：

* 已中止的產品
* 秋季／冬季目錄現在是唯一應該線上上顯示的目錄。 夏季型錄中的任何項目都無法再購買。
* 在大部分頁面／螢幕上（成人產品、NC-17影片等）可能不適合建議的項目
* 含有不完整中繼資料欄位的產品（遺失縮圖、價格或其他重要中繼資料）
* 不應建議的產品（系統中可能存在某種產品的SKU，但它不是可購買的項目，或是QA團隊模擬購買而不實際訂購某些產品的假SKU等）

>[!IMPORTANT]
>
>靜態和動態排除規是可協助您從事行銷活動的強大功能。如需詳細資訊、範例和使用案例，請參閱[使用動態和靜態包含規則](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)。

## 建立排除項目

1. 按一下&#x200B;**[!UICONTROL 「Recommendations]** > **[!UICONTROL 排除項目」]**，顯示現有排除項目的清單。

   ![](assets/exclusions_list.png)

   [!UICONTROL 「排除項目」]清單檢視上各排除項目顯示的「項目數量」，為預設 Recommendations [主機群組](/help/administrating-target/hosts.md) (環境) 內符合該排除項目規則的產品數量。請參閱[設定](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)，瞭解如何變更預設主機群組。

1. 按一下&#x200B;**[!UICONTROL 「建立排除項目」]**。

1. (依條件) 建立 (或更新) 排除項目時，從&#x200B;**[!UICONTROL 「環境」]**&#x200B;篩選器中選擇一個環境，以便預覽該環境中的排除項目內容。依照預設，會顯示預設主機群組的結果。

   ![建立排除項目](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. 輸入排除項目&#x200B;**[!UICONTROL 名稱]**，然後選填說明。

1. 使用規則產生器來建立排除項目。

   在「規則」清單中選取參數，選取運算子，然後輸入一或多個值以辨別產品。使用逗號分隔多個值。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 使用進階搜尋建立排除項目

您也可以在[目錄搜尋](/help/c-recommendations/c-products/catalog-search.md#save-as)頁面（[!UICONTROL 建議] > [!UICONTROL 目錄搜尋] > [!UICONTROL 進階搜尋]）上使用[!UICONTROL 進階搜尋]建立排除。

![另存為對話框](/help/c-recommendations/c-products/assets/save-as.png)

例如，使用「id > contains」建立搜尋之後，您就可以按一下[!UICONTROL 「另存新檔] > [!UICONTROL 排除項目」]。

>[!IMPORTANT]
>
>[!UICONTROL 進階搜尋]功能不區分大小寫；不過，在傳送時傳回的產品會以區分大小寫的搜尋為基礎。 此不相符的情況可能導致混淆。使用「進階搜尋」功能來根據結果建立排除項目時，務必注意大小寫。例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您接著建立排除項目而希望排除含有 &quot;holiday&quot; 的產品，則只會排除含有 &quot;holiday&quot; 的產品。不會排除含有 &quot;Holiday&quot; 的產品。

## 編輯、複製或刪除排除項目

將滑鼠指標暫留在清單中所要的排除項目上，然後按一下適當的圖示：編輯、複製或刪除。

![排除的暫留圖示](/help/c-recommendations/c-products/assets/hover-exclusions.png)

您可以複製現有的排除，以建立重複的排除，然後您可加以修改。 這可讓您以更輕鬆的方式建立類似的排除。

請注意，整個帳戶都有排除項目。 在刪除排除前，請務必考慮這一點。 無法刪除排除。

## 訓練影片：在Recommendations中建立系列和排除(7:05)![教學課程標章](/help/assets/tutorial.png)

此影片包含下列資訊:

* 建立集合
* 建立排除項目

>[!VIDEO](https://video.tv.adobe.com/v/27689)