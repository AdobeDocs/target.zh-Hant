---
keywords: 自訂參數;目標自訂參數;targetpageparams;目標 mbox 參數
description: 了解如何將自訂參數傳遞至 [!DNL Adobe Target] 用於對象中。
title: 我可以根據自訂參數定位訪客嗎？
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
source-git-commit: 8890d29a71506095a166321e324a000b5ad862a6
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 40%

---

# 自訂參數

自訂參數是 [!DNL Adobe Target]. 如果您將任何mbox參數傳遞至mbox，或使用 `targetPageParams` 函式中，這些參數會顯示在此以用於對象。

如需詳細資訊，請參閱 [傳遞參數至全域mbox](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/){target=_blank}。

當您根據 mbox 參數建立自訂對象時，`mboxParameter` 不再提示您輸入 `mboxName`。mbox 名稱現在是可選項目。此變更可讓您使用多個 mbox 中的參數，或參考尚未記錄在 Edge 上的參數。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名並新增選用說明。
1. 拖放 **[!UICONTROL 自訂]** 匯入Audience Builder。

   若要選取需要的參數:

   * 建立對象時，從清單中選取參數名稱、開始輸入所需參數名稱的前幾個字元，或輸入所需參數名稱的完整名稱。
   * 如果您記得mbox名稱，但不記得參數名稱，請使用 [!UICONTROL 篩選依據] 下拉式清單，以篩選傳遞所需參數的已知mbox。

   不論使用哪一種方法，mbox 和參數之間並沒有任何連結。對象的運作方式會根據傳遞該參數之所有mbox上的參數。

   >[!NOTE]
   >
   >您從 [!UICONTROL 篩選依據] 建立活動時不會儲存下拉式清單。 此選項可讓您根據選取的mbox來篩選參數。

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
1. （選用）為對象設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

對象的[定義詳細資料快顯卡](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)會顯示「規則」區段中的參數名稱。****&#x200B;不會參照用來篩選的 mbox。

>[!NOTE]
>
>針對在 [!DNL Target] 18.5.1版（2018年5月22日）,mbox名稱不會顯示在對象的定義快顯卡中。 再次儲存自訂對象，以取得要顯示在卡片中的mbox名稱。

## 考量事項 {#considerations}

* 系統會針對特定 mbox 評估受眾和活動。例如，如果全域mbox傳遞特定參數，但地區mbox不傳遞，則定位該參數的活動/對象不符合地區mbox上的資格。
* 不會針對內部mbox參數（例如mboxPC、mboxSession、mbox3rdPartyId、mboxMCSDID、mboxMCVID、mboxMCGVID、mboxMCGVID、mboxCount、mboxId和mboxVersion）評估鎖定目標。

## 訓練影片：建立對象 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
