---
keywords: 實作;Mbox;mbox.js;下載 mbox.js;設定 mbox.js
description: 了解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform Web SDK(AEP Web SDK)或最新版at.js。
title: 如何下載 [!DNL Target] mbox.js程式庫？
feature: at.js
role: Developer
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 74%

---

# 下載 mbox.js

Target Standard 和 Premium 使用經修改的 Adobe Target mbox.js 檔案版本。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免您的網站出現任何潛在問題。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

若要使用 [!DNL Adobe Target][!UICONTROL  可視化體驗編輯程式]，您必須隨著您的 [!DNL mbox.js] 檔案包括額外的一行 JavaScript。

1. 按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]** in [!DNL Target Standard]。
1. 按一下&#x200B;**[!UICONTROL 「下載 mbox.js」]**，並依照提示操作來儲存檔案。
1. (條件式) 如果您使用 [!DNL mbox.js] 版本 60 或更新版本，您可以設定資料庫以依預設自動隱藏頁面內容直到 mbox 載入，以減少回應式網站上的閃爍。

1. 在網站上建立 [!DNL mbox.js] 參考。

   從 [!DNL mbox.js] 57 版開始，[!DNL mbox.js] 參照可以放置在頁面上 `<head>` 區段中的任意位置。

   >[!IMPORTANT]
   >
   >如果您使用的 [!DNL mbox.js] 版本早於 57 版，參照必須是您的頁面上 `<head>` 區段中的最後一個項目。如果參考不是最後一個項目，可能會造成顯示或效能問題。

1. 上傳已儲存的 [!DNL mbox.js] 檔案至您在代碼中指定的託管環境中的位置。
