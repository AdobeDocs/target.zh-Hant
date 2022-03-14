---
keywords: 目標；AP報告；自動個性化報告；活動級別報告；提供級別報告；提供詳細報告；faq
description: 瞭解如何解釋Adobe Target的Automated Personalization摘要報告。 可以從此報告切換到「自動段」和「重要屬性」報告。
title: 如何使用Automated Personalization摘要報告？
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 38%

---

# ![PREMIUM](/help/main/assets/premium.png) 自動個人化摘要報表

專門的摘要報告可供 [!UICONTROL Automated Personalization] 活動 [!DNL Adobe Target]。

>[!NOTE]
>
>[!DNL Target Premium] 解決方案提供[!UICONTROL 自動個人化]功能。不包含在 [!DNL Target Standard] 沒有 [目標高級許可證](/help/main/c-intro/intro.md#premium)。

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，從清單中按一下所需的[!UICONTROL 「自動個人化」]活動，然後按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

   如果您有許多活動，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「自動個人化」]，以篩選清單。

1. (可選) 按&#x200B;**[!UICONTROL 「下載」]**&#x200B;圖示，以下載依所有可用成功量度分解的摘要檢視 (例如，比較「控制」與「目標」流量)。

[!UICONTROL 自動個人化]提供下列報表:

* 活動級別
* 服務級別
* 自動化區段
* 重要屬性

## 活動層報表 {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活動層級]報表會比較使用[!UICONTROL 自動個人化]演算法與隨機提供內容 (控制) 兩者的彙總效能。

![活動層級報表](/help/main/c-reports/assets/box_plot_ap.png)

A/B 測試結果解釋的標準規則 (包括提升度、信賴度、趨勢、期間等等) 仍然適用。如需解釋結果的相關資訊，請參閱[關於轉換率](/help/main/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)。

## 聘用級別報告 {#section_CAA6409879E349C6906E2BE8156D87A1}

隨機森林 (Random Forest) 體驗的[!UICONTROL 選件層級]報表中，會比較每個套用演算法的選件與同樣的隨機提供選件 (控制) 兩者的效能。因此，在此檢視中，選件不應該相互比較。

按一下體驗算法（隨機林或控制項）查看 [!UICONTROL 服務級別] 報告。

![](assets/ap_OfferLevelRpt.png)

選件可顯示在報表群組內，而這些報表群組可以折疊和展開。在下拉式清單中選取[!UICONTROL 「報表群組」]，以檢視依報表群組 (而不是依選件) 彙總的資訊。

>[!NOTE]
>
>時鐘圖示表示演算法模型還在建立中。複選標籤表徵圖表示已建立基本算法。

## 自動化區段

按一下 [!UICONTROL 自動化段] 表徵圖 此報告顯示不同訪問者對AP/AT活動中的服務/體驗的不同反應。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![自動段表徵圖](/help/main/c-reports/assets/icon-automated-sements-ap.png)

有關詳細資訊，請參見 [「 Automated Segments 」報告](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要屬性

按一下 [!UICONTROL 重要屬性] 表徵圖 此報表顯示在不同活動中，不同屬性對模型決定如何個性化更重要（或更不重要）。 此報表顯示影響模型及其相對重要性的常見屬性。

![重要屬性表徵圖](/help/main/c-reports/assets/icon-important-attributes-ap.png)

有關詳細資訊，請參見 [重要屬性報告](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

## 常見問題

### 為什麼「活動級別」和「服務級別」報告之間的資料存在差異？

**[!UICONTROL 活動級別] 報告**:記錄在 [!UICONTROL 活動級別] 報告捕獲訪問控制體驗的次數與「目標」流量。 目標流量包括勘探流量和個性化流量的混合。

**聘用級別報告**:記錄在 [!UICONTROL 服務級別] 報告可捕獲每個優惠的印數。 因此，在一個以上地點的活動中，記錄在 [!UICONTROL 服務級別] 所有報告組中的報告等於中為控制或目標通信記錄的訪問次數的倍數 [!UICONTROL 活動級別] 報告乘以活動中的位置總數。 在預設內容為可用選項的位置出現的預設內容印象記錄在「預設內容」服務組中。 未分配給報告組的報價印象記錄在「未分組」報價組中。

>[!NOTE]
>
>記錄在 [!UICONTROL 服務級別] 報告可能不是記錄在 [!UICONTROL 活動級別] 報告。 這是由於捕獲網際網路上的報告資料流量時出現少量差異（典型差異率低於5%）。 因此，當活動激活後活動中可用位置的數量發生更改時，印象數不會是確切的倍數。
