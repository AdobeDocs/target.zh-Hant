---
kewords: redirect;redirect url;send to different page
description: 瞭解如何在Adobe中使用重定向到URL選項 [!DNL Target] 當您希望將訪問者發送到其他頁面，而不是在同一頁面上顯示內容時。
title: 是否可以將頁面重定向到其他URL?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 84%

---

# 重新導向至 URL

使用 [!UICONTROL 重定向至URL] 選項 [!DNL Adobe Target] 當您希望將訪問者發送到其他頁面，而不是在同一頁面上顯示內容時。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。若是這種情況，您的 A/B 測試會比較頁面 A 和頁面 B。使用兩個體驗來設定 A/B 測試促銷活動: 一個指向預設的頁面 A，另一個重新導向至頁面 B。在「體驗動作」功能表中，透過按一下體驗的字母標籤，接著選擇&#x200B;**[!UICONTROL 「重新導向至 URL」]**，然後指定頁面 B 的 URL 來找到。選件會設定為將訪客重新導向至不同頁面。

重新導向選件會執行 JavaScript 程式碼來重新導向瀏覽器。此選件會使用 `window.location.replace();` 方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。這可讓訪客仍然可以使用瀏覽器中的上一步按鈕。

重新導向選件有一些限制:

* 針對使用 A4T 活動中的重新導向選件，您的實施必須符合某些最低需求。此外，還有需要您知道的重要資訊。如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
* 使用表單式體驗撰寫器時，重新導向選件不應該用於屬於頁面的 mbox 中。來自屬於 HTML `<head>` 一部分的指令碼標記時，才應該使用重新導向選件。您應該一律使用自動建立，並為全域 mbox 設定重新導向選件。

>[!NOTE]
>
>如果要傳入登陸頁面的反向連結值，建議您使用 HTML 選件，而不要使用重新導向選件。

若要建立重新導向選件:

1. 建立體驗。
1. 將滑鼠指標暫留在滑鼠體驗上，然後按一下「重新導向至 URL」圖示(![](assets/icon_redirect_url.png))。

   ![](assets/exp_actions.png)

1. 輸入 URL。
1. 如果需要，請選取包括目前的查詢參數的選項。

   如果已選取此選項，訪客的 URL 中，? 之後的任何內容會在重新導向時附加至重新導向 URL。

   依預設會選取此選項。
1. (可選) 建立其他規則。

   其他規則可以根據以下任何項目:

   * URL
   * 網域
   * 路徑
   * 雜湊 (#) 片段
   * 查詢
   * mbox 參數
   可以使用「與」或「或」將其他規則加入活動 URL。您新增的所有規則會使用「與」彼此進行評估。