---
keywords: 產品;集合
description: 瞭解Adobe [!DNL Target] Recommendations中的實體。 實體會使用[!DNL Target]參考您想要建議的專案，例如文章、影片或產品。
title: 如何使用實體？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: ffe23eea-b914-4c86-ad54-c63c1cc1c0d7
TQID: 'https://experienceleague.adobe.com/zfISb59XJ5qrD1-FA0syglPPswIL8cA0N0pBpY4tgIE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%
---
# 開始使用實體 {#get-started-entities}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解[!DNL Adobe Target Recommendations]中的實體以及在何處管理這些實體。

>[!ENDSHADEBOX]

實體是[!DNL Recommendations]可以建議的專案。 實體可以是產品、內容（例如文章、投影片、影像、電影或電視節目）、工作清單、餐廳等。

[!DNL Recommendations]會根據您設定的條件，顯示您集合中的專案。

## 實體如何達成建議

您實體的相關資訊可以數種方式傳遞至[!DNL Recommendations]，包括：

* 使用mbox或`targetPageParams`，從您的頁面傳送[實體屬性](/help/main/c-recommendations/c-products/entity-attributes.md)。
* 具有[摘要](/help/main/c-recommendations/c-products/feeds.md)，可使用CSV檔案、[!DNL Google Product Search]摘要格式或[!DNL Adobe Analytics]產品分類。
* 透過傳送API。

如果[!DNL Target]同時從摘要和mbox收集專案的資料，則會使用最新的資料。

上傳的實體和實體屬性值會在61天後過期。 每隔60天至少再次傳送每個專案一次。 否則，[!DNL Target]會認為該專案已不再相關，並將其從目錄中移除。

## 管理您的實體

使用下列頁面處理您的實體：

* [實體屬性](/help/main/c-recommendations/c-products/entity-attributes.md)和[自訂實體屬性](/help/main/c-recommendations/c-products/custom-entity-attributes.md)：定義您傳遞給[!DNL Recommendations]的產品或內容資訊。
* [摘要](/help/main/c-recommendations/c-products/feeds.md)：將實體或內容資訊加入您的建議中。
* [目錄搜尋](/help/main/c-recommendations/c-products/catalog-search.md)：在您的目錄中尋找專案。
* [集合](/help/main/c-recommendations/c-products/collections.md)：設定您的集合。 當您建立[!DNL Recommendations]活動時，會為每個體驗選取一個集合。
* [排除專案](/help/main/c-recommendations/c-products/exclusions.md)：防止某些專案顯示在您的建議中。 排除專案適用於帳戶中的所有活動。
