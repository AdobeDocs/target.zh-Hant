---
keywords: global mbox;target classic;use global mbox from target classic
description: 依預設，Target Standard 會建立名為 target-global-mbox 的全域 mbox，用來執行 Target Standard 中建立的活動。不過，若您已為您的舊版實作在頁面上建立全域 mbox，則可將該 mbox 用於您的 Target Standard 活動。
title: 使用來自舊版實作的全域 mbox
subtopic: Getting Started
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 91%

---


# 使用來自舊版實作的全域 mbox{#use-a-global-mbox-from-a-legacy-implementation}

依預設，Target Standard 會建立名為 target-global-mbox 的全域 mbox，用來執行 Target Standard 中建立的活動。不過，若您已為您的舊版實作在頁面上建立全域 mbox，則可將該 mbox 用於您的 Target Standard 活動。

>[!NOTE]
>
>每個帳戶只能有一個全域 mbox。

若想同時在 [!DNL Target Standard] 和您的舊版實施中使用現有的全域 mbox，您必須設定幾個參數。

1. Go to [!DNL Target Standard], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   預設會啟用「[!UICONTROL 自動建立全域 Mbox]」，而自訂全域 mbox 命名為 `target-global-mbox`。
1. 如果您想使用現有的 mbox，請停用「[!UICONTROL 自動建立全域 Mbox]」，並在「[!UICONTROL 自訂全域 Mbox]」欄位中指定先前建立之全域 mbox 的名稱。

   [!UICONTROL 「自訂全域 Mbox」]下拉式清單會列出您帳戶中的所有 mbox。如果您想使用尚未存在的 mbox，請在 Target Classic中建立 mbox。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   接著會更新您帳戶的 mbox.js 設定。
1. 下載新的 mbox.js 檔案並在您的網站上參考該檔案。

   使用新 mbox.js 檔案更新您的生產網站後，即可設定您的偏好設定。
1. 按一 **[!UICONTROL 下「管理]** > **[!UICONTROL 視覺體驗撰寫器]**」。
1. In the [!UICONTROL Global Mbox] field, specify the name of the global mbox you selected on the Implementation page.
1. 按一下&#x200B;**[!UICONTROL 「提交」]**。

   所有現有活動都會更新為使用指定的全域 mbox，包括先前已建立和實施的活動。
   **疑難排解全域 Mbox 實施***全域 mbox 為什麼不會載入，或為什麼頁面載入時載入全域 mbox 發生延遲?*

確定 mbox.js 參考是頁面上的第一個 JavaScript 呼叫。針對此問題的其他解決方案，請參閱 [mbox.js 實作](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420)。
