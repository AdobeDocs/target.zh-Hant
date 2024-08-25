---
keywords: 活動設定；目標與設定；多變數；mvt
description: 瞭解如何使用 [!DNL Adobe Target] 中的[!UICONTROL Goals & Settings]頁面來指定[!UICONTROL Multivariate Test] (MVT)活動目標的相關資訊。
title: 如何在[!UICONTROL Multivariate Test] (MVT)活動中指定目標與設定？
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 41%

---

# 目標與設定([!UICONTROL Multivariate Test])

[!DNL Adobe Target]中的[!UICONTROL Goals & Settings]頁面是您輸入[!UICONTROL Multivariate Test] (MVT)活動之目標相關資訊的位置。

下列章節可供使用：

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

每個區段中的可用設定取決於您是使用[!DNL Target]或[!DNL Analytics]作為報表來源。

## 活動設定 {#section_DCBDC354261F420EBD4B43EA34947BAC}

可使用下列設定:

### 目標

輸入可選目標。目標可以是可協助您和團隊成員識別促銷活動的任何資訊。

### 優先順序

根據您的設定，[!UICONTROL Priority]的[!DNL Target] UI和選項會有所不同。 您可以使用[!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]的舊版設定，也可以啟用0到999的精細優先順序。

如果將多個活動指派至具有相同客群的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。

如果未在[!UICONTROL Administration] > [!UICONTROL Reporting] （預設）中啟用此選項，請指定優先順序： [!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]。

若要啟用微調優先順序，請按一下「[!UICONTROL Administration] > [!UICONTROL Reporting]」，然後將「[!UICONTROL Enable Fine-Grained Priorities]」選項切換到「開啟」位置。

如果已啟用此選項，請指定從0到999的值：

* 0 = 低
* 999 = 高

對於在舊版[!DNL Target]中建立的活動，[!UICONTROL Low]優先順序會轉換為0，[!UICONTROL Medium]優先順序會轉換為5，而[!UICONTROL High]優先順序會轉換為10。 您可以視需要調整這些值。

>[!NOTE]
>
>在使用微調優先順序後，在您可以停用此選項之前，必須將所有優先順序設定回 0、5 和 10。

### 持續時間

活動可以在核准後開始，或者您可以設定特定的日期和時間。同樣地，活動可以在停用時結束，或者您可以設定日期和時間。時間選擇器使用 24 小時時鐘，午夜為 00:00。時區會設為瀏覽器中設定的時區。若要使用不同的時區，請將您的瀏覽器設定為其他時區並重新啟動瀏覽器。

## 報表設定 {#section_13119392051044FBA6387D9B3B1C43CF}

有以下設定可使用：

### 報表來源

指定收集來源的解決方案資料：

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

如果已在您的[帳戶設定](/help/main/administrating-target/reporting.md)中指定報表解決方案，則會使用指定的解決方案，而且此設定不會顯示。

為了讓報表保持一致，在活動上線後，您無法變更您的報表來源。

**[!DNL Adobe Analytics]**：檢視[[!DNL Adobe Analytics] 作為 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的報告來源，以瞭解報告解決方案之間的差異和各自的優點。

選取[!DNL Analytics]做為[!DNL Target] (A4T)的報告來源時，請選取[!DNL Analytics]報告套裝來接收[!DNL Target]活動資料。 若要這麼做，請先從您帳戶繫結的[!DNL Analytics]家公司中選擇任一，接著為該活動選取適當的報表套裝。 只有布建為連線至[!DNL Target]的報表套裝才可供選取。 如果您沒有看到預期的報表套裝，請先嘗試登出並重新登入[!DNL Adobe Experience Cloud]以重試。 如果清單中仍缺少報表套裝，請連絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

[!DNL Analytics for Target] (A4T)需要追蹤伺服器才能正確回報結果。 預設追蹤伺服器會顯示在[!UICONTROL Tracking Server]欄位中。 如果您使用多個追蹤伺服器，請確定您在此欄位中包含正確的追蹤伺服器。 如需詳細資訊，請參閱[使用Analytics追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

**[!DNL Adobe Customer Journey Analytics]**：如需有關[!DNL Adobe Customer Journey Analytics]與[!DNL Target]之間整合的詳細資訊，請參閱[[!DNL Target] 在 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中報告。

### 目標量度

選取訪客為了達成目標採取的動作。例如，選擇一個[!UICONTROL Conversion]量度，然後設定決定何時可取得成功的引數。

>[!NOTE]
>
>如果報表解決方案設為[!DNL Analytics]，則唯一可用的目標量度是[!UICONTROL Conversion]。 無法選取[!DNL Analytics]個量度作為目標。

選取您的成功量度時，即會顯示選取器。使用此選取器來選擇成功量度的特定項目。

如果已啟用，[!UICONTROL Estimated Value of the Conversion]欄位（[!UICONTROL Page Score]量度無法使用）可提供目標的值，但不適用其他量度。 此值可讓 [!DNL Target] 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。對於所有收入量度（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales]和[!UICONTROL Orders]），預估會使用[!UICONTROL Revenue per Visitor]。 資料類型為貨幣。

達到活動目標之後，訪客會繼續看見活動內容，除非該訪客符合較高優先順序活動的資格。 如果訪客再次達到目標，將會將其計為另一次轉換。此行為與[!DNL Target Classic]中的預設行為不同，如果訪客再次看到測試，則會將其計為新訪客。

### 其他量度

建立其他的成功量度。

如果報表解決方案設為[!DNL Analytics]，則無法使用此設定。 在此情況下，會套用為[!DNL Analytics]報表套裝定義的量度。

### 報表的對象

依預設，報表會顯示所有符合資格訪客的結果。您可以新增報表客群以僅顯示關於特定客群的資訊。

### 進階設定 {#section_E2FE441AFB324E498793ABB025ED9974}

進階設定可用於[!UICONTROL Multivariate Test]個目標量度。

![進階設定功能表](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>如果您使用 [!DNL Adobe Analytics] 作為您的報表來源，則設定是由 [!DNL Analytics] 伺服器管理。進階設定選項無法使用。

#### 遞增此量度時，應達到什麼成功量度?

使用此選項時，如果某人先前達到不同的成功量度，則僅將其計算為達到成功量度。 例如，測試轉換可能只有在轉換之前訪客點選了選件，或達到特定頁面時才有效。

您可以提供多個量度上的相依性，並且具有彈性可選擇量度應為達到或未到達時計數才會增加。

定義兩個（或多個）成功量度，之後才可以讓某個量度相依於另一個量度。

[!UICONTROL Add Dependency]選項允許在已達到另一個成功量度或尚未達到時遞增成功量度。

若要新增相依性:

1. 新增其他量度後，請按一下&#x200B;**[!UICONTROL Advanced Settings]**。
2. 按一下&#x200B;**[!UICONTROL Add Dependency]**&#x200B;選項：

   ![新增相依性](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. 將需要的量度從左窗格拖曳到右窗格，然後按一下「**[!UICONTROL Reached]**」以在「達到」與「未達到」之間切換設定。

   ![已達到相依性](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

您可以在新增相依性之後加以編輯或移除。

### 使用者達到此目標量度後會發生什麼事?

有三個選項可控制訪客達到目標量度後會發生什麼事:

* [!UICONTROL Select Increment Count & Keep User in Activity]以指定遞增計數的方式。
* [!UICONTROL Select Increment Count, Release User & Allow Reentry]以指定如果使用者重新進入活動，使用者會看到的體驗。
* [!UICONTROL Select Increment Count, Release User & Bar from Reentry]以指定使用者看到的內容，而非活動內容。

請參閱[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)以取得關於進階設定的詳細資訊。

## 其他中繼資料 {#section_2E8917BEFB954480A4206B9E9E917F80}

可使用下列設定:

### 附註

輸入任何對您自己或其他團隊成員有用的活動相關資訊。 [!UICONTROL Notes]窗格可調整大小。

## 培訓影片

以下影片含有本文章探討之概念的詳細資訊。

### 活動設定 (3:02)

此影片包括關於活動設定的資訊。

* 輸入活動的目標
* 設定活動的優先順序層級
* 排程活動開始和結束時間
* 新增報表的對象，以建立報表篩選器
* 輸入活動的備註

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### 建立多變數測試 (9:25)

此影片示範如何使用[!DNL Target]三步驟引導式工作流程建立多變數測試。 在 7:00 開始討論目標和設定。

* 定義和設計多變數測試
* 建立多變數測試

>[!VIDEO](https://video.tv.adobe.com/v/17395)
