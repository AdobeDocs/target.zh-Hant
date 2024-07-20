---
kewords: redirect;redirect url;send to different page
description: 瞭解當您想要將訪客傳送至其他頁面而不是在同一頁面上顯示內容時，如何使用Adobe [!DNL Target] 中的「重新導向至URL」選項。
title: 我可以將頁面重新導向至不同的URL嗎？
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
source-git-commit: b0bf54d47ac44afc3597f308ea38fd479c54026d
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 68%

---

# 重新導向至 URL

當您想要將訪客傳送至不同頁面而不是在同一頁面上顯示內容時，請在[!DNL Adobe Target]中使用[!UICONTROL Redirect to URL]選項。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。若是這種情況，您的A/B測試會比較頁面A與頁面B。使用兩個體驗來設定A/B測試行銷活動：一個指向預設頁面A，另一個重新導向至頁面B。在「體驗動作」功能表（按一下體驗的字母標籤即可找到）中，選擇&#x200B;**[!UICONTROL Redirect to URL]**&#x200B;並指定頁面B的URL。選件已設定為將訪客重新導向至不同頁面。

重新導向選件會執行 JavaScript 程式碼來重新導向瀏覽器。此選件會使用 `window.location.replace();` 方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。這可讓訪客仍然可以使用瀏覽器中的上一步按鈕。

重新導向選件有一些限制:

* 針對使用 A4T 活動中的重新導向選件，您的實施必須符合某些最低需求。此外，還有需要您知道的重要資訊。如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
* 使用表單式體驗撰寫器時，重新導向選件不應該用於屬於頁面的 mbox 中。來自屬於 HTML `<head>` 一部分的指令碼標記時，才應該使用重新導向選件。您應該一律使用自動建立，並為全域 mbox 設定重新導向選件。

>[!NOTE]
>
>如果要傳入登陸頁面的反向連結值，建議您使用 HTML 選件，而不要使用重新導向選件。

若要建立重新導向選件:

1. 建立體驗。
1. 將滑鼠指標暫留在滑鼠體驗上，然後按一下「重新導向至URL」圖示(![icon_redirect_url image](assets/icon_redirect_url.png))。

   ![exp_actions影像](assets/exp_actions.png)

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

## 已知問題

* at.js 實作中的重新導向活動可能會造成預覽 URL 進入迴圈 (重複傳送選件)。您可以使用 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)，而不是執行預覽和 QA。此問題不會影響選件的實際傳送。(TGT-23019)
