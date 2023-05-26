---
keywords: 鎖定目標； AP報表；自動個人化報表；活動層級報表；選件層級報表；選件詳細資料報表；常見問題集
description: 瞭解如何在Adobe Target中解譯Automated Personalization摘要報表。 您可以從此報表切換至「自動化區段」和「重要屬性」報表。
title: 如何使用Automated Personalization摘要報表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 31%

---

# Automated Personalization 摘要報表

使用者可以使用專門的摘要報告 [!UICONTROL Automated Personalization] 中的活動 [!DNL Adobe Target].

>[!NOTE]
>
>[!DNL Target Premium] 解決方案提供[!UICONTROL 自動個人化]功能。但不包含在 [!DNL Target Standard] 不含 [Target Premium授權](/help/main/c-intro/intro.md#premium).

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，從清單中按一下所需的[!UICONTROL 「自動個人化」]活動，然後按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

   如果您有許多活動，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「自動個人化」]，以篩選清單。

1. (可選) 按&#x200B;**[!UICONTROL 「下載」]**&#x200B;圖示，以下載依所有可用成功量度分解的摘要檢視 (例如，比較「控制」與「目標」流量)。

[!UICONTROL 自動個人化]提供下列報表:

* 活動層級
* 選件層級
* 自動化區段
* 重要屬性

## 活動層級報表 {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活動層級]報表會比較使用[!UICONTROL 自動個人化]演算法與隨機提供內容 (控制) 兩者的彙總效能。

![活動層級報表](/help/main/c-reports/assets/box_plot_ap.png)

A/B 測試結果解釋的標準規則 (包括提升度、信賴度、趨勢、期間等等) 仍然適用。如需解釋結果的相關資訊，請參閱 [A/Bn 測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## 選件層級報表 {#section_CAA6409879E349C6906E2BE8156D87A1}

隨機森林 (Random Forest) 體驗的[!UICONTROL 選件層級]報表中，會比較每個套用演算法的選件與同樣的隨機提供選件 (控制) 兩者的效能。因此，在此檢視中，選件不應該相互比較。

按一下體驗演演算法（隨機森林或控制）以檢視 [!UICONTROL 選件層級] 報告。

![Adobe Target中的選件層級報表](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>時鐘圖示表示演演算法模型仍在建立中。 勾號圖示表示已建立基本演演算法。

選件會顯示於 [報表群組](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)，且這些報表群組可收合和展開。 按一下 **[!UICONTROL 控制]** 或 **[!UICONTROL 已定位]** 以按報表群組（而非選件）檢視彙總資訊。

## 自動化區段

按一下 [!UICONTROL 自動化區段] 圖示。 此報表顯示不同訪客對您的AP/AT活動中的選件/體驗有何不同回應。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![「自動化區段」圖示](/help/main/c-reports/assets/icon-automated-sements-ap.png)

如需詳細資訊，請參閱 [「自動化區段」報表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## 重要屬性

按一下 [!UICONTROL 重要屬性] 圖示。 此報表說明在不同的活動中，不同屬性對於模型決定個人化的方式有多重要。 此報表顯示影響模型及其相對重要性的常見屬性。

![「重要屬性」圖示](/help/main/c-reports/assets/icon-important-attributes-ap.png)

如需詳細資訊，請參閱 [「重要屬性」報表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## 常見問題集

### 活動層級和選件層級報表之間的資料為何不同？

**[!UICONTROL 活動層級] 報告**：訪客記錄於 [!UICONTROL 活動層級] 報表會擷取控制體驗與「鎖定目標」流量的造訪次數。 目標流量包括探索流量和個人化流量的混合。

**選件層級報表**：在上錄製的曝光數 [!UICONTROL 選件層級] 報表擷取每個選件的曝光次數。 因此，在一個以上位置的活動中，在中記錄的造訪總數 [!UICONTROL 選件層級] 跨所有報表群組的報表等於中針對「控制」或「已鎖定目標」流量所記錄的造訪次數的倍數。 [!UICONTROL 活動層級] 報告乘以活動中的位置總數。 在預設內容為可用選項的位置發生的預設內容曝光次數，會記錄在「預設內容」選件群組中。 未指派給報表群組的優惠方案曝光次數會記錄在「未分組」優惠方案群組中。

>[!NOTE]
>
>上記錄的曝光次數 [!UICONTROL 選件層級] 報表可能不是中記錄之造訪次數的確切整數倍。 [!UICONTROL 活動層級] 報告。 這是由於透過網際網路擷取報表資料流量時發生輕微差異（一般差異率低於5%）。 因此，當活動啟動後活動中可用的位置數量變更時，曝光次數不會是確切的倍數。
