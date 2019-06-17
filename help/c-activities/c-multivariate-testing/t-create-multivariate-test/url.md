---
description: 「活動URL」會決定多變數測試(MVT)中使用的頁面，並在測試是在Target中設計時開啓。
keywords: 定位
seo-description: 「活動URL」會決定多變數測試(MVT)中使用的頁面，並在測試是在Adobe Target中設計時開啓。
seo-title: 活動 URL
solution: Target
title: 活動 URL
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 0730d5f8f6aa2b72c2069c81d6e5a0183489e91c

---


# 活動 URL{#activity-url}

活動URL會決定 [!M用於極端測試(] MVT)中的頁面，並在測試所設計 [!DNL Adobe Target]時開啓。

在 [活動建立](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)期間出現提示時，請指定活動URL。輸入完整的URL(包括 `https://`)，然後按「下一步 **[!UICONTROL 」]**。

>[!NOTE]
>
>[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 都相符。

根據預設， [!UICONTROL Visual Experience Composer] (CMS)會開啓 [您的帳戶偏好設定中指定的頁面](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)。您可以在活動建立期間指定不同的頁面。

若要在CMS開啓後顯示不同的頁面，請按一下 **[!UICONTROL 「設定]** 」圖示，然後選取 **[!UICONTROL 「頁面傳送]**」，然後指定URL。

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