---
keywords: 範本測試; 範本; 類似頁面上有相同體驗; 範本測試
description: 瞭解如何使用Adobe [!DNL Target] 視覺化體驗撰寫器(VEC)，在結構類似或包含相同範本元素的多個頁面上包含相同體驗。
title: 我可以在類似頁面上包含相同體驗嗎？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
TQID: https://experienceleague.adobe.com/zk7U6g7gk7XkpWsEFQbwuCm7xbpIb1lCaZefxjn-39g
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 564
ht-degree: 23%

---

# 在類似頁面上包含相同體驗

在[!DNL Adobe Target]中使用頁面範本為您的頁面提供結構，或如果您的頁面包含類似的元素，則以類似的結構化頁面元素或整個網域來測試變數。

若要正確運作，此功能必須用於具有類似結構的頁面，或包含在所有頁面上具有相同結構的範本元素的頁面。

>[!IMPORTANT]
>
>使用此功能變更不同頁面上的元素可能會造成非預期的結果。

例如，您可能會使用此功能來執行下列其中一項:

* 透過重新排列或移除元素來測試全域導覽列
* 從使用特定頁面範本的所有產品頁面移除項目
* 新增橫幅至所有產品頁面
* 變更文章範本的版面

您可以指定包含變更元素的頁面，或將變更套用至您的網站或網域。

1. 建立或編輯活動，如[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)中所述。

1. 若要指定顯示體驗的頁面，請在[!UICONTROL 視覺化體驗撰寫器] (VEC)中按一下[!UICONTROL 設定]圖示（ ![設定圖示](/help/main/assets/icons/Setting.svg) ），然後選取&#x200B;**[!UICONTROL 頁面傳送]**。

1. 按一下&#x200B;**[!UICONTROL 新增規則]**，然後指定您要新增體驗的頁面的條件。

1. 指定頁面範圍。 頁面範圍可以是下列其中一項:

   * [!UICONTROL URL] （如需[!DNL Target]如何評估URL的詳細資訊，請參閱[鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。）
   * [!UICONTROL 網域]
   * [!UICONTROL 路徑]
   * [!UICONTROL 雜湊(#)片段] （目標為#符號之後的URL部分。）
   * [!UICONTROL 查詢]
   * [!UICONTROL 自訂]

1. 選擇一個運算子。

   運算子可指定運算子之後的項目與頁面範圍的相關性。 可用的運運算元包括：

   * [!UICONTROL 包含]
   * [!UICONTROL 不包含]
   * [!UICONTROL 是（區分大小寫）]
   * [!UICONTROL 不是]
   * [!UICONTROL 開頭為]
   * [!UICONTROL 結尾為]

1. 在頁面名稱中輸入可定義要新增體驗位置的字串，例如網域或包含的字串。

   例如，如果您選取&#x200B;**[!UICONTROL 網域]**&#x200B;和&#x200B;**[!UICONTROL 是（區分大小寫）]**，請輸入要將體驗新增至所有頁面的網域。

   您可以包括多個項目。

   >[!IMPORTANT]
   >
   >多個專案使用OR邏輯，表示清單中的任何單一專案都會讓條件成立。

1. 如有需要，請按一下[新增規則] **[!UICONTROL 並重複先前步驟中的程式來輸入其他條件。]**

   以 AND 邏輯聯合多個規則。 [!DNL Target]會將體驗新增至符合指定條件的所有頁面。

>[!IMPORTANT]
>
> [!DNL Target]無法檢查頁面以確定它們能如預期般顯示，因此在將頁面公開之前，請務必使用此功能來測試受影響的頁面。

## 使用案例

檢閱下列使用案例，瞭解在您的網站上使用範本規則的方式：

### 在整個網域中呈現相同活動

您不妨考慮針對下列使用案例，使用範本規則在整個網域中呈現相同的活動：

* 若要包含全域頁首或頁尾
* 加入全球橫幅（例如COVID-19公告）
* 包含全球免運費促銷活動

1. 建立或編輯活動，如[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)中所述。

1. 若要指定顯示體驗的網域，請在[!UICONTROL 視覺化體驗撰寫器]中按一下[!UICONTROL 設定]圖示（ ![設定圖示](/help/main/assets/icons/Setting.svg)），然後選取&#x200B;**[!UICONTROL 頁面傳送]**。

1. 按一下&#x200B;**[!UICONTROL 新增規則]** > **[!UICONTROL 網域]**。

1. 從&#x200B;**[!UICONTROL 選擇評估器]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 包含]**，然後指定網域。
