---
keywords: Recommendations；選件；預覽；啟動；狀態；條件；演算法
description: '了解如何在啟動活動之前預覽Adobe [!DNL Target] Recommendations活動，以確保結果可用。 '
title: 如何預覽和啟動Recommendations活動？
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: f4972f04906cb3476f50abedd6cec847e015daf9
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 17%

---

# 預覽和啟動 Recommendations 活動

建立包含[Recommendations選件](/help/c-recommendations/recommendations-as-an-offer.md)的[!UICONTROL Recommendations]、[!UICONTROL A/B測試]或[!UICONTROL 體驗鎖定目標](XT)活動（選件）之後，您將要預覽建議，以確保在啟動活動之前結果可供使用。 [!DNL Target Recommendations] 提供多種預覽建議的方式。

## 檢查Recommendations演算法狀態

建立活動後，[!DNL Recommendations]會執行演算法以產生建議。 此演算法可能需要數小時的時間才能執行。

您可以在[!UICONTROL Activity]概觀圖中檢查演算法是否已完成執行，其中會列出條件狀態。 下圖顯示[!DNL Recommendations]活動之[!UICONTROL 概述]頁面上的活動圖表狀態：

![Recommendations活動概覽頁面](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

下圖描述[!UICONTROL A/B測試]或XT活動的[!UICONTROL 概述]頁面上的狀態：

![A/B測試概覽頁面](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

狀態結果包括下列項目，如下所示：

* &#x200B;[!UICONTROL 可用結果]:指出演算法已傳回結果
* &#x200B;[!UICONTROL 結果未就緒]:指出演算法尚未完成執行。
* &#x200B;[!UICONTROL 摘要失敗]:指出無法擷取自訂條件摘要檔案。

![結果對話框](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 演算法要執行多久？

儲存包含條件的活動後，[!DNL Target]會根據選取的集合、條件、設計和促銷活動來計算建議。 執行此計算需要一些時間，且時間範圍會根據選取的建議邏輯、資料範圍、目錄中的項目數、客戶已產生的行為資料量，以及選取的行為資料來源而有所差異。

行為資料來源對處理時間有最大的影響，如下所示:

### mbox

如果選取 mbox 做為行為資料來源，建立後，條件會立即執行。根據使用的行為資料數量和目錄大小，演算法最多可能需 12 小時來執行。變更條件設定通常會導致演算法重新執行。視所做的變更而定，在重新執行完成之前，可能無法使用先前計算的建議，或對於較大的變更，只有備份或預設內容可供在重新執行完成之前使用。 如果沒有修改演算法，[!DNL Target] 則會根據所選的資料範圍每隔 12 到 48 小時自動執行。

### Adobe Analytics

如果條件使用 [!DNL Adobe Analytics] 做為行為資料來源，建立後，條件可用時間會根據其他條件是否已使用選取的報表套裝和回顧期間而定。

* **一次性報表套裝設定**: 報表套裝第一次搭配指定資料範圍回顧期間使用時，[!DNL Target Recommendations] 可能需要二到七天才能從 [!DNL Analytics] 完全下載所選報表套裝的行為資料。此時間範圍取決於 [!DNL Analytics] 系統負載。
* **使用已可用報表套裝的新條件或已編輯的條件**:建立新條件或編輯現有條件時，如果選取的報表套裝已搭配使用，且資料範圍等於或小於選取的資料範圍， [!DNL Target Recommendations]資料便可立即使用，且不需要一次性設定。在此情況下，或是在未修改所選報表套裝或資料範圍時已編輯演算法的設定，演算法會在 12 小時內執行或重新執行。
* **現有演算法執行**: 資料會每天從 [!DNL Analytics] 流動到 [!DNL Target Recommendations]。例如，針對[!UICONTROL 已檢視的相關性]建議，當使用者檢視某個產品時，產品檢視追蹤呼叫會以近乎即時的速度傳送到 [!DNL Analytics]。第二天早上，[!DNL Analytics]資料會推送至[!DNL Target]，而[!DNL Target]會在12小時內執行演算法。

>[!NOTE]
>
>[!UICONTROL 最近查看] 的項目不需要離線演算法運行，結果可立即獲得。[!UICONTROL 基] 於mbox [!UICONTROL 資] 料的Top Viewed和Top Sellersal演算法一般會快速產生結果，因為需要更簡單的計算。當您想要預覽設計變更或確認行為資料正確收集時，這些選項可能是不錯的選項。

## 使用QA連結來預覽Recommendations

演算法就緒後，您就可以使用[!DNL Adobe Target]的[QA連結](/help/c-activities/c-activity-qa/activity-qa.md)功能預覽這些結果。 「活動概覽」頁面的[!UICONTROL 「活動QA]」區段中提供QA連結：

![活動 QA 連結](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>依預設，[!DNL Target]會自動將您新增至QA連結的必要對象。 如果此設定已關閉，且您的活動有鎖定目標規則，則您的使用者設定檔必須符合這些鎖定目標規則，才能查看包含建議的體驗。

使用QA連結可讓您在頁面上預覽建議：

![精選產品](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Target QA模式是「自黏」，並儲存在Cookie中。 如果您沒有退出QA模式，您會持續在整個網站看到QA結果。 若要退出QA模式，請使用[書籤小程式](/help/c-activities/c-activity-qa/activity-qa-bookmark.md)。
   >
   >
* 在QA模式下，瀏覽網站不會影響設定檔的[!UICONTROL 最近查看的項目]或[!UICONTROL 最近購買的項目]。 這種行為是設計性的，以避免生產行為資料的無意污染。 若要預覽來自[!UICONTROL 最近查看的項目]或[!UICONTROL 使用者型Recommendations]條件的結果，請先在QA模式之外瀏覽網站，然後使用相同的工作階段開啟QA模式連結。


## 使用CSV下載預覽建議

在某些情況下，您可能會想要稽核建議的特定項目。 若使用[!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]演算法，這個方法特別實用，因為根據使用者目前檢視的項目，建議使用不同的項目集，而您的目錄中可能有數千或數百萬個不同的項目。

在活動中至少顯示一個演算法的[!UICONTROL 「結果就緒」]狀態之前，無法下載結果。

若要下載預覽結果，請按一下「活動概覽」頁面右上角的功能表圖示，然後按一下「下載資料&#x200B;****」。

![下載資料選項](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

下載CSV檔案。 開啟它以查看建議的項目：

![建議項目CSV檔案](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

從左至右是建議項目的清單，此例中檢視頻率最高。 建議會依環境分隔，在此情況下，只有生產環境有建議。 對於此演算法，我們並未根據索引鍵值套用任何限制，因此標示為星號(*)的列包含完整的建議集。 對於根據鍵值的其他演算法類型，例如[!UICONTROL 瀏覽過此項目、已檢視其]的人，鍵值（即&quot;This&quot;項目）會列在最左側的欄中，而建議的項目（即&quot;That&quot;項目）會從左至右列在Recommendation_X欄中。

>[!NOTE]
>
>包含[!UICONTROL 使用者型Recommendations]演算法的活動無法使用結果下載。 使用[!UICONTROL 最近查看的項目]建議邏輯的條件無法使用結果下載。

## 啟用Recommendations活動

從[!UICONTROL 活動概覽]標籤中，按一下狀態旁的下拉式箭頭，然後選取&#x200B;**[!UICONTROL 啟動]**。

![啟動選項](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

請注意，狀態會變成[!UICONTROL Activating]:

![啟動](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

幾秒後，狀態會切換為[!UICONTROL Live]:

![現時](/help/c-recommendations/t-create-recs-activity/assets/live.png)

請注意，您也可以使用相同的下拉式清單來停用或封存活動。

## 避免變更Recommendations設定時發生中斷

在即時活動中變更[!DNL Recommendations]集合、條件、促銷活動或設計設定，可能會導致演算法結果無效，而演算法的狀態會變更為[!UICONTROL 結果未就緒]。

為避免中斷已上線活動，建議在修改已上線活動時採取下列方法：

1. 複製您要修改的活動和條件。
1. 變更重複的活動和條件，並等待演算法產生結果。
1. 預覽新的已修改活動，並確認結果已視需要。
1. 啟動新活動。
1. 停用舊活動。

如果您需要保留相同活動的歷史報表結果，則可能採用替代方法，這可能導致建議可用性暫時中斷：

1. 複製您要修改的活動和條件。
1. 變更重複的活動和條件，並等待演算法產生結果。
1. 預覽新的已修改活動，並確認結果已視需要。
1. 暫停現有活動，並將設定/條件交換至新條件。
1. 預覽現有活動，並確認結果如需要。
1. 重新啟動活動。
