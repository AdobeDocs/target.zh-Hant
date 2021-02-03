---
keywords: 範本測試; 範本; 類似頁面上有相同體驗; 範本測試
description: 使用Adobe Target中的頁面範本為您的頁面提供結構，或是您的頁面包含類似元素時，測試類似結構頁面元素的變化。
title: 在類似頁面上包含相同體驗
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 47%

---


# 在類似頁面上包含相同體驗

使用[!DNL Adobe Target]中的頁面範本為頁面提供結構，或若您的頁面包含類似元素，則可測試類似結構化頁面元素或整個網域的變化。

若要正常運作，此功能必須用於結構類似或包含結構相同之範本元素的頁面上。

>[!IMPORTANT]
>
>使用此功能來變更不同頁面上的元素將可能造成未預期的結果。

例如，您可能會使用此功能來執行下列其中一項:

* 透過重新排列或移除元素來測試全域導覽列
* 從使用特定頁面範本的所有產品頁面移除項目
* 新增橫幅至所有產品頁面
* 變更文章範本的配置

您可以指定包含變更元素的頁面，或跨網站或網域套用變更。

1. 按[Activity](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)中所述建立或編輯活動。

1. 若要指定體驗將出現的頁面，請在[!UICONTROL Visual Experience Composer](VEC)中按一下齒輪圖示，然後選取&#x200B;**[!UICONTROL 頁面傳送]**。

   ![齒輪圖示>頁面傳送](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. 按一下&#x200B;**[!UICONTROL 新增範本規則]**，然後指定您要新增體驗的頁面的條件。

1. 指定頁面範圍。頁面範圍可以是下列其中一項:

   * URL （如需Target如何評估URL的詳細資訊，請參閱[目標與觀眾常見問答集](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。）
   * 網域
   * 路徑
   * 雜湊 (#) 片段 （定位#符號後面URL的部分）。
   * 查詢
   * 參數

1. 選擇一個運算子。

   運算子可指定運算子之後的項目與頁面範圍的相關性。可用運算子包括：

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
   >多個項目使用OR邏輯，這表示清單中的任何單一項目都會使條件成真。

1. 如果需要，請通過按一下&#x200B;**[!UICONTROL 添加模板規則]**&#x200B;並重複上述步驟來輸入附加標準。

   以 AND 邏輯聯合多個規則。[!DNL Target] 會將體驗新增至符合指定條件的所有頁面。

>[!IMPORTANT]
>
> [!DNL Target] 無法檢查頁面以確定它們能如預期般出現，因此，在將頁面公開之前，請務必使用此功能來測試受影響的頁面。

## 使用個案

請檢閱下列使用案例，以瞭解在您的網站上使用範本規則的方式：

### 在整個網域中呈現相同的活動

您可能會考慮針對下列使用案例，使用範本規則在整個網域中呈現相同的活動：

* 要包含全局頁眉或頁腳
* 若要包含全域橫幅（例如，COVID-19公告）
* 若要納入全球免運費促銷

1. 按[Activity](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)中所述建立或編輯活動。

1. 若要指定體驗將出現的網域，請在Visual Experience Composer中按一下齒輪圖示，然後選取&#x200B;**[!UICONTROL 頁面傳送]**。

1. 按一下「**[!UICONTROL 添加模板規則]** > **[!UICONTROL 域]**」。

1. 從&#x200B;**[!UICONTROL 選擇求值器]**&#x200B;下拉式清單中，選擇&#x200B;**[!UICONTROL 包含]**，然後指定網域。

   ![網域包含](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## 訓練影片：Visual Experience Composer（2個，共2個）(7:29)![教學課程徽章](/help/assets/tutorial.png)

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)