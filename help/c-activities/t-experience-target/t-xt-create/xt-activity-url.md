---
description: 「活動URL」會決定「體驗定位」活動中使用的頁面，並在設計活動時於Visual Experience Composer(CMS)或表單型體驗撰寫器中開啓。
keywords: 定位
seo-description: 「活動URL」會決定「體驗定位」活動中使用的頁面，並在設計活動時於Adobe Target Visual Experience Composer(CMS)或表單型體驗撰寫器中開啓。
seo-title: 活動 URL
solution: Target
title: 活動 URL
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 活動 URL{#activity-url}

「活動URL」會決定「體驗鎖定(Experience Targeting)」(XT)活動中使用的頁面，並在設計活動時於Visual Experience Composer(CMS)或表單型體驗撰寫器中開啓。

1. [在建立XT活動](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)時出現提示時，請指定活動URL。輸入完整的 URL (包括 `https://`)，然後按一下&#x200B;**[!UICONTROL 「建立活動」]**。

   >[!NOTE]
   >
   >[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 都相符。
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). 您可以在活動建立期間指定不同的頁面。
   >
   >如果您為不包含Target Standard JavaScript程式碼的網站指定URL，則無法選取頁面元素。

1. (Conditional) To display a different page after the VEC opens, click **[!UICONTROL Configure]**, select **[!UICONTROL Page Delivery]**, and specify the URL in the [!UICONTROL URL] field.

   ![頁面傳送對話方塊](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。

1. (Conditional) Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

   其他規則可以根據以下任何項目:

   * URL
   * 網域
   * 路徑
   * 雜湊 (#) 片段
   * 查詢
   * mbox 參數
   可以使用「與」或「或」將其他規則加入活動 URL。您新增的所有規則會使用「與」彼此進行評估。

1. 完成後，按一下&#x200B;**[!UICONTROL 「儲存」]。**