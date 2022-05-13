---
keywords: 排除項目
description: 瞭解如何在Adobe中建立排除項 [!DNL Target] Recommendations防止向訪問者推薦產品或內容。
title: 如何在Recommendations活動中使用排除項？
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: db288fbb4ddf011b7051257fdc8126d1158c8469
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 43%

---

# 排除項目

在 [!DNL Adobe Target Recommendations] 防止向訪問者推薦產品或內容。 排除是不應推薦給訪問者的產品或內容的子集。

在整個帳戶中都有排除項。 與集合不同，在建立集合時，您為每個體驗指定特定的集合 [!UICONTROL Recommendations] 活動，排除適用於帳戶中的所有活動。 在建立活動期間，沒有指定排除組的選項。

您使用排除項的一些示例包括：

* 已停產的產品
* 秋季/冬季目錄現在是唯一應線上顯示的目錄。 夏季目錄中的任何物料都不再可供購買。
* 在大多數頁面/螢幕（成人產品、 NC-17電影等）上可能不適宜推薦的項目
* 元資料欄位不完整（缺少縮略圖、價格或其他重要元資料）的產品
* 不應推薦的產品（系統中可能存在某種SKU，但它不是可購買的產品，或者QA團隊模擬購買而不實際訂購某種產品，等等）

>[!IMPORTANT]
>
>排除規則將全局應用於所有環境。
>
>靜態和動態排除規是可協助您從事行銷活動的強大功能。如需詳細資訊、範例和使用案例，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)。

## 建立排除項目

1. 按一下&#x200B;**[!UICONTROL 「Recommendations]** > **[!UICONTROL 排除項目」]**，顯示現有排除項目的清單。

   ![](assets/exclusions_list.png)

   [!UICONTROL 「排除項目」]清單檢視上各排除項目顯示的「項目數量」，為預設 Recommendations [主機群組](/help/main/administrating-target/hosts.md) (環境) 內符合該排除項目規則的產品數量。請參閱[設定](/help/main/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)，瞭解如何變更預設主機群組。

1. 按一下&#x200B;**[!UICONTROL 「建立排除項目」]**。

1. (依條件) 建立 (或更新) 排除項目時，從&#x200B;**[!UICONTROL 「環境」]**&#x200B;篩選器中選擇一個環境，以便預覽該環境中的排除項目內容。依照預設，會顯示預設主機群組的結果。

   ![建立排除項目](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. 輸入排除項目&#x200B;**[!UICONTROL 名稱]**，然後選填說明。

1. 使用規則產生器來建立排除項目。

   在「規則」清單中選取參數，選取運算子，然後輸入一或多個值以辨別產品。使用逗號分隔多個值。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 使用進階搜尋建立排除項目

您還可以使用 [!UICONTROL 高級搜索] 的 [目錄搜索](/help/main/c-recommendations/c-products/catalog-search.md#save-as) 頁(P) [!UICONTROL Recommendations] > [!UICONTROL 目錄搜索] > [!UICONTROL 高級搜索])。

![另存為對話框](/help/main/c-recommendations/c-products/assets/save-as.png)

例如，使用「id > contains」建立搜尋之後，您就可以按一下[!UICONTROL 「另存新檔] > [!UICONTROL 排除項目」]。

>[!IMPORTANT]
>
>的 [!UICONTROL 高級搜索] 功能不區分大小寫；但是，在交付時返回的產品基於區分大小寫的搜索。 此不相符的情況可能導致混淆。使用「進階搜尋」功能來根據結果建立排除項目時，務必注意大小寫。例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您接著建立排除項目而希望排除含有 &quot;holiday&quot; 的產品，則只會排除含有 &quot;holiday&quot; 的產品。不會排除含有 &quot;Holiday&quot; 的產品。

## 編輯、複製或刪除排除

將滑鼠懸停在清單中所需的排除項上，然後按一下相應的表徵圖：編輯、複製或刪除。

![懸停錶徵圖排除](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

您可以複製現有排除，以建立重複的排除，然後可以修改。 這樣，您就可以以較少的工作量建立類似的排除。

請注意，整個帳戶中都有排除項。 請確保在刪除排除之前考慮此問題。 無法恢復已刪除的排除。

## 培訓視頻：在Recommendations建立收藏和排除(7:05) ![教程徽章](/help/main/assets/tutorial.png)

此影片包含下列資訊:

* 建立集合
* 建立排除項目

>[!VIDEO](https://video.tv.adobe.com/v/27689)
