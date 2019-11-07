---
keywords: 行動應用程式；常問問題；常見問題；常見問題；目標行動應用程式
description: 行動應用程式專用Adobe Target的常見問題。
title: 行動應用程式專用Adobe Target的常見問題
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 行動應用程式的Target常見問答集

行動應用程式的常見問 [!DNL Target] 題清單。

## 我是否應使 [!DNL Adobe Experience Platform Launch] 用來部署SDK，或我是否可部署SDK而不使用 [!DNL Launch]?

SDK可從 [Adobe Marketing Cloud Git取得](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。 如果您不使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)，則必須管理您自己的設定檔案，並在應用程式中加以管理。

## 行動應用程式的Visual Experience Composer(VEC)是否可與Adobe Experience Platform SDK v5的React-Native支援搭配使用？

原生 [行動應用程式的VEC](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) 目前不支援React原生應用程式。 您必須使 [用表單型Experience Composer](/help/c-experiences/form-experience-composer.md)。

## Mobile SDK整合是否允許推出新的行動功能？ 我是否可以在不部署新程式碼的情況下開啟或關閉功能標幟？

是的，您可以使用我們的行動SDK逐步推出功能。

## 若是更複雜的邏輯，我是否應直接在應用程式中開發，而非使用Mobile VEC? 如果是，我應使用哪種開發語言？

目前，VEC支援常用的使用案例，例如變更影像、文字、顏色等。 如需進階的使用案例，例如個人化應用程式版面，您必須在程式碼中插入請求／位置(mbox)，並使用 [!DNL Target] Form-Based Experience Composer [](/help/c-experiences/form-experience-composer.md) ，來設計體驗並分配流量。 我們的行動SDK支援Java、Objective c和Swift。 選擇語言取決於您團隊的偏好和資源。

## 目前有哪些SDK可供使用？

Adobe Experience Platform Mobile SDK目前支援iOS、Android和React。 如需詳細資訊，請參 [閱Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 根據經緯度的驗證，以位置為基礎的功能的頻率為何？

如需詳 [細資訊，請參閱](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe Places檔案。

## 行動「檢視」支援哪些原生類別？ 它們是否支援任何NSObject派生類（或任何Android對象）或僅支援NSViewController和活動？

如需詳細資訊，請造訪Android檔案，以手動 [方式宣告檢視](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views)。

## 我是否需要at.js才能讓Adobe Experience Platform Mobile SDK運作？

不行，您不需要at.js就能使用行動SDK。 at.js是網站的 [!DNL Target] JavaScript程式庫。 Adobe Experience Platform Mobile SDK適用於行動應用程式。

## Target mobile是否僅為Adobe Target Premium產品SKU的功能？

對於Adobe Target Standard客戶，您只能將我們的行動SDK用於A/B測試和體驗定位(XT)活動。 如果您想要在行動應用程式中使用Recommendations或人工智慧功能，則需要 [Adobe Target Premium授權](/help/c-intro/intro.md#premium) 。

## 我是否可在適用於行動應用程式的VEC中運用Adobe Audience Manager(AAM)的受眾？

是的，Adobe Experience Platform Mobile SDK是專為 [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)、 [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html)、 [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)和Target打造。 您在Audience manager中的觀眾會與共用 [!DNL Target]。

## Adobe Experience Manager(AEM)和Target行動活動之間是否有行動應用程式整合？

它已列在我們的路線圖上，但還沒有時間表。 目前，您可以將JSON [Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md) （體驗片段）從AEM共用至Target，然後可能會在行動應用程式活動中使用這些片段。

## 我是否可以使用VEC新增更多影像，或僅變更現有影像？

您目前只能變更現有的影像。
