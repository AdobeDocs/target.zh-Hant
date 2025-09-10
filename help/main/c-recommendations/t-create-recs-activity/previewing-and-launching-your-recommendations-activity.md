---
keywords: Recommendations；選件；預覽；啟動；狀態；條件；演演算法
description: 瞭解如何預覽Adobe [!DNL Target] Recommendations活動，以確保在啟動活動之前結果可用。
title: 如何預覽和啟動Recommendations活動？
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 26b0c5455e82014dab92c925ecc88bddb3947d2f
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 15%

---

# 預覽和啟動推薦活動

在您建立包含[!UICONTROL Recommendations]Recommendations選件[!UICONTROL A/B Test]的[!UICONTROL Experience Targeting]、[或](/help/main/c-recommendations/recommendations-as-an-offer.md) (XT)活動後，您將會想要預覽您的建議，以確保在啟動活動之前結果可用。 [!DNL Target Recommendations]提供多種預覽建議的方式。

## 正在檢查Recommendations演演算法狀態

建立活動後，[!DNL Recommendations]會執行演演算法以產生建議。 此演演算法可能需要幾個小時的時間才能執行。

您可以檢查演演算法是否已在[!UICONTROL Activity]概觀圖表中完成執行，其中會列出條件狀態。 下圖顯示[!DNL Recommendations]活動[!UICONTROL Overview]頁面上的活動圖表狀態：

![Recommendations活動概觀頁面](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

狀態結果包括下列專案，如下所示：

* [!UICONTROL Results Ready]：表示演演算法已傳回結果
* [!UICONTROL Results Not Ready]：表示演演算法尚未完成執行。
* [!UICONTROL Feed Failure]：表示無法擷取自訂條件摘要檔案。

![結果對話方塊](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 演演算法需要多久的時間才能執行？

儲存包含條件的活動後，[!DNL Target]會根據選取的集合、條件、設計和促銷來計算建議。 執行此計算需要一些時間，而時間範圍會根據選取的建議邏輯、資料範圍、目錄中的專案數、客戶已產生的行為資料量，以及選取的行為資料來源而有所不同。

行為資料來源對處理時間有最大的影響，如下所示:

### mbox

如果選取 mbox 做為行為資料來源，建立後，條件會立即執行。根據使用的行為資料數量和目錄大小，演算法最多可能需 12 小時來執行。變更條件設定通常會導致演算法重新執行。根據所做的變更，先前計算的建議在重新執行完成前可能無法使用，或者若是較大的變更，則只有備份或預設內容在重新執行完成前才可使用。 如果沒有修改演算法，[!DNL Target] 則會根據所選的資料範圍每隔 12 到 48 小時自動執行。

### [!DNL Adobe Analytics]

如果條件使用 [!DNL Adobe Analytics] 做為行為資料來源，建立後，條件可用時間會根據其他條件是否已使用選取的報表套裝和回顧期間而定。

* **一次性報表套裝設定**: 報表套裝第一次搭配指定資料範圍回顧期間使用時，[!DNL Target Recommendations] 可能需要二到七天才能從 [!DNL Analytics] 完全下載所選報表套裝的行為資料。此時間範圍取決於 [!DNL Analytics] 系統負載。
* **使用已可取得之報表套裝的全新或已編輯的條件**：建立新條件或編輯現有條件時，如果選取的報表套裝已搭配[!DNL Target Recommendations]使用，且資料範圍等於或小於選取的資料範圍，資料即可立即使用且不需要一次性設定。 在此情況下，或是在未修改所選報表套裝或資料範圍時已編輯演算法的設定，演算法會在 12 小時內執行或重新執行。
* **現有演算法執行**: 資料會每天從 [!DNL Analytics] 流動到 [!DNL Target Recommendations]。例如，針對[!UICONTROL Viewed Affinity]建議，當使用者檢視產品時，產品檢視追蹤呼叫會以近乎即時的速度傳遞到[!DNL Analytics]。 [!DNL Analytics]資料會在隔天很早推送到[!DNL Target]，[!DNL Target]會在12小時內執行演演算法。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items]不需要執行離線演演算法，結果立即可用。 以mbox資料為基礎的[!UICONTROL Top Viewed]和[!UICONTROL Top Sellers]演演算法通常可快速產生結果，因為所需的運算較簡單。 當您想要預覽設計變更或確認行為資料正在正確收集時，這些可能是很好的選項。

## 使用QA連結來預覽建議

演演算法有結果可供使用後，您可以使用[的](/help/main/c-activities/c-activity-qa/activity-qa.md)QA連結[!DNL Adobe Target]功能來預覽這些結果。 QA連結可在[!UICONTROL Activity Location]概觀頁面的[!UICONTROL Activity]區段中取得：

>[!NOTE]
>
>根據預設，[!DNL Target]會自動將您新增至QA連結的必要對象。 如果此設定關閉，且您的活動具有目標定位規則，則您的使用者設定檔需要符合這些目標定位規則，才能檢視包含建議的體驗。

使用QA連結可讓您預覽頁面上的建議：

![精選產品](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Target QA模式為「粘性」，並儲存在Cookie中。 如果您沒有退出QA模式，您會在整個網站中持續看到QA結果。 若要結束QA模式，請使用[書籤小程式](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md)。
>
>* 在QA模式中，瀏覽網站將不會影響設定檔的[!UICONTROL Recently Viewed Items]或[!UICONTROL Recently Purchased Items]。 這種行為是透過設計進行的，以避免生產行為資料的無意汙染。 若要預覽來自[!UICONTROL Recently Viewed Items]或[!UICONTROL User-Based Recommendations]條件的結果，請先在QA模式之外瀏覽網站，然後使用相同的工作階段來開啟QA模式連結。

## 使用CSV下載檔案來預覽建議

在某些情況下，您可能會想要稽核建議的特定專案。 這在使用[!UICONTROL People Who Viewed This, Viewed That]之類的演演算法時特別有用，因為根據使用者目前檢視的專案，而您可能在目錄中擁有數千或數百萬個不同的專案，因此會建議使用不同的專案集。

在活動中至少顯示一個演演算法的[!UICONTROL Results Ready]狀態之前，無法下載結果。

若要下載結果以進行預覽，請按一下活動概觀頁面右上角的功能表圖示，然後按一下&#x200B;**[!UICONTROL Download data]**。

![下載資料選項](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

下載CSV檔案。 開啟它以檢視建議專案：

![建議專案CSV檔案](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

從左到右是建議專案清單，此例中是檢視次數最多的專案。 建議會依環境分隔，在此情況下，只有生產環境有建議。

如果一列的第一個值是星號(*)，則表示[備份專案](/help/main/c-recommendations/c-algorithms/backup-recs.md)。 如果設計中並非所有位置都能由演演算法（條件）的建議專案填滿，則會顯示備份專案。

對於以索引鍵值為基礎的其他演演算法型別（例如[!UICONTROL People Who Viewed This, Viewed That]），索引鍵值（即「此」專案）會列在最左側的欄中，而建議專案（即「該」專案）則會從Recommendation_X欄中的由左至右列出。

>[!NOTE]
>
>包含[!UICONTROL User-Based Recommendations]演演算法的活動無法使用結果下載。 無法使用[!UICONTROL Recently-Viewed Items]建議邏輯的條件下載結果。

### 基於人氣和金鑰的演演算法的CSV下載格式 {#format}

CSV下載檔案會一致地反映後端條件執行後產生的結果。

* **若為基於人氣的演演算法（非基於金鑰），檔案包含：**

   * 前置詞為* （星號）的備份建議列
   * 根據演演算法設定列出建議的獨立列

* **對於金鑰式演演算法，檔案包含：**

   * 與熱門程度演演算法類似的備份列
   * 鍵值格式的多列，其中第一個專案是鍵的產品ID，後面是代表建議候選人的逗號分隔產品ID

## 啟用您的Recommendations活動

從[!UICONTROL Activity Overview]索引標籤，按一下[狀態]下拉式箭頭，然後選取&#x200B;**[!UICONTROL Activate]**。

如果您的[!UICONTROL Recommendations]活動目前處於[!UICONTROL Inactive]狀態，下拉式清單會標示為[!UICONTROL Inactive]。

幾秒鐘到幾分鐘後，狀態會切換為[!UICONTROL Live]。

您也可以使用相同的下拉式清單來停用或封存活動。

## 避免變更Recommendations設定時發生中斷

變更已上線活動中的[!DNL Recommendations]集合、條件、促銷活動或設計設定，可能會導致演演算法結果無效，且演演算法的狀態變更為[!UICONTROL Results Not Ready]。

若要避免中斷已上線的活動，建議在修改已上線的活動時採取下列方法：

1. 複製原始活動（活動1）和您要修改的准則以建立新活動（活動2）。
1. 變更重複的活動（活動2）和條件，並等待演演算法產生結果。
1. 預覽已修改的新活動（活動2），並確認所需結果。
1. 啟動新活動（活動2）。
1. 停用原始活動（活動1）。

如果您需要保留相同活動中的歷史報表結果，則可能有替代方法，這可能會導致建議可用性暫時中斷：

1. 複製原始活動（活動1）和您要修改的准則以建立新活動（活動2）。
1. 變更重複的活動（活動2）和條件，並等待演演算法產生結果。
1. 預覽已修改的新活動（活動2），並確認所需結果。
1. 暫停已修改的新活動（活動2），並將設定/條件交換給原始活動（活動1）。
1. 預覽原始活動（活動1）並確認結果如所需。
1. 重新啟用原始活動（活動1）。
