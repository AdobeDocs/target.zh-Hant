---
keywords: 行為資料來源；analytics；建議；條件；產品變數
description: 瞭解如何使用 [!DNL Adobe Analytics] 作為行為資料來源，以使用來自的檢視型和/或購買型行為資料 [!DNL Analytics] 在 [!DNL Target Recommendations].
title: 如何使用 [!DNL Adobe Analytics] 替換為 [!DNL Target Recommendations]？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---

# 使用 [!DNL Adobe Analytics] 替換為 [!DNL Recommendations]

使用 [!DNL Adobe Analytics] 作為行為資料來源可讓使用者端使用來自的檢視型和/或購買型行為資料 [!DNL Analytics] 在 [!DNL Adobe Target] [!DNL Recommendations] 活動。 此功能在 [!DNL Target Recommendations] 設定是新的，而且 [!DNL Analytics] 有許多歷史資料可供使用。

使用 [!DNL Analytics] 因為行為資料來源可作為使用者行為的豐富資訊來源， 此資訊可能包含僅與共用的第三方來源或摘要的資料 [!DNL Analytics].

當 [建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) 在 [!DNL Recommendations]，您有兩個選項按鈕可選擇要使用的資料來源： [!UICONTROL mboxes] 或 [!UICONTROL 分析]. 若要建立條件，請按一下 [!UICONTROL Recommendations] > [!UICONTROL 條件] > [!UICONTROL 建立條件] > [!UICONTROL 建立條件]. 如需詳細資訊，請參閱[建立準則](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

![行為資料來源按鈕](assets/behavioral-data-source.png)

>[!NOTE]
>
>如果這兩個按鈕未顯示在您的帳戶中，請聯絡 [客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Target中Analytics資料的使用案例

使用 [!DNL Analytics] 由於recommendations的行為資料來源也可讓您部署特定的使用案例，而不需要使用所有 [!DNL Target] 實體引數。 雖然上述要求必須具備特定必要條件，但「產品變數」的可用性是該功能順暢運作的最重要因素。 一般eVar和Prop不足以讓此交握自動在兩者之間發生 [!DNL Analytics] 和 [!DNL Target].

您可以使用 [!DNL Analytics] 作為行為資料來源，可以：

* 根據上個月其他使用者從相同類別購買的內容，使用在產品詳細資料頁面上向使用者顯示零售網站上的建議 [!DNL Analytics] 資料。
* 根據目前趨勢的特定類別，在媒體網站的主畫面上顯示最受歡迎內容的內容 [!DNL Analytics] 資料。

## 中的實作 [!DNL Analytics]

以下小節可協助您在 [!DNL Analytics] 側。

### 先決條件：在中設定產品變數 [!DNL Analytics]

在中實作產品變數 [!DNL Analytics] 具有所需的必要屬性 [!DNL Target Recommendations].

A [!DNL Target Recommendations] 範例摘要格式可作為指南，用於定義產品變數中的所有屬性。 稍後，這些值必須在 [!DNL Target] 個別UI [!DNL Target] 實體值。

>[!NOTE]
>
>如果是內容網站，個別內容片段必須視為「產品」，與該內容相關的屬性必須作為屬性傳遞。 這類屬性可包括作者名稱、發佈日期、內容標題、發行月份等。 類別層級或類別型別的詳細程度，應由業務根據使用案例需求決定。

如需如何設定產品變數的詳細資訊，請參閱 [產品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) 在 *實作Adobe Analytics* 指南。 該檔案中有些附註需要部署它的團隊自行決定（例如：類別）。 請務必諮詢下列資訊： [!DNL Adobe] ，然後再開始此活動。

### 考量事項

[!DNL Analytics] 資料會透過每日摘要傳送。 行為結果可能需要24小時的時間，才會反映在您網站上的建議結果中。 與所有專案一樣 [!DNL Recommendations] 條件設定時，此資料來源可以而且應該進行測試。

若要快速決定要使用哪個資料來源，如果使用者每天產生的自然資料很多，而且不需要太多歷史資料的相依性，則使用 [!DNL Target] mbox做為行為資料來源非常適合。 如果最近產生的有機資料可用性較低，且您想要根據以下條件進行銀行 [!DNL Analytics] 資料，然後使用 [!DNL Analytics] 因為行為資料來源非常適合。

現在應該將這些變數對應至 [!DNL Target] 用於持續提供行為資料的side。

## 在中實作 [!DNL Target]

1. 在 [!DNL Target]，按一下 **[!UICONTROL Recommendations]**，然後按一下 **[!UICONTROL 摘要]** 標籤。

   ![動態消息](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 按一下 **[!UICONTROL 建立摘要]**.

1. 選取 **[!UICONTROL Analytics分類]**，然後指定報表套裝。

   ![Analytics分類選項](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 按一下 **[!UICONTROL 下一個]** 前往 **[!UICONTROL 排程]** 設定，則選取摘要的頻率期間：

   * [!UICONTROL 每日]
   * [!UICONTROL 每週]
   * [!UICONTROL 每2週]
   * [!UICONTROL 從不]

   您也可以選取一天中要處理摘要的時間。

1. 按一下 **[!UICONTROL 下一個]** 前往  **[!UICONTROL 對應]** 設定，然後將欄位欄標題對應至適當的 [!UICONTROL Recommendations] 欄位名稱。

   ![對應區段](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 常見問題集

在使用時請考量下列常見問題 [!DNL Analytics] 替換為 [!DNL Target]：

### 是 `entity.id` 和 `entity.categoryId` 需要在以下位置傳遞的值： [!DNL Target] mbox呼叫？

是，這兩個值仍為必要值。 其餘屬性可透過 [!DNL Analytics] 摘要，如本檔案所述。

### 我可以使用動態包含規則嗎？例如，實體引數符合使用 [!DNL Analytics] 摘要方法？

可以。 使用時，方法類似 [!DNL Target] 獨立。 不過，在此情況下，您必須留意時間因素。 應該與設定檔變數相符的實體變數取決於資料層，而資料層可能會稍後出現在頁面上。
