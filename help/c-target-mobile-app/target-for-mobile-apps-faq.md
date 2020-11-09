---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: 行動應用程式專用Adobe Target的常見問題。
title: 行動應用程式專用Adobe Target的常見問題
feature: mobile implementation
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---


# 行動應用程式的Target常見問答集

行動應用程式的常見問 [!DNL Target] 題清單。

## 我是否應使 [!DNL Adobe Experience Platform Launch] 用來部署SDK，或我是否可部署SDK而不使用 [!DNL Launch]?

SDK可從 [Adobe Marketing Cloud Git取得](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。 如果您不使用 [Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html)，則必須管理您自己的設定檔案，並在應用程式中加以管理。

## 目前有哪些SDK可供使用？

Adobe Experience Platform Mobile SDK目前支援iOS、Android和React。 如需詳細資訊，請參 [閱Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 根據經緯度的驗證，以位置為基礎的功能的頻率為何？

如需詳 [細資訊，請參閱](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe Places檔案。

## 我是否需要at.js才能讓Adobe Experience Platform Mobile SDK運作？

不行，您不需要at.js就能使用行動SDK。 at.js是網站的 [!DNL Target] JavaScript程式庫。 Adobe Experience Platform Mobile SDK適用於行動應用程式。

## Target Mobile是否僅為Adobe Target Premium產品SKU的功能？

無.對 [!DNL Adobe Target Standard] 於客戶，您只能搭配「行動應用程式」附加元件，將我們的行動SDK用於A/B測試和體驗目標(XT) [!DNL Target Standard] 活動。 如果您想要在行動應用程式中使用Recommendations或人工智慧功能，則需要 [Adobe Target Premium授權](/help/c-intro/intro.md#premium) 。

## Adobe Experience Manager(AEM)和Target行動活動之間是否有行動應用程式整合？

它已列在我們的路線圖上，但還沒有時間表。 目前，您可以將JSON [Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md) （體驗片段）從AEM共用至Target，然後可能會在行動應用程式活動中使用這些片段。
