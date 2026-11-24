---
keywords: 行為資料來源；analytics；建議；條件；產品變數
description: 瞭解如何在[!DNL Target Recommendations]中使用[!DNL Adobe Analytics]作為行為資料來源。
title: 使用 Adobe Analytics 和推薦
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
TQID: 'https://experienceleague.adobe.com/2ryixOT-YoKjDlMbqs8g2DJElNVmlCUFhbdZzpfSnNs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 374d176c5c40826d958a8b87d220422466433690
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 1%
---
# 搭配[!DNL Recommendations]使用[!DNL Adobe Analytics] {#use-analytics-with-recommendations}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!DNL Adobe Target Recommendations]活動中使用[!DNL Adobe Analytics]作為行為資料來源。

>[!ENDSHADEBOX]

使用[!DNL Adobe Analytics]做為行為資料來源，可讓[!DNL Adobe Target Recommendations]個活動使用來自[!DNL Analytics]的檢視型與購買型行為資料。 當[!DNL Target Recommendations]設定是新的，且[!DNL Analytics]有許多歷史資料要使用時，這個用法很有用。 資料也可能包含僅與[!DNL Analytics]共用的第三方來源或摘要的資訊。

資料來源是使用&#x200B;**[!UICONTROL 行為資料Source]**&#x200B;選項選取，同時[在[!DNL Recommendations]中建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#data-source)： **[!UICONTROL Adobe Target]**&#x200B;或&#x200B;**[!UICONTROL Analytics]**。

>[!NOTE]
>
>如果這兩個選項未顯示在帳戶中，請連絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## [!DNL Target]中[!DNL Analytics]資料的使用案例 {#use-cases}

使用[!DNL Analytics]做為行為資料來源也允許部署特定使用案例，而不需使用所有[!DNL Target]實體引數標籤實體頁面。 這需要一些先決條件，而「產品變數」的可用性是最重要的必要條件。 一般eVar和Prop不足，[!DNL Analytics]和[!DNL Target]無法自動交換此資料。

[!DNL Analytics]可作為行為資料來源使用，以：

* 根據上個月其他使用者從相同類別購買的內容（使用[!DNL Analytics]資料），在零售網站上向使用者顯示產品詳細資料頁面上的建議。
* 根據[!DNL Analytics]資料，在媒體網站的主畫面上顯示目前趨勢特定類別中最受歡迎內容的內容。

## [!DNL Analytics]中的實作

### 先決條件：在[!DNL Analytics]中設定產品變數 {#prerequisites}

使用[!DNL Target Recommendations]所需的屬性在[!DNL Analytics]中實作產品變數。 [!DNL Target Recommendations]範例摘要格式會指導您必須在產品變數中定義哪些屬性。 這些值之後必須在[!DNL Target] UI中「對應」到個別[!DNL Target]實體值。

>[!NOTE]
>
>如果是內容網站，個別內容片段必須視為「產品」，而該內容的關聯屬性必須作為屬性傳遞。 此類屬性可包括作者名稱、發佈日期、內容標題、發行月份等。 企業應根據使用案例的需求，決定類別層級的詳細程度或類別型別。

如需如何設定產品變數的詳細資訊，請參閱&#x200B;*實作Adobe Analytics*&#x200B;指南中的[產品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=zh-Hant)。 該檔案中的一些附註（例如有關類別）需要部署該檔案的團隊做出判斷。 建議先諮詢[!DNL Adobe]再進行此活動。

### 考量事項 {#considerations}

[!DNL Analytics]資料會透過每日摘要傳送。 行為結果可能需要24小時的時間，才能反映在網站上的建議結果中。 如同所有[!DNL Recommendations]條件設定一樣，應該測試此資料來源。

若要選擇資料來源，請執行下列動作：

* 當使用者每天產生大量有機資料，而且幾乎不需要依賴歷史資料時，[!DNL Target] mbox會很適合。
* 當最近產生的有機資料較少且將使用[!DNL Analytics]資料時，[!DNL Analytics]非常適合。

`entity.id`和`entity.categoryId`值仍必須在[!DNL Target] mbox呼叫中傳遞。 其他屬性可透過[!DNL Analytics]摘要傳遞，如本頁所述。

動態包含規則（例如比對實體引數與設定檔屬性）可與[!DNL Analytics]摘要方法搭配使用。 此方法類似於使用[!DNL Target]獨立式，但必須考量時機：應該符合設定檔變數的實體變數取決於資料層，而資料層可能稍後出現在頁面上。

## 在[!DNL Target]中實作 {#implement-target}

產品變數在[!DNL Target]中完成對應，以提供連續的行為資料供給。

1. 在[!DNL Target]中，按一下&#x200B;**[!UICONTROL 建議]**，然後按一下&#x200B;**[!UICONTROL 摘要]**&#x200B;索引標籤。

1. 按一下&#x200B;**[!UICONTROL 建立摘要]**。

   ![摘要頁面中的[建立摘要]按鈕反白顯示](../assets/feeds_1.png)

1. Select **[!UICONTROL Analytics分類]**，然後指定報表套裝。

1. 按一下[下一步]&#x200B;**&#x200B;**&#x200B;以前進到&#x200B;**[!UICONTROL 排程]**&#x200B;設定，然後選取摘要的頻率： **[!UICONTROL 每日]**、**[!UICONTROL 每週]**、**[!UICONTROL 每兩週]**&#x200B;或&#x200B;**[!UICONTROL 永不]**。 您也可以選取一天中要處理的摘要時間。

   ![使用「每日」、「每週」、「每兩週」和「永不」頻率選項，以及「每日時間」欄位，排程「建立摘要」對話方塊的步驟](../assets/feeds_3.png)

1. 按一下[下一步]&#x200B;**&#x200B;**&#x200B;前進到&#x200B;**[!UICONTROL 對應]**&#x200B;設定，然後將欄位資料行標題對應到適當的&#x200B;**[!UICONTROL Recommendations]**&#x200B;欄位名稱。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

如需建立摘要的詳細資訊，請參閱[建立摘要](/help/main/c-recommendations/c-products/feeds.md#steps)。
