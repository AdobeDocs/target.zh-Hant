---
keywords: 行為資料源；分析；建議；標準；產品變數
description: 瞭解如何使用Adobe Analytics作為行為資料來源，從Target Recommendations中使用Analytics的檢視型和／或購買型行為資料。
title: 如何搭配Target Recommendations使用Adobe Analytics?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 3%

---


# 搭配使用Adobe Analytics和Recommendations

使用[!DNL Adobe Analytics]作為行為資料來源可讓客戶在[!DNL Adobe Target]建議活動中使用[!DNL Analytics]中的檢視型和／或購買型行為資料。 此功能在[!DNL Target Recommendations]設定是新的，而[!DNL Analytics]有許多歷史資料可運用的情況下特別有用。

使用[!DNL Analytics]作為行為資料來源可做為使用者行為的豐富資訊來源。 這可能包括來自第三方來源或僅與[!DNL Analytics]共用之饋送的資料。

當[在Recommendations中建立准則](/help/c-recommendations/c-algorithms/create-new-algorithm.md)時，有兩個選項按鈕可讓您選擇要使用的資料來源：[!UICONTROL mboxes]或[!UICONTROL Analytics]。

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

如需如何設定產品變數的詳細資訊，請參閱&#x200B;*Analytics實施指南*&#x200B;中的[products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html)。 該檔案中的部分附註需要由部署人員自行決定(例如：類別)。 建議您在進行此活動前，先與Adobe諮詢。

### 考量事項

[!DNL Analytics] 資料會透過每日饋送傳送。行為結果最多需要24小時，才能反映在您網站上的建議結果中。 與所有[!DNL Recommendations]標準設定一樣，此資料來源可以且應該進行測試。

為快速決策要使用哪些資料來源，如果使用者每天產生大量有機資料，而且對歷史資料的依賴性不大，則使用[!DNL Target] mbox做為行為資料來源是相當適合的。 如果最近產生的有機資料可用性較低，如果您想要將[!DNL Analytics]資料儲存在上，則使用[!DNL Analytics]作為行為資料來源是最適合的。

### 部署步驟

假設所有先決條件都已就緒，則[!DNL Adobe Target Recommendations]團隊必須執行下列工作：

>[!IMPORTANT]
>
>以下步驟僅供說明之用。 [!DNL Recommendations]團隊的成員當前必須執行這些步驟。 [如需詳細資訊，請連絡 客戶服務。](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)

1. 在[!DNL Target]中，按一下「**[!UICONTROL 管理]** > **[!UICONTROL 實施]**」以取得您的[!DNL Target]用戶端程式碼。

   ![用戶端代碼](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. 取得您的[!DNL Analytics]報表套裝。

   使用您的[!DNL Analytics]生產網站報表套裝。 這是追蹤您已部署[!DNL Recommendations]的網站的報表套裝。

1. 在[!DNL Analytics]中，按一下「**[!UICONTROL 管理]** > **[!UICONTROL 資料饋送]**」。

   ![設定>資料饋送](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. 按一下「新增&#x200B;****」以建立新的動態消息。

   ![新增動態消息](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. 填寫動態消息資訊：

   * **名稱**:重新收集產品饋送
   * **報表套裝**:您預先決定的報表套裝
   * **電子郵件**:為管理員使用者指定任何適當的地址
   * **饋送間隔**:選擇所需間隔
   * **延遲處理**:沒有延遲。
   * **開始和結束日期**:連續饋送

   ![摘要資訊區段](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. 填寫&#x200B;**[!UICONTROL Destination]**&#x200B;部分中的詳細資訊：

   >[!NOTE]
   > 
   >執行此步驟前，請洽詢[!DNL Adobe Analytics]團隊。

   * **類型**:FTP
   * **Host**: `xxx.yyy.com`
   * **路徑**:您的 [!DNL Target] 用戶端代碼
   * **使用者名稱**:指定您的使用者名稱
   * **密碼**:指定您的密碼

   螢幕擷取僅供參考。 您的部署將擁有不同的認證。 執行此步驟時，請洽詢[!DNL Adobe Analytics]團隊或客戶服務。

   ![目標區](/help/c-recommendations/c-algorithms/assets/destination.png)

1. 填寫&#x200B;**[!UICONTROL 資料欄]**&#x200B;定義：

   * **壓縮格式**:Gzip
   * **封裝類型**:單一檔案
   * **資訊清單：** 完成檔案

      ![壓縮格式、封裝類型和資訊清單設定](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **包含的欄**:

      >[!IMPORTANT]
      >
      >欄必須依此處說明的相同順序新增。 按下列順序選擇列，然後為每個列按一下&#x200B;**[!UICONTROL 添加]**。

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   ![「資料列定義」部分](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

這樣，[!DNL Analytics]側的設定就完成了。 現在，是時候在[!DNL Target]端映射這些變數，以持續提供行為資料了。

## 在Target中實施

1. 在Target中，按一下「**[!UICONTROL Recommendations]**」，然後按一下「**[!UICONTROL Feeds]**」標籤。

   ![動態消息](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 按一下「建立動態消息」。****

1. 選擇&#x200B;**[!UICONTROL Analytics分類]**，然後指定報表套裝。

   ![Analytics分類選項](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 按一下「對應&#x200B;****」，然後將欄位欄標題對應至適當的[!UICONTROL Recommendations]欄位名稱。

   ![映射部分](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 常見問題

當您搭配使用[!DNL Analytics]和[!DNL Target]時，請考慮下列常見問答：

### `entity.id`和`entity.categoryId`值是否需要傳入至[!DNL Target] mbox呼叫中？

是的，這兩個值仍為必要值。 其餘屬性可透過[!DNL Analytics]饋送傳遞，如本文所述。

### 我是否可使用動態包含規則，例如實體參數會使用[!DNL Analytics]饋送方法比對描述檔屬性？

是的，你可以。 當使用[!DNL Target]獨立時，此方法很類似。 但是，在這種情況下，您必須留意時間因素。 應與描述檔變數相符的實體變數，會依據日後可能出現在頁面上的資料層而定。

