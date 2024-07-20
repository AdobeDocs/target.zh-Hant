---
keywords: Target;報表;報表設定;極端訂單;極端值
description: 瞭解如何排除極端值，以免影響Adobe [!DNL Target] 中的報告，讓少數不尋常的訂單不會影響您的活動結果。
title: 如何在報表中排除極端值？
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 65%

---

# 排除極端值

您可以排除極端值，以免影響[!DNL Adobe Target]中的報表，讓少數不尋常的訂單不會影響您的活動結果。 異常訂單的範例可能是為整個團隊購買制服的教練，而非購買個別制服的個別購買者。

>[!NOTE]
>
>[!UICONTROL Exclude Extreme Values]旗標僅適用於具有[!UICONTROL Revenue]和[!UICONTROL Engagement]量度型別的活動。

系統會根據下述規則自動標記極端值。您可在報表中的查看極端訂單和排除極端值之間切換。一旦活動執行超過一小時或 15 筆訂單 (以先到者為準)，活動便會排除其極端值。

如果值與使用上個月資料的平均訂購值 (直到進行計算的時間點) 相差超過 +/- 3 個標準差，就視為極端值。

例如，極端值篩選器在使用 RPV 時經常相當實用。RPV 結合了轉換率和平均訂購值，通常會公開這些的揮發性。如果您使用 RPV 並判斷訂單未顯示為常態分佈，則在套用巨量訂購篩選器後應該能看到較常態的結果。

將值標記為極端時，其在促銷活動期間至該時間點的訂單值會以「體驗的平均訂購值」取代，並排除極端訂購內容。在[!UICONTROL Order Details]報表和CSV下載中，訂單也會標示為極端以用於每日結果。

**若要從您的報表中排除極端值:**

1. 開啟包含收入或參與量度型別的活動，然後按一下「**[!UICONTROL Reports]**」標籤。
1. 按一下齒輪圖示以顯示&#x200B;**[!UICONTROL Settings]**&#x200B;對話方塊。

   ![步驟結果](assets/exclude_extreme_values.png)

1. 視需要將&#x200B;**[!UICONTROL Exclude Extreme Values]**&#x200B;切換滑至「開啟」或「關閉」位置。
1. 按一下 **[!UICONTROL Save]**。
