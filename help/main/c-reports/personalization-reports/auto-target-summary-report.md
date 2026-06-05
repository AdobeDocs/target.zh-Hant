---
keywords: 報表；自動鎖定目標；AT；報表
description: 瞭解如何解譯Adobe Target中的自動鎖定目標摘要報表。 您可以從此報表切換至「自動化區段」和「重要屬性」報表。
title: 如何使用自動鎖定目標摘要報表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
TQID: https://experienceleague.adobe.com/de9ST0undYRSL-BMmwEhvbU7PsfHgYieNAWY-qsQ-Z8
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 666
ht-degree: 35%

---

# [!UICONTROL 自動鎖定目標摘要報表]

有關如何解譯[!DNL Adobe Target]中[!UICONTROL 自動鎖定目標摘要]報表的資訊。

>[!NOTE]
>
>[!UICONTROL 自動鎖定目標]屬於[!DNL Target Premium]方案的一部分。 沒有[Target Premium授權](/help/main/c-intro/intro.md#premium)的[!DNL Target Standard]不包含此專案。

若要顯示[!UICONTROL 自動鎖定目標摘要]報告：

1. 從[!UICONTROL 活動]頁面，按一下所需的[!UICONTROL 自動鎖定目標]活動。

   如果您有許多活動，請按一下篩選器（![篩選器圖示](/help/main/assets/icons/Filter.svg)）圖示，以篩選清單，方法是從[!UICONTROL 型別]、[!UICONTROL 狀態]、[!UICONTROL 報告Source]、[!UICONTROL 體驗撰寫器]、[!UICONTROL 量度型別]和[!UICONTROL 活動Source]下拉式清單中選取選項。

1. 按一下&#x200B;**[!UICONTROL 報表]**&#x200B;標籤，然後按一下所需的圖示：

   * **[!UICONTROL 表格檢視]** （![表格檢檢視示](/help/main/assets/icons/Table.svg) ）
   * **[!UICONTROL 圖表檢視]** （ ![圖表檢檢視示](/help/main/assets/icons/GraphTrend.svg) ）
   * **[!UICONTROL 自動化區段]** （ ![自動化區段報表](/help/main/assets/icons/AutomatedSegment.svg) ）
   * [!UICONTROL 重要屬性]** （![重要屬性圖示](/help/main/assets/icons/ViewList.svg) ）

## 表格檢視

解譯[!UICONTROL 自動鎖定目標]報表時的一些秘訣和考量：

* 表格中的各個列可協助您瞭解活動績效。

   * 報表頁面上表格的前兩列顯示指派給控制的訪客（亦即隨機提供的體驗）與指派給個人化演演算法的訪客之間的A/B測試結果。 此資訊可用於測量個人化演演算法與隨機提供控制相較之下的執行情形。
   * 剩餘的列會顯示體驗等級的結果。 對於每個體驗，兩種訪客的平均回應之間會相互比較: 以隨機提供的控制來顯示體驗，或利用個人化演算法來顯示體驗。

* 在報告中，每個體驗旁的綠色勾號圖示表示已為該體驗產生的個人化機器學習模型。 時鐘圖示表示，提供的流量還不足以建立模型。

   * 因為是針對每個體驗而建立模型，看到的模型可能屬於有綠色勾號的一些體驗，也可能屬於有時鐘圖示的體驗。
   * 在此情況下，為了加速活動來為所有體驗建立模型，更多流量會傳送至未建立模型的體驗。
   * 至少必須有兩個體驗具有已建置的模型（綠色勾號），個人化才能開始。

* 比較體驗A和體驗B的轉換率在[!UICONTROL 自動鎖定目標]中不是正確的比較。 問題在於智慧地或隨機地提供時 (即與控制相比)，體驗 A 何時表現較佳。 市場行銷人員也要小心解讀個別體驗的提升度，因為個人化演算法會嘗試以整個活動的成功量度而最佳化，而非針對每個體驗。
* 提升度最高的體驗可視為在母體內有最大的差異性。 也就是說，演演算法已找到最喜歡該特定體驗的區段。
* 表格中的各個欄會顯示造訪次數、轉換率、平均提升度和信賴等級，以及信賴度。 如需詳細資訊，請參閱[A/B測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## 圖表檢視

使用兩個下拉式清單，選擇所需的量度、計數方法等。 如需詳細資訊，請參閱[報表設定總覽](/help/main/c-reports/c-report-settings/report-settings.md)：

## 自動化區段

此報表會顯示不同訪客對您的AP/AT活動中的選件/體驗有何不同回應。 此報表顯示[!DNL Target]個人化模型定義的不同自動化區段如何回應活動中的選件/體驗。

如需詳細資訊，請參閱[自動化區段報表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要屬性

此報表說明在不同的活動中，不同屬性對於模型決定個人化的方式有多大（或多少）重要性。 此報表顯示影響模型及其相對重要性的常見屬性。

如需詳細資訊，請參閱[重要屬性報表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。
