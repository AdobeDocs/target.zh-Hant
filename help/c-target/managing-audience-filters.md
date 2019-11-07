---
keywords: 定位；對象篩選；對象；篩選
description: Adobe Target（或觀眾）中的觀眾篩選器是一組具有特定特性或一組特性的訪客。
title: Adobe target中報告的對象篩選
uuid: ca2632c0-87e4-4a85-95e6-e63cf800ab2f
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 報表的對象篩選條件{#audience-filters-for-reporting}

對象篩選 (或數個對象) 是指共用特定特性或一組特性的訪客群組。

使用對象篩選條件來指定用於報表的對象。您可以選取對象，並比較其效能與整體流量。您可能想要與一般流量進行比較，以瞭解獲勝者在各種流量來源下是否不同。這可協助您尋找應該潛在地鎖定以不同內容為目標的對象。在許多情況下，單一成功者並不適用於所有流量。

例如，從特定搜尋引擎到達頁面的訪客可歸為一個對象。其他對象可依據性別、年齡、地點、註冊狀態、購買歷史記錄，或您幾乎可以為訪客收集的任何其他詳細資料。使用對象篩選條件來分隔訪客流量，並比較每個流量區段的體驗效能。

在規劃對活動使用對象篩選條件時，請考量下列準則：

* **訪客可能屬於多個對象。** 如果設定了兩個對象（例如「新訪客」和「來自Google的訪客」），且一個人同時符合這兩個條件，則會在兩個對象中計算並追蹤此訪客。 因此，對象中的訪客總數和活動中的訪客數並不相符。
* **在啟動活動之前設定觀眾。**&#x200B;無法回溯擷取對象資料。如果您在啟動活動之前未設定對象篩選條件，然後在活動執行一段時間後，又決定使用對象篩選條件，則無法收集已成過去的資料。
* **從兩個到四個對象開始。**&#x200B;著重於基本資訊，例如流量來源。
* **視需要重新命名對象。**&#x200B;您可以在不影響資料的情況下重新命名對象，讓對象名稱在正在收集的結果中更有意義，即使活動在使用中也一樣。
* **輸入精確值。**&#x200B;對象篩選值區分大小寫。例如，若您使用對象來篩選城市，則應使用 "OR" 條件來包含可能的拼字與大小寫變化，例如 "Vienna"、"vienna"、"wien" 和 "Wien"。
* **從「對象」清單建立的對象可重複使用。**&#x200B;在活動中建立的對象無法重複使用。

下列幾節提供有關設定和報告對象的詳細資訊:

| 任務 | 主題 |
|--- |--- |
| 建立適當的活動或測試。 | [活動和測試](/help/c-intro/target-key-concepts.md) |
| 必要的話，建立對象。 | [建立對象](/help/c-target/c-audiences/create-audience.md) |
| 必要的話，合併多個對象。 | [合併多個對象](/help/c-target/combining-multiple-audiences.md) |
| 在活動的「目標與設定」頁面上套用對象。 | A/B Test: [Goals and Settings](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization:  [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>Experience Targeting: [Goals and Settings](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Multivariate Test:  [Goals and Settings](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Recommendations activity settings](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Activity Settings: [Activity Settings](/help/c-activities/activity-settings.md) |
| 檢視含有對象篩選條件之相關資訊的報表。 | [報表設定](/help/c-reports/c-report-settings/report-settings.md) |

