---
keywords: 鎖定目標；AP報表；自動個人化報表；活動層級報表；選件層級報表；選件詳細資料報表；faq
description: 瞭解如何解譯Adobe Target中的Automated Personalization摘要報表。 您可以從此報表切換至「自動化區段」和「重要屬性」報表。
title: 如何使用Automated Personalization摘要報表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 11%

---

# Automated Personalization 摘要報表

[!DNL Adobe Target]中[!UICONTROL Automated Personalization]個活動的使用者可以使用專門的摘要報告。

>[!NOTE]
>
>[!UICONTROL Automated Personalization]是[!DNL Target Premium]解決方案的一部分。 在沒有[Target Premium授權](/help/main/c-intro/intro.md#premium)的情況下，[!DNL Target Standard]不包含此專案。

1. 按一下「**[!UICONTROL Activities]**」，從清單中按一下所需的[!UICONTROL Automated Personalization]活動，然後按一下「**[!UICONTROL Reports]**」標籤。

   如果您有許多活動，您可以從[!UICONTROL Type]下拉式清單中選取[!UICONTROL Automated Personalization]，以篩選清單。

1. （選用）按一下&#x200B;**[!UICONTROL Download]**&#x200B;圖示以下載依所有可用成功量度劃分的摘要檢視（例如，比較控制與鎖定流量）。

[!UICONTROL Automated Personalization]提供下列報表：

* 活動層級
* 選件層級
* 自動化區段
* 重要屬性

## 活動層級報表 {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL Activity Level]報告會比較使用[!UICONTROL Automated Personalization]演演算法的彙總效能與隨機提供的內容（控制）。

![活動層級報表](/help/main/c-reports/assets/box_plot_ap.png)

A/B 測試結果解釋的標準規則 (包括提升度、信賴度、趨勢、期間等等) 仍然適用。如需解譯結果的詳細資訊，請參閱[A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## 選件層級報表 {#section_CAA6409879E349C6906E2BE8156D87A1}

隨機森林體驗的[!UICONTROL Offer Level]報表會比較每個演演算法套用選件的效能，與相同隨機提供選件（控制）的效能。 因此，在此檢視中，不應將選件互相比較。

按一下體驗演演算法（隨機森林或控制）以檢視[!UICONTROL Offer Level]報表。

Adobe Target中的![選件層級報告](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>時鐘圖示表示演演算法模型仍在建立中。 勾號圖示表示已建立基礎演演算法。

選件會顯示在[報表群組](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)中，而且這些報表群組可以收合和展開。 按一下表格中的&#x200B;**[!UICONTROL Control]**&#x200B;或&#x200B;**[!UICONTROL Targeted]**，即可依報表群組檢視彙總資訊，而非依選件檢視。

## 自動化區段

按一下[!UICONTROL Automated Segments]圖示。 此報表會顯示不同訪客對您的AP/AT活動中的選件/體驗有何不同回應。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![自動化區段圖示](/help/main/c-reports/assets/icon-automated-sements-ap.png)

如需詳細資訊，請參閱[自動化區段報表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要屬性

按一下[!UICONTROL Important Attributes]圖示。 此報表說明在不同的活動中，不同屬性對於模型決定個人化的方式有多大（或多少）重要性。 此報表顯示影響模型及其相對重要性的常見屬性。

![重要屬性圖示](/help/main/c-reports/assets/icon-important-attributes-ap.png)

如需詳細資訊，請參閱[重要屬性報表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

## 常見問題集

### 活動層級和選件層級報表之間的資料為何不同？

**[!UICONTROL Activity Level]報告**： [!UICONTROL Activity Level]報告上記錄的造訪會擷取控制體驗與「已鎖定目標」流量的造訪次數。 目標流量包括探索流量和個人化流量的混合。

**選件層級報表**： [!UICONTROL Offer Level]報表上記錄的曝光數會擷取每個選件的曝光數。 因此，在一個以上位置的活動中，在[!UICONTROL Offer Level]報表中記錄的所有報表群組的造訪總數，等於[!UICONTROL Activity Level]報表中針對控制或目標流量記錄的造訪數乘以活動中的位置總數。 在預設內容為可用選項的位置中發生的預設內容閱聽，會記錄在「預設內容」選件群組中。 取消指派給報表群組的優惠方案曝光次數，會記錄在「未分組」優惠方案群組中。

>[!NOTE]
>
>[!UICONTROL Offer Level]報表上記錄的曝光數可能不是[!UICONTROL Activity Level]報表中記錄的造訪數的整數倍。 這是因為在網際網路上擷取報表資料流量時發生輕微差異（一般差異率低於5%）。 因此，當活動中的可用位置數量在活動啟動後有所變更時，曝光次數不會是確切的倍數。
