---
keywords: 多變數測試；活動URL
description: 瞭解如何指定活動URL，以決定測試中使用以及使用Adobe Target設計多變數測試活動時開啟的頁面。
title: 多變數(MVT)活動中的活動URL為何？
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 85%

---

# 活動 URL

活動 URL 會決定[!UICONTROL 多變數測試] (MVT) 中使用以及 [!DNL Adobe Target] 中設計測試時開啟的頁面。

在[建立活動](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)期間出現提示時，請指定活動 URL。輸入完整的 URL (包括 `https://`)，然後按一下&#x200B;**[!UICONTROL 下一步]**。

>[!NOTE]
>
>[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 都相符。

根據預設，[!UICONTROL 可視化體驗撰寫器] (VEC) 會開啟[可視化體驗撰寫器設定](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的頁面。您可以在活動建立期間指定不同的頁面。

若要在 VEC 開啟之後顯示不同的頁面，請按一下&#x200B;**[!UICONTROL 設定]**&#x200B;圖示，然後選取&#x200B;**[!UICONTROL 頁面傳送]**，再指定 URL。

![頁面傳送對話方塊](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

按一下&#x200B;**[!UICONTROL 「新增範本規則」]**&#x200B;來新增更多頁面或區段至活動。

其他規則可以根據以下任何項目:

* URL
* 網域
* 路徑
* 雜湊 (#) 片段
* 查詢
* 參數

可以使用「與」或「或」將其他規則加入活動 URL。您新增的所有規則會使用「與」彼此進行評估。

完成後，按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>如果您輸入的網站 URL 不包括 Target Standard JavaScript 程式碼，則無法選取頁面元素。

根據預設，VEC 不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。如果想要能夠使用&#x200B;**[!UICONTROL 可視化體驗撰寫器]**&#x200B;更改這些元素，您可以將[!UICONTROL 使用 JavaScript 呈現]切換為關閉。

>[!NOTE]
>
>如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。
