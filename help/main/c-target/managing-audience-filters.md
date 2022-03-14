---
keywords: 目標；受眾篩選；受眾；篩選
description: 瞭解如何在 [!DNL Adobe Target] 查看共用特徵的訪問者的資料。
title: 我是否可以使用受眾篩選器進行報告？
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 74%

---

# 報表的對象篩選條件

受眾篩選（或受眾） [!DNL Adobe Target] 是一組具有特定特徵或一組特徵的訪問者。

使用對象篩選條件來指定用於報表的對象。您可以選取對象，並比較其效能與整體流量。您可能想要與一般流量進行比較，以瞭解獲勝者在各種流量來源下是否不同。受眾篩選器可幫助您發現可能針對不同內容的受眾。 在許多情況下，單一成功者並不適用於所有流量。

例如，從特定搜尋引擎到達頁面的訪客可歸為一個對象。其他對象可依據性別、年齡、地點、註冊狀態、購買歷史記錄，或您幾乎可以為訪客收集的任何其他詳細資料。使用對象篩選條件來分隔訪客流量，並比較每個流量區段的體驗效能。

在規劃對活動使用對象篩選條件時，請考量下列準則：

* **訪客可能屬於多個對象。** 如果設定了兩個觀眾(例如，&quot;新訪客&quot;和&quot;Google訪客&quot;)，並且一個人符合這兩個標準，則在兩個觀眾中統計並跟蹤該訪客。 因此，對象中的訪客總數和活動中的訪客數並不相符。
* **在啟動活動之前設定受眾。**&#x200B;無法回溯擷取對象資料。如果您在啟動活動之前未設定對象篩選條件，然後在活動執行一段時間後，又決定使用對象篩選條件，則無法收集已成過去的資料。
* **從兩個到四個對象開始。**&#x200B;著重於基本資訊，例如流量來源。
* **視需要重新命名對象。**&#x200B;您可以在不影響資料的情況下重新命名對象，讓對象名稱在正在收集的結果中更有意義，即使活動在使用中也一樣。
* **輸入精確值。**&#x200B;對象篩選值區分大小寫。例如，若您使用對象來篩選城市，則應使用 &quot;OR&quot; 條件來包含可能的拼字與大小寫變化，例如 &quot;Vienna&quot;、&quot;vienna&quot;、&quot;wien&quot; 和 &quot;Wien&quot;。
* **[!UICONTROL 從「對象」清單建立的對象可重複使用。]**&#x200B;在活動中建立的對象無法重複使用。

下列幾節提供有關設定和報告對象的詳細資訊:

| 任務 | 主題 |
|--- |--- |
| 建立適當的活動或測試。 | [活動和測試](/help/main/c-intro/target-key-concepts.md) |
| 必要的話，建立對象。 | [建立對象](/help/main/c-target/c-audiences/create-audience.md) |
| 必要的話，合併多個對象。 | [合併多個對象](/help/main/c-target/combining-multiple-audiences.md) |
| 在活動的「目標與設定」頁面上套用對象。 | A/BTest: [目標和設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization:  [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>經驗目標： [目標和設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>多元Test:  [目標和設定](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Recommendations活動設定](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>活動設定： [活動設定](/help/main/c-activities/activity-settings.md) |
| 檢視含有對象篩選條件之相關資訊的報表。 | [報表設定](/help/main/c-reports/c-report-settings/report-settings.md) |
