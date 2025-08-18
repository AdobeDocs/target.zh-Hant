---
keywords: 鎖定目標； Analytics；追蹤伺服器； Analytics for Target； A4T
description: 瞭解如何在 [!DNL Adobe Target] 中設定活動以使用 [!DNL Adobe Analytics] 作為報表來源(A4T)。
title: 如何在 [!DNL Analytics] 中使用 [!DNL Target]資料？
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 16%

---

# 使用[!DNL Adobe Analytics]資料

您可以在[!DNL Adobe Target]中設定活動以使用[!DNL Adobe Analytics]作為報表來源(A4T)。

如需將[!DNL Analytics]設定為[!DNL Target]資料來源的詳細資訊，請參閱[Adobe Analytics作為Adobe Target的報表Source](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

在您設定使用[!DNL Analytics]作為報表來源的活動之前，請先建立活動的目標，例如提高每位訪客帶來的收入(RPV)或增加購物車的點按次數。 選擇活動的最終成功量度。雖然您可以隨時在[!DNL Analytics]中選取其他量度，但您仍必須指定您預期此測試會影響的特定量度。

>[!NOTE]
>
>如果您已將您的[!DNL Adobe Analytics]帳戶與[!DNL Adobe Experience Cloud]和[!DNL Analytics]連結，則即使尚未為您的帳戶設定[!DNL Target]和[!DNL Target]之間的整合，仍可使用[!DNL Analytics]選項。

選取[!DNL Analytics]做為[!DNL Target]的報告來源時，請選取[!DNL Analytics]報告套裝來接收[!DNL Target]活動資料。 若要指定報表來源，請先從您帳戶繫結的[!DNL Analytics]家公司中選擇任一，接著為該活動選取適當的報表套裝。 只有布建為連線至[!DNL Adobe Target]的報表套裝才可供選取。 如果您沒有看到預期的報表套裝，請先嘗試登出並重新登入[!DNL Adobe Experience Cloud]以重試。 如果清單中仍缺少報表套裝，請聯絡客戶服務。

[!UICONTROL Analytics for Target] (A4T)需要追蹤伺服器才能正確回報結果。 預設追蹤伺服器會顯示在[!UICONTROL Tracking Server]欄位中。 如果您使用多個追蹤伺服器，請確定您在此欄位中包含正確的追蹤伺服器。 如需詳細資訊，請參閱[使用Analytics追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

>[!NOTE]
>
>如果您使用[!DNL Adobe Analytics]作為活動的報表來源，若您使用的是at.js 0.9.1版（或更新版本），則不需要在活動建立期間指定追蹤伺服器。 at.js 程式庫會自動傳送追蹤伺服器值給 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL Tracking Server]頁面上的[!UICONTROL Goals & Settings]欄位保留空白。

在將[!DNL Analytics]設定為您的報表來源之後設定活動時，沒有選項可用來設定報表對象。 [!DNL Analytics] [!DNL Target]報告中有[!UICONTROL Activities]個可用區段。

您必須選取成功量度，以用作每個活動的目標。 您的活動目標為代表成功活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。您可以選擇[!DNL Analytics]量度選擇器中任何可用的[!DNL Analytics]量度。

設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對測試改善之項目的提示。

訪客完成目標後，該訪客將不再納入活動中。 如果訪客在完成活動後重新進入您的活動，則該訪客會計為新訪客。
