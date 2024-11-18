---
keywords: 活動url；url；不同的url
description: 探索如何設定[!UICONTROL Activity URL]以定義測試頁面，並確保測試設計準確。
title: A/B活動中的活動URL為何？
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
source-git-commit: d5bd3b0d7cdf6eb06175a6365da6b8173f76800f
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 40%

---

# 活動 URL

活動URL會決定測試中使用以及使用[!DNL Adobe Target]設計測試時開啟的頁面。

在建立活動期間出現提示時，請指定活動 URL。輸入完整的URL （包括`https://`），然後按一下&#x200B;**[!UICONTROL Create]**。

>[!NOTE]
>
>[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `http://www.adobe.com`]和[!DNL `https://www.adobe.com`]都相符。

## 指定不同的 URL

根據預設，[!UICONTROL Visual Experience Composer]會開啟[視覺化體驗撰寫器設定](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的頁面。 您可以在活動建立期間指定不同的頁面。

1. （視條件而定）若要在[!UICONTROL Visual Experience Composer]開啟之後顯示不同的頁面，請在&#x200B;**[!UICONTROL Experiences]**&#x200B;頁面上按一下頁面頂端的&#x200B;**[!UICONTROL Configure]**，然後選取&#x200B;**[!UICONTROL Page Delivery]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;欄位中指定URL。

1. （視條件而定）按一下&#x200B;**[!UICONTROL Add Rule]**&#x200B;以新增更多頁面或區段至活動。

   其他規則可以根據以下任何項目:

   * URL
   * 網域
   * 路徑
   * 雜湊 (#) 片段
   * 查詢
   * mbox 參數
   * 自訂

   其他規則可以用AND或OR聯結到活動URL。 您新增的所有規則會使用「與」彼此進行評估。

1. 完成時，請按一下&#x200B;**[!UICONTROL Save]**。

<!-- If you entered a URL for a site that does not include the [!DNL Target]s JavaScript code, you cannot select page elements.

By default, the [!UICONTROL Visual Experience Composer] does not allow changes to elements containing JavaScript, such as rotating banners. You can toggle off **[!UICONTROL Render using JavaScript]** if you want to be able to alter those elements using the [!UICONTROL Visual Experience Composer].-->

>[!NOTE]
>
>如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。
