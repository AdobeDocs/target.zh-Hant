---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: 您可以在 Target Standard/Premium 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。
title: 建立使用A4T做為報告來源的活動
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 95e2ed4d9ca22e18b91533365624bcc001d09c34
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 36%

---


# 建立使用Analytics做為報告來源的活動

您可以設定[!DNL Target]中的活動，使用[!DNL Adobe Analytics]做為報告來源(A4T)。

在您設定使用[!DNL Analytics]作為報告來源的活動之前，請先建立活動的目標，例如提高每位訪客的收入(RPV)或增加購物車的點按。 選擇活動的最終成功量度。雖然您可以隨時在[!DNL Analytics]中選取其他量度，但您仍必須指定您預期此測試會影響的特定量度。

## 建立活動

建立使用[!DNL Analytics]作為報告來源的[!DNL Target]活動類似於設定一般的[!DNL Target]活動，但有一些重要差異。 例如，您無法在建立活動時選取報表的區段，因為[!DNL Analytics]中所有可用的區段都可在檢視報表時套用。

1. 按一下&#x200B;**[!UICONTROL 「建立活動」]**。

   >[!NOTE]
   >
   >如果[!DNL Analytics]是報告來源，則活動名稱不能包含「%」字元。

1. 選取活動類型並開始設定活動。

   如果要建立[!UICONTROL 自動分配]或[!UICONTROL 自動目標]活動，請參閱[A4T支援自動分配和自動目標活動](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)以瞭解詳細資訊。

1. 進入活動建立流程的&#x200B;**[!UICONTROL 「設定」]**&#x200B;部分時，請選擇&#x200B;**[!UICONTROL 「Adobe Analytics」]**&#x200B;並指定您的公司。
1. 選擇一個報表套裝。

   您可以選擇[!DNL Analytics]中任何可用的報表套裝。 報表套裝會定義所收集的資料將可供使用的位置。報表套裝清單中未包括虛擬報表套裝。

   選取報表套裝時，您可能遇到兩個可能的錯誤:

   * 您遇到沒有可用的報表套裝的錯誤，但您的帳戶已正確設定。

      您可能需要檢查[!DNL Analytics]公司。 如果您的[!DNL Adobe Experience Cloud]帳戶系結至多個[!DNL Analytics]公司，請登出[!DNL Target]，然後登入右公司下方的[!DNL Analytics]。 然後返回[!DNL Target]，報表套裝就會載入。

   * 您並未看到所預期的報表套裝。

      只有已布建以連線至[!DNL Target]的報表套裝才可供選取。 如果您未看到預期的報表套裝，請先嘗試登出並重新登入[!DNL Adobe Experience Cloud]以再試一次。
   如果報表套裝仍未從清單中遺失，請[連絡客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. 指定您的追蹤伺服器。

   請參閱[使用 Analytics 追蹤伺服器](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定義體驗。
1. 指定活動目標。

   您必須選取成功度量，以用作每個活動的目標。 您的活動目標為代表成功活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。您可以選擇[!DNL Analytics]量度選擇器中任何可用的[!DNL Analytics]量度。

   >[!NOTE]
   >
   >您可以傳送自訂的Target型量度至[!DNL Analytics]，而不只依賴[!DNL Analytics]資料。 例如，您可以監視在頁面上的點按情況，通常不會由[!DNL Analytics]追蹤。 此自訂量度會自動從[!DNL Target]伺服器傳送至[!DNL Analytics]，並顯示為[!DNL Analytics]量度選擇器中的「[!DNL Target]轉換」量度。 如果您選擇使用[!DNL Analytics]度量，則「[!DNL Target]轉換」度量為空。

   設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對活動改善之項目的提示。

   在訪客達到目標之後會保持在活動中。訪客會繼續看見活動內容，但不會被計為新活動項目。

   >[!NOTE]
   >
   >在將[!DNL Analytics]設定為報表來源後設定活動時，沒有設定報表對象的選項。 [!DNL Analytics] 區段可在「活動」報 [!DNL Target] 表中使用。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

