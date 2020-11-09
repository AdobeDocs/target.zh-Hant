---
keywords: Implementation;Mbox;mbox.js;download mbox.js;configure mbox.js
description: Target Standard 和 Premium 使用經修改的 Adobe Target mbox.js 檔案版本。
title: 下載 mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 94%

---


# 下載 mbox.js{#download-mbox-js}

Target Standard 和 Premium 使用經修改的 Adobe Target mbox.js 檔案版本。

若要使用 [!DNL Adobe Target][!UICONTROL  可視化體驗編輯程式]，您必須隨著您的 [!DNL mbox.js] 檔案包括額外的一行 JavaScript。

1. 按一 **[!UICONTROL 下「管理]** >實 **[!UICONTROL 施]** 」 [!DNL Target Standard]。
1. 按一下&#x200B;**[!UICONTROL 「下載 mbox.js」]**，並依照提示操作來儲存檔案。
1. (條件式) 如果您使用 [!DNL mbox.js] 版本 60 或更新版本，您可以設定資料庫以依預設自動隱藏頁面內容直到 mbox 載入，以減少回應式網站上的閃爍。

   如需詳細資訊，請參閱 [mbox.js 進階設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C)中的「抑制頁面載入忽隱忽現」。

1. 在網站上建立 [!DNL mbox.js] 參考。

   從 [!DNL mbox.js] 57 版開始，[!DNL mbox.js] 參照可以放置在頁面上 `<head>` 區段中的任意位置。

   >[!IMPORTANT]
   >
   >如果您使用的 [!DNL mbox.js] 版本早於 57 版，參照必須是您的頁面上 `<head>` 區段中的最後一個項目。如果參考不是最後一個項目，可能會造成顯示或效能問題。如需 [詳細資訊，請參閱mbox.js的功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) 。

1. 上傳已儲存的 [!DNL mbox.js] 檔案至您在代碼中指定的託管環境中的位置。
