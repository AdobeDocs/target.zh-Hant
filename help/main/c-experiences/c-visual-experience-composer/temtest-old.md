---
keywords: 範本測試; 範本; 類似頁面上有相同體驗; 範本測試
description: 瞭解如何使用Adobe [!DNL Target] 視覺化體驗撰寫器(VEC)，在結構類似或包含相同範本元素的多個頁面上包含相同體驗。
title: 我可以在類似頁面上包含相同體驗嗎？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 33%

---

# 在類似頁面上包含相同體驗

在[!DNL Adobe Target]中使用頁面範本為您的頁面提供結構，或如果您的頁面包含類似的元素，則以類似的結構化頁面元素或整個網域來測試變數。

若要正確運作，此功能必須用於具有類似結構的頁面，或包含在所有頁面上具有相同結構的範本元素的頁面。

>[!IMPORTANT]
>
>使用此功能來變更不同頁面上的元素將可能造成未預期的結果。

例如，您可能會使用此功能來執行下列其中一項:

* 透過重新排列或移除元素來測試全域導覽列
* 從使用特定頁面範本的所有產品頁面移除項目
* 新增橫幅至所有產品頁面
* 變更文章範本的配置

您可以指定包含變更元素的頁面，或將變更套用至您的網站或網域。

1. 建立或編輯活動，如[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)中所述。

1. 若要指定顯示體驗的頁面，請在[!UICONTROL Visual Experience Composer] (VEC)中按一下齒輪圖示，然後選取&#x200B;**[!UICONTROL Page Delivery]**。

   ![齒輪圖示>頁面傳送](/help/main/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. 按一下「**[!UICONTROL Add Template Rule]**」，然後指定您要新增體驗的頁面的條件。

1. 指定頁面範圍。頁面範圍可以是下列其中一項:

   * URL （如需Target如何評估URL的詳細資訊，請參閱[鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。）
   * 網域
   * 路徑
   * 雜湊(#)片段（目標為URL中#符號之後的部分。）
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

   例如，如果您選取&#x200B;**[!UICONTROL Domain]**&#x200B;和&#x200B;**[!UICONTROL Is (case sensitive)]**，請輸入要將體驗新增至所有頁面的網域。

   您可以包括多個項目。

   >[!IMPORTANT]
   >
   >多個專案使用OR邏輯，表示清單中的任何單一專案都會讓條件成立。

1. 如有需要，請按一下&#x200B;**[!UICONTROL Add Template Rule]**&#x200B;並重複先前步驟中的程式來輸入其他條件。

   以 AND 邏輯聯合多個規則。[!DNL Target]會將體驗新增至符合指定條件的所有頁面。

>[!IMPORTANT]
>
> [!DNL Target]無法檢查頁面以確定它們能如預期般顯示，因此在將頁面公開之前，請務必使用此功能來測試受影響的頁面。

## 使用案例

檢閱下列使用案例，瞭解在您的網站上使用範本規則的方式：

### 在整個網域中呈現相同的活動

您不妨考慮針對下列使用案例，使用範本規則在整個網域中呈現相同的活動：

* 若要包含全域頁首或頁尾
* 加入全球橫幅（例如COVID-19公告）
* 包含全球免運費促銷活動

1. 建立或編輯活動，如[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)中所述。

1. 若要指定顯示體驗的網域，請在視覺化體驗撰寫器中按一下齒輪圖示，然後選取「**[!UICONTROL Page Delivery]**」。

1. 按一下&#x200B;**[!UICONTROL Add Template Rule]** > **[!UICONTROL Domain]**。

1. 從&#x200B;**[!UICONTROL Choose evaluator]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Contains]**，然後指定網域。

   ![網域包含](/help/main/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## 訓練影片：視覺化體驗撰寫器(2/2) (7:29) ![教學課程徽章](/help/main/assets/tutorial.png)

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)
