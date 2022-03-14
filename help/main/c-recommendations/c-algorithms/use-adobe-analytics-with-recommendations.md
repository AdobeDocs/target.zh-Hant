---
keywords: 行為資料源；分析；建議；標準；產品變數
description: 瞭解如何使用 [!DNL Adobe Analytics] 作為行為資料源，使用來自 [!DNL Analytics] 在 [!DNL Target Recommendations]。
title: 如何使用 [!DNL Adobe Analytics] 與 [!DNL Target Recommendations]?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 2%

---

# ![高級](/help/main/assets/premium.png) 使用 [!DNL Adobe Analytics] 與 [!DNL Recommendations]

使用 [!DNL Adobe Analytics] 作為行為資料源，客戶端可以使用基於視圖和/或基於購買的行為資料 [!DNL Analytics] 在 [!DNL Adobe Target] [!DNL Recommendations] 活動。 此功能在以下情況下特別有用： [!DNL Target Recommendations] 設定是新的， [!DNL Analytics] 有很多歷史資料可以使用。

使用 [!DNL Analytics] 因為行為資料源可以充當有關用戶行為的豐富資訊源。 此資訊可能包括來自第三方源或僅與共用的源的資料 [!DNL Analytics]。

同時 [建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) 在 [!DNL Recommendations]，有兩個單選按鈕，您可以選擇要使用的資料源： [!UICONTROL 框] 或 [!UICONTROL 分析]。 要建立條件，請按一下 [!UICONTROL Recommendations] > [!UICONTROL 標準] > [!UICONTROL 建立條件] > [!UICONTROL 建立條件]。 如需詳細資訊，請參閱[建立準則](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

![行為資料源按鈕](assets/behavioral-data-source.png)

>[!NOTE]
>
>如果這兩個按鈕未顯示在您的帳戶中，請聯繫 [客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## 目標中分析資料的使用案例

使用 [!DNL Analytics] 作為建議的行為資料源，還允許您部署特定的使用案例，而無需使用所有 [!DNL Target] 實體參數。 儘管這要求具備某些先決條件，但是「產品變數」的可用性是該功能無縫工作的最重要內容。 常規eVars和Props不足以使此握手在以下時間之間自動發生 [!DNL Analytics] 和 [!DNL Target]。

您可以使用 [!DNL Analytics] 行為資料源：

* 根據上個月其他用戶從同一類別購買的內容，在零售網站上向產品詳細資訊頁面上的用戶顯示建議 [!DNL Analytics] 資料。
* 在媒體站點的主螢幕上顯示當前趨勢的特定類別中最流行的內容(基於 [!DNL Analytics] 資料。

## 實施 [!DNL Analytics]

以下各節將幫助您在 [!DNL Analytics] 邊。

### 先決條件：在中設定產品變數 [!DNL Analytics]

在中實現產品變數 [!DNL Analytics] 具有所需的必要屬性 [!DNL Target Recommendations]。

A [!DNL Target Recommendations] 示例源格式用作在產品變數中必須定義所有屬性的指南。 以後，這些值必須在 [!DNL Target] 各自的UI [!DNL Target] 實體值。

>[!NOTE]
>
>如果內容站點，則必須將各個內容段視為「產品」，並且必須將有關該內容的相關屬性作為屬性傳遞。 這些屬性可以包括作者姓名、發佈日期、內容標題、發佈月份等。 類別級別或類別類型的粒度應由業務根據用例要求確定。

有關如何設定產品變數的詳細資訊，請參閱 [產品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) 的 *實施Adobe Analytics* 的子菜單。 該文檔中的一些注釋需要由部署團隊自行決定(例如：類別)。 我們總是建議與 [!DNL Adobe] 進行此活動之前。

### 考量事項

[!DNL Analytics] 資料通過每日饋送發送。 行為結果可能需要24小時才能反映在您站點上的建議結果中。 與所有 [!DNL Recommendations] 條件設定，此資料源可以且應該進行測試。

為了快速決策要使用哪個資料源，如果用戶每天生成的有機資料很多，而對歷史資料的依賴性不大，則使用 [!DNL Target] mbox作為行為資料源可以很合適。 如果最近生成的有機資料的可用性較低，如果您希望 [!DNL Analytics] 資料，然後使用 [!DNL Analytics] 因為行為資料源非常適合。

現在是時候在 [!DNL Target] 持續提供行為資料的側。

## 在中實施 [!DNL Target]

1. 在 [!DNL Target]按一下 **[!UICONTROL Recommendations]**，然後按一下 **[!UICONTROL 源]** 頁籤。

   ![動態消息](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 按一下 **[!UICONTROL 建立源]**。

1. 選擇 **[!UICONTROL 分析分類]**，然後指定報表套件。

   ![分析分類選項](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 按一下 **[!UICONTROL 下一個]** 向 **[!UICONTROL 計畫]** 設定，選擇饋送的頻率段：

   * [!UICONTROL 每日]
   * [!UICONTROL 每週]
   * [!UICONTROL 每兩週]
   * [!UICONTROL 從不]

   您也可以選擇一天中要處理的源的時間。

1. 按一下 **[!UICONTROL 下一個]** 向  **[!UICONTROL 映射]** 設定，然後將欄位列標題映射到相應的 [!UICONTROL Recommendations] 欄位名稱。

   ![映射節](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 常見問題

使用時請考慮以下常見問題 [!DNL Analytics] 與 [!DNL Target]:

### 是 `entity.id` 和 `entity.categoryId` 要傳遞的值 [!DNL Target] 電話？

是的，這兩個值仍然是必需的。 其餘屬性可通過 [!DNL Analytics] feed ，如本文檔中討論的。

### 是否可以使用動態包含規則，如實體參數與配置檔案屬性匹配 [!DNL Analytics] 餵？

你可以的。 在使用 [!DNL Target] 獨自行動。 但是，在這種情況下，您必須注意時間因素。 本應與配置檔案變數匹配的實體變數取決於稍後可能出現在頁面上的資料層。
