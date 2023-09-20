---
keywords: 鎖定目標； Analytics；追蹤伺服器； Analytics for Target； A4T
description: 瞭解如何在中設定活動 [!DNL Adobe Target] 使用 [!DNL Adobe Analytics] 做為報表來源(A4T)。
title: 如何使用 [!DNL Analytics] 資料輸入 [!DNL Target]？
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 19%

---

# 使用 [!DNL Adobe Analytics] 資料

您可在以下位置設定活動： [!DNL Adobe Target] 使用 [!DNL Adobe Analytics] 做為報表來源(A4T)。

如需關於設定的詳細資訊 [!DNL Analytics] 做為的資料來源 [!DNL Target]，請參閱 [Adobe Analytics作為Adobe Target的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

在您設定使用之活動之前 [!DNL Analytics] 做為報表來源，建立活動的目標，例如提高每位訪客帶來的收入(RPV)或增加購物車的點按次數。 選擇活動的最終成功量度。雖然您可以隨時在「 」中選取其他量度 [!DNL Analytics]，您仍須指定您預期此測試會影響的特定量度。

>[!NOTE]
>
>此 [!DNL Adobe Analytics] 如果您已連結 [!DNL Adobe Experience Cloud] 帳戶與兩者 [!DNL Analytics] 和 [!DNL Target]，即使整合介於 [!DNL Target] 和 [!DNL Analytics] 尚未為您的帳戶設定。

當選取 [!DNL Analytics] 做為的報表來源 [!DNL Target]，您選取 [!DNL Analytics] 要接收的報表套裝 [!DNL Target] 活動資料。 若要指定報表來源，請先從 [!DNL Analytics] 您的帳戶繫結的公司，然後為活動選取適當的報表套裝。 僅限布建為可連線的報表套裝 [!DNL Adobe Target] 可供選取。 如果您沒有看到預期的報表套裝，請先嘗試登出並重新登入 [!DNL Adobe Experience Cloud] 再試一次。 如果清單中仍缺少報表套裝，請聯絡客戶服務。

[!UICONTROL 目標分析] (A4T)需要追蹤伺服器才能正確回報結果。 預設追蹤伺服器會顯示在 [!UICONTROL 追蹤伺服器] 欄位。 如果您使用多個追蹤伺服器，請確定您在此欄位中包含正確的追蹤伺服器。 另請參閱 [使用Analytics追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 以取得詳細資訊。

>[!NOTE]
>
>如果您使用 [!DNL Adobe Analytics] 如果您使用at.js 0.9.1版（或更新版本），做為活動的報表來源，在活動建立期間就不需要指定追蹤伺服器。 at.js 程式庫會自動傳送追蹤伺服器值給 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL 目標與設定]頁面上的[!UICONTROL 追蹤伺服器]欄位保留空白。

設定後設定活動時 [!DNL Analytics] 作為您的報表來源，沒有選項可設定報表對象。 [!DNL Analytics] 您可在以下位置找到區段： [!DNL Target] [!UICONTROL 活動] 報告。

您必須選取成功量度，以用作每個活動的目標。 您的活動目標為代表成功活動的轉換活動。最佳作法永遠不要執行未以某些特定方式改善目標的測試。您可以選擇任何 [!DNL Analytics] 中的可用量度 [!DNL Analytics] 量度選擇器。

設定目標並不表示您無法在評估測試結果時使用其他量度。不過，目標為您要對測試改善之項目的提示。

訪客完成目標後，該訪客將不再納入活動中。 如果訪客在完成活動後重新進入您的活動，則該訪客會計為新訪客。
