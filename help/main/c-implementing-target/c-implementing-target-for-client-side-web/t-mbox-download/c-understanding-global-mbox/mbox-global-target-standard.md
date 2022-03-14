---
keywords: 全域 mbox;target classic;使用來自 target classic 的全域 mbox
description: 瞭解如何將舊式全局框用於您的Adobe [!DNL Target] 活動。
title: 是否可以使用舊式實施中的全局框？
feature: at.js
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 36%

---

# 使用舊式實施中的「全局」框

預設情況下， [!DNL Target] 建立名為target-global-mbox的全局框，用於運行在 [!DNL Target]。 不過，若您已為您的舊版實作在頁面上建立全域 mbox，則可將該 mbox 用於您的 [!DNL Target] 活動。

>[!NOTE]
>
>每個帳戶只能有一個全域 mbox。

若想同時在 [!DNL Target] 和您的舊版實施中使用現有的全域 mbox，您必須設定幾個參數。

1. 轉到 [!DNL Target]，然後按一下 **[!UICONTROL 管理]** > **[!UICONTROL 實施]**。

   預設情況下， **[!UICONTROL 已啟用頁面載入（自動建立全局框）]** 啟用，並命名自定義全局框 `target-global-mbox`。

1. 如果要使用現有框，請禁用 **[!UICONTROL 已啟用頁面載入（自動建立全局框）]**，並在 **[!UICONTROL 全局框]** 的子菜單。

   的 [!UICONTROL 全局框] 下拉清單列出了帳戶中的所有複選框。 如果要使用尚不存在的框，請建立該框。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   接著會更新您帳戶的 設定。

1. 下載新的at.js檔案並在您的站點上引用它。

   所有現有活動都會更新為使用指定的全域 mbox，包括先前已建立和實施的活動。

## 全局框實施故障排除

以下常見問題可用於解決您的全局框實施問題：

### 全域 mbox 為什麼不會載入，或為什麼頁面載入時載入全域 mbox 發生延遲?

確保at.js引用是該頁上的第一個JavaScript調用。 有關此問題的其他解決方案，請參見 [Global Mbox常見問題](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)。
