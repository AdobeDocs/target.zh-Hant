---
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
description: 瞭解如何在Adobe中配置活動 [!DNL Target] 以Adobe Analytics為報告來源(A4T)。
title: 如何建立使用A4T的活動？
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 35%

---

# 建立使用 Analytics 作為報告來源的活動

可以在中配置活動 [!DNL Adobe Target] 使用 [!DNL Adobe Analytics] 作為報告源(A4T)。

在設定使用 [!DNL Analytics] 作為報告來源，為活動制定目標，例如提高每位訪問者的收入(RPV)或增加購物車的點擊量。 選擇活動的最終成功量度。儘管您可以在中隨時選擇更多度量 [!DNL Analytics]，您仍必須指定您希望此test影響的特定度量。

## 建立活動

建立 [!DNL Target] 活動 [!DNL Analytics] 因為報告源與設定常規 [!DNL Target] 活動，但有一些重要差異。 例如，在建立活動時不能選擇用於報告的段，因為在 [!DNL Analytics] 可在查看報表時應用。

1. 按一下&#x200B;**[!UICONTROL 「建立活動」]**。

   >[!NOTE]
   >
   >如果 [!DNL Analytics] 用作報告源。

1. 選取活動類型並開始設定活動。

   如果要建立 [!UICONTROL 自動分配] 或 [!UICONTROL 自動目標] 活動，請參閱 [A4T支援自動分配和自動目標活動](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) 的子菜單。

1. 進入活動建立流程的&#x200B;**[!UICONTROL 「設定」]**&#x200B;部分時，請選擇&#x200B;**[!UICONTROL 「Adobe Analytics」]**&#x200B;並指定您的公司。
1. 選擇一個報表套裝。

   您可以選擇在 [!DNL Analytics]。 報告套件定義收集資料的可用位置。 報表套裝清單中未包括虛擬報表套裝。

   選取報表套裝時，您可能遇到兩個可能的錯誤:

   * 您遇到沒有可用的報表套裝的錯誤，但您的帳戶已正確設定。

      檢查 [!DNL Analytics] 公司。 如果 [!DNL Adobe Experience Cloud] 帳戶與多個帳戶關聯 [!DNL Analytics] 公司，註銷 [!DNL Target]，然後登錄 [!DNL Analytics] 正確的公司。 然後返回到 [!DNL Target]，並載入報表套件。

   * 您並未看到所預期的報表套裝。

      僅設定為連接到的報告套件 [!DNL Target] 的下界。 如果您未看到預期的報告套件，請首先嘗試註銷並重新登錄到 [!DNL Adobe Experience Cloud] 重試。
   如果清單中仍缺少一個或多個報告套件，請 [聯繫客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. 指定您的追蹤伺服器。

   請參閱[使用 Analytics 追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定義體驗。
1. 指定活動目標。

   您需要選擇一個成功度量作為每個活動的目標。 您的活動目標為代表成功活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。您可以選擇任何 [!DNL Analytics] 度量 [!DNL Analytics] 度量選擇器。

   >[!NOTE]
   >
   >您可以將基於目標的自定義度量發送到 [!DNL Analytics] 而不是只依靠 [!DNL Analytics] 資料。 例如，可以監視按一下頁面的情況，該頁面通常不由 [!DNL Analytics]。 此自定義度量將發送到 [!DNL Analytics] 自動 [!DNL Target] 伺服器，並顯示為「[!DNL Target] 中度量選擇器中的「轉換」度量 [!DNL Analytics]。 的 [!DNL Target] 如果選擇使用，則轉換度量為空 [!DNL Analytics] 度量。

   設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對活動改善之項目的提示。

   在訪客達到目標之後會保持在活動中。訪客會繼續看見活動內容，但不會被計為新活動項目。

   >[!NOTE]
   >
   >設定後設定活動時 [!DNL Analytics] 作為報告來源，沒有設定報告受眾的選項。 [!DNL Analytics] 可於 [!DNL Target] 活動報告。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## A4T和自動分配和自動目標活動

如需詳細資訊，請參閱[「自動分配」和「自動鎖定目標」活動的 A4T 支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。
