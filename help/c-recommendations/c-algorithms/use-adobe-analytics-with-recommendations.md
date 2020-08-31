---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: 使用Adobe Analytics做為行為資料來源可讓客戶使用Adobe Recommendations中以檢視為基礎和／或購買為基礎的行為資料。
title: 搭配使用Adobe Analytics和Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: 9bf30d6397fefdc85e51e2bd431ba163b10f6c09
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 1%

---


# 搭配使用Adobe Analytics和Recommendations

使 [!DNL Adobe Analytics] 用行為資料來源可讓客戶使用建議活動中的檢視型和／或購買型行 [!DNL Analytics] 為 [!DNL Adobe Target] 資料。 此功能在設定為新功能且有 [!DNL Target Recommendations] 大量歷史資料 [!DNL Analytics] 可運用的情況下特別有用。

使 [!DNL Analytics] 用行為資料來源可做為使用者行為的豐富資訊來源。 這可能包括來自第三方來源或僅與共用之動態消息的資料 [!DNL Analytics]。

在Recommendations [中建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md) ，有兩個選項按鈕可讓您選擇要使用的資料來源： [!UICONTROL mbox] 或 [!UICONTROL Analytics]。

![行為資料來源按鈕](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>如果帳戶中未顯示這兩個按鈕，請聯絡客 [戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## 使用個案

使用 [!DNL Analytics] 為建議的行為資料來源也提供部署特定使用案例的能力，而不需使用所有實體參數來標籤實體 [!DNL Target] 頁面。 雖然這需要具備特定的先決條件，但「產品變數」的可用性是該功能順利運作的最重要因素。 一般eVar和Prop不足以讓此握手在和之間自動 [!DNL Analytics] 發生 [!DNL Target]。

您可以用 [!DNL Analytics] 作行為資料來源，以：

* 使用Analytics資料，根據上個月其他使用者從相同類別購買的商品，在零售網站上向PDP頁面上的使用者顯示建議。
* 根據資料，在媒體網站的首頁畫面上顯示目前趨勢特定類別中最受歡迎內容的內 [!DNL Analytics] 容。

## Analytics中的實作

以下幾節將協助您實作此功 [!DNL Analytics] 能。

### 必要條件：Analytics中的產品變數

您必須使用所需的必 [!DNL Analytics] 要屬性，在中實作產品變數 [!DNL Target Recommendations]。

范 [!DNL Target Recommendations] 例動態消息格式將做為在產品變數中定義所有屬性的指南。 之後，這些值必須在UI中「對應」 [!DNL Target] 個別實體 [!DNL Target] 值。

>[!NOTE]
>
>如果它是內容網站，則必須將各個內容片段視為「產品」，以及該內容的相關屬性(例如：作者名稱、發佈日期、內容標題、發行月等) 必須作為屬性傳遞。 類別層級或類別類型的詳細程度應由業務根據使用案例需求決定。

如需如何設定產品變數的詳細資訊，請參閱 [Analytics實作指南](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/products.html)*中的產品*。 該檔案中的部分附註需要由部署人員自行決定(例如：類別)。 建議您在進行此活動前，先與Adobe諮詢。

### 考量事項

[!DNL Analytics] 資料會透過每日饋送傳送。 行為結果最多需要24小時，才能反映在您網站上的建議結果中。 與所有標準 [!DNL Recommendations] 設定一樣，此資料來源可以且應該進行測試。

為了快速決策要使用哪個資料來源，如果使用者每天產生大量有機資料，而且對歷史資料的依賴性不大，那麼使用 [!DNL Target] mbox作為行為資料來源就很適合。 如果最近產生的有機資料的可用性較低，如果您想要儲存資料 [!DNL Analytics] ，則使用行 [!DNL Analytics] 為資料來源非常適合。

### 請連絡客戶服務，為您建立資料饋送

假設所有預先要求皆已落實，請連絡 [客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ，為您建立資料饋送。

## 在Target中實施

1. 在Target中，按一 **[!UICONTROL 下Recommendations]**，然後按一下 **[!UICONTROL Feed]** 標籤。

   ![動態消息](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 按一 **[!UICONTROL 下「建立動態消息]**」。

1. 選取 **[!UICONTROL Analytics分類]**，然後指定報表套裝。

   ![Analytics分類選項](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 按一 **[!UICONTROL 下「對應]**」，然後將欄位欄標題對應至適當的 [!UICONTROL Recommendations] 欄位名稱。

   ![映射部分](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 常見問題

當您搭配使用時，請考慮下列常見 [!DNL Analytics] 問答 [!DNL Target]集：

### 在mbox `entity.id` 呼叫 `entity.categoryId` 中傳遞所需的 [!DNL Target] 和值嗎？

是的，這兩個值仍為必要值。 其餘屬性可透過動態消息傳 [!DNL Analytics] 遞，如本文所述。

### 我是否可以使用動態包含規則，例如實體參數會使用動態消息方法比對描述 [!DNL Analytics] 檔屬性？

是的，你可以。 該方法在單獨使用時 [!DNL Target] 類似。 但是，在這種情況下，您必須留意時間因素。 應與描述檔變數相符的實體變數，會依據日後可能出現在頁面上的資料層而定。

