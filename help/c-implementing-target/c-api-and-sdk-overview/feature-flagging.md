---
description: 當代技術產品團隊在產品發佈時，正採用持續傳遞原則。 Target可協助開發人員和產品團隊快速有效率地推出新的產品功能。
keywords: 推出；推出；連續交付；產品推出；分階段推出
seo-description: 當代技術產品團隊在產品發佈時，正採用持續傳遞原則。 Adobe Target helps developers and product teams roll out new product capabilities quickly and efficiently in a phased rollout.
seo-title: 當代技術產品團隊在產品發佈時，正採用持續傳遞原則。 Adobe Target可協助開發人員和產品團隊快速有效率地推出新的產品功能。
solution: Target
title: 功能標幟
topic: Standard
translation-type: tm+mt
source-git-commit: 08debab3ec3d2f6e6bfd3c42476dc1a021185ab7

---


# Feature flagging

Contemporary technology product teams are adopting continuous delivery principles for product launches. Adobe Target helps developers and product teams roll out new product capabilities quickly and efficiently in a phased rollout.

The following links provide information for key concepts you need to understand to enable continuous delivery:

* [A/B測試活動](/help/c-activities/t-test-ab/test-ab.md)
* [JSON offers](/help/c-experiences/c-manage-content/create-json-offer.md)
* [Audience refinements](/help/c-target/c-audiences/creating-a-profile-attribute-comparison-audience.md)

## 持續傳送

1. By default, turn the feature "off" on release.

   使用伺服器端或應用程式內變數來控制此項。

1. 建立Target JSON選件，將此變數設定為「on」。

1. 在具有兩個體驗的 [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)中建立A/B測試活動，並使用在單一體驗的上一個步驟中建立的JSON選件。

   或

   在表單式體驗撰寫器中建立A/B [測試活動](/help/c-experiences/form-experience-composer.md) ，並使用在上一步驟中建立的JSON選件。

   >[!NOTE]
   >
   >表單型體驗撰寫器可讓您建立單一體驗的A/B測試活動。 您無法使用VEC建立具有單一體驗的活動。

1. 指定您所要的活動流量配置。

   If you want to start by rolling this feature out to 5% of your visitors, specify 5 in the Targeting step of the three-part guided workflow and send 100% of the qualifying visitors to the experience with the JSON offer (Experience A).

   下圖顯示具有兩個體驗的VEC。

   ![Traffic allocation for feature flagging in the VEC](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging.png)

   The following illustration shows the Form-based Experience Composer with a single experience.

   ![Traffic allocation for feature flagging in the Form-based Experience Composer](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging-form.png)

1. You can increase the traffic allocation to this activity by gradually increasing the 5% either through the Target UI or using the API until you reach 100% traffic allocation.

   >[!NOTE]
   >
   >A/B測試活動會對作業中的訪客造成黏著影響。 如果您減少流量分配，開始檢視此功能的訪客會繼續檢視，直到重設工作階段為止。

## A/B Test features

如果您使用A/B/...N測試功能，請使用上述方法並進行下列改進：

* 每個功能變體都應使用適當的JSON選件來表示，以便提供Target體驗。
* 您可以按上述方式管理此測試的流量分配。

## 參數化展開

上述方法可協助您管理受控制的轉出。

您只能為測試版參與者推出功能，然後再將功能推展給所有其他客戶。 這可透過運用「目標位置」( [mbox)參數或描述檔參數](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) ，輕 [松達成](/help/c-target/c-audiences/c-target-rules/visitor-profile.md)。 這些參數可與分階段流量分配一起使用。

## Server-side vs. client-side

Feature rollouts and testing can be delivered via Target APIs (and server-side SDKs) as well as the client side SDKs (JS, Mobile SDK). [](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)視您的網站、行動應用程式或資訊站的架構而定，您可運用Target的不同整合選項。
