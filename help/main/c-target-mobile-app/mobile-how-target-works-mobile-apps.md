---
description: 瞭解如何使用Adobe移動軟體開發工具包向移動應用程式訪問者顯示最佳體驗。
title: 如何 [!DNL Target] 在移動應用中工作？
feature: Implement Mobile
role: Developer
exl-id: 1a5f34dc-932d-47c7-b730-6d1658343fb4
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 84%

---

# 如何 [!DNL Target] 在移動應用中工作

Adobe Mobile SDK 會連絡 Target 伺服器來取得內容以及其他資料點，對使用者顯示正確的體驗。

## 目標位置和成功量度 {#section_A08AAB0ABA9C4568A5AFD4D27EF1CE74}

*目標位置*&#x200B;又稱為 mbox。應用程式中識別的位置可供測試或個人化 (例如，主畫面的歡迎訊息)。測試建立程序期間會識別這些位置。

A *[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)*&#x200B;是使用者執行的動作，可指出特定的活動是否成功 (例如，註冊、購物、訂票等)。

![](assets/mobile-target-location.png)

* **目標位置:** 註冊按鈕下方顯示的內容。

   此特定使用者在下午 6 點以前免運費。此位置可重複用於多個 Target 活動，以執行 A/B 測試和個人化。

* **成功量度:** 使用者點選註冊按鈕而執行的動作。

**瞭解 Target 在 SDK 中如何運作**

![](assets/how-target-mobile-works.png)
