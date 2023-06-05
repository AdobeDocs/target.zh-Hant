---
keywords: 鎖定目標;對象;報表;成功量度
description: 瞭解如何在中選擇成功量度 [!DNL Adobe Target] 可讓使用者符合報表對象的資格。
title: 我可以套用報表對象至成功量度嗎？
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: bcbb6dec9d6add07c109b07bf125c1356ad2a8b9
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 43%

---

# 套用報表對象至成功量度

選擇符合報表對象使用者資格的成功量度 [!DNL Adobe Target].

對於所有活動，[!UICONTROL 「套用於」]下拉式清單可讓您將對象套用至成功量度，在達到量度之後和針對後續動作，您就可以檢視報表數字。

![success_metric圖片](assets/success_metric.png)

例如，假設您已經為所有從首頁進入並抵達轉換頁面的訪客建立活動，但對於轉換之前已在購物車中增加 $50 以上的訪客，您還想要進一步向下鑽研。

此 [!UICONTROL 套用位置] 下拉式清單可能會提供三個類別：

* 活動的任何訪客
* 僅限達到活動中特定步驟的訪客
* 僅限達到轉換的訪客

或者，換一種說法，您可以指定訪客必須到達活動進入頁面上的 Mbox、定義活動中途某一點的 Mbox，或活動最後的轉換 Mbox。

>[!NOTE]
>
>[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)必須先設定給活動才可使用。如果您尚未定義成功量度，您只會從下拉式清單中看到兩個選項： [!UICONTROL 行銷活動專案] 和 [!UICONTROL 轉換].


## 考量事項

將報表對象套用至成功量度時，請考量下列資訊:

* 只有從套用對象的量度開始的成功量度，才會顯示依對象分段的報表資料
* 對象套用對象之前的成功量度不會依對象分段，且會顯示所有訪客資料
* 系統會根據量度在活動定義中的順序來考慮量度，且 [!UICONTROL 主要目標] 是最後一個。

## 在報告中檢視分段

若要在報表中檢視細分，請從「 」中選取所需的對象 [!UICONTROL 對象] 活動報表中的下拉式清單。

![reporting_audience_dropdown圖片](assets/reporting_audience_dropdown.png)

## 範例

考慮具有成功量度1、成功量度2、成功量度3和主要目標的活動。

假設您已在「登入」上設定報告Audience1，並在「成功量度2」上設定報告Audience2。 對象會依下列方式篩選報表資料：

|  | 訪客 | 成功量度1 | 成功量度2 | 成功量度3 | 主要目標 |
| --- | --- | --- | --- | --- | --- |
| Audience1 | 已應用 | 已應用 | 已應用 | 已應用 | 已應用 |
| Audience2 | 未套用 | 未套用 | 已應用 | 已應用 | 已應用 |
