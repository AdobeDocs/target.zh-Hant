---
keywords: 行動應用程式；常問問題；常見問題；常見問題；目標行動應用程式
description: 檢視行動應用程式的Adobe [!DNL Target] 常見問題及解答。
title: 關於行動應用程式的 [!DNL Target] 常見問題有哪些？
feature: 實施行動
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# 行動應用程式的Target常見問答集

行動應用程式的[!DNL Target]常見問題清單。

## 我是否應使用[!DNL Adobe Experience Platform Launch]來部署SDK，或者我是否可部署SDK而不使用[!DNL Launch]?

SDK可在[Adobe Marketing Cloudgit](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)上取得。 如果您不使用[Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html)，您必須管理自己的設定檔案，並在應用程式中加以管理。

## 目前有哪些SDK可供使用？

Adobe Experience Platform行動SDK目前支援iOS、Android和React。 如需詳細資訊，請參閱[Adobe Experience Cloud平台行動SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 根據經緯度的驗證，以位置為基礎的功能的頻率為何？

如需詳細資訊，請參閱[Adobe放置檔案](https://placesdocs.com/places-services-by-adobe-documentation/)。

## 我是否需要at.js才能讓Adobe Experience Platform行動SDK運作？

不行，您不需要at.js就能使用行動SDK。 at.js是網站的[!DNL Target] JavaScript程式庫。 Adobe Experience Platform行動SDK適用於行動應用程式。

## [!DNL Target] Mobile是否僅是Adobe[!DNL Target] Premium產品SKU的功能？

無.對於[!DNL Adobe Target Standard]客戶，您只能搭配[!DNL Target Standard]行動應用程式附加元件，將我們的行動SDK用於A/B測試和體驗定位(XT)活動。 如果您想要在行動應用程式中使用Recommendations或人工智慧功能，則需要[Adobe TargetPremium](/help/c-intro/intro.md#premium)授權。

## Adobe Experience Manager(AEM)和[!DNL Target]行動活動之間是否有行動應用程式整合？

它已列在我們的路線圖上，但還沒有時間表。 目前，您可以將JSON [體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)從Target共用AEM，然後可能會在行動應用程式活動中使用這些片段。
