---
description: 特製的報表可供自動個人化的使用者使用。
keywords: 鎖定目標;AP 報表;自動個人化報表;活動層級報表;選件層級報表;選件詳細資料報表
seo-description: 特製的報表可供自動個人化的使用者使用。
seo-title: 自動個人化摘要報表
solution: Target
title: 自動個人化摘要報表
title-outputclass: premium
uuid: 959b6814-9686-4741-8a79-5957e64f6209
badge: premium
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) 自動個人化摘要報表{#automated-personalization-summary-reports}

特製的報表可供自動個人化的使用者使用。

>[!NOTE]
>
>自動個人化屬於 [!DNL Target Premium] 解決方案的一部分。[!DNL Target Standard] 若沒有 [!DNL Target Premium] 授權則不包含此功能。

1. 按一下 **[!UICONTROL 「活動」]**，從清單中按一下所需的[!UICONTROL 「自動個人化」]活動，然後按一下 **[!UICONTROL 「報表」]** 標籤。

   如果您有許多活動，您可以從[!UICONTROL 「類型」]下拉式清單中選取[!UICONTROL 「自動個人化」]，以篩選清單。

1. (可選) 按[!UICONTROL 「下載」]圖示，以下載依所有可用成功量度分解的摘要檢視 (例如，比較「控制」與「目標」流量)。

>[!NOTE]
>
>[!UICONTROL 自動個人化]報表沒有[!UICONTROL 「設定」]圖示可用。

[!UICONTROL 自動個人化]提供下列報表:

## 活動層級報表 {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活動層級]報表會比較使用[!UICONTROL 自動個人化]演算法與隨機提供內容 (控制) 兩者的彙總效能。

![](assets/box_plot_ap.jpg)

A/B 測試結果解釋的標準規則 (包括提升度、信賴度、趨勢、期間等等) 仍然適用。如需解釋結果的相關資訊，請參閱[關於轉換率](../c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)。

## 選件層級報表 {#section_CAA6409879E349C6906E2BE8156D87A1}

隨機森林 (Random Forest) 體驗的[!UICONTROL 選件層級]報表中，會比較每個套用演算法的選件與同樣的隨機提供選件 (控制) 兩者的效能。因此，在此檢視中，選件不應該相互比較。在下列範例中，可看出選件 D 在根據演算法邏輯 (隨機森林) 提供時，相較於隨機提供 (控制)，顯出有 12.43% 的提升度。

按一下體驗演算法 (隨機森林或控制)，以檢視「選件層級」報表。

![](assets/ap_OfferLevelRpt.png)

選件可顯示在報表群組內，而這些報表群組可以折疊和展開。在下拉式清單中選取[!UICONTROL 「報表群組」]，以檢視依報表群組 (而不是依選件) 彙總的資訊。

>[!NOTE]
>
>時鐘圖示表示演算法模型還在建立中。勾號圖示表示已建立基礎演算法。

