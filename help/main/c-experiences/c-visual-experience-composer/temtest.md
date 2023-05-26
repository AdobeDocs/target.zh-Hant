---
keywords: 範本測試; 範本; 類似頁面上有相同體驗; 範本測試
description: 瞭解如何使用Adobe [!DNL Target] 視覺化體驗撰寫器(VEC)可在結構類似或包含相同範本元素的多個頁面上包含相同體驗。
title: 我可以在類似頁面上包含相同體驗嗎？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 46%

---

# 在類似頁面上包含相同體驗

在中使用頁面範本 [!DNL Adobe Target] 提供結構給您的頁面，或如果您的頁面包含類似的元素，以測試類似結構化的頁面元素中或整個網域的變數。

若要正確運作，此功能必須用於具有類似結構或包含在所有頁面上具有相同結構的範本元素的頁面。

>[!IMPORTANT]
>
>使用此功能來變更不同頁面上的元素將可能造成未預期的結果。

例如，您可能會使用此功能來執行下列其中一項:

* 透過重新排列或移除元素來測試全域導覽列
* 從使用特定頁面範本的所有產品頁面移除項目
* 新增橫幅至所有產品頁面
* 變更文章範本的配置

您可以指定包含變更元素的頁面，或將變更套用至您的網站或網域。

1. 建立或編輯活動，如所述 [活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. 若要指定顯示體驗的頁面，請在 [!UICONTROL 視覺化體驗撰寫器] (VEC)按一下齒輪圖示，然後選取 **[!UICONTROL 頁面傳送]**.

   ![齒輪圖示>頁面傳送](/help/main/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. 按一下&#x200B;**[!UICONTROL 新增範本規則]**，然後指定您要新增體驗的頁面的條件。

1. 指定頁面範圍。頁面範圍可以是下列其中一項:

   * URL (如需Target如何評估URL的詳細資訊，請參閱 [鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * 網域
   * 路徑
   * 雜湊 (#) 片段 （將URL中跟隨#符號的部分設為目標。）
   * 查詢
   * 參數

1. 選擇一個運算子。

   運算子可指定運算子之後的項目與頁面範圍的相關性。可用的運運算元包括：

   * 包含
   * 不包含
   * 是 (區分大小寫)
   * 不是
   * 開始於
   * 終止於

1. 在頁面名稱中輸入可定義要新增體驗位置的字串，例如網域或包含的字串。

   例如，如果您選取&#x200B;**[!UICONTROL 網域]**&#x200B;和&#x200B;**[!UICONTROL 是 (區分大小寫)]**，請輸入要將體驗新增至所有頁面的網域。

   您可以包括多個項目。

   >[!IMPORTANT]
   >
   >多個專案會使用OR邏輯，這表示清單中的任何單一專案都會讓條件成立。

1. 如有需要，請按一下「 」以輸入其他條件 **[!UICONTROL 新增範本規則]** 並重複先前步驟中的程式。

   以 AND 邏輯聯合多個規則。[!DNL Target] 會將體驗新增至符合指定條件的所有頁面。

>[!IMPORTANT]
>
> [!DNL Target] 無法檢查頁面以確定它們能如預期般出現，因此，在將頁面公開之前，請務必使用此功能來測試受影響的頁面。

## 使用個案

檢閱下列使用案例，瞭解在您的網站上使用範本規則的方式：

### 在整個網域中呈現相同的活動

針對下列使用案例，您可以考慮使用範本規則在整個網域中呈現相同的活動：

* 若要包含全域頁首或頁尾
* 加入全球橫幅（例如COVID-19公告）
* 若要包含全域免運費促銷，請執行下列步驟：

1. 建立或編輯活動，如所述 [活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. 若要指定將顯示體驗的網域，請在視覺化體驗撰寫器中按一下齒輪圖示，然後選取 **[!UICONTROL 頁面傳送]**.

1. 按一下 **[!UICONTROL 新增範本規則]** > **[!UICONTROL 網域]**.

1. 從 **[!UICONTROL 選擇計算器]** 下拉式清單，選取 **[!UICONTROL 包含]**，然後指定網域。

   ![網域包含](/help/main/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## 訓練影片：視覺化體驗撰寫器(2/2) （上午07:29） ![教學課程徽章](/help/main/assets/tutorial.png)

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)
