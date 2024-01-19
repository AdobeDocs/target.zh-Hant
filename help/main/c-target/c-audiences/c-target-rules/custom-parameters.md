---
keywords: 自訂參數;目標自訂參數;targetpageparams;目標 mbox 參數
description: 瞭解如何將自訂引數傳遞至 [!DNL Adobe Target] （僅適用於audiences）。
title: 我可以根據自訂引數鎖定訪客嗎？
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 37%

---

# 自訂參數

自訂引數是中的mbox引數 [!DNL Adobe Target]. 如果您將任何mbox引數傳遞至mbox，或使用 `targetPageParams` 函式，這些引數會出現在這裡，以用於對象。

如需詳細資訊，請參閱 [傳遞引數至全域mbox](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html){target=_blank}.

當您根據 mbox 參數建立自訂對象時，`mboxParameter` 不再提示您輸入 `mboxName`。mbox 名稱現在是可選項目。此變更可讓您使用多個 mbox 中的參數，或參考尚未記錄在 Edge 上的參數。

1. 在 [!DNL Target] 介面，按一下 **[!UICONTROL 受眾]** > **[!UICONTROL 建立對象]**.
1. 為對象命名並新增選擇性說明。
1. 拖放 **[!UICONTROL 自訂]** 放入對象產生器。

   若要選取需要的參數:

   * 建立對象時，請從清單中選取引數名稱，開始輸入所需引數名稱的第一個字元，或輸入所需引數名稱的完整名稱。
   * 如果您記得mbox名稱，但忘記引數名稱，請使用 [!UICONTROL 篩選依據] 下拉式清單，用於篩選傳遞所需引數的已知mbox。

   不論使用哪一種方法，mbox 和參數之間並沒有任何連結。對象會根據引數在所有傳遞該引數的mbox間運作。

   >[!NOTE]
   >
   >您從中選擇的mbox [!UICONTROL 篩選依據] 建立活動時沒有儲存下拉式清單。 此選項可讓您根據選取的 mbox 篩選參數。

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
   * 引數存在
   * 引數不存在
   * 引數值存在
   * 引數值不存在
   * 引數或值不存在
   * 請先閱讀
   * 終止於

   ![自訂參數受眾](assets/custom.png)

1. 在新行中輸入每個值。
1. （選用）為對象設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

對象的 [定義詳細資訊快顯示卡片](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) 在中顯示引數名稱 **[!UICONTROL 規則]** 區段。 不會參照用來篩選的 mbox。

>[!NOTE]
>
>對於在之前建立的自訂對象 [!DNL Target] 18.5.1版（2018年5月22日），mbox名稱不會顯示在對象的定義快顯示卡片中。 再次儲存自訂對象，讓mbox名稱顯示於卡片中。

## 考量事項 {#considerations}

* 系統會針對特定 mbox 評估受眾和活動。例如，如果全域mbox傳送特定引數，但區域mbox並未這麼做，則以該引數為目標的活動/對象不符合區域mbox上的資格。
* 不會在內部mbox引數（例如mboxPC、mboxSession、mbox3rdPartyId、mboxMCSDID、mboxMCAVID、mboxMCGVID、mboxCount、mboxId和mboxVersion）上評估鎖定目標。

## 訓練影片：建立對象 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
