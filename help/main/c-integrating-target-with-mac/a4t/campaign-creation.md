---
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
description: 瞭解如何在Adobe中設定活動 [!DNL Target] 使用Adobe Analytics作為報表來源(A4T)的報表套裝。
title: 如何建立使用A4T的活動？
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 30%

---

# 建立使用 Analytics 作為報告來源的活動

您可在以下位置設定活動： [!DNL Adobe Target] 使用 [!DNL Adobe Analytics] 做為報表來源(A4T)。

在您設定使用之活動之前 [!DNL Analytics] 做為報表來源，建立活動的目標，例如提高每位訪客帶來的收入(RPV)或增加購物車的點按次數。 選擇活動的最終成功量度。雖然您可以隨時在清單中選取更多量度 [!DNL Analytics]，您仍須指定您預期此測試會影響的特定量度。

## 建立活動

建立 [!DNL Target] 使用的活動 [!DNL Analytics] 由於報表來源類似於設定一般 [!DNL Target] 活動，但有一些重要差異。 例如，您無法在建立活動時選取要報告的區段，因為所有區段都可在 [!DNL Analytics] 可在檢視報表時套用。

1. 按一下&#x200B;**[!UICONTROL 「建立活動」]**。

   >[!NOTE]
   >
   >如果符合以下條件，活動名稱不能包含「%」字元 [!DNL Analytics] 設為報表來源。
   >
   >請勿對來自不同的兩個活動使用相同的活動名稱 [工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 使用A4T報表的客戶。

1. 選取活動類型並開始設定活動。

   如果您想要建立 [!UICONTROL 自動分配] 或 [!UICONTROL 自動鎖定目標] 活動，請參閱 [自動分配和自動鎖定目標活動的A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) 以取得詳細資訊。

1. 當您前往 **[!UICONTROL 設定]** 活動建立流程的一部分，選擇 **[!UICONTROL Adobe Analytics]** 並指定您的公司。
1. 選擇一個報表套裝。

   您可以在中選擇任何您可用的報表套裝 [!DNL Analytics]. 報表套裝會定義可在何處使用收集到的資料。 報表套裝清單中未包括虛擬報表套裝。

   選取報表套裝時，您可能遇到兩個可能的錯誤:

   * 您遇到沒有可用的報表套裝的錯誤，但您的帳戶已正確設定。

     檢查您的 [!DNL Analytics] 公司。 若您的 [!DNL Adobe Experience Cloud] 帳戶繫結至多個專案 [!DNL Analytics] 公司，登出 [!DNL Target]，並登入 [!DNL Analytics] 在正確的公司下。 然後返回 [!DNL Target]，則會載入報表套裝。

   * 您並未看到所預期的報表套裝。

     僅限布建為可連線的報表套裝 [!DNL Target] 可供選取。 如果您沒有看到預期的報表套裝，請先嘗試登出並重新登入 [!DNL Adobe Experience Cloud] 再試一次。

   如果清單中仍缺少一個或多個報表套裝，請 [聯絡客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. 指定您的追蹤伺服器。

   請參閱[使用 Analytics 追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定義體驗。
1. 指定活動目標。

   您必須選取成功量度，以用作每個活動的目標。 您的活動目標為代表成功活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。您可以選擇任何 [!DNL Analytics] 中的可用量度 [!DNL Analytics] 量度選擇器。

   >[!NOTE]
   >
   >您可以傳送自訂Target型量度至 [!DNL Analytics] 而不是僅依賴 [!DNL Analytics] 資料。 例如，您可以監視點按頁面，這通常不會由追蹤 [!DNL Analytics]. 此自訂量度會傳送至 [!DNL Analytics] 自動從 [!DNL Target] 伺服器，並顯示為「[!DNL Target] 中的量度選擇器中的「轉換」量度 [!DNL Analytics]. 此 [!DNL Target] 如果您選擇使用，轉換量度會是空的 [!DNL Analytics] 量度。

   設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對活動改善之項目的提示。

   在訪客達到目標之後會保持在活動中。訪客會繼續看見活動內容，但不會被計為新活動項目。

   >[!NOTE]
   >
   >在設定後設定活動時 [!DNL Analytics] 作為您的報表來源，沒有選項可設定報表對象。 [!DNL Analytics] 您可在以下位置找到區段： [!DNL Target] 活動報表。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## A4T以及自動分配和自動鎖定目標活動

如需詳細資訊，請參閱 [自動分配和自動鎖定目標活動的A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
