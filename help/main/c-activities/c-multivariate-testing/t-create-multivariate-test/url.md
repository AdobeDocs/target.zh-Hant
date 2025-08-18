---
keywords: 多變數測試；活動URL
description: 瞭解如何指定活動URL，以決定測試中使用以及使用[!UICONTROL Multivariate Test]設計 [!DNL Adobe Target]活動時開啟的頁面。
title: '[!UICONTROL Multivariate Test] (MVT)活動中的活動URL為何？'
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 31%

---

# 活動 URL

活動URL會決定[!UICONTROL Multivariate Test] (MVT)中使用以及[!DNL Adobe Target]中設計測試時開啟的頁面。

1. 在[建立活動](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)期間出現提示時，請指定活動 URL。輸入完整的URL （包括`https://`），然後按一下&#x200B;**[!UICONTROL Create]**。

   >[!NOTE]
   >
   >[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `https://www.adobe.com`]和[!DNL `http://www.adobe.com`]都相符。

   根據預設，[!UICONTROL Visual Experience Composer] (VEC)會開啟[視覺化體驗撰寫器設定](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的頁面。 您可以在活動建立期間指定不同的頁面。

1. （視條件而定）若要在VEC開啟之後顯示不同的頁面，請按一下&#x200B;**[!UICONTROL Configure]**&#x200B;圖示，然後選取&#x200B;**[!UICONTROL Page Delivery]**，再指定URL。

1. （視條件而定）按一下&#x200B;**[!UICONTROL Add Rule]**&#x200B;以新增更多頁面或區段至活動。

   其他規則可以根據以下任何項目:

   * [!UICONTROL  URL]
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment]
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

   其他規則可以用AND或OR聯結到活動URL。 您新增的所有規則都會使用AND相互評估。

   完成時，請按一下&#x200B;**[!UICONTROL Save]**。

>[!NOTE]
>
>如果您輸入的網站URL不包括[!DNL Target] JavaScript程式碼，則無法選取頁面元素。
>
>根據預設，VEC 不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。如果您想要能夠使用&#x200B;**[!UICONTROL Render using JavaScript]**&#x200B;變更這些元素，可以將[!UICONTROL Visual Experience Composer]切換為關閉。

>[!NOTE]
>
>如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。
