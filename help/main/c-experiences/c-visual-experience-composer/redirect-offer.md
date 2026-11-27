---
keywords: 重新導向；重新導向url；傳送至不同頁面
description: 瞭解當您想要將訪客傳送至其他頁面而不是在相同頁面上顯示內容時，如何使用Adobe [!DNL Target]中的「重新導向至URL」選項。
title: 我可以將頁面重新導向至不同的URL嗎？
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: 'https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 2%
---
# 重新導向至 URL {#redirect-to-url}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何使用&#x200B;**[!UICONTROL 重新導向至URL]**&#x200B;選項，將訪客傳送至不同頁面，而不是在同一頁面上顯示內容。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 重新導向至URL]**&#x200B;選項會將訪客傳送至不同頁面，而不是在相同頁面上顯示內容。 它適合比較兩個完全不同的頁面，而不是一個頁面內內容的片段。 A/B測試則會比較頁面A與頁面B：一個體驗指向預設頁面A，另一個體驗會重新導向至頁面B。

重新導向選件會執行可重新導向瀏覽器的JavaScript程式碼。 程式碼使用`window.location.replace();`方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。 因此，訪客仍然可以使用瀏覽器的返回按鈕。

## 建立重新導向選件 {#create-redirect-offer}

重新導向的體驗會定義將訪客傳送至的頁面，以及重新導向的條件（選擇性）。

1. 建立體驗。

1. 在&#x200B;**[!UICONTROL 體驗]**&#x200B;框架中，針對重新導向的體驗按一下&#x200B;**[!UICONTROL 更多動作]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ）。

1. 按一下&#x200B;**[!UICONTROL 重新導向至URL]**。

   ![其他動作圖示](assets/redirect_1.png)

1. 在&#x200B;**[!UICONTROL 重新導向至URL]**&#x200B;對話方塊中，輸入頁面B的URL。

   ![其他動作圖示](assets/redirect_2.png)

1. （選用） Select包含目前查詢引數的選項。

   選取此選項時，訪客URL中`?`之後的所有專案都會在重新導向時附加至重新導向URL。

## 限制

重新導向選件有下列限制：

* **A4T：**&#x200B;使用A4T之活動中的重新導向選件需要符合特定最低需求的實作，且適用其他重要資訊。 請參閱[重新導向選件 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。
* **表單式體驗撰寫器：**&#x200B;在屬於頁面的mbox中不使用重新導向選件。 僅使用屬於HTML `<head>`一部分的指令碼標籤中的重新導向選件，且一律使用自動建立並設定全域mbox的重新導向選件。

>[!NOTE]
>
>若要傳遞登入頁面的反向連結值，請使用HTML選件，而非重新導向選件。

## 已知問題

at.js實作中的重新導向活動可能會導致預覽URL進入回圈，並重複傳送選件。 請改用[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)來預覽及測試活動。 此問題不會影響實際傳送選件。 (TGT-23019)
