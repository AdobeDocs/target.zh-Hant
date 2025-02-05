---
keywords: 行為資料來源；analytics；建議；條件；產品變數
description: 瞭解如何在 [!DNL Target Recommendations]中使用 [!DNL Adobe Analytics] 作為行為資料來源。
title: 如何搭配 [!DNL Target Recommendations]使用 [!DNL Adobe Analytics] ？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# 搭配[!DNL Recommendations]使用[!DNL Adobe Analytics]

使用[!DNL Adobe Analytics]做為行為資料來源，可讓使用者端在[!DNL Adobe Target Recommendations]活動中使用[!DNL Analytics]的檢視型與購買型行為資料。 此功能在[!DNL Target Recommendations]設定是新的，且[!DNL Analytics]有許多歷史資料要使用的情況下特別有用。

使用[!DNL Analytics]做為行為資料來源可以做為使用者行為的豐富資訊來源。 此資訊可能包含僅與[!DNL Analytics]共用的協力廠商來源或摘要的資料。

在[!DNL Recommendations]中[建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)時，有兩個選項按鈕可讓您選擇要使用的資料來源： [!UICONTROL mboxes]或[!UICONTROL Analytics]。 若要建立條件，請按一下[!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL Create Criteria] > [!UICONTROL Create Criteria]。 如需詳細資訊，請參閱[建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

>[!NOTE]
>
>如果這兩個按鈕未顯示在您的帳戶中，請聯絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## [!DNL Target]中[!DNL Analytics]資料的使用案例

使用[!DNL Analytics]做為建議的行為資料來源也可讓您部署特定的使用案例，而不需要使用所有[!DNL Target]實體引數標籤實體頁面。 雖然上述要求必須具備特定必要條件，但「產品變數」的可用性是確保該功能順暢運作的最重要因素。 一般eVar和Prop不足以讓此交握在[!DNL Analytics]和[!DNL Target]之間自動發生。

您可以使用[!DNL Analytics]做為行為資料來源來：

* 根據上個月其他使用者從相同類別購買的內容（使用[!DNL Analytics]資料），在零售網站上向使用者顯示產品詳細資料頁面上的建議。
* 根據[!DNL Analytics]資料，在媒體網站的主畫面上顯示目前趨勢特定類別中最受歡迎內容的內容。

## [!DNL Analytics]中的實作

以下章節可協助您在[!DNL Analytics]端實作此功能。

### 先決條件：在[!DNL Analytics]中設定產品變數

使用[!DNL Target Recommendations]所需的必要屬性在[!DNL Analytics]中實作產品變數。

[!DNL Target Recommendations]範例摘要格式可作為必須定義產品變數中所有屬性的指南。 之後，這些值必須在[!DNL Target] UI中為個別[!DNL Target]實體值「對應」。

>[!NOTE]
>
>如果是內容網站，個別內容片段必須視為「產品」，且該內容的關聯屬性必須作為屬性傳遞。 此類屬性可包括作者名稱、發佈日期、內容標題、發行月份等。 類別層級或類別型別的詳細程度，應由企業根據使用案例需求決定。

如需如何設定產品變數的詳細資訊，請參閱&#x200B;*實作Adobe Analytics*&#x200B;指南中的[產品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html)。 該檔案中有些附註需要部署團隊自行決定（例如：類別）。 在執行此活動之前，請一律建議諮詢[!DNL Adobe]。

### 考量事項

[!DNL Analytics]資料會透過每日摘要傳送。 行為結果可能需要24小時的時間，才會反映在您網站上的建議結果中。 如同所有[!DNL Recommendations]條件設定一樣，此資料來源可以而且應該進行測試。

為了快速決定要使用哪個資料來源，如果使用者每天產生的有機資料很多，而且不需要太多歷史資料相依性，則使用[!DNL Target] mbox作為行為資料來源可能非常適合您。 在最近產生的有機資料可用性較低的情況下，如果您想要以[!DNL Analytics]資料為基礎進行儲存，則使用[!DNL Analytics]作為行為資料來源會很合適。

現在應該在[!DNL Target]端對應這些變數，以持續提供行為資料。

## 在[!DNL Target]中實作

1. 在[!DNL Target]中，按一下&#x200B;**[!UICONTROL Recommendations]**，然後按一下&#x200B;**[!UICONTROL Feeds]**&#x200B;索引標籤。

1. 按一下 **[!UICONTROL Create Feed]**。

1. 選取&#x200B;**[!UICONTROL Analytics Classifications]**，然後指定報表套裝。

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以前進到&#x200B;**[!UICONTROL Schedule]**&#x200B;設定，選取摘要的頻率週期：

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 weeks]
   * [!UICONTROL Never]

   您也可以選取一天中要處理摘要的時間。

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以前進到&#x200B;**[!UICONTROL Mapping]**&#x200B;設定，然後將欄位欄位標題對應到適當的[!UICONTROL Recommendations]欄位名稱。

1. 按一下 **[!UICONTROL Save]**。

## 常見問題集

將[!DNL Analytics]與[!DNL Target]搭配使用時，請考量下列常見問題：

### 需要在[!DNL Target] mbox呼叫中傳遞`entity.id`和`entity.categoryId`值嗎？

是的，這兩個值仍然是必要的。 其餘屬性可透過[!DNL Analytics]摘要傳遞，如本檔案所述。

### 我可以使用動態包含規則（例如使用[!DNL Analytics]摘要方法的實體引數符合設定檔屬性）嗎？

可以。 使用[!DNL Target]獨立時的方法類似。 不過，在此情況下，您必須留意時間因素。 應該與設定檔變數相符的實體變數取決於資料層，而資料層可能會稍後出現在頁面上。
