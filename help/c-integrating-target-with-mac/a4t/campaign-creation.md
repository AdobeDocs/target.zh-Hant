---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: 您可以在 Target Standard/Premium 中設定活動以使用 Adobe Analytics 做為報表來源 (A4T)。
title: 建立使用A4T做為報告來源的活動
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '1394'
ht-degree: 17%

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

## Analytics for Target(A4T)支援自動分配和自動目標活動{#a4t-aa}

我們已將Adobe Target整合升級至Adobe Analytics，稱為[Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)。 「自動分配」和「自動目標」活動現在支援Analytics for Target。

此整合可讓您：

* 使用[自動配置](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)的多武裝強盜功能，將流量驅動至成功體驗
* 使用[Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md)的整合機器學習演算法，根據每位訪客的描述檔、行為和上下文選擇最佳體驗，同時使用[!DNL Adobe Analytics]目標量度和[!DNL Adobe Analytics]的豐富報告和分析功能。

請確定您已實作[ A4T，以便與A/B測試和體驗定位活動](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)搭配使用。 如果您使用`analyticsLogging = client_side`，則還需要將`sessionId`值傳遞至[!DNL Analytics]。 如需詳細資訊，請參閱&#x200B;*Adobe Target SDK*&#x200B;指南中的[ Analytics for Target(A4T)reporting](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

若要開始執行:

1. 在建立A/B測試活動時，在&#x200B;**[!UICONTROL 定位]**&#x200B;頁面上，選取下列其中一個選項作為&#x200B;**[!UICONTROL 流量分配方法]**:

   * 自動分配以獲得最佳體驗
   * 自動鎖定個人化體驗

1. 在&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面上，為&#x200B;**[!UICONTROL 報表來源]**&#x200B;選取&#x200B;**[!UICONTROL Adobe Analytics]**，並選取與您所要最佳化目標對應的報表套裝。

1. 選擇主要目標量度。

   * 選擇&#x200B;**[!UICONTROL 轉換]**&#x200B;以使用[!DNL Adobe Target]指定最佳化目標。
   * 選擇&#x200B;**[!UICONTROL 使用Analytics量度]**，然後從[!DNL Analytics]中選取量度，以用作最佳化目標。 您可以使用現成可用的[!DNL Analytics]轉換度量或[!DNL Analytics]自訂事件。

1. 儲存並啟動您的活動。

   [!UICONTROL 自動配] 置將使用您選取的量度來最佳化活動，將訪客帶往體驗，以最大化您的目標量度。

   或

   [!UICONTROL 自動定位] 會使用您選取的量度來最佳化活動，將訪客帶向個人化的最佳體驗。

1. 使用&#x200B;**[!UICONTROL 報表]**&#x200B;標籤，依您選擇的[!DNL Adobe Analytics]量度來檢視您活動的報表。 按一下「Analytics中的檢視」，深入探索並進一步細分報表資料。****

### 支援的目標量度

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-] Target可讓您選擇下列任何量度類型作為最佳化的主要目標量度：

* [!DNL Adobe Target] 轉換量度
* [!DNL Adobe Analytics] 轉換量度
* [!DNL Adobe Analytics] 個自訂事件

[!UICONTROL A4] Tfor   Auto- [!UICONTROL Allocate和] Auto-Target要求您選擇以二項式事件（即發生或未發生的事件，例如點按、轉換、訂購等）為基礎的量度。（這些類型的事件有時也稱為Bernoulli、二進位或離散事件。）

[!UICONTROL A4] T for  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-] Target不支援對連續度量進行最佳化，例如收入、訂購的產品數、工作階段持續時間、工作階段中的頁面檢視次數等。（這些不支援的量度類型有時也稱為非二項式或非伯努利量度。）

下列量度類型不支援做為主要目標量度：

* [!DNL Adobe Target] 參與度與收入度量
* [!DNL Adobe Analytics] 參與度與收入度量

   您可能會選擇[!DNL Analytics]參與或收入量度作為主要目標量度，因為[!DNL Target]無法識別並排除[!DNL Analytics]的所有參與和收入量度。 請小心，只從[!DNL Analytics]選取二項式轉換度量或自訂事件。

* [!DNL Adobe Analytics] 計算量度

### 限制與附註

某些限制和附註適用於自動分配和自動目標。 其他限制和附註適用於一種或另一種活動類型。

#### 自動分配和自動目標

* 啟動活動後，報表來源無法從[!DNL Analytics]變更為[!DNL Target]，反之亦然。
* 雖然計算量度不支援做為主要目標量度，但通常可以選擇自訂事件作為主要目標量度，以達到預期結果。 例如，如果您想要最佳化度量（例如「每位訪客表單填寫」），請選取與「表單填寫」對應的自訂事件作為主要目標度量。 [!DNL Target] 自動標準化每次瀏覽的轉換量度，以考慮不均勻的流量分佈，因此不需要使用計算量度來執行標準化。
* [!DNL Target] 使用「自動配置」功能中的「相同觸 [!UICONTROL 控」歸] 因模型：Analytics for Target(A4T)。

#### 自動分配

* [!UICONTROL 自動配置] 機型會像往常一樣每兩小時進行一次培訓。

#### 自動鎖定目標

* [!UICONTROL 自動定] 位機型會照常每24小時進行一次培訓。但是，來自[!DNL Analytics]的轉換事件資料會延遲6到24小時。 此延遲表示[!DNL Target]的流量分配將跟蹤[!DNL Analytics]中記錄的最新事件。 在活動首次啟動後的48小時內，效果最大；活動的效能將更密切地反映經過5天後的[!DNL Analytics]轉換行為。 您應考慮在短期活動中使用[!UICONTROL 自動分配]而非[!UICONTROL 自動目標]，其中大部分流量發生在活動生命週期的前五天內。
* 當使用[!DNL Analytics]作為[!UICONTROL 自動目標]活動的資料源時，會將會話視為在經過6小時後結束。 六小時後發生的轉換將不會計算在內。

如需詳細資訊，請參閱&#x200B;*分析工具指南*&#x200B;中的[歸因模型和回顧windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)。
