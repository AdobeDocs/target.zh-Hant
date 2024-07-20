---
keywords: 體驗鎖定目標； XT；活動URL； URL
description: 瞭解如何指定[!UICONTROL Activity URL]，以決定測試中使用以及使用 [!DNL Adobe Target]設計[!UICONTROL Experience Targeting]活動時開啟的頁面。
title: 什麼是[!UICONTROL Experience Targeting] (XT)活動中的[!UICONTROL Activity URL]？
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 24513d8cb39d38dcfbc74bf40961d5517cc90a4b
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 39%

---

# [!UICONTROL Experience Targeting] (XT)活動中的活動URL

[!UICONTROL Activity URL]決定[!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT)活動中使用的頁面。 這是設計活動時在[!UICONTROL Visual Experience Composer] (VEC)或[!UICONTROL Form-Based Experience Composer]中開啟的頁面。

1. 在[建立 XT 活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)期間出現提示時，請指定活動 URL。輸入完整的URL （包括`https://`），然後按一下&#x200B;**[!UICONTROL Create Activity]**。

   >[!NOTE]
   >
   >[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `https://www.adobe.com`]和[!DNL `http://www.adobe.com`]都相符。
   >
   >依預設，VEC或[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)會開啟[視覺化體驗撰寫器設定](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的頁面。 您可以在活動建立期間指定不同的頁面。
   >
   >如果您指定的網站URL不包括[[!DNL Target] at.js JavaScript資料庫或 [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}，則無法選取頁面元素。

1. （視條件而定）若要在VEC開啟之後顯示不同的頁面，請按一下&#x200B;**[!UICONTROL Configure]**，選取&#x200B;**[!UICONTROL Page Delivery]**，然後在[!UICONTROL URL]欄位中指定URL。

   ![頁面傳送對話方塊](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。

1. （視條件而定）按一下&#x200B;**[!UICONTROL Add Template Rule]**&#x200B;以新增更多頁面或區段至活動。

   其他規則可以根據以下任何項目:

   * URL
   * 網域
   * 路徑
   * 雜湊 (#) 片段
   * 查詢
   * mbox 參數

   可以使用「與」或「或」將其他規則加入活動 URL。您新增的所有規則會使用「與」彼此進行評估。

1. 完成時，請按一下&#x200B;**[!UICONTROL Save]**。
