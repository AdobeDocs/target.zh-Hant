---
keywords: 體驗目標；xt；活動url;url
description: 瞭解如何指定活動URL，該URL確定在test中使用的頁面，並在使用Adobe Target設計「體驗目標」活動時開啟該頁面。
title: 體驗目標(XT)活動中的活動URL是什麼？
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 63%

---

# 體驗目標(XT)活動中的活動URL

的 [!UICONTROL 活動URL] 確定在 [!DNL Adobe Target] [!UICONTROL 體驗目標] (XT)活動，在 [!UICONTROL 視覺體驗作曲家] (VEC)或 [!UICONTROL 基於表單的體驗作曲家] 在設計活動時。

1. 在[建立 XT 活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)期間出現提示時，請指定活動 URL。輸入完整的 URL (包括 `https://`)，然後按一下&#x200B;**[!UICONTROL 「建立活動」]**。

   >[!NOTE]
   >
   >[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 都相符。
   >
   >預設情況下，VEC或基於表單的體驗作曲家將開啟在 [Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)。 您可以在活動建立期間指定不同的頁面。
   >
   >如果您指定的網站 URL 不包括 Target Standard JavaScript 程式碼，則無法選取頁面元素。

1. (視條件而定) 若要在 VEC 開啟之後顯示不同的頁面，請按一下&#x200B;**[!UICONTROL 設定]**、選取&#x200B;**[!UICONTROL 頁面傳送]**，然後在 [!UICONTROL URL] 欄位中指定 URL。

   ![頁面傳送對話方塊](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。

1. (視條件而定) 按一下&#x200B;**[!UICONTROL 新增範本規則]**&#x200B;來新增更多頁面或區段至活動。

   其他規則可以根據以下任何項目:

   * URL
   * 網域
   * 路徑
   * 雜湊 (#) 片段
   * 查詢
   * mbox 參數

   可以使用「與」或「或」將其他規則加入活動 URL。您新增的所有規則會使用「與」彼此進行評估。

1. 完成後，按一下&#x200B;**[!UICONTROL 「儲存」]**。
