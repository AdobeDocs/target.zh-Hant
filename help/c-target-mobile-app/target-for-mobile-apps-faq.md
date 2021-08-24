---
keywords: 行動應用程式；常見問題集；faq;target行動應用程式
description: 檢視行動應用程式Adobe [!DNL Target] 的常見問題及解答。
title: 有關適用於行動應用程式的 [!DNL Target] 常見問題集為何？
feature: 實作行動
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# 適用於行動應用程式的 Target 常見問答

關於行動應用程式[!DNL Target]常見問題的清單。

## 我應在[!DNL Adobe Experience Platform]中使用標籤來部署SDK嗎？或者我是否可以不使用[!DNL Launch]來部署SDK?

SDK可在[Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)上使用。 如果您未在Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)中使用[標籤，則必須管理您自己的設定檔案，並在您的應用程式中管理它。

## 目前提供哪些SDK?

Adobe Experience Platform Mobile SDK目前支援iOS、Android和React。 如需詳細資訊，請參閱[Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 就經緯度的驗證而言，以位置為基礎的功能的頻率為何？

如需詳細資訊，請參閱[Adobe放置檔案](https://placesdocs.com/places-services-by-adobe-documentation/)。

## 我是否需要at.js才能讓Adobe Experience Platform Mobile SDK運作？

不需要，您不需要at.js即可使用行動SDK。 at.js是網站的[!DNL Target] JavaScript資料庫。 Adobe Experience Platform Mobile SDK適用於行動應用程式。

## [!DNL Target]行動裝置是否僅是Adobe[!DNL Target] Premium產品SKU的功能？

無.若為[!DNL Adobe Target Standard]客戶，您只能透過[!DNL Target Standard]行動應用程式附加元件，將行動SDK用於A/B測試和體驗鎖定目標(XT)活動。 如果您想在行動應用程式中使用Recommendations或AI支援的功能，需要[Adobe Target Premium](/help/c-intro/intro.md#premium)授權。

## Adobe Experience Manager(AEM)和[!DNL Target]行動活動之間是否有行動應用程式整合？

這是在我們的路線圖上，但還沒有時間表。 目前，您可以從AEM共用JSON [體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)至Target，然後可能會在行動應用程式活動中使用這些片段。
