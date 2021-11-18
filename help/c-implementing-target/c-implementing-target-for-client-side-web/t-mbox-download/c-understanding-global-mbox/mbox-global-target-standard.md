---
keywords: 全域 mbox;target classic;使用來自 target classic 的全域 mbox
description: 了解如何為Adobe使用舊版全域mbox [!DNL Target] 活動（若您已在您的頁面上為舊版實施建立全域mbox）。
title: 我可以使用舊版實作的全域mbox嗎？
feature: at.js
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 36%

---

# 使用來自舊版實作的全域mbox

依預設， [!DNL Target] 會建立名為target-global-mbox的全域mbox，用於執行中建立的活動 [!DNL Target]. 不過，若您已為您的舊版實作在頁面上建立全域 mbox，則可將該 mbox 用於您的 [!DNL Target] 活動。

>[!NOTE]
>
>每個帳戶只能有一個全域 mbox。

若想同時在 [!DNL Target] 和您的舊版實施中使用現有的全域 mbox，您必須設定幾個參數。

1. 前往 [!DNL Target]，然後按一下 **[!UICONTROL 管理]** > **[!UICONTROL 實作]**.

   依預設， **[!UICONTROL 啟用頁面載入（自動建立全域mbox）]** 已啟用，且自訂全域mbox的名稱為 `target-global-mbox`.

1. 如果您想使用現有的mbox，請停用 **[!UICONTROL 啟用頁面載入（自動建立全域mbox）]**，並在 **[!UICONTROL 全域mbox]** 欄位。

   此 [!UICONTROL 全域mbox] 下拉式清單會列出您帳戶中的所有mbox。 如果您想使用尚未存在的mbox，請建立mbox。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   接著會更新您帳戶的 設定。

1. 下載新的at.js檔案並在您的網站上參考。

   所有現有活動都會更新為使用指定的全域 mbox，包括先前已建立和實施的活動。

## 疑難排解全域mbox實作

下列常見問題集可用來疑難排解全域mbox實作：

### 全域 mbox 為什麼不會載入，或為什麼頁面載入時載入全域 mbox 發生延遲?

確認at.js參考是頁面上的第一個JavaScript呼叫。 有關此問題的其他解決方案，請參見 [全域mbox常見問題](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
