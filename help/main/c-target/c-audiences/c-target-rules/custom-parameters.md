---
keywords: 自訂參數;目標自訂參數;targetpageparams;目標 mbox 參數
description: 瞭解如何將自定義參數傳遞到 [!DNL Adobe Target] 供觀眾使用。
title: 是否可以基於自定義參數瞄準訪問者？
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 41%

---

# 自訂參數

自定義參數是中的mbox參數 [!DNL Adobe Target]。 如果將任何mbox參數傳遞給mboxes，或使用 `targetPageParams` 函式，這些參數將顯示在此供用戶使用。

有關詳細資訊，請參見 [將參數傳遞到全局框](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/)。

當您根據 mbox 參數建立自訂對象時，`mboxParameter` 不再提示您輸入 `mboxName`。mbox 名稱現在是可選項目。此變更可讓您使用多個 mbox 中的參數，或參考尚未記錄在 Edge 上的參數。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 命名訪問群體並添加可選說明。
1. 拖放 **[!UICONTROL 自定義]** 到「受眾構建器」。

   若要選取需要的參數:

   * 建立訪問群體時，從清單中選擇參數名稱，開始鍵入所需參數名稱的首個字元，或鍵入所需參數名稱的全名。
   * 如果記住mbox名稱，但不記得參數名稱，請使用 [!UICONTROL 篩選依據] 下拉清單，在傳遞所需參數的已知框上進行篩選。

   不論使用哪一種方法，mbox 和參數之間並沒有任何連結。受眾根據傳遞該參數的所有框中的參數工作。

   如果您編輯現有對象，篩選條件會並陳在建立期間提供的 mbox 名稱。

1. 選擇一個求值器:

   * 包含 (不區分大小寫)
   * 不包含 (不區分大小寫)
   * 等於
   * 不等於
   * 大於
   * 大於或等於
   * 小於
   * 小於或等於
   * 參數存在
   * 參數不存在
   * 參數值存在
   * 參數值不存在
   * 參數或值不存在
   * 請先閱讀
   * 終止於

   ![自訂參數受眾](assets/custom.png)

1. 在新行中輸入每個值。
1. （可選）為受眾設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

對象的[定義詳細資料快顯卡](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)會顯示「規則」區段中的參數名稱。****&#x200B;不會參照用來篩選的 mbox。

>[!NOTE]
>
>對於在 [!DNL Target] 18.5.1版（2018年5月22日），在觀眾定義彈出式卡中不顯示框名。 再次保存自定義受眾，以獲取要在卡中顯示的框名。

## 考量事項 {#considerations}

* 系統會針對特定 mbox 評估受眾和活動。例如，如果全局框傳遞了某個參數，但區域框不傳遞，則針對該參數的活動/受眾在區域框上不合格。
* 不會根據內部mbox參數（如mboxPC、mboxSession、mbox3rdPartyId、mboxMCSDID、mboxMCVID、mboxMCGVID、mboxCount、mboxId和mboxVersion）評估目標。

## 培訓視頻：建立受眾 ![教程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
