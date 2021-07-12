---
keywords: 全域mbox；自訂全域mbox；編輯at.js;at.js；實作at.js
description: 了解如何在Adobe Target的「管理 — 實作」頁面上自訂at.js的全域mbox。
title: 如何自訂全域mbox?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: fb0a62ecc5609e7b8ef5f6a4fb5a94f8ba025fec
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 22%

---

# 自訂全域 mbox

可協助您為at.js自訂全域mbox的資訊。

1. 按一下「**[!UICONTROL 管理]** > 「**[!UICONTROL 實施]**」。

1. 停用&#x200B;**[!UICONTROL 啟用頁面載入（自動建立全域mbox）]**，然後新增您要用來從[!DNL Target]傳送活動的自訂全域mbox名稱。

   >[!IMPORTANT]
   >
   >當您選取不同的全域mbox時，會自動儲存變更。

   此自訂全域 mbox 也用於點擊追蹤。

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 在您的網站上實作[!DNL at.js]資料庫。

   如需詳細資訊，請參閱[如何部署at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) 。

1. 計算您的發行轉變所需的時間。

   當您準備好[!DNL Target]以開始對未來的所有活動使用您的全域mbox時，您可以繼續執行此步驟。

   更新自訂全域 mbox 的名稱以符合以上的步驟 2 中使用的名稱。

   >[!IMPORTANT]
   >
   >您帳戶中的所有活動都會與此mbox同步。 如果此mbox不在您的網站上，則所有活動都會停止運作。
