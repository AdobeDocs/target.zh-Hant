---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: 如何使用「自動個人化摘要」報表？
title: 自動個人化摘要報表
feature: Reports
translation-type: tm+mt
source-git-commit: eb51e8951643fcf64d7a9464d57f809636c9c931
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 41%

---


# ![PREMIUM](/help/assets/premium.png) 自動個人化摘要報表

專門報告適用於[!DNL Adobe Target]中[!UICONTROL  Automated Personalization]活動的用戶。

>[!NOTE]
>
>[!DNL Target Premium] 解決方案提供[!UICONTROL 自動個人化]功能。它不包含在[!DNL Target Standard]中，而不含[Target Premium授權](/help/c-intro/intro.md#premium)。

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，從清單中按一下所需的[!UICONTROL 「自動個人化」]活動，然後按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

   如果您有許多活動，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「自動個人化」]，以篩選清單。

1. (可選) 按&#x200B;**[!UICONTROL 「下載」]**&#x200B;圖示，以下載依所有可用成功量度分解的摘要檢視 (例如，比較「控制」與「目標」流量)。

[!UICONTROL 自動個人化]提供下列報表:

* 活動層級
* 選件層級
* 自動化區段
* 重要屬性

## 活動級別報告{#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活動層級]報表會比較使用[!UICONTROL 自動個人化]演算法與隨機提供內容 (控制) 兩者的彙總效能。

![活動層級報表](/help/c-reports/assets/box_plot_ap.png)

A/B 測試結果解釋的標準規則 (包括提升度、信賴度、趨勢、期間等等) 仍然適用。如需解釋結果的相關資訊，請參閱[關於轉換率](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)。

## 選件層級報表{#section_CAA6409879E349C6906E2BE8156D87A1}

隨機森林 (Random Forest) 體驗的[!UICONTROL 選件層級]報表中，會比較每個套用演算法的選件與同樣的隨機提供選件 (控制) 兩者的效能。因此，在此檢視中，選件不應該相互比較。

按一下體驗演算法（隨機森林或控制項）以檢視「選件層級」報表。

![](assets/ap_OfferLevelRpt.png)

選件可顯示在報表群組內，而這些報表群組可以折疊和展開。在下拉式清單中選取[!UICONTROL 「報表群組」]，以檢視依報表群組 (而不是依選件) 彙總的資訊。

>[!NOTE]
>
>時鐘圖示表示演算法模型還在建立中。複選標籤表徵圖表示已建立基本算法。

## 「活動層級」和「選件層級」報表之間的資料差異

**[!UICONTROL 活動] 級別報告**:「活動層級」報 [!UICONTROL 表] 上記錄的瀏覽次數會擷取控制體驗與「目標」流量。目標流量包括探索流量和個人化流量的混合。

**選件層級報表**:「選件層級」報 [!UICONTROL 表記] 錄的曝光次數會擷取每個選件的曝光次數。因此，在具有多個位置的活動中，所有報告群組中，[!UICONTROL 選件層級]報告中記錄的瀏覽總數等於[!UICONTROL 活動層級]報告中針對控制或目標流量記錄的瀏覽次數乘以活動中的位置總數。 在預設內容為可用選項的位置發生預設內容的曝光記錄在「預設內容」選件群組中。 未指派給報告群組的選件印象會記錄在「未分組」選件群組中。

>[!NOTE]

[!UICONTROL 選件層級]報表中記錄的曝光次數，可能不是[!UICONTROL 活動層級]報表中記錄之瀏覽次數的精確整數倍。 這是由於擷取網路上的報告資料流量時，會發生輕微差異（一般差異率低於5%）。 因此，當活動啟動後活動中可用的位置數量變更時，印象數量將不是精確倍數。

## 自動化區段

按一下「自動化區段」圖示。 此報表顯示不同訪客對您AP/AT活動中的選件／體驗的回應方式。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![自動化區段圖示](/help/c-reports/assets/icon-automated-sements-ap.png)

如需詳細資訊，請參閱[自動化區段報表](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要屬性

按一下[!UICONTROL 重要屬性]表徵圖。 此報表顯示在不同活動中，不同屬性對於模型決定個人化的方式更重要（或更少）。 此報表顯示影響模型及其相對重要性的常見屬性。

![重要屬性圖示](/help/c-reports/assets/icon-important-attributes-ap.png)

如需詳細資訊，請參閱[重要屬性報表](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。
