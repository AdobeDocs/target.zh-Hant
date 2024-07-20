---
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
description: 瞭解如何在Adobe [!DNL Target] 中設定使用Adobe Analytics作為報表來源(A4T)的活動。
title: 如何建立使用A4T的活動？
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 30%

---

# 建立使用 Analytics 作為報告來源的活動

您可以在[!DNL Adobe Target]中設定活動以使用[!DNL Adobe Analytics]作為報表來源(A4T)。

在您設定使用[!DNL Analytics]作為報表來源的活動之前，請先建立活動的目標，例如提高每位訪客帶來的收入(RPV)或增加購物車的點按次數。 選擇活動的最終成功量度。雖然您可以隨時在[!DNL Analytics]中選取更多量度，但您仍必須指定您預期此測試會影響的特定量度。

## 建立活動

建立使用[!DNL Analytics]作為報告來源的[!DNL Target]活動類似於設定一般[!DNL Target]活動，但有一些重要差異。 例如，您無法在建立活動時選取要報告的區段，因為檢視報告時可套用[!DNL Analytics]中所有可用的區段。

1. 按一下 **[!UICONTROL Create Activity]**。

   >[!NOTE]
   >
   >如果使用[!DNL Analytics]作為報表來源，活動名稱不能包含「%」字元。
   >
   >請勿對使用A4T報表之不同[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)中的兩個活動使用相同的活動名稱。

1. 選取活動類型並開始設定活動。

   如果您想要建立[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target]活動，請參閱自動分配和自動鎖定目標活動的[A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)以取得詳細資訊。

1. 當您到達活動建立流程的&#x200B;**[!UICONTROL Settings]**&#x200B;部分時，請選擇&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;並指定您的公司。
1. 選擇一個報表套裝。

   您可以在[!DNL Analytics]中選擇任何您可用的報表套裝。 報表套裝會定義可在何處使用收集到的資料。 報表套裝清單中未包括虛擬報表套裝。

   選取報表套裝時，您可能遇到兩個可能的錯誤:

   * 您遇到沒有可用的報表套裝的錯誤，但您的帳戶已正確設定。

     檢查您的[!DNL Analytics]公司。 如果您的[!DNL Adobe Experience Cloud]帳戶繫結至超過一個[!DNL Analytics]公司，請登出[!DNL Target]，然後在正確的公司底下登入[!DNL Analytics]。 然後返回[!DNL Target]，報表套裝便會載入。

   * 您並未看到所預期的報表套裝。

     只有布建為連線至[!DNL Target]的報表套裝才可供選取。 如果您沒有看到預期的報表套裝，請先嘗試登出並重新登入[!DNL Adobe Experience Cloud]以重試。

   如果清單中仍遺漏一或多個報表套裝，請[聯絡客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. 指定您的追蹤伺服器。

   請參閱[使用 Analytics 追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定義體驗。
1. 指定活動目標。

   您必須選取成功量度，以用作每個活動的目標。 您的活動目標為代表成功活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。您可以選擇[!DNL Analytics]量度選擇器中任何可用的[!DNL Analytics]量度。

   >[!NOTE]
   >
   >您可以傳送自訂Target型量度至[!DNL Analytics]，而非僅依賴[!DNL Analytics]資料。 例如，您可以監視點選的頁面，這通常不會由[!DNL Analytics]追蹤。 此自訂量度會自動從[!DNL Target]伺服器傳送至[!DNL Analytics]，並在[!DNL Analytics]的量度選擇器中顯示為「[!DNL Target]轉換」量度。 如果您選擇使用[!DNL Analytics]量度，[!DNL Target]轉換量度會是空的。

   設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對活動改善之項目的提示。

   在訪客達到目標之後會保持在活動中。訪客會繼續看見活動內容，但不會被計為新活動項目。

   >[!NOTE]
   >
   >在將[!DNL Analytics]設定為您的報表來源之後設定活動時，沒有選項可用來設定報表對象。 [!DNL Target]活動報表中有[!DNL Analytics]個可用區段。

1. 按一下 **[!UICONTROL Save]**。

## A4T以及自動分配和自動鎖定目標活動

如需詳細資訊，請參閱自動分配和自動鎖定目標活動的[A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。
