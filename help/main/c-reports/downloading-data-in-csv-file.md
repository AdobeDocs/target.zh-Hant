---
keywords: 報表;下載報表;csv;成功量度;訂單詳細資料
description: 瞭解如何從Adobe下載資料 [!DNL Target] 以CVS格式快速導入到Excel、Access或其他資料分析程式的活動。
title: 如何在CSV檔案中下載報告資料？
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 83%

---

# 將資料下載為 CSV 檔案

將資料下載為 .csv 格式，以快速匯入至 Excel、Access 或其他資料分析程式。

若要下載 CSV 檔案中的資料:

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，然後從清單按一下需要的活動。

   如果您有許多活動，您可以利用從[!UICONTROL 「類型」]、[!UICONTROL 「狀態」]、[!UICONTROL 「報表來源」]、[!UICONTROL 「體驗撰寫器」]、[!UICONTROL 「量度類型」]和[!UICONTROL 「活動來源」]下拉式清單選取選項來篩選清單。

1. 按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL 「下載」]**&#x200B;圖示，然後選取要下載到 Excel 和其他工具中分析的報表類型。

   * [!UICONTROL 將報告導出到CSV]
   * [!UICONTROL 匯出訂單詳細資料至 CSV]

   ![下載選項](/help/main/c-reports/assets/download-options.png)

## 匯出報表至 CSV {#section_38BD9743EB254453B5F4A0A6F2720CD3}

「成功量度」報表顯示成功量度的相關資訊，以及下列量度 (在 Target UI 中看不到):

* 平均轉換時間以小時計，這樣您就可以看到一般訪客到達轉換點所花的時間
* 離線統計信賴計算的收入總和平方

活動結束時才會儲存資料。

>[!NOTE]
>
>CSV報告僅包括原始資料，不包括計算的度量，如A/Btest使用的每位訪問者的收入、提升或信心。 要計算這些計算的度量，請下載目標 [完全置信度計算器](/help/main/assets/complete_confidence_calculator.xlsx) Excel檔案，用於輸入活動值或查看 [目標使用的統計計算](/help/main/assets/statistical-calculations.pdf)。

## 匯出訂單詳細資料至 CSV {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

「訂單詳細資訊」報表顯示有關訂單的資訊，包括：

* 訂單日期與時間
* 訂單金額 (若您插入「下單」mbox)

   只在您有訂單時，「訂單詳細資料」報表才會運作。

* 訂單標幟 (重複或巨量訂購)

   如果訂單與上個月資料的平均訂購值 (直到計算完成的時間點為止) 相差超過 +/- 3 個標準偏差，就視為極端訂單。一旦活動執行超過一小時或直到 15 筆訂單之後 (以先到者為準)，活動便會排除其極端訂單。如需詳細資訊，請參閱[排除極端訂單](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

* 產品 ID

   以逗號串連的產品 ID 總長度不應超過 255 個字元，否則 ID 將無法正確顯示於報表中。例如，如果您的訂單中的產品 ID 為「aa, bb」，則總長度為「aa,bb」= 5。

* 體驗

   在 [!UICONTROL A/B 測試]、[!UICONTROL 體驗鎖定目標] (XT) 和[!UICONTROL 多變數測試] (MVT) 活動的[!UICONTROL 訂單詳細資料]報表中，[!UICONTROL 「體驗」]欄包含體驗 `localId`。這是從選件 Token 中的 `$campaign.recipe.id` 輸出的值。

   [!UICONTROL 自動個人化] (AP) 活動沒有[!UICONTROL 「體驗」]欄。目前的[!UICONTROL 「演算法名稱」]欄已取代為「控制」或「已鎖定目標」術語，如 [!DNL Target] 的其他部分所示。

   [!UICONTROL 建議]活動不受影響。

>[!NOTE]
>
>* 對於預設環境 (主機群組)，訂單報表資料包含四週的資料，而對於所有非預設環境，則包含兩週的資料。
>* 設為「增加計數並讓使用者留在活動中」的收入量度只會記錄相同訪客所下的第一個訂單的訂單詳細資料。所有後續訂單會增加轉換計數，但將不會對 RPV/AOV/銷售額新增收入，且將不會包括在訂單詳細資料報表中。


## 最佳實務

* 若要記錄訂單記錄，您必須傳遞 `orderTotal` 參數。
* 透過 `ProductPurchasedId` mbox 參數傳遞的值會列在「訂單詳細資料」報表中。
* 最佳作法是納入 `orderID` 與 `orderTotal`。這樣可以自動忽略重複的訂單。

## 注意事項 {#section_49B9590904A645B18E694B4EFFFC1DEF}

下列資訊適用於「下載」選項:

* 您可以下載A/BTest、Automated Personalization、體驗目標和多變數活動的兩個報告。 對於「建議」活動，您無法下載「成功量度」報表。
* 對於 Target 15.7.1 版 (2015 年 7 月) 以前建立的 A/B 和「體驗鎖定目標」活動，無法使用「下載」選項。
* 下載的報表中不會記錄沒有相關聯資料的體驗。
* Target 報表 UI 中套用的受眾不會繼續存在於下載報表中。
