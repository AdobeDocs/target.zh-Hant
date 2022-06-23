---
keywords: 全局mbox；自定義全局mbox；編輯at.js;at.js;implement at.js
description: 瞭解如何在Adobe Target的「管理 — 實施」頁面上為at.js自定義全局框。
title: 如何自定義全局框？
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 16%

---

# 自訂全域 mbox

幫助您自定義 [!DNL Adobe Target] at.js的全局框。

1. 按一下「**[!UICONTROL 管理]** > 「**[!UICONTROL 實施]**」。

1. 禁用 **[!UICONTROL 已啟用頁面載入（自動建立全局框）]**，然後添加要用於傳遞活動的自定義全局框的名稱 [!DNL Target]。

   >[!IMPORTANT]
   >
   >當您選擇其他全局框時，將自動保存更改。

   此自訂全域 mbox 也用於點擊追蹤。

   ![自定義全局框](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 實施 [!DNL at.js] 的子目錄。

   請參閱 [如何部署at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/how-to-deployatjs/){target=_blank}以獲取詳細資訊。

1. 計算您的發行轉變所需的時間。

   準備好 [!DNL Target] 要開始將全局框用於將來的所有活動，您可以繼續此步驟。

   更新自訂全域 mbox 的名稱以符合以上的步驟 2 中使用的名稱。

   >[!IMPORTANT]
   >
   >帳戶中的所有活動都與此框同步。 確保您的站點上存在全局框，以便活動繼續運行。 請確保編輯並重新保存使用與此框同步的Visual Experience Composer(VEC)建立的受影響活動。 不必重新保存在基於表單的體驗作曲家或通過API建立的活動。

