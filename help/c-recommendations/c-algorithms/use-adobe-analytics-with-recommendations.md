---
keywords: 行為資料來源；analytics；建議；條件；產品變數
description: 了解如何使用Adobe Analytics做為行為資料來源，以在 [!DNL Target] Recommendations。
title: 如何使用Adobe Analytics搭配 [!DNL Target] Recommendations?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 2a4cae206bf634bf3fbec65c5c4b289aadefede1
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 1%

---

# 使用 Adobe Analytics 和 Recommendations

使用 [!DNL Adobe Analytics] 作為行為資料來源，客戶可使用以檢視為基礎和/或購買為基礎的行為資料， [!DNL Analytics] in [!DNL Adobe Target] 建議活動。 此功能在 [!DNL Target Recommendations] 設定是新的， [!DNL Analytics] 有很多歷史資料要利用。

使用 [!DNL Analytics] 作為行為資料來源，可做為使用者行為的豐富資訊來源。 這可能包括來自第三方來源或僅與共用之摘要的資料 [!DNL Analytics].

同時 [建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md) 在Recommendations中，有兩個選項按鈕可讓您選擇要使用的資料來源： [!UICONTROL mbox] 或 [!UICONTROL Analytics].

![行為資料來源按鈕](assets/behavioral-data-source.png)

>[!NOTE]
>
>如果您的帳戶中未顯示這兩個按鈕，請聯絡 [客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Target中Analytics資料的使用案例

使用 [!DNL Analytics] 作為建議的行為資料來源，也提供部署特定使用案例的功能，而不需要使用所有 [!DNL Target] 實體參數。 雖然這需要具備某些必要條件，但是「產品變數」的可用性是該功能順暢運作的最重要因素。 一般eVar和Prop不足以讓此交握在 [!DNL Analytics] 和 [!DNL Target].

您可以使用 [!DNL Analytics] 行為資料來源：

* 使用Analytics資料，根據上個月其他使用者從相同類別購買的內容，在零售網站上向PDP頁面上的使用者顯示建議。
* 根據，在媒體網站的主畫面上顯示目前趨勢之特定類別中最受歡迎內容的內容 [!DNL Analytics] 資料。

## Analytics中的實作

以下幾節將協助您在 [!DNL Analytics] 側。

### 必要條件：在Analytics中設定產品變數

您必須在 [!DNL Analytics] 以及 [!DNL Target Recommendations].

A [!DNL Target Recommendations] 範例摘要格式可作為在產品變數中定義所有屬性的指南。 稍後，這些值必須在 [!DNL Target] 個別的UI [!DNL Target] 實體值。

>[!NOTE]
>
>如果是內容網站，則個別內容片段必須視為該內容的「產品」及相關屬性(例如：作者名稱、發佈日期、內容標題、發行月份等) 必須以屬性的形式傳遞。 類別層級或類別類型的粒度應由業務根據使用案例需求決定。

如需如何設定產品變數的詳細資訊，請參閱 [產品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) 在 *Analytics實施指南*. 說明檔案中的部分附註需要由部署團隊自行決定(例如：類別)。 在執行此活動之前，一律建議您諮詢Adobe。

### 考量事項

[!DNL Analytics] 資料會透過每日摘要傳送。 行為結果最多需要24小時才會反映在網站上的建議結果中。 與所有 [!DNL Recommendations] 條件設定，此資料來源可以且應進行測試。

為了快速決策要使用哪個資料來源，如果每天由使用者產生大量有機資料，且對歷史資料的依賴度不高，則使用 [!DNL Target] mbox作為行為資料來源可非常適合。 如果最近生成的有機資料可用性較低，如果您希望 [!DNL Analytics] 資料，然後使用 [!DNL Analytics] 因為行為資料來源非常適合。

現在可以在 [!DNL Target] 持續提供行為資料。

## 在Target中實作

1. 在Target中，按一下 **[!UICONTROL Recommendations]**，然後按一下 **[!UICONTROL 動態消息]** 標籤。

   ![動態消息](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 按一下 **[!UICONTROL 建立摘要]**.

1. 選擇 **[!UICONTROL Analytics分類]**，然後指定報表套裝。

   ![Analytics分類選項](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 按一下 **[!UICONTROL 對應]**，然後將欄位欄標題對應至適當的 [!UICONTROL Recommendations] 欄位名稱。

   ![映射節](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 常見問題

使用時請考量下列常見問題集 [!DNL Analytics] with [!DNL Target]:

### 是 `entity.id` 和 `entity.categoryId` 在 [!DNL Target] mbox呼叫？

是，這兩個值仍為必要。 其餘的屬性可透過 [!DNL Analytics] 摘要，如本檔案所述。

### 我可以使用動態包含規則，例如實體參數會使用 [!DNL Analytics] 摘要方法？

是的，你可以。 使用時的方法類似 [!DNL Target] 獨立。 但在此情況下，您必須留意時間因素。 應與設定檔變數相符的實體變數取決於稍後可能出現在頁面上的資料層。
