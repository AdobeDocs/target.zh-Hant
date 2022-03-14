---
keywords: 活動url;url；不同的url
description: 瞭解如何指定活動URL，該URL確定test中使用的頁面，以及使用Adobe Target設計test時開啟的頁面。
title: A/B活動中的活動URL是什麼？
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 73%

---

# 活動 URL

「活動URL」確定在test中使用的頁面，當test使用Adobe Target設計時，該頁面將開啟。

在建立活動期間出現提示時，請指定活動 URL。輸入完整的 URL (包括 `https://`)，然後按一下&#x200B;**[!UICONTROL 「建立」]**。

>[!NOTE]
>
>[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://www.adobe.com`] 都相符。

## 指定不同的 URL

預設情況下， [!UICONTROL 視覺體驗作曲家] 開啟在您的 [Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)
。 您可以在活動建立期間指定不同的頁面。

若要在[!UICONTROL 可視化體驗撰寫器]開啟之後顯示不同頁面，請按一下&#x200B;**[!UICONTROL 「設定」]**&#x200B;齒輪圖示，然後選取 **[!UICONTROL 「頁面傳送」]**。在「活動 URL」欄位中輸入 URL。

![頁面傳送對話方塊](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

按一下&#x200B;**[!UICONTROL 「新增範本規則」]**&#x200B;來新增更多頁面或區段至活動。

其他規則可以根據以下任何項目:

* URL
* 網域
* 路徑
* 雜湊 (#) 片段
* 查詢
* mbox 參數

可以使用「與」或「或」將其他規則加入活動 URL。您新增的所有規則會使用「與」彼此進行評估。

完成後，按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>如果您輸入的網站 URL 不包括 [!DNL Target] Standard JavaScript 程式碼，則無法選取頁面元素。

依預設，[!UICONTROL 可視化體驗撰寫器]不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。如果想要能夠使用&#x200B;**[!UICONTROL 可視化體驗撰寫器]**&#x200B;更改這些元素，您可以將[!UICONTROL 使用 JavaScript 呈現]切換為關閉。

>[!NOTE]
>
>如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。
