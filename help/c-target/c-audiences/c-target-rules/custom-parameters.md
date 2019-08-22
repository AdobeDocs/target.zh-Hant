---
description: 自訂參數為 mbox 參數。如果您傳遞任何 mbox 參數至 mbox，或使用 targetPageParams 函數，則那些參數會出現在此處以便用於對象。
keywords: 自訂參數;目標自訂參數;targetpageparams;目標 mbox 參數
seo-description: 自訂參數為 mbox 參數。如果您傳遞任何 mbox 參數至 mbox，或使用 targetPageParams 函數，則那些參數會出現在此處以便用於對象。
seo-title: 自訂參數
solution: Target
title: 自訂參數
topic: Standard
uuid: a9eb62a6-e86a-4e7b-922c-ad87570435ba
translation-type: tm+mt
source-git-commit: 95adb145c9ac5a7135d489cf68c1a7c50cdfe33b

---


# 自訂參數{#custom-parameters}

自訂參數為 mbox 參數。如果您傳遞任何 mbox 參數至 mbox，或使用 targetPageParams 函數，則那些參數會出現在此處以便用於對象。

如需詳細資訊, 請參閱[將參數傳遞至全域 Mbox](https://marketing.adobe.com/resources/help/en_US/target/ov/c_pass_parameters_to_global_mbox.html)。

當您根據 mbox 參數建立自訂對象時，`mboxParameter` 不再提示您輸入 `mboxName`。mbox 名稱現在是可選項目。此變更可讓您使用多個 mbox 中的參數，或參考尚未記錄在 Edge 上的參數。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象]** &gt; **[!UICONTROL 建立對象」]**。
1. 為對象命名。
1. 按一下&#x200B;**[!UICONTROL 新增規則]** &gt; **[!UICONTROL 自訂]**。

   若要選取需要的參數:

   * 建立新對象時，從清單中選取參數名稱、開始輸入所需參數名稱的前幾個字元，或輸入所需參數名稱的全名。
   * 如果您記得 mbox 名稱，但不記得參數名稱，請使用核取方塊來篩選會傳遞所需參數的確定 mbox。
   不論使用哪一種方法，mbox 和參數之間並沒有任何連結。對象會以參數為基礎，在傳遞參數的所有 mbox 之間運作。

   如果您編輯現有對象，篩選條件會並陳在建立期間提供的 mbox 名稱。

1. 選擇一個求值器:

   * 包含 (不區分大小寫)
   * 不包含 (不區分大小寫)
   * 等於
   ![自訂參數受眾](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. 在新行中輸入每個值。
1. (可選) 按一下&#x200B;**[!UICONTROL 「新增規則」]並設定對象的其他規則。**
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

對象的[定義詳細資料快顯卡](../../../c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)會顯示「規則」區段中的參數名稱。不會參照用來篩選的 mbox。

>[!NOTE]
>
>對於 Target 18.5.1 版本 (2018 年 5 月 22 日) 前建立的自訂對象，mbox 名稱不會顯示於對象的定義快顯卡中。您必須重新儲存自訂對象，才能讓 mbox 名稱顯示於卡片中。

## 考量事項 {#considerations}

* 系統會評估特定mbox的觀眾和活動。如果全域mbox傳遞一個參數，但區域mbox不適用，則訪客不符合該活動的資格。

## 訓練影片: 建立對象

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=chi_hant)