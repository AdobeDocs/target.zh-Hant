---
keywords: 鎖定目標;對象;報表;成功量度
description: 了解如何在 [!DNL Adobe Target] 符合報表對象使用者的資格。
title: 我可以將報表對象套用至成功量度嗎？
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 52%

---

# 套用報表對象至成功量度

選擇符合中報表對象使用者資格的成功量度 [!DNL Adobe Target].

對於所有活動，[!UICONTROL 「套用於」]下拉式清單可讓您將對象套用至成功量度，在達到量度之後和針對後續動作，您就可以檢視報表數字。

![success_metric影像](assets/success_metric.png)

例如，假設您已經為所有從首頁進入並抵達轉換頁面的訪客建立活動，但對於轉換之前已在購物車中增加 $50 以上的訪客，您還想要進一步向下鑽研。

此 [!UICONTROL 套用於] 下拉式清單可能提供三個類別：活動的任何訪客、只有達到活動中特定步驟的訪客，或只有達到轉換的訪客。 或者，換一種說法，您可以指定訪客必須到達活動進入頁面上的 Mbox、定義活動中途某一點的 Mbox，或活動最後的轉換 Mbox。

[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)必須先設定給活動才可使用。如果您尚未定義成功量度，下拉式清單中只會顯示兩個選項： [!UICONTROL 促銷活動參加項目] 和 [!UICONTROL 轉換].

將報表對象套用至成功量度時，請考量下列資訊:

* 若是套用成功量度的動作之前的動作， [!DNL Target] 不會套用分段的對象。
* 若是套用成功量度之後的動作， [!DNL Target] 套用分段的對象。

若要在報表中檢視區段，請從 [!UICONTROL 對象] 活動報表中的下拉式清單。

![reporting_audience_dropdown影像](assets/reporting_audience_dropdown.png)
