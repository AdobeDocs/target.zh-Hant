---
keywords: global mbox;target classic;use global mbox from target classic
description: 依預設，Target Standard 會建立名為 target-global-mbox 的全域 mbox，用來執行 Target Standard 中建立的活動。不過，若您已為您的舊版實作在頁面上建立全域 mbox，則可將該 mbox 用於您的 Target Standard 活動。
title: 使用來自舊版實作的全域 mbox
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---


# 使用來自舊版實作的全域 mbox{#use-a-global-mbox-from-a-legacy-implementation}

By default, [!DNL Target] creates a global mbox called target-global-mbox, which is used to run activities created in [!DNL Target]. 不過，若您已為您的舊版實作在頁面上建立全域 mbox，則可將該 mbox 用於您的 [!DNL Target] 活動。

>[!NOTE]
>
>每個帳戶只能有一個全域 mbox。

若想同時在 [!DNL Target] 和您的舊版實施中使用現有的全域 mbox，您必須設定幾個參數。

1. Go to [!DNL Target], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   By default, **[!UICONTROL Page load enabled (Auto-create global mbox]** is enabled, and the custom global mbox is named `target-global-mbox`.

1. If you want to use an existing mbox, disable **[!UICONTROL Page load enabled (Auto-create global mbox]**, and specify the name of a previously created global mbox in the **[!UICONTROL Global Mbox]** field.

   The [!UICONTROL Global Mbox] drop-down lists all mboxes in your account. 如果您想要使用尚不存在的mbox，請建立mbox。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   接著會更新您帳戶的 mbox.js 設定。

1. 下載新的at.js檔案並在您的網站上參考它。

   所有現有活動都會更新為使用指定的全域 mbox，包括先前已建立和實施的活動。

## 疑難排解全域mbox實作

下列常見問答集可用來疑難排解全域mbox實作：

### 全域 mbox 為什麼不會載入，或為什麼頁面載入時載入全域 mbox 發生延遲?

請確定at.js參考是頁面上的第一個JavaScript呼叫。 如需此問題的其他解決方案，請參 [閱全域mbox常見問題](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)。
