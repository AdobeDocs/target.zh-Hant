---
keywords: Recommendations；選件；預覽；啟動；狀態；條件；演演算法
description: 瞭解如何預覽Adobe [!DNL Target] Recommendations活動，以確保在啟動活動之前可獲得結果。
title: 如何預覽和啟動Recommendations活動？
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 7732f3af0fd995309035a8a214afd438ab7a1823
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 17%

---

# 預覽和啟動 Recommendations 活動

在您建立您的 [!UICONTROL Recommendations]， [!UICONTROL A/B測試]，或 [!UICONTROL 體驗鎖定] (XT)活動包含 [Recommendations優惠方案](/help/main/c-recommendations/recommendations-as-an-offer.md)，您會想要預覽建議，以確保在啟動活動之前就能取得結果。 [!DNL Target Recommendations] 提供多種預覽建議的方法。

## 檢查Recommendations演演算法狀態

建立活動後， [!DNL Recommendations] 執行演演算法以產生建議。 此演演算法可能需要幾個小時才能執行。

您可以檢查演演算法是否已在中完成執行 [!UICONTROL 活動] 概述圖表，其中列出條件狀態。 下圖顯示上活動圖表的狀態 [!DNL Recommendations] 活動 [!UICONTROL 概觀] 頁面：

![Recommendations活動概觀頁面](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

下圖說明 [!UICONTROL A/B測試] 或XT活動的 [!UICONTROL 概觀] 頁面：

![A/B測試概觀頁面](/help/main/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

狀態結果包括下列專案，如下所示：

* [!UICONTROL 已備妥結果]：表示演演算法已傳回結果
* [!UICONTROL 結果未就緒]：指出演演算法尚未完成執行。
* [!UICONTROL 摘要失敗]：表示無法擷取自訂條件摘要檔案。

![結果對話方塊](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 演演算法需要多久執行？

儲存包含條件的活動後， [!DNL Target] 會根據選取的集合、條件、設計和促銷活動計算建議。 執行此計算需要一些時間，而時間範圍會根據選取的建議邏輯、資料範圍、目錄中的專案數、客戶已產生的行為資料量，以及選取的行為資料來源而有所不同。

行為資料來源對處理時間有最大的影響，如下所示:

### mbox

如果選取 mbox 做為行為資料來源，建立後，條件會立即執行。根據使用的行為資料數量和目錄大小，演算法最多可能需 12 小時來執行。變更條件設定通常會導致演算法重新執行。根據所做的變更，先前計算的建議可能要在重新執行完成後才能使用，或者若是較大的變更，則只有在重新執行完成後才能使用備份或預設內容。 如果沒有修改演算法，[!DNL Target] 則會根據所選的資料範圍每隔 12 到 48 小時自動執行。

### Adobe Analytics

如果條件使用 [!DNL Adobe Analytics] 做為行為資料來源，建立後，條件可用時間會根據其他條件是否已使用選取的報表套裝和回顧期間而定。

* **一次性報表套裝設定**: 報表套裝第一次搭配指定資料範圍回顧期間使用時，[!DNL Target Recommendations] 可能需要二到七天才能從 [!DNL Analytics] 完全下載所選報表套裝的行為資料。此時間範圍取決於 [!DNL Analytics] 系統負載。
* **使用已可取得之報表套裝的全新或編輯條件**：建立新條件或編輯現有條件時，如果所選報表套裝已搭配使用 [!DNL Target Recommendations]，若資料範圍等於或小於所選資料範圍，資料即可立即使用，且不需要一次性設定。 在此情況下，或是在未修改所選報表套裝或資料範圍時已編輯演算法的設定，演算法會在 12 小時內執行或重新執行。
* **現有演算法執行**: 資料會每天從 [!DNL Analytics] 流動到 [!DNL Target Recommendations]。例如，針對[!UICONTROL 已檢視的相關性]建議，當使用者檢視某個產品時，產品檢視追蹤呼叫會以近乎即時的速度傳送到 [!DNL Analytics]。此 [!DNL Analytics] 資料已推送至 [!DNL Target] 隔天早上和 [!DNL Target] 會在12小時內執行演演算法。

>[!NOTE]
>
>[!UICONTROL 最近檢視的專案] 不需要執行離線演演算法，結果立即可用。 [!UICONTROL 最常檢視] 和 [!UICONTROL 最暢銷商品] 由於mbox資料演演算法所需的運算較簡單，因此通常可快速產生結果。 當您想要預覽設計變更或確認行為資料正確收集時，這些可能是很好的選項。

## 使用QA連結預覽Recommendations

在演演算法中有結果準備就緒後，您可以使用預覽這些結果 [QA連結](/help/main/c-activities/c-activity-qa/activity-qa.md) 的功能 [!DNL Adobe Target]. QA連結可在 [!UICONTROL 活動QA] 活動概觀頁面的區段：

![活動 QA 連結](/help/main/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>依預設， [!DNL Target] 自動將您新增至QA連結的必要對象。 如果此設定關閉，且您的活動具有鎖定目標規則，則您的使用者設定檔需要符合這些鎖定目標規則，才能檢視包含建議的體驗。

使用QA連結可讓您預覽頁面上的建議：

![精選產品](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Target QA模式為「粘性」且儲存在Cookie中。 如果您沒有退出QA模式，您會在整個網站中持續看到QA結果。 若要結束QA模式，請使用 [小書籤](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* 在QA模式中，瀏覽網站將不會影響您的設定檔 [!UICONTROL 最近檢視的專案] 或 [!UICONTROL 最近購買的專案]. 這種行為是透過設計進行的，以避免生產行為資料無意造成的汙染。 若要預覽結果，請執行下列動作： [!UICONTROL 最近檢視的專案] 或 [!UICONTROL 以使用者為基礎的Recommendations] 條件，首先在QA模式之外瀏覽網站，然後使用相同工作階段來開啟QA模式連結。


## 使用CSV下載專案預覽建議

在某些情況下，您可能想要稽核建議的特定專案。 這在使用如的演演算法時特別實用 [!UICONTROL 瀏覽過此專案、也瀏覽了其他專案的使用者]：根據使用者目前檢視的專案，建議不同的專案集，而您的目錄中可能有數千或數百萬個不同的專案。

結果要等到 [!UICONTROL 已備妥結果] 至少會針對活動中的一個演演算法顯示狀態。

若要下載結果以供預覽，請按一下「活動概覽」頁面右上角的功能表圖示，然後按一下 **[!UICONTROL 下載資料]**.

![下載資料選項](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

下載CSV檔案。 開啟它以檢視建議專案：

![建議專案CSV檔案](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

從左到右是建議專案清單，在此案例中是檢影片率最高的專案。 建議會依環境分隔，在此情況下，只有生產環境有建議。 對於此演演算法，我們尚未根據索引鍵值套用任何限制，因此標示為星號(*)的列包含完整的建議集。 針對其他根據索引鍵值的演演算法型別，例如 [!UICONTROL 瀏覽過此專案、也瀏覽了其他專案的使用者]，機碼值（即「This」專案）會列在最左側的欄中，而建議專案（即「That」專案）則會從Recommendation_X欄的左至右列出。

>[!NOTE]
>
>包含下列專案的活動無法下載結果： [!UICONTROL 以使用者為基礎的Recommendations] 演演算法。 無法使用條件下載結果 [!UICONTROL 最近檢視的專案] 建議邏輯。

## 啟用您的Recommendations活動

從 [!UICONTROL 活動概覽] 索引標籤中，按一下狀態旁邊的下拉箭頭，然後選取 **[!UICONTROL 啟動]**.

![啟用選項](/help/main/c-recommendations/t-create-recs-activity/assets/activate.png)

請注意，狀態會變成 [!UICONTROL 啟用]：

![啟動](/help/main/c-recommendations/t-create-recs-activity/assets/activating.png)

幾秒鐘到幾分鐘後，狀態會切換為 [!UICONTROL 即時]：

![現時](/help/main/c-recommendations/t-create-recs-activity/assets/live.png)

請注意，您也可以使用相同的下拉式清單來停用或封存活動。

## 避免變更Recommendations設定時發生中斷

變更 [!DNL Recommendations] 上線活動中的集合、條件、促銷活動或設計設定可能會導致演演算法結果無效，且演演算法的狀態會變更為 [!UICONTROL 結果未就緒].

為避免中斷已上線的活動，我們建議在修改已上線的活動時採取下列方法：

1. 複製原始活動（活動1）和您要修改的條件以建立新活動（活動2）。
1. 變更重複的活動（活動2）和條件，並等待演演算法產生結果。
1. 預覽已修改的新活動（活動2），並確認結果符合預期。
1. 啟動新活動（活動2）。
1. 停用原始活動（活動1）。

如果您需要在相同活動中保留歷史報表結果，則可能有替代方法，這可能會對建議可用性造成暫時性中斷：

1. 複製原始活動（活動1）和您要修改的條件以建立新活動（活動2）。
1. 變更重複的活動（活動2）和條件，並等待演演算法產生結果。
1. 預覽已修改的新活動（活動2），並確認結果符合預期。
1. 暫停已修改的新活動（活動2），並將設定/條件交換為原始活動（活動1）。
1. 預覽原始活動（活動1）並確認結果符合預期。
1. 重新啟用原始活動（活動1）。
