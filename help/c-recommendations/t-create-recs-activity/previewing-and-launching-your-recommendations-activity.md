---
keywords: Recommendations;offer;preview;launch;status;criteria；算法
description: '瞭解如何在啟動Adobe之前預覽您的Recommendations [!DNL Target] 活動，以確保結果可用。 '
title: 如何預覽和啟動Recommendations活動？
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 17%

---

# 預覽並啟動您的Recommendations活動

在您建立包含[Recommendations選件](/help/c-recommendations/recommendations-as-an-offer.md)的[!UICONTROL Recommendations]、[!UICONTROL A/B測試]或[!UICONTROL 體驗定位](XT)活動後，您會想要預覽建議，以確保在啟動活動前有結果可供使用。 [!DNL Target Recommendations] 提供多種方式來預覽建議。

## 檢查Recommendations算法狀態

建立活動後，[!DNL Recommendations]會執行演算法以產生建議。 此演算法可能需要數小時才能執行。

您可以在[!UICONTROL Activity]概觀圖中檢查演算法是否已完成，其中列出了條件狀態。 下圖顯示[!DNL Recommendations]活動[!UICONTROL 概述]頁面上的活動圖中的狀態：

![Recommendations活動概述頁面](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

下圖描述[!UICONTROL A/B Test]或XT活動的[!UICONTROL 概述]頁面的狀態：

![A/B測試概述頁面](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

狀態結果包括下列項目，如下所示：

* [!UICONTROL 結果就緒]:指出演算法已傳回結果
* [!UICONTROL 結果未就緒]:表示演算法尚未完成執行。
* [!UICONTROL 摘要失敗]:指出無法擷取自訂條件饋送檔案。

![結果對話框](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 演算法要執行多久？

儲存包含條件的活動後，[!DNL Target]會根據選取的系列、條件、設計和促銷來計算建議。 此計算需要一些時間執行，而且時間範圍會根據選取的建議邏輯、資料範圍、型錄中的項目數、客戶產生的行為資料量以及選取的行為資料來源而有所不同。

行為資料來源對處理時間有最大的影響，如下所示:

### mbox

如果選取 mbox 做為行為資料來源，建立後，條件會立即執行。根據使用的行為資料數量和目錄大小，演算法最多可能需 12 小時來執行。變更條件設定通常會導致演算法重新執行。視所做的變更而定，先前計算的建議可能在重新執行完成之前無法使用，或對於較大的變更，只有備份或預設內容可在重新執行完成之前使用。 如果沒有修改演算法，[!DNL Target] 則會根據所選的資料範圍每隔 12 到 48 小時自動執行。

### Adobe Analytics

如果條件使用 [!DNL Adobe Analytics] 做為行為資料來源，建立後，條件可用時間會根據其他條件是否已使用選取的報表套裝和回顧期間而定。

* **一次性報表套裝設定**: 報表套裝第一次搭配指定資料範圍回顧期間使用時，[!DNL Target Recommendations] 可能需要二到七天才能從 [!DNL Analytics] 完全下載所選報表套裝的行為資料。此時間範圍取決於 [!DNL Analytics] 系統負載。
* **使用現有報表套裝新增或編輯的准則**:建立新准則或編輯現有准則時，如果選取的報表套裝已與之搭配使用 [!DNL Target Recommendations]，且資料範圍等於或小於選取的資料範圍，則資料會立即可用，而不需要單次設定。在此情況下，或是在未修改所選報表套裝或資料範圍時已編輯演算法的設定，演算法會在 12 小時內執行或重新執行。
* **現有演算法執行**: 資料會每天從 [!DNL Analytics] 流動到 [!DNL Target Recommendations]。例如，針對[!UICONTROL 已檢視的相關性]建議，當使用者檢視某個產品時，產品檢視追蹤呼叫會以近乎即時的速度傳送到 [!DNL Analytics]。[!DNL Analytics]資料會在第二天早上推送至[!DNL Target]，而[!DNL Target]在少於12小時內執行演算法。

>[!NOTE]
>
>[!UICONTROL 「最近檢視] 的項目」不需要執行離線演算法，而且結果可立即使用。[!UICONTROL 基於] mbox資料 [!UICONTROL 的Top ] Viewed和Top Sellersals算法通常會因為運算更簡單而快速產生結果。當您想要預覽設計變更或確認行為資料已正確收集時，這些選項可能很好。

## 使用QA連結預覽Recommendations

演算法結果就緒後，您可以使用[!DNL Adobe Target]的[QA連結](/help/c-activities/c-activity-qa/activity-qa.md)功能預覽這些結果。 「活動概述」頁的[!UICONTROL Activity QA]部分提供QA連結：

![活動 QA 連結](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>依預設，[!DNL Target]會自動將您新增至QA連結的必要對象。 如果此設定已關閉，而您的活動有定位規則，則您的使用者設定檔必須符合這些定位規則，才能查看包含建議的體驗。

使用QA連結可讓您預覽頁面上的建議：

![精選產品](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* 目標QA模式是「自黏」，並儲存在Cookie中。 如果您未退出QA模式，您會持續看到整個網站的QA結果。 若要退出QA模式，請使用[書籤小工具](/help/c-activities/c-activity-qa/activity-qa-bookmark.md)。
   >
   >
* 在QA模式下，瀏覽網站不會影響您個人資料的[!UICONTROL 最近檢視的項目]或[!UICONTROL 最近購買的項目]。」 這種行為是設計為避免生產行為資料的無意污染。 若要預覽[!UICONTROL 最近檢視的項目]或[!UICONTROL 使用者導向的Recommendations]准則的結果，請先瀏覽QA模式以外的網站，然後使用相同的作業來開啟QA模式連結。


## 使用CSV下載來預覽建議

在某些情況下，您可能會想要審核建議的特定項目。 當使用[!UICONTROL 「檢視過此項目的人」、「檢視過的人」等演算法時，這特別有用，因為建議使用不同的項目集，視使用者目前檢視的項目而定，而您的目錄中可能有數千或數百萬個不同的項目。]

在活動中至少顯示一個演算法的[!UICONTROL Results Ready]狀態之前，無法下載結果。

若要下載預覽結果，請按一下「活動概述」頁面右上角的功能表圖示，然後按一下「下載資料&#x200B;**[!UICONTROL 」。]**

![下載資料選項](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

下載CSV檔案。 開啟它以檢視建議的項目：

![建議的項目CSV檔案](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

從左至右是建議項目的清單，在此例中，檢視頻率最高。 建議依環境區隔，在本例中，只有生產環境有建議。 對於此演算法，我們並未根據索引鍵值套用任何限制，因此標有星號(*)的列包含完整的建議集。 對於基於關鍵值的其他演算法類型，例如[!UICONTROL 檢視過此、檢視過該]，關鍵值（即&quot;This&quot;項目）會列在最左側的欄中，而建議項目（即&quot;That&quot;項目）則會在Recommendation_X欄中由左至右列出。

>[!NOTE]
>
>結果下載不適用於包含[!UICONTROL 以使用者為基礎的Recommendations]演算法的活動。 使用[!UICONTROL 最近檢視的項目]建議邏輯的准則無法使用結果下載。

## 激活您的Recommendations活動

在[!UICONTROL 活動概述]標籤中，按一下狀態旁的下拉箭頭，然後選擇&#x200B;**[!UICONTROL 啟動]**。

![啟動選項](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

請注意，狀態變為[!UICONTROL Activating]:

![啟動](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

幾秒到幾分鐘後，狀態將切換到[!UICONTROL Live]:

![現時](/help/c-recommendations/t-create-recs-activity/assets/live.png)

請注意，您也可以使用相同的下拉式清單來停用或封存活動。

## 在變更Recommendations設定時避免中斷

變更即時活動中的[!DNL Recommendations]系列、准則、促銷或設計設定，可能會導致演算法結果變成無效，而演算法的狀態會變更為[!UICONTROL 結果未就緒]。

為避免中斷即時活動，建議在修改即時活動時採取下列方法：

1. 複製您要修改的活動和標準。
1. 變更複製的活動和准則，並等待演算法產生結果。
1. 預覽新的已修改活動，並確認結果符合需要。
1. 啟動新活動。
1. 停用舊活動。

如果您需要在相同活動中保留歷史報告結果，則可能會採取其他方法，這可能導致建議可用性暫時中斷：

1. 複製您要修改的活動和標準。
1. 變更複製的活動和准則，並等待演算法產生結果。
1. 預覽新的已修改活動，並確認結果符合需要。
1. 暫停現有活動，並將設定／條件交換至新標準。
1. 預覽現有活動並確認結果符合需求。
1. 重新啟動活動。
