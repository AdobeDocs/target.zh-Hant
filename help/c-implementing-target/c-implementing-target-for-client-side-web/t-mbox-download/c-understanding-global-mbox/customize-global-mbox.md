---
keywords: 全域mbox；自訂全域mbox；編輯at.js;at.js；實作at.js
description: 協助您自訂at.js之全域mbox的資訊。
title: 自訂全域 mbox
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 55%

---


# 自訂全域 mbox

協助您自訂at.js之全域mbox的資訊。

1. 按一下「**[!UICONTROL 管理]** > **[!UICONTROL 實施]**」。

1. 停用&#x200B;**[!UICONTROL 啟用頁面載入（自動建立全域mbox）]**，然後新增您要用來傳送[!DNL Target]活動的自訂全域mbox名稱。

   此自訂全域 mbox 也用於點擊追蹤。

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 完成後按一下&#x200B;**[!UICONTROL 「儲存」]**。

1. 在您的網站上實作[!DNL at.js]程式庫。

   如需詳細資訊，請參閱[如何部署at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md)。

1. 計算您的發行轉變所需的時間。

   在您準備好使用 [!DNL Target] 時，若要開始對未來的所有活動使用您的全域 mbox，您可以繼續進行此步驟。

   更新自訂全域 mbox 的名稱以符合以上的步驟 2 中使用的名稱。

   >[!IMPORTANT]
   >
   >儲存時，您帳戶中的所有活動都會與此 mbox 同步。如果此 mbox 不在您的網站上，則所有活動將停止運作。

