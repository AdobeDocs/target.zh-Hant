---
keywords: 對象;傾向;設定檔屬性;比較;比較;建立對象;建立對象
description: 瞭解如何定義訪問群體以比較兩個配置檔案屬性。
title: 是否可以比較兩個配置檔案屬性以供觀眾使用？
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 62%

---

# 建立設定檔屬性比較對象

在 [!DNL Adobe Target] 比較您的 [受眾庫](/help/main/c-target/c-audiences/audiences.md) 或 [僅活動受眾](/help/main/c-target/creating-activity-only-audience.md)。 使用大於、小於或等於這類運算子來定義對象，以動態比較兩個不同設定檔屬性的值。

>[!NOTE]
>
>此功能僅適用於[[!UICONTROL 訪客設定檔]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)類別。

## 總覽 {#section_303CBC78194D49A2A004945D425441E1}

對象是由可決定要從 [!DNL Target] 活動中包括或排除的規則定義。對象定義可以包括多個規則，並且每個規則可以包括多個參數。如果您包括的規則之一使用 [!UICONTROL 訪問者簡介] 類別中，您可以根據訪問者配置檔案屬性的特定值定義規則，或將該屬性的值與其他訪問者配置檔案屬性進行比較。

舉例來說，假設您服務於一間家具公司，上傳了兩個客戶傾向分數至 [!DNL Target]:

* 在接下來 90 天內購買餐廳家具的可能性
* 在接下來 90 天內購買客廳家具的可能性

您可以建立一個對象，定義成購買餐廳家具的傾向大於購買客廳家具的傾向。[!DNL Target] 便會動態比較特定訪客在餐廳與客廳上的傾向分數，判斷該訪客是否符合此對象。

有關詳細資訊，請參見 [將資料獲取到目標的方法](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}。

## 建立設定檔屬性比較對象 {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. 按一下 **[!UICONTROL 觀眾]** > **[!UICONTROL 建立受眾]**。
1. 命名訪問群體並添加可選說明。
1. 拖放 **[!UICONTROL 訪問者簡介]** 對話框。
1. 從&#x200B;**[!UICONTROL 「訪客設定檔」]**&#x200B;下拉式清單選取屬性:

   ![傾向分數 1](assets/propensity_score_1.png)

1. 選取求值器:

   ![傾向分數 2](assets/propensity_score_2.png)

1. 從&#x200B;**[!UICONTROL 「選取比較類型」]**&#x200B;下拉式清單中選擇&#x200B;**[!UICONTROL 「屬性」]**。

   「靜態值」比較類型允許您將訪問者配置檔案屬性與特定值進行比較。

   ![傾向分數 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >如果使用預設訪問者配置檔案類別（例如，新訪問者或返回訪問者），則只能選擇靜態值選項。 預設類別無法使用動態比較選項。其他無法使用動態比較選項的範例包括「工作階段首頁」、「不在其他測試中」、「非工作階段首頁」和「類別相關性」。

1. 選取您要與初始屬性比較的額外屬性。

   ![](assets/propensity_score_4.png)

1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

## 培訓視頻 ![概述徽章](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

觀看下列影片以獲得詳細資訊，並瞭解您可使用此功能的情況:

>[!VIDEO](https://video.tv.adobe.com/v/23218/)
