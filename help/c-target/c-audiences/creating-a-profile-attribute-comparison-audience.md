---
description: 定義對象來比較您的Target對象程式庫或僅限活動對象的兩個描述檔屬性。使用大於、小於或等於這類運算子來定義對象，以動態比較兩個不同設定檔屬性的值。
keywords: 對象;傾向;設定檔屬性;比較;比較;建立對象;建立對象
seo-description: 定義對象來比較您的Target對象程式庫或僅限活動對象的兩個描述檔屬性。使用大於、小於或等於這類運算子來定義對象，以動態比較兩個不同設定檔屬性的值。
seo-title: 建立設定檔屬性比較對象在Adobe Target中
solution: Target
title: 建立設定檔屬性比較對象
topic: Advanced,Standard,Classic
uuid: 17c1f2e0-4c1e-4b7a-8398-9ec147253a5f
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 建立設定檔屬性比較對象{#create-a-profile-attribute-comparison-audience}

Define an audience to compare two profile attributes for your [Audience library](/help/c-target/c-audiences/audiences.md) or in an [activity-only audience](/help/c-target/creating-activity-only-audience.md). 使用大於、小於或等於這類運算子來定義對象，以動態比較兩個不同設定檔屬性的值。

>[!NOTE]
>
>此功能僅適用於[訪客設定檔](../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)類別。

## 概述 {#section_303CBC78194D49A2A004945D425441E1}

對象是由可決定要從 Target 活動中包括或排除的規則定義。對象定義可以包括多個規則，並且每個規則可以包括多個參數。如果您加入的規則會使用到訪客設定檔類別，您可根據訪客設定檔屬性的特定值來定義規則，或將該屬性值與另一個訪客設定檔屬性比較。

舉例來說，假設您服務於一間家具公司，上傳了兩個客戶傾向分數至 Target:

* 在接下來 90 天內購買餐廳家具的可能性
* 在接下來 90 天內購買客廳家具的可能性

您可以建立一個對象，定義成購買餐廳家具的傾向大於購買客廳家具的傾向。Target 便會動態比較特定訪客在餐廳與客廳上的傾向分數，判斷該訪客是否符合此對象。

如需詳細資訊，請參閱[將資料傳入 Target 的方法](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)。

## 建立設定檔屬性比較對象 {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. 依序按下 **[!UICONTROL 「對象]** &gt; **[!UICONTROL 建立對象]** &gt; **[!UICONTROL 新增規則]** &gt; **[!UICONTROL 訪客設定檔」]**。
1. 從 **[!UICONTROL 「訪客設定檔」]下拉式清單選取屬性:**

   ![傾向分數1](assets/propensity_score_1.png)

1. 選取求值器:

   ![傾向分數2](assets/propensity_score_2.png)

1. 從 **[!UICONTROL 「選取比較類型」]** 下拉式清單中選擇 **[!UICONTROL 「屬性」]**。

   「靜態值」比較類型可讓您將訪客設定檔屬性與特定值比較。

   ![傾向分數3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >如果您在步驟 1 使用其中一個預設的訪客設定檔類別 (例如「新訪客」或「回頭客」)，您只能選擇靜態值選項。預設類別無法使用動態比較選項。其他無法使用動態比較選項的範例包括「工作階段首頁」、「不在其他測試中」、「非工作階段首頁」和「類別相關性」。

1. 選取您要與初始屬性比較的額外屬性。

   ![](assets/propensity_score_4.png)

## 訓練影片 {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

觀看下列影片以獲得詳細資訊，並瞭解您可使用此功能的情況:

>[!VIDEO](https://video.tv.adobe.com/v/23218/?captions=chi_hant)