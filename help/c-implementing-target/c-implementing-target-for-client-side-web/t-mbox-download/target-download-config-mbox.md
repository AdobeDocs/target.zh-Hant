---
keywords: 實作;Mbox;mbox.js;下載 mbox.js;設定 mbox.js
description: 瞭解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform網頁SDK（AEP網頁SDK）或最新版的at.js。
title: 如何下載Target mbox.js程式庫？
feature: at.js
role: 開發人員
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 58%

---

# 下載 mbox.js{#download-mbox-js}

Target Standard 和 Premium 使用經修改的 Adobe Target mbox.js 檔案版本。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

若要使用 [!DNL Adobe Target][!UICONTROL  可視化體驗編輯程式]，您必須隨著您的 [!DNL mbox.js] 檔案包括額外的一行 JavaScript。

1. 按一下&#x200B;**[!UICONTROL [!DNL Target Standard]中的]** > **[!UICONTROL 實施]**。
1. 按一下&#x200B;**[!UICONTROL 「下載 mbox.js」]**，並依照提示操作來儲存檔案。
1. (條件式) 如果您使用 [!DNL mbox.js] 版本 60 或更新版本，您可以設定資料庫以依預設自動隱藏頁面內容直到 mbox 載入，以減少回應式網站上的閃爍。

   如需詳細資訊，請參閱 [mbox.js 進階設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C)中的「抑制頁面載入忽隱忽現」。

1. 在網站上建立 [!DNL mbox.js] 參考。

   從 [!DNL mbox.js] 57 版開始，[!DNL mbox.js] 參照可以放置在頁面上 `<head>` 區段中的任意位置。

   >[!IMPORTANT]
   >
   >如果您使用的 [!DNL mbox.js] 版本早於 57 版，參照必須是您的頁面上 `<head>` 區段中的最後一個項目。如果參考不是最後一個項目，可能會造成顯示或效能問題。如需詳細資訊，請參閱[mbox.js的功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md)。

1. 上傳已儲存的 [!DNL mbox.js] 檔案至您在代碼中指定的託管環境中的位置。
