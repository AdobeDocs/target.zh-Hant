---
keywords: 報表;下載報表;csv;成功量度;訂單詳細資料
description: 瞭解如何從Adobe下載資料 [!DNL Target] CVS格式的活動，可快速匯入至Excel、Access或其他資料分析程式。
title: 如何將報表資料下載為CSV檔案？
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 54%

---

# 將資料下載為 CSV 檔案

將資料下載為 .csv 格式，以快速匯入至 Excel、Access 或其他資料分析程式。

若要下載 CSV 檔案中的資料:

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，然後從清單按一下需要的活動。

   如果您有許多活動，您可以利用從[!UICONTROL 「類型」]、[!UICONTROL 「狀態」]、[!UICONTROL 「報表來源」]、[!UICONTROL 「體驗撰寫器」]、[!UICONTROL 「量度類型」]和[!UICONTROL 「活動來源」]下拉式清單選取選項來篩選清單。

1. 按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL 「下載」]**&#x200B;圖示，然後選取要下載到 Excel 和其他工具中分析的報表類型。

   * [!UICONTROL 匯出報表至CSV]
   * [!UICONTROL 匯出訂單詳細資料至 CSV]

   ![下載選項](/help/main/c-reports/assets/download-options.png)

## [!UICONTROL 匯出報表至 CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

此 [!UICONTROL 成功量度] 報表會顯示成功量度的相關資訊，以及「 」中未提供的下列量度 [!DNL Target] UI：

* 平均轉換時間以小時計，這樣您就可以看到一般訪客到達轉換點所花的時間
* 離線統計信賴計算的收入總和平方

活動結束時才會儲存資料。

>[!NOTE]
>
>CSV報表僅包含原始資料，不含計算量度，例如每次造訪帶來的收入、提升度或用於A/B測試的信賴度。 若要計算這些計算量度，請下載 [!DNL Target] [完整可信度電腦](/help/main/assets/complete_confidence_calculator.xlsx) 輸入活動值或檢閱的Excel檔案 [A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL 匯出訂單詳細資料至 CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

此 [!UICONTROL 訂單詳細資料] 報表會顯示訂單的相關資訊，包括：

* 訂單日期與時間
* 訂單金額 (若您插入「下單」mbox)

   此 [!UICONTROL 訂單詳細資料] 只有當您有訂單時，報表才有效。

* 訂單標幟 (重複或巨量訂購)

   如果訂單與平均訂單值的偏差超過+/- 3個標準差，則會將訂單標籤為極端。 此計算使用資料的最後一個月（截至計算的時間點）。 一旦活動執行超過一小時或直到 15 筆訂單之後 (以先到者為準)，活動便會排除其極端訂單。如需詳細資訊，請參閱[排除極端訂單](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

* 產品 ID

   產品ID的總長度若以逗號串連，不應超過255個字元，否則該ID無法在報表中正確顯示。 例如，如果您的訂單中的產品 ID 為「aa, bb」，則總長度為「aa,bb」= 5。

* 體驗

   在 [!UICONTROL A/B 測試]、[!UICONTROL 體驗鎖定目標] (XT) 和[!UICONTROL 多變數測試] (MVT) 活動的[!UICONTROL 訂單詳細資料]報表中，[!UICONTROL 「體驗」]欄包含體驗 `localId`。這是從選件 Token 中的 `$campaign.recipe.id` 輸出的值。

   [!UICONTROL 自動個人化] (AP) 活動沒有[!UICONTROL 「體驗」]欄。目前的[!UICONTROL 「演算法名稱」]欄已取代為「控制」或「已鎖定目標」術語，如 [!DNL Target] 的其他部分所示。

   [!UICONTROL 建議]活動不受影響。

>[!NOTE]
>
>* 對於預設環境 (主機群組)，訂單報表資料包含四週的資料，而對於所有非預設環境，則包含兩週的資料。
>* 收入量度設為&quot;[!UICONTROL 增加計數並讓使用者留在活動中]「僅記錄相同訪客下第一筆訂單的訂單詳細資料。 所有後續訂單都會增加轉換計數，但不會將收入新增至RPV/AOV/銷售，且不會包含在 [!UICONTROL 訂單詳細資料] 報告。


## 最佳實務

* 若要記錄訂單記錄，請 `orderTotal` 引數必須傳遞。
* 透過 `ProductPurchasedId` mbox 參數傳遞的值會列在「訂單詳細資料」報表中。
* 最佳實務是納入 `orderID` 和 `orderTotal`. 這樣可以自動忽略重複的訂單。

## 注意事項 {#section_49B9590904A645B18E694B4EFFFC1DEF}

下列資訊適用於 [!UICONTROL 下載] 選項：

* 您可以下載以下專案的兩個報表： [!UICONTROL A/B測試]， [!UICONTROL Automated Personalization]， [!UICONTROL 體驗鎖定]、和 [!UICONTROL 多變數] 活動。 您無法下載 [!UICONTROL 成功量度] 報告 [!UICONTROL Recommendations] 活動。
* 此 [!UICONTROL 下載] 選項不可用於 [!UICONTROL A/B測試] 和 [!UICONTROL 體驗鎖定] 之前建立的活動 [!DNL Target] 15.7.1版（2015年7月）。
* 下載的報表中不會記錄沒有相關聯資料的體驗。
* 對象套用於 [!DNL Target] 報告UI不會繼續存在於下載的報表中。
* 如果活動使用多個量度，則為下載所產生的 .csv 報告會不一致。可下載的報告僅是根據報告設定而產生，並會針對使用的任何其他量度考慮相同的值。真相來源永遠是在 [!DNL Target] UI 中顯示的報告。
