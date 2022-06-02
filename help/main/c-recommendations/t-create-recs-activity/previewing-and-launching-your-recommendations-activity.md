---
keywords: Recommendations；提供；預覽；啟動；狀態；標準；算法
description: '瞭解如何預覽Adobe [!DNL Target] Recommendations活動，以確保在啟動活動前有結果。 '
title: 如何預覽和啟動Recommendations活動？
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 7732f3af0fd995309035a8a214afd438ab7a1823
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 17%

---

# 預覽和啟動 Recommendations 活動

在建立 [!UICONTROL Recommendations]。 [!UICONTROL A/BTest]或 [!UICONTROL 體驗目標] (XT)活動包含 [Recommendations提供](/help/main/c-recommendations/recommendations-as-an-offer.md)，您將希望預覽建議，以確保在啟動活動之前結果可用。 [!DNL Target Recommendations] 提供了多種預覽建議的方法。

## 檢查Recommendations算法狀態

建立活動後， [!DNL Recommendations] 運行生成建議的算法。 此算法可能需要幾個小時才能運行。

您可以檢查算法是否已在 [!UICONTROL 活動] 概述圖，其中列出了條件狀態。 下圖顯示了上的活動圖中的狀態 [!DNL Recommendations] 活動 [!UICONTROL 概述] 頁：

![Recommendations活動概述頁](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

下圖描述了 [!UICONTROL A/BTest] 或XT活動 [!UICONTROL 概述] 頁：

![A/BTest概述頁](/help/main/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

狀態結果包括以下內容，如下所示：

* [!UICONTROL 結果就緒]:指示算法已返回結果
* [!UICONTROL 結果未就緒]:表示算法尚未完成運行。
* [!UICONTROL 饋送失敗]:指示無法檢索自定義條件饋送檔案。

![結果對話框](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 該算法需要多長時間才能運行？

保存包含條件的活動後， [!DNL Target] 根據所選集合、標準、設計和促銷計算建議。 此計算需要一些時間執行，並且時間框架因所選的建議邏輯、資料範圍、目錄中的項數、客戶已生成的行為資料量以及所選行為資料源而異。

行為資料來源對處理時間有最大的影響，如下所示:

### mbox

如果選取 mbox 做為行為資料來源，建立後，條件會立即執行。根據使用的行為資料數量和目錄大小，演算法最多可能需 12 小時來執行。變更條件設定通常會導致演算法重新執行。根據所做的更改，在重新運行完成之前，先前計算的建議案可能不可用，或者對於較大的更改，只有備份或預設內容才可用，直到重新運行完成。 如果沒有修改演算法，[!DNL Target] 則會根據所選的資料範圍每隔 12 到 48 小時自動執行。

### Adobe Analytics

如果條件使用 [!DNL Adobe Analytics] 做為行為資料來源，建立後，條件可用時間會根據其他條件是否已使用選取的報表套裝和回顧期間而定。

* **一次性報表套裝設定**: 報表套裝第一次搭配指定資料範圍回顧期間使用時，[!DNL Target Recommendations] 可能需要二到七天才能從 [!DNL Analytics] 完全下載所選報表套裝的行為資料。此時間範圍取決於 [!DNL Analytics] 系統負載。
* **使用已用報告套件新建或編輯的條件**:建立新條件或編輯現有條件時，如果所選報告套件已與 [!DNL Target Recommendations]如果資料範圍等於或小於選定資料範圍，則資料立即可用，不需要一次性設定。 在此情況下，或是在未修改所選報表套裝或資料範圍時已編輯演算法的設定，演算法會在 12 小時內執行或重新執行。
* **現有演算法執行**: 資料會每天從 [!DNL Analytics] 流動到 [!DNL Target Recommendations]。例如，針對[!UICONTROL 已檢視的相關性]建議，當使用者檢視某個產品時，產品檢視追蹤呼叫會以近乎即時的速度傳送到 [!DNL Analytics]。的 [!DNL Analytics] 資料推送到 [!DNL Target] 第二天早上 [!DNL Target] 在不到12小時內運行算法。

>[!NOTE]
>
>[!UICONTROL 最近查看的項目] 不需要離線算法運行，結果可立即獲得。 [!UICONTROL 已查看的最多] 和 [!UICONTROL 暢銷] 基於mbox資料的算法由於計算量較大，通常計算速度較快。 當您想要預覽設計更改或確認正確收集行為資料時，這些選項可能是不錯的選項。

## 使用QA連結預覽Recommendations

在算法已準備好結果後，可以使用 [QA連結](/help/main/c-activities/c-activity-qa/activity-qa.md) 功能 [!DNL Adobe Target]。 QA連結可在 [!UICONTROL 活動QA] 「活動概述」頁的「

![活動 QA 連結](/help/main/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>預設情況下， [!DNL Target] 自動將您添加到QA連結所需的受眾。 如果此設定被關閉，並且您的活動具有目標規則，則您的用戶配置檔案需要滿足這些目標規則才能查看包含建議的體驗。

使用QA連結可以預覽頁面上的建議：

![特色產品](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* 目標QA模式為「粘滯」，並保存在Cookie中。 如果不退出QA模式，您將繼續查看整個站點的QA結果。 要退出QA模式，請使用 [書籤](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md)。
>
>* 在QA模式下，瀏覽網站不會影響您的配置檔案 [!UICONTROL 最近查看的項目] 或 [!UICONTROL 最近購買的物料]。 這種行為是通過設計來避免無意污染生產行為資料的。 預覽來自 [!UICONTROL 最近查看的項目] 或 [!UICONTROL 基於用戶的Recommendations] 條件，首先在QA模式之外瀏覽站點，然後使用同一會話開啟QA模式連結。


## 使用CSV下載預覽建議

在某些情況下，您可能希望審計建議的特定項目。 當使用類似 [!UICONTROL 看過這個的人，看過]，其中根據用戶當前查看的項目推薦不同的項目集，並且您的目錄中可能有成千上萬個不同的項目。

結果在 [!UICONTROL 結果就緒] 活動中至少顯示一個算法的狀態。

要下載預覽結果，請按一下「活動概述」頁面右上角的菜單表徵圖，然後按一下 **[!UICONTROL 下載資料]**。

![下載資料選項](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

下載CSV檔案。 開啟它以查看建議的項目：

![建議的項目CSV檔案](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

從左到右是建議項的清單，在本例中是查看頻率最高的項。 這些建議按環境分開，在這種情況下，只有生產環境有建議。 對於此算法，我們沒有根據鍵值應用任何限制，因此標有星號(*)的行包含完整的建議集。 對於基於鍵值的其他算法類型，如 [!UICONTROL 看過這個的人，看過]，鍵值（即「This」項）在最左側列中列出，而建議項（即「That」項）在Recommendation_X列中從左到右列出。

>[!NOTE]
>
>結果下載不適用於包含 [!UICONTROL 基於用戶的Recommendations] 算法。 結果下載不可用於使用 [!UICONTROL 最近查看的項目] 推薦邏輯。

## 激活您的Recommendations活動

從 [!UICONTROL 活動概述] 頁籤，按一下狀態旁邊的下拉箭頭，然後選擇 **[!UICONTROL 激活]**。

![激活選項](/help/main/c-recommendations/t-create-recs-activity/assets/activate.png)

請注意，狀態將變為 [!UICONTROL 激活]:

![啟動](/help/main/c-recommendations/t-create-recs-activity/assets/activating.png)

幾秒到幾分鐘後，狀態將切換到 [!UICONTROL 實況]:

![現時](/help/main/c-recommendations/t-create-recs-activity/assets/live.png)

請注意，您也可以使用同一下拉清單停用或存檔活動。

## 更改Recommendations設定時避免中斷

更改 [!DNL Recommendations] 即時活動中的集合、條件、促銷或設計設定可能會導致算法結果無效，並且算法的狀態將更改為 [!UICONTROL 結果未就緒]。

為避免中斷即時活動，建議在修改即時活動時採用以下方法：

1. 複製原始活動（活動1）和要修改以建立新活動（活動2）的標準。
1. 更改複製的活動（活動2）和標準，並等待算法生成結果。
1. 預覽新的已修改活動（活動2）並確認結果是否符合要求。
1. 激活新活動（活動2）。
1. 停用原始活動（活動1）。

如果您需要將歷史報告結果保留在同一活動中，則可以採用另一種方法，這可能導致建議可用性暫時中斷：

1. 複製原始活動（活動1）和要修改以建立新活動（活動2）的標準。
1. 更改複製的活動（活動2）和標準，並等待算法生成結果。
1. 預覽新的已修改活動（活動2）並確認結果是否符合要求。
1. 暫停新的、已修改的活動（活動2），並將設定/條件交換到原始活動（活動1）。
1. 預覽原始活動（活動1）並確認結果是否符合要求。
1. 重新激活原始活動（活動1）。
