---
keywords: 對象;傾向;設定檔屬性;比較;比較;建立對象;建立對象
description: 瞭解如何定義受眾以比較兩個設定檔屬性。
title: 我可以比較兩個設定檔屬性以用於對象嗎？
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: 1383088bb2f6be0432e6f140400d8723048c8530
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 59%

---

# 建立設定檔屬性比較對象

在中定義對象 [!DNL Adobe Target] 若要比較您的兩個設定檔屬性 [對象庫](/help/main/c-target/c-audiences/audiences.md) 或在 [僅限於此活動的對象](/help/main/c-target/creating-activity-only-audience.md). 使用大於、小於或等於這類運算子來定義對象，以動態比較兩個不同設定檔屬性的值。

>[!NOTE]
>
>此功能僅適用於[[!UICONTROL 訪客設定檔]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)類別。

## 總覽 {#section_303CBC78194D49A2A004945D425441E1}

對象是由可決定要從 [!DNL Target] 活動中包括或排除的規則定義。對象定義可以包括多個規則，並且每個規則可以包括多個參數。如果您包含的其中一個規則使用 [!UICONTROL 訪客設定檔] 類別時，您可以根據訪客設定檔屬性的特定值來定義規則，或比較該屬性的值與另一個訪客設定檔屬性。

例如，假設您在一家傢俱公司工作，並將兩個客戶傾向分數上傳至 [!DNL Target]：

* 在接下來 90 天內購買餐廳家具的可能性
* 在接下來 90 天內購買客廳家具的可能性

您可以建立一個對象，定義成購買餐廳家具的傾向大於購買客廳家具的傾向。[!DNL Target] 便會動態比較特定訪客在餐廳與客廳上的傾向分數，判斷該訪客是否符合此對象。

如需詳細資訊，請參閱 [將資料傳入Target的方法](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}.

## 建立設定檔屬性比較對象 {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. 按一下 **[!UICONTROL 受眾]** > **[!UICONTROL 建立對象]**.
1. 為對象命名並新增選擇性說明。
1. 拖放 **[!UICONTROL 訪客設定檔]** 放入對象產生器窗格。
1. 從&#x200B;**[!UICONTROL 「訪客設定檔」]**&#x200B;下拉式清單選取屬性:

   ![傾向分數 1](assets/propensity_score_1.png)

1. 選取求值器:

   ![傾向分數 2](assets/propensity_score_2.png)

1. 從&#x200B;**[!UICONTROL 「選取比較類型」]**&#x200B;下拉式清單中選擇&#x200B;**[!UICONTROL 「屬性」]**。

   「靜態值」比較型別可讓您將訪客設定檔屬性與特定值比較。

   ![傾向分數 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >如果您使用其中一個預設的訪客設定檔類別（例如「新訪客」或「回頭客」），您只能選擇靜態值選項。 預設類別無法使用動態比較選項。其他無法使用動態比較選項的範例包括「工作階段首頁」、「不在其他測試中」、「非工作階段首頁」和「類別相關性」。

1. 選取您要與初始屬性比較的額外屬性。

   ![propensity_score_4圖片](assets/propensity_score_4.png)

1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

## 訓練影片 ![Overview badge](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

觀看下列影片以獲得詳細資訊，並瞭解您可使用此功能的情況:

>[!VIDEO](https://video.tv.adobe.com/v/23218/)
