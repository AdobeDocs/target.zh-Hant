---
keywords: 範本測試; 範本; 類似頁面上有相同體驗; 範本測試
description: 瞭解如何使用Adobe [!DNL Target]視覺化體驗撰寫器(VEC)，在結構類似或包含相同範本元素的多個頁面上包含相同體驗。
title: 我可以在類似頁面上包含相同體驗嗎？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
TQID: 'https://experienceleague.adobe.com/zk7U6g7gk7XkpWsEFQbwuCm7xbpIb1lCaZefxjn-39g'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: ef98a6e0-f26c-4870-9bd4-e6b72e9cc699
    internal-label: Experiences and offers
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 17%
---
# 在類似頁面上包含相同體驗 {#similar-pages}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!UICONTROL 視覺化體驗撰寫器] (VEC)中使用頁面傳送規則，以便在具有類似結構的頁面上包含相同體驗。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的頁面範本為頁面提供結構。 當頁面包含類似的元素時，這些類似結構化的頁面元素中的變數可以在多個頁面或整個網域中進行測試。

若要正確運作，此功能必須用於具有類似結構的頁面，或包含在所有頁面上具有相同結構的範本元素的頁面。

>[!IMPORTANT]
>
>使用此功能變更不同頁面上的元素可能會造成非預期的結果。

例如，此功能可用於執行下列任一項作業：

* 透過重新排列或移除元素來測試全域導覽列
* 從使用特定頁面範本的所有產品頁面移除項目
* 新增橫幅至所有產品頁面
* 變更文章範本的版面

## 指定體驗的頁面 {#specify-pages}

出現體驗的頁面會以頁面傳送規則指定。 規則可包含特定頁面，或將變更套用至整個網站或網域。

1. 建立或編輯活動，如[活動](/help/main/c-activities/activities.md)中所述。

1. 在[!UICONTROL 視覺化體驗撰寫器] (VEC)中，按一下&#x200B;**[!UICONTROL 設定]**&#x200B;圖示（ ![設定圖示](/help/main/assets/icons/Setting.svg)），然後選取&#x200B;**[!UICONTROL 頁面傳送]**。

   ![活動](assets/vec_edit_1.png)

1. 按一下「**[!UICONTROL 新增規則]**」，然後指定要將體驗新增至的頁面的條件。

1. 指定頁面範圍： **[!UICONTROL URL]**、**[!UICONTROL 網域]**、**[!UICONTROL 路徑]**、**[!UICONTROL 雜湊(#)片段]** （URL中#符號之後的部分）、**[!UICONTROL 查詢]**&#x200B;或&#x200B;**[!UICONTROL 自訂]**。

   如需[!DNL Target]如何評估URL的詳細資訊，請參閱[鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。

   ![活動](assets/vec_edit_2.png)

1. 選擇一個運算子。 運算子可指定運算子之後的項目與頁面範圍的相關性。

1. 在頁面名稱中輸入可定義要新增體驗位置的字串，例如網域或包含的字串。

   例如，如果選取&#x200B;**[!UICONTROL 網域]**&#x200B;和&#x200B;**[!UICONTROL 是（區分大小寫）]**，請輸入要將體驗新增至所有頁面的網域。

   可包含多個專案。 多個專案使用OR邏輯，表示清單中的任何單一專案都會讓條件成立。

1. （選擇性）按一下&#x200B;**[!UICONTROL 新增規則]**&#x200B;並重複步驟3到6以輸入其他條件。

   以 AND 邏輯聯合多個規則。 [!DNL Target]會將體驗新增至符合指定條件的所有頁面。

>[!IMPORTANT]
>
>[!DNL Target]無法檢查頁面以確定它們能如預期般顯示，因此在將頁面公開之前，請務必使用此功能來測試受影響的頁面。

## 使用案例 {#use-cases}

範本規則可在網站上以不同方式使用，如下列使用案例所示。

### 在整個網域中呈現相同活動 {#entire-domain}

範本規則可以呈現整個網域中的相同活動，例如：

* 若要包含全域頁首或頁尾
* 加入全球橫幅（例如COVID-19公告）
* 包含全球免運費促銷活動

1. 建立或編輯活動，如[活動](/help/main/c-activities/activities.md)中所述。

1. 若要指定顯示體驗的網域，請在[!UICONTROL 視覺化體驗撰寫器]中按一下&#x200B;**[!UICONTROL 設定]**&#x200B;圖示（ ![設定圖示](/help/main/assets/icons/Setting.svg)），然後選取&#x200B;**[!UICONTROL 頁面傳送]**。

1. 按一下&#x200B;**[!UICONTROL 新增規則]** > **[!UICONTROL 網域]**。

1. 從&#x200B;**[!UICONTROL 選擇評估器]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 包含]**，然後指定網域。

   ![活動](assets/vec_edit_3.png)
