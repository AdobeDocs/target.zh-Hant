---
keywords: 範本測試; 範本; 類似頁面上有相同體驗; 範本測試
description: 瞭解如何使用Adobe [!DNL Target] Visual Experience Composer(VEC)，用於在結構相似或包含相同模板元素的多個頁面上包含相同的體驗。
title: 我是否可以在類似頁面上包含相同的體驗？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 46%

---

# 在類似頁面上包含相同體驗

在中使用頁面模板 [!DNL Adobe Target] 為頁面提供結構，或如果頁面包含類似元素，則test類似結構化頁面元素或整個域中的變體。

要正確工作，此功能必須用於結構相似或包含結構相同的模板元素的頁面上。

>[!IMPORTANT]
>
>使用此功能來變更不同頁面上的元素將可能造成未預期的結果。

例如，您可能會使用此功能來執行下列其中一項:

* 透過重新排列或移除元素來測試全域導覽列
* 從使用特定頁面範本的所有產品頁面移除項目
* 新增橫幅至所有產品頁面
* 變更文章範本的配置

您可以指定包含變更元素的頁面，或在您的站點或域中應用變更。

1. 建立或編輯活動，如中所述 [活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。

1. 要指定將出現體驗的頁面，請在 [!UICONTROL 視覺體驗作曲家] (VEC)按一下齒輪表徵圖，然後選擇 **[!UICONTROL 頁面傳遞]**。

   ![「齒輪」表徵圖>「頁交貨」](/help/main/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. 按一下&#x200B;**[!UICONTROL 新增範本規則]**，然後指定您要新增體驗的頁面的條件。

1. 指定頁面範圍。頁面範圍可以是下列其中一項:

   * URL (有關目標如何計算URL的詳細資訊，請參見 [目標和受眾常見問題](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。)
   * 網域
   * 路徑
   * 雜湊 (#) 片段 （以#符號後面的URL部分為目標。）
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
   >多個項使用OR邏輯，這意味著清單中的任何單個項都使條件為true。

1. 如果需要，請按一下 **[!UICONTROL 添加模板規則]** 並重複上述步驟。

   以 AND 邏輯聯合多個規則。[!DNL Target] 會將體驗新增至符合指定條件的所有頁面。

>[!IMPORTANT]
>
> [!DNL Target] 無法檢查頁面以確定它們能如預期般出現，因此，在將頁面公開之前，請務必使用此功能來測試受影響的頁面。

## 使用個案

查看以下使用案例，瞭解在站點上使用模板規則的方法：

### 在整個域中呈現相同的活動

您可能考慮使用模板規則在整個域中呈現同一活動，用於以下使用情形：

* 包含全局頁眉或頁腳
* 要包括全球橫幅（例如，COVID-19聲明）
* 包括全球免費運輸促銷

1. 建立或編輯活動，如中所述 [活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。

1. 要指定體驗將出現的域，請在「視覺體驗作曲家」中按一下齒輪表徵圖，然後選擇 **[!UICONTROL 頁面傳遞]**。

1. 按一下 **[!UICONTROL 添加模板規則]** > **[!UICONTROL 域]**。

1. 從 **[!UICONTROL 選擇計算器]** 下拉，選擇 **[!UICONTROL 包含]**，然後指定域。

   ![域包含](/help/main/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## 培訓視頻：Visual Experience作曲家（共2個）(7:29) ![教程徽章](/help/main/assets/tutorial.png)

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)
