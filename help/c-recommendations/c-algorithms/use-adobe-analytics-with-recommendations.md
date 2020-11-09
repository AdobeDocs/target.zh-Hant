---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: 使用Adobe Analytics做為行為資料來源可讓客戶使用Adobe Recommendations中以檢視為基礎和／或購買為基礎的行為資料。
title: 搭配使用Adobe Analytics和Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 3%

---


# 搭配使用Adobe Analytics和Recommendations

使 [!DNL Adobe Analytics] 用行為資料來源可讓客戶使用建議活動中的檢視型和／或購買型行 [!DNL Analytics] 為 [!DNL Adobe Target] 資料。 此功能在設定為新功能且有 [!DNL Target Recommendations] 大量歷史資料 [!DNL Analytics] 可運用的情況下特別有用。

使 [!DNL Analytics] 用行為資料來源可做為使用者行為的豐富資訊來源。 這可能包括來自第三方來源或僅與共用之動態消息的資料 [!DNL Analytics]。

在Recommendations [中建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md) ，有兩個選項按鈕可讓您選擇要使用的資料來源： [!UICONTROL mbox] 或 [!UICONTROL Analytics]。

![行為資料來源按鈕](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>如果帳戶中未顯示這兩個按鈕，請聯絡客 [戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## Target中Analytics資料的使用案例

使用 [!DNL Analytics] 為建議的行為資料來源也提供部署特定使用案例的能力，而不需使用所有實體參數來標籤實體 [!DNL Target] 頁面。 雖然這需要具備特定的先決條件，但「產品變數」的可用性是該功能順利運作的最重要因素。 一般eVar和Prop不足以讓此握手在和之間自動 [!DNL Analytics] 發生 [!DNL Target]。

您可以用 [!DNL Analytics] 作行為資料來源，以：

* 使用Analytics資料，根據上個月其他使用者從相同類別購買的商品，在零售網站上向PDP頁面上的使用者顯示建議。
* 根據資料，在媒體網站的首頁畫面上顯示目前趨勢特定類別中最受歡迎內容的內 [!DNL Analytics] 容。

## Analytics中的實作

以下幾節將協助您實作此功 [!DNL Analytics] 能。

### 必要條件：在Analytics中設定產品變數

您必須使用所需的必 [!DNL Analytics] 要屬性，在中實作產品變數 [!DNL Target Recommendations]。

范 [!DNL Target Recommendations] 例動態消息格式將做為在產品變數中定義所有屬性的指南。 之後，這些值必須在UI中「對應」 [!DNL Target] 個別實體 [!DNL Target] 值。

>[!NOTE]
>
>如果它是內容網站，則必須將各個內容片段視為「產品」，以及該內容的相關屬性(例如：作者名稱、發佈日期、內容標題、發行月等) 必須作為屬性傳遞。 類別層級或類別類型的詳細程度應由業務根據使用案例需求決定。

如需如何設定產品變數的詳細資訊，請參閱 [Analytics實作指南](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html)*中的產品*。 該檔案中的部分附註需要由部署人員自行決定(例如：類別)。 建議您在進行此活動前，先與Adobe諮詢。

### 考量事項

[!DNL Analytics] 資料會透過每日饋送傳送。 行為結果最多需要24小時，才能反映在您網站上的建議結果中。 與所有標準 [!DNL Recommendations] 設定一樣，此資料來源可以且應該進行測試。

為了快速決策要使用哪個資料來源，如果使用者每天產生大量有機資料，而且對歷史資料的依賴性不大，那麼使用 [!DNL Target] mbox作為行為資料來源就很適合。 如果最近產生的有機資料的可用性較低，如果您想要儲存資料 [!DNL Analytics] ，則使用行 [!DNL Analytics] 為資料來源非常適合。

### 部署步驟

假設所有預先要求都已就緒，團隊必須執行下列工 [!DNL Adobe Target Recommendations] 作：

>[!IMPORTANT]
>
>以下步驟僅供說明之用。 團隊成員目前必 [!DNL Recommendations] 須執行這些步驟。 [如需詳細資訊，請連絡 客戶服務。](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)

1. 在中 [!DNL Target]，按一 **[!UICONTROL 下「管理]** >實 **[!UICONTROL 作]** 」以取得您 [!DNL Target] 的用戶端代碼。

   ![用戶端代碼](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. 取得您的 [!DNL Analytics] 報表套裝。

   使用您的 [!DNL Analytics] 生產網站報表套裝。 這是追蹤您已部署之網站的報表套 [!DNL Recommendations] 裝。

1. 在中 [!DNL Analytics]，按一下「 **[!UICONTROL 管理]** >資 **[!UICONTROL 料饋送」]**。

   ![設定>資料饋送](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Click **[!UICONTROL Add]** to create a new feed.

   ![新增動態消息](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. 填寫動態消息資訊：

   * **名稱**:重新收集產品饋送
   * **報表套裝**:您預先決定的報表套裝
   * **電子郵件**:為管理員使用者指定任何適當的地址
   * **饋送間隔**:選擇所需間隔
   * **延遲處理**:沒有延遲。
   * **開始和結束日期**:連續饋送

   ![摘要資訊區段](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Fill in the details in the **[!UICONTROL Destination]** section:

   >[!NOTE]
   > 
   >在執行此步 [!DNL Adobe Analytics] 驟之前，請洽詢團隊。

   * **類型**:FTP
   * **Host**: `xxx.yyy.com`
   * **路徑**:您的 [!DNL Target] 客戶代碼
   * **使用者名稱**:指定您的使用者名稱
   * **密碼**:指定您的密碼

   螢幕擷取僅供參考。 您的部署將擁有不同的認證。 執行此步驟 [!DNL Adobe Analytics] 時，請洽詢團隊或客戶服務。

   ![目標區](/help/c-recommendations/c-algorithms/assets/destination.png)

1. 填寫「資 **[!UICONTROL 料欄]** 」定義：

   * **壓縮格式**:Gzip
   * **封裝類型**: 單一檔案
   * **資訊清單：** 完成檔案

      ![壓縮格式、封裝類型和資訊清單設定](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **包含的欄**:

      >[!IMPORTANT]
      >
      >欄必須依此處說明的相同順序新增。 按下列順序選取欄，然後按一 **[!UICONTROL 下每欄]** 「新增」。

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   ![「資料列定義」部分](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

這樣，側面的設定就 [!DNL Analytics] 完成了。 現在，是時候將這些變數並列對 [!DNL Target] 應，以持續提供行為資料了。

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

