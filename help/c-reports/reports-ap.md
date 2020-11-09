---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Adobe Target中「自動個人化」活動的使用者可使用專用報表。
title: 自動個人化摘要報表
feature: reports
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 68%

---


# ![PREMIUM](/help/assets/premium.png) 自動個人化摘要報表{#automated-personalization-summary-reports}

Specialized reports are available to users of [!UICONTROL Automated Personalization] activities in [!DNL Adobe Target].

>[!NOTE]
>
>[!DNL Target Premium] 解決方案提供[!UICONTROL 自動個人化]功能。It is not included with [!DNL Target Standard] without a [Target Premium license](/help/c-intro/intro.md#premium).

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，從清單中按一下所需的[!UICONTROL 「自動個人化」]活動，然後按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

   如果您有許多活動，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「自動個人化」]，以篩選清單。

1. (可選) 按[!UICONTROL 「下載」]圖示，以下載依所有可用成功量度分解的摘要檢視 (例如，比較「控制」與「目標」流量)。

[!UICONTROL 自動個人化]提供下列報表:

## Activity Level report {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活動層級]報表會比較使用[!UICONTROL 自動個人化]演算法與隨機提供內容 (控制) 兩者的彙總效能。

![活動層級報表](/help/c-reports/assets/box_plot_ap.png)

A/B 測試結果解釋的標準規則 (包括提升度、信賴度、趨勢、期間等等) 仍然適用。如需解釋結果的相關資訊，請參閱[關於轉換率](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)。

## Offer Level report {#section_CAA6409879E349C6906E2BE8156D87A1}

隨機森林 (Random Forest) 體驗的[!UICONTROL 選件層級]報表中，會比較每個套用演算法的選件與同樣的隨機提供選件 (控制) 兩者的效能。因此，在此檢視中，選件不應該相互比較。

Click the experience algorithm (Random Forest or control) to view the [!UICONTROL Offer Level] report.

![](assets/ap_OfferLevelRpt.png)

選件可顯示在報表群組內，而這些報表群組可以折疊和展開。在下拉式清單中選取[!UICONTROL 「報表群組」]，以檢視依報表群組 (而不是依選件) 彙總的資訊。

>[!NOTE]
>
>時鐘圖示表示演算法模型還在建立中。勾號圖示表示已建立基礎演算法。

## 自動化區段

按一下「自 [!UICONTROL 動化區段] 」圖示。 此報表顯示不同訪客對您AP/AT活動中的選件／體驗的回應方式。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![自動化區段圖示](/help/c-reports/assets/icon-automated-sements-ap.png)

如需詳細資訊，請參閱「自 [動化區段」報表](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要屬性

按一下「重 [!UICONTROL 要屬性] 」表徵圖。 此報表顯示在不同活動中，不同屬性對於模型決定個人化的方式更重要（或更少）。 此報表顯示影響模型及其相對重要性的常見屬性。

![重要屬性圖示](/help/c-reports/assets/icon-important-attributes-ap.png)

如需詳細資訊，請參閱「重 [要屬性」報表](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。