---
description: 行動應用程式的Adobe Target常見問題。
keywords: 行動應用程式；常見問題；常見問題；目標行動應用程式
seo-description: 行動應用程式的Adobe Target常見問題。
seo-title: 行動應用程式的Adobe Target常見問題
title: 適用於行動應用程式的Adobe Target常見問答集
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# 行動應用程式的Target常見問題

行動應用程式的常見問題 [!DNL Target] 清單。

## 我是否應使用 [!DNL Adobe Experience Platform Launch] SDK部署SDK，或我是否可部署SDK而不使用 [!DNL Launch]？

SDK適用於 [Adobe Marketing Cloud壁虎](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。如果您不使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)，您必須管理自己的設定檔案，並在應用程式中管理它。

## 適用於行動應用程式的Visual Experience Composer(CMS)是否可與Adobe Experience Platform SDK v的回應原生支援搭配使用？

[Native Mobile Apps的CMS](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) 目前不支援回應原生應用程式。您必須使用 [表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md)。

## Mobile SDK整合是否允許推出新的行動功能？我可以在沒有新程式碼部署的情況下開啓和關閉功能標幟嗎？

是的，您可以使用我們的行動SDK逐步推出功能。

## 如果是更複雜的邏輯，我應該直接在應用程式中開發，而不是使用行動CMS嗎？如果是，我應該使用哪一種開發語言？

目前，CMS支援一般使用案例，例如變更影像、文字、色彩等。對於更進階的使用案例，例如個人化應用程式版面，您必須在程式碼中插入 [!DNL Target] 請求/位置(mbox)，並使用 [表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md) 來設計體驗並分配流量。我們的行動SDK支援Java、Objective C和Swift。這取決於您團隊的偏好設定和資源，以選擇語言。

## 哪些SDK目前已推出？

Adobe Experience Platform Mobile SDK目前支援iOS、Android和回應。如需詳細資訊，請參閱 [Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 關於緯度和經度的驗證，以位置為基礎的功能頻率為何？

如需 [詳細資訊，請參閱Adobe Places文件](https://placesdocs.com/places-services-by-adobe-documentation/) 。

## 行動「檢視」支援哪些原生類別？它們是否支援任何NSObject衍生類別(或任何Android物件)或NSViewController和活動？

如需詳細資訊，請造訪Android文件以 [手動宣告檢視。](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views)

## Adobe Experience Platform Mobile SDK是否需要使用. js？

不需要，您不需要at. js即可使用行動SDK。at. js代表網站 [!DNL Target] 的JavaScript程式庫。Adobe Experience Platform Mobile SDK適用於行動應用程式。

## Target Mobile是否僅適用於Adobe Target Premium產品SKU？

對於Adobe Target Standard客戶，您只能將我們的Mobile SDK用於A/B測試和體驗定位(XT)活動。如果您想要在行動應用程式中使用Recommendations或AI功能，則需要 [Adobe Target Premium](/help/c-intro/intro.md#premium) 授權。

## 我可以在行動應用程式的CMS中運用Adobe Audience Manager(AAM)的受眾嗎？

是的，Adobe Experience Platform Mobile SDK是專為 [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)、 [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html)、 [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)和Target建立的。Audience Manager中的觀眾會共用 [!DNL Target]。

## Adobe Experience Manager(AEM)和Target行動活動之間是否有行動應用程式整合？

它正在規劃藍圖，但尚未推出時間軸。目前，您可以將JSON [體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md) 從AEM共用至Target，而且可能會在行動應用程式活動中使用這些片段。

## 我可以使用CMS新增更多影像，還是只變更現有的影像？

您目前只能變更現有影像。
