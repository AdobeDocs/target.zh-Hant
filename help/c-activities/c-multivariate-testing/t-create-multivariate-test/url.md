---
description: 「活動URL」會決定多變數測試(MVT)中使用的頁面，並在測試是在Target中設計時開啓。
keywords: 定位
seo-description: 「活動URL」會決定多變數測試(MVT)中使用的頁面，並在測試是在Adobe Target中設計時開啓。
seo-title: 活動 URL
solution: Target
title: 活動 URL
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 活動 URL{#activity-url}

The activity URL determines the page that is used in the [!UICONTROL Multivariate Test] (MVT), and that opens when the test is designed in [!DNL Adobe Target].

When prompted during [activity creation](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), specify the activity URL. Type the complete URL (including `https://`), then click **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 都相符。

By default, the [!UICONTROL Visual Experience Composer] (VEC) opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). 您可以在活動建立期間指定不同的頁面。

To display a different page after the VEC opens, click the **[!UICONTROL Configure]** icon, then select **[!UICONTROL Page Delivery]**, then specify the URL.

![頁面傳送對話方塊](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

按一下 **[!UICONTROL 「新增範本規則」]來新增更多頁面或區段至活動。**

其他規則可以根據以下任何項目:

* URL
* 網域
* 路徑
* 雜湊 (#) 片段
* 查詢
* 參數

可以使用「與」或「或」將其他規則加入活動 URL。您新增的所有規則會使用「與」彼此進行評估。

完成後，按一下 **[!UICONTROL 「儲存」]。**

>[!NOTE]
>
>如果您輸入的網站 URL 不包括 Target Standard JavaScript 程式碼，則無法選取頁面元素。

根據預設，CMS不允許變更包含JavaScript的元素(例如旋轉橫幅)。如果想要能夠使用 **[!UICONTROL 可視化體驗撰寫器]更改這些元素，您可以將**[!UICONTROL 使用 JavaScript 呈現]切換為關閉。

>[!NOTE]
>
>如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。