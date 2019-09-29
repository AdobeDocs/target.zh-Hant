---
description: Frequently Asked Questions about Adobe Target for mobile apps.
keywords: 行動應用程式；常問問題；常見問題；常見問題；目標行動應用程式
seo-description: 行動應用程式專用Adobe Target的常見問題。
seo-title: 行動應用程式專用Adobe Target的常見問題
title: 行動應用程式的Adobe Target常見問答集
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# 行動應用程式的Target常見問答集

行動應用程式的常見問 [!DNL Target] 題清單。

## 我是否應使 [!DNL Adobe Experience Platform Launch] 用來部署SDK，或我是否可部署SDK而不使用 [!DNL Launch]?

SDK可從 [Adobe Marketing Cloud Git取得](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。 如果您不使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)，則必須管理您自己的設定檔案，並在應用程式中加以管理。

## 行動應用程式的Visual Experience Composer(VEC)是否可與Adobe Experience Platform SDK v5的React-Native支援搭配使用？

原生 [行動應用程式的VEC](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) 目前不支援React原生應用程式。 您必須使 [用表單型Experience Composer](/help/c-experiences/form-experience-composer.md)。

## Mobile SDK整合是否允許推出新的行動功能？ 我是否可以在不部署新程式碼的情況下開啟或關閉功能標幟？

是的，您可以使用我們的行動SDK逐步推出功能。

## For more complex logic, should I develop directly in the app instead of using the Mobile VEC? 如果是，我應使用哪種開發語言？

目前，VEC支援常用的使用案例，例如變更影像、文字、顏色等。 如需進階的使用案例，例如個人化應用程式版面，您必須在程式碼中插入請求／位置(mbox)，並使用 [!DNL Target] Form-Based Experience Composer [](/help/c-experiences/form-experience-composer.md) ，來設計體驗並分配流量。 我們的行動SDK支援Java、Objective c和Swift。 選擇語言取決於您團隊的偏好和資源。

## 目前有哪些SDK可供使用？

Adobe Experience Platform Mobile SDK目前支援iOS、Android和React。 如需詳細資訊，請參 [閱Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 根據經緯度的驗證，以位置為基礎的功能的頻率為何？

如需詳 [細資訊，請參閱](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe Places檔案。

## 行動「檢視」支援哪些原生類別？ 它們是否支援任何NSObject派生類（或任何Android對象）或僅支援NSViewController和活動？

如需詳細資訊，請造訪Android檔案，以手動 [方式宣告檢視](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views)。

## 我是否需要at.js才能讓Adobe Experience Platform Mobile SDK運作？

不行，您不需要at.js就能使用行動SDK。 at.js is the  JavaScript library for websites. [!DNL Target]The Adobe Experience Platform Mobile SDKs are for mobile apps.

## Is Target Mobile a functionality of Adobe Target Premium Product SKU only?

For Adobe Target Standard customers, you can use our Mobile SDKs for A/B Test and Experience Targeting (XT) activities only. If you want to use Recommendations or AI-powered features in the mobile app, you need an Adobe Target Premium license.[](/help/c-intro/intro.md#premium)

## Can I leverage audiences from Adobe Audience Manager (AAM) in the VEC for Mobile Apps?

Yes, Adobe Experience Platform Mobile SDKs are built for Audience Manager, Analytics, Campaign, and Target. [](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)[](https://docs.adobe.com/content/help/en/analytics/landing/home.html)[](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)Your audiences in Audience Manager are shared with .[!DNL Target]

## Is there a mobile app integration between Adobe Experience Manager (AEM) and Target mobile activities?

It is on our roadmap but there is no timeline yet. Currently, you can share JSON Experience Fragments from AEM to Target and there might be potential to then use them in a mobile app activity.[](/help/c-experiences/c-manage-content/aem-experience-fragments.md)

## Can I add more images using the VEC or only change existing images?

You can currently change existing images only.
