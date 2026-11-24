---
keywords: 建議設計;範本;建立設計;傳送;輸出
description: 瞭解如何在Adobe [!DNL Target] Recommendations中使用設計來定義建議出現在頁面上的方式（1X4、1X6、2X2等）。
title: 開始使用設計
feature: Recommendations
exl-id: 348b1d77-49c9-4a6b-ba85-7ba051713d5b
TQID: 'https://experienceleague.adobe.com/08jboJLkp6MhgXiISjkVzh2kVze5DRrxO8BbQBFLeA4'
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
source-git-commit: f9c9c7b2b78ec020fcabae420686b8955e350a0e
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 9%
---
# 開始使用設計 {#design-overview}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解設計如何定義[!DNL Adobe Target Recommendations]中建議的版面配置和格式。

>[!ENDSHADEBOX]

[!DNL Adobe Target Recommendations]中的設計會定義建議在頁面上的顯示方式。 設計會定義建議的版面配置和格式。

[!DNL Recommendations]附帶幾個預設（預先建立）設計，也可以建立自訂設計。 如需詳細資訊，請參閱[建立設計](/help/main/c-recommendations/c-design-overview/create-design.md)。

[!DNL Target]可以提供建議完整的觀感，如下圖所示。 設計可以包含 HTML、JavaScript 和 CSS。 此設計稱為4 x 1設計：一列有四個空間。

![標題為「其他有趣的活動」的4 x 1設計範例，其中四個專案分別顯示像片、名稱、價格、評分和距離](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

[!DNL Target]也可以以JSON物件的形式傳送建議，這些物件可用於電子郵件訊息、物聯網(IoT)裝置、主控台或語音使用案例（Amazon Alexa或Google首頁）。

設計會決定：

* 建議中顯示的專案數
* 專案的顯示方式（在列、欄、網格或表格中）
* 訪客是否只能看到指定數量的專案，或者可以捲動瀏覽數個專案
