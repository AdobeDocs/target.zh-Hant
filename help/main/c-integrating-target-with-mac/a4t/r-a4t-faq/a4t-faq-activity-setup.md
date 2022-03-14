---
keywords: faq;常見問題集;analytics for target;a4T;活動設定
description: 使用Analytics時查找有關活動設定的問題的答案 [!DNL Target] (A4T)。 A4T允許您使用Analytics報告 [!DNL Target] 活動。
title: 在何處可以找到有關A4T活動設定的常見問題？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 20%

---

# 活動設定 - A4T 常見問題集

本主題包含有關活動設定和使用的常見問題解答 [!DNL Analytics] 作為 [!DNL Target] (A4T)。

## Analytics 作為報表來源 (A4T) 時支援哪些活動類型? {#section_5E4F58CD25A5424E869E6FE0803968EF}

如需完整清單，請參閱 [Adobe Analytics 作為 Adobe Target (A4T) 的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)中的「支援的活動類型」。

## 配置我的目標度量時，為什麼無法訪問高級設定？

對於使用 [!DNL Analytics] 作為報告源(A4T)，目標度量使用[!UICONTROL 增量計數和保留活動中的用戶]&quot;和&quot;[!UICONTROL 論每個印象]。 這些設定是 *不* 可配置。

有關詳細資訊，請參閱「配置我的目標度量時，為什麼無法訪問高級設定選項？」 在 [度量定義 — A4T常見問題](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)。

## 我剛才建立了活動。為何沒看到任何資料進入? {#section_9F8092BE4225442896F926540292F221}

建立活動時， [!DNL Target] 將分類檔案發送到 [!DNL Analytics]。 儘管 [!DNL Analytics] 是捕獲和處理資料，它在更新分類檔案之前不會在報告中顯示。 此過程最多需要24小時。 如果 48 小時之後沒看到資料，請[聯絡客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。或者，如果您知道您啟動了活動，則可以提前幾天建立活動，並在保存活動時發送分類。 於是，啟動後資料即會立即出現在報表中。請注意，處理資料需要45-90分鐘 [!DNL Analytics]。

## 建立活動時，為什麼不能選擇分析作為報告源？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

您可以更改 [!UICONTROL 報告設定] 選項 [!UICONTROL 管理]。

1. 在 [!DNL Target]按一下 **[!UICONTROL 管理]**。
1. 在&#x200B;**[!UICONTROL 「用於報表的 Experience Cloud 解決方案」]**&#x200B;下拉式清單中，按一下&#x200B;**[!UICONTROL 「為每個活動選取」]**。

![](assets/select-per-activity.png)

**[!UICONTROL 「目標與設定」]**&#x200B;畫面中會啟用&#x200B;**[!UICONTROL 「報表來源」下拉式清單，以供您建立和編輯活動。]**

始終使用 [!DNL Analytics] 作為報告源，選擇 **[!UICONTROL Adobe Analytics]** 從中的下拉清單 [!UICONTROL 管理]。

## 訪問者能否在使用A4T的「自動目標」活動中在不同訪問中在目標體驗和受控體驗之間切換？

以下假設訪問期間訪問者的visitorId不會更改，則為正確。

如果在活動中調整流量分配百分比，則訪問者有可能在目標體驗和控制體驗之間移動。

如果百分比未在活動中調整，則最初看到控制項的訪問者將始終被發送到控制項。 發送到目標體驗的訪問者始終被發送到目標體驗。

* 在目標「桶」中，如果機器學習模型確定不同的體驗與新的訪問相關，則訪問者可以被發送到與訪問不同的體驗。
* 將訪問者分配給流量的控制「儲存桶」後，將始終看到相同的體驗，因為經驗分配基於訪問者的visitorId的確定性偽隨機散列。


## 我能用二項式 [!DNL Analytics] 以段作為優化目標的度量 [!UICONTROL 自動分配] 活動？ {#binomial}

不能使用 [!DNL Analytics] 以段作為優化目標的度量 [!UICONTROL 自動分配] 的子菜單。 作為一種解決方法，您可以定義實現相同目標的自定義事件，並將其用作優化目標度量。