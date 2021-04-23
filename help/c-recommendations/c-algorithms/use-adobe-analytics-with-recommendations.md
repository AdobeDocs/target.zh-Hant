---
keywords: 行為資料源；分析；建議；標準；產品變數
description: 瞭解如何使用Adobe Analytics作為行為資料來源，從 [!DNL Target] Recommendations的Analytics使用檢視型和／或購買型行為資料。
title: 如何將Adobe Analytics與 [!DNL Target] Recommendations一起使用？
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 1%

---

# 使用Adobe Analytics與Recommendations

使用[!DNL Adobe Analytics]作為行為資料來源可讓客戶在[!DNL Adobe Target]建議活動中使用[!DNL Analytics]中的檢視型和／或購買型行為資料。 此功能在[!DNL Target Recommendations]設定是新的，而[!DNL Analytics]有許多歷史資料可運用的情況下特別有用。

使用[!DNL Analytics]作為行為資料來源可做為使用者行為的豐富資訊來源。 這可能包括來自第三方來源或僅與[!DNL Analytics]共用之饋送的資料。

在[在Recommendations建立准則](/help/c-recommendations/c-algorithms/create-new-algorithm.md)時，有兩個選項按鈕可讓您選擇要使用的資料來源：[!UICONTROL mboxes]或[!UICONTROL Analytics]。

![行為資料來源按鈕](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>如果帳戶中未顯示這兩個按鈕，請聯絡[客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## Target中Analytics資料的使用案例

使用[!DNL Analytics]作為建議的行為資料來源，也提供部署特定使用案例的能力，而不需使用所有[!DNL Target]實體參數來標籤實體頁面。 雖然這需要具備特定的先決條件，但「產品變數」的可用性是該功能順利運作的最重要因素。 一般eVar和Prop不足以讓此握手在[!DNL Analytics]和[!DNL Target]之間自動發生。

您可以使用[!DNL Analytics]作為行為資料來源，以：

* 使用Analytics資料，根據上個月其他使用者從相同類別購買的商品，在零售網站上向PDP頁面上的使用者顯示建議。
* 根據[!DNL Analytics]資料，在媒體網站的首頁畫面上顯示目前趨勢特定類別中人氣最高的內容。

## Analytics中的實作

以下幾節將幫助您在[!DNL Analytics]一側實作此功能。

### 必要條件：在Analytics中設定產品變數

您必須在[!DNL Analytics]中實作產品變數，並使用[!DNL Target Recommendations]所需的必要屬性。

[!DNL Target Recommendations]範例饋送格式將作為指南，在產品變數中需要定義所有屬性。 稍後，這些值必須在[!DNL Target] UI中「mapped」（對應），以取得個別的[!DNL Target]實體值。

>[!NOTE]
>
>如果它是內容網站，則必須將各個內容片段視為「產品」，以及該內容的相關屬性(例如：作者名稱、發佈日期、內容標題、發行月等) 必須作為屬性傳遞。 類別層級或類別類型的詳細程度應由業務根據使用案例需求決定。

如需如何設定產品變數的詳細資訊，請參閱&#x200B;*Analytics實施指南*&#x200B;中的[products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html)。 該檔案中的部分附註需要由部署人員自行決定(例如：類別)。 建議您在進行此活動前，先與Adobe協商。

### 考量事項

[!DNL Analytics] 資料會透過每日饋送傳送。行為結果最多需要24小時，才能反映在您網站上的建議結果中。 與所有[!DNL Recommendations]標準設定一樣，此資料來源可以且應該進行測試。

為快速決策要使用哪些資料來源，如果使用者每天產生大量有機資料，而且對歷史資料的依賴性不大，則使用[!DNL Target] mbox作為行為資料來源是相當適合的。 如果最近產生的有機資料的可用性較低，如果您想要將[!DNL Analytics]資料儲存起來，則使用[!DNL Analytics]作為行為資料來源是最適合的。

現在，是時候在[!DNL Target]端映射這些變數，以持續提供行為資料了。

## 在Target中實施

1. 在Target中，按一下&#x200B;**[!UICONTROL Recommendations]**，然後按一下&#x200B;**[!UICONTROL 饋送]**&#x200B;標籤。

   ![動態消息](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 按一下「建立動態消息」。****

1. 選擇&#x200B;**[!UICONTROL Analytics分類]**，然後指定報表套裝。

   ![Analytics分類選項](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 按一下&#x200B;**[!UICONTROL 映射]**，然後將欄位列標題映射到相應的[!UICONTROL Recommendations]欄位名稱。

   ![映射部分](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 常見問題

當您搭配使用[!DNL Analytics]和[!DNL Target]時，請考慮下列常見問答：

### `entity.id`和`entity.categoryId`值是否需要傳入至[!DNL Target] mbox呼叫中？

是的，這兩個值仍為必要值。 其餘屬性可透過[!DNL Analytics]饋送傳遞，如本文所述。

### 我是否可使用動態包含規則，例如實體參數會使用[!DNL Analytics]饋送方法比對描述檔屬性？

是的，你可以。 當使用[!DNL Target]獨立時，此方法很類似。 但是，在這種情況下，您必須留意時間因素。 應與描述檔變數相符的實體變數，會依據日後可能出現在頁面上的資料層而定。
