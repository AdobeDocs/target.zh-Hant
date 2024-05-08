---
keywords: 活動設定; A/B目標與設定; 報表設定; 目標量度; 成功量度; 相依成功量度; 進階設定; 主要目標; 其他量度; 目標; 優先順序; 持續時間; 報表解決方案; 目標; 報表對象; 增加此量度前需要達成哪些成功量度; 使用者達到此目標量度後會發生什麼事; 備註
description: 瞭解如何使用 [!UICONTROL Goals and Settings] 頁面來指定有關A/B活動目標的資訊。
title: 如何在「 」中指定目標與設定 [!DNL Target] A/B活動？
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: b5f508d283390c859085d4ee52c582312085addc
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 35%

---

# 目標與設定

此 [!UICONTROL Goals & Settings] 頁面位置 [!DNL Adobe Target] 是指定活動目標相關資訊的位置。

可用的設定視您使用Target還是 [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 作為報表來源。

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

此 [!UICONTROL Activity Settings] 的區段 [!UICONTROL Goals & Settings] 頁面可讓您設定下列選項：

| 設定 | 說明 |
|--- |--- |
| [!UICONTROL Objective] | 輸入可選目標。目標可以是任何有助於您與您的團隊成員識別活動的資訊。 |
| [!UICONTROL Priority] | 根據您的設定， [!DNL Target] 的UI和選項 [!UICONTROL Priority] 視情況而定。 您可以使用舊版設定 [!UICONTROL Low]， [!UICONTROL Medium]，或 [!UICONTROL High]，或您可啟用0至999的精細優先順序。<P>如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。<P>如果未在中啟用此選項 [!UICONTROL Administration] （預設值），指定優先順序： [!UICONTROL Low]， [!UICONTROL Medium]，或 [!UICONTROL High].<P>若要啟用 [微調優先順序](/help/main/administrating-target/reporting.md)，按一下 [!UICONTROL Administration] > [!UICONTROL Reporting]，然後切換 [!UICONTROL Enable Fine-Grained Priorities] 選項切換至「開啟」位置。 <P>如果已啟用此選項，請指定從0到999的值： 0 = [!UICONTROL Low] 和999 = [!UICONTROL High]. <P>針對在舊版中建立的活動 [!DNL Target]， [!UICONTROL Low] 優先順序已轉換為0， [!UICONTROL Medium] 會轉換為5，並且 [!UICONTROL High] 會轉換為10。 您可以視需要調整這些值。<P>注意：在使用微調優先順序後，在您可以停用此選項之前，必須將所有優先順序設定回0、5和10。 |
| 持續時間 | 活動可以在核准後開始，或者您可以設定特定的日期和時間。同樣地，活動可以在停用時結束，或者您可以設定日期和時間。時間選擇器使用 24 小時時鐘，午夜為 00:00。時區會設為瀏覽器中設定的時區。若要使用不同的時區，請將您的瀏覽器設定為其他時區並重新啟動瀏覽器。 |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

此 [!UICONTROL Reporting Settings] 的區段 [!UICONTROL Goals & Settings] 頁面可讓您設定下列選項：

| 設定 | 說明 |
|--- |--- |
| [!UICONTROL Reporting Source] | 指定收集來源的解決方案資料：<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>如果您已在以下專案中指定報表來源： [帳戶設定](/help/main/administrating-target/reporting.md)，則會使用指定的來源，且此設定不會顯示。<P>為了讓報表保持一致，在活動上線後，您無法變更您的報表來源。<P>**Adobe Analytics**：請參閱 [Adobe Analytics作為Target的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 以瞭解報告解決方案之間的差異和各自的優點。 當選取 [!DNL Analytics] 做為的報表來源 [!DNL Target]，您選取 [!DNL Analytics] 要接收的報表套裝 [!DNL Target] 活動資料。<P>若要指定報表來源，請先從 [!DNL Analytics] 您的帳戶繫結的公司，然後為活動選取適當的報表套裝。 僅限布建為可連線的報表套裝 [!DNL Adobe Target] 可供選取。 如果您沒有看到預期的報表套裝，請先嘗試登出並重新登入 [!DNL Adobe Experience Cloud] 再試一次。 如果清單中仍缺少報表套裝，請聯絡客戶服務。<P><P>**Adobe Customer Journey Analytics**：請參閱 [[!DNL Target] 報告位置 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) 以取得關於以下各項整合的詳細資訊： [!DNL Adobe Customer Journey Analytics] 和 [!DNL Target].<P>[!DNL Target] 報告位置 [!DNL Customer Journey Analytics] 支援在含有手動流量分割的A/B活動中。 [!UICONTROL Auto-Target] 和 [!UICONTROL Auto-Allocate] A/B活動無法使用 [!DNL Target] 報告位置 [!DNL Customer Journey Analytics]. |
| [!UICONTROL Goal Metric] | 選取訪客為了達成目標採取的動作。例如，選擇 [!UICONTROL Conversion] 量度，然後設定決定何時取得成功的引數。 如需關於設定量度的詳細資訊，請參閱[設定量度](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)。<P>注意：如果報表解決方案設為 [!DNL Analytics]，唯一可用的目標量度是 [!UICONTROL Conversion]. [!DNL Analytics] 量度無法選取作為目標。 選取您的成功量度時，即會顯示選取器。使用此選取器來選擇成功量度的特定項目。<P>如果已啟用， [!UICONTROL Estimated Value of the Conversion] 欄位(不適用於 [!UICONTROL Page Score] 量度)為您的目標提供值，但此值不適用於其他量度。 此值可讓 [!DNL Target] 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。針對所有收入量度([!UICONTROL Revenue per Visitor]， [!UICONTROL Average Order Value]， [!UICONTROL Total Sales]、和 [!UICONTROL Orders])，預估使用 [!UICONTROL Revenue per Visitor]. 資料類型為貨幣。<P>達到活動目標之後，訪客會繼續看見活動內容，除非該訪客符合較高優先順序活動的資格。 如果訪客再次達到目標，將會將其計為另一次轉換。這與中的預設行為不同 [!DNL Target Classic]，如果訪客再次看到活動，會將訪客計為新訪客。 |
| [!UICONTROL Additional Metrics] | 建立其他成功量度。 如果報表解決方案設為，則無法使用此設定 [!DNL Analytics]. 在此案例中，為定義的量度 [!DNL Analytics] 套用報表套裝。 |
| [!UICONTROL Audiences for Reporting] | 依預設，報表會顯示所有符合資格訪客的結果。您可以新增報表對象以顯示有關特定對象的資訊。 如果您選擇 [!DNL Analytics] 作為您的報表解決方案。 為定義的對象 [!DNL Analytics] 報表套裝已套用。 |

## 進階設定 {#section_E2FE441AFB324E498793ABB025ED9974}

此 [!UICONTROL Advanced Settings] 的區段 [!UICONTROL Goals & Settings] 頁面可讓您設定下列選項：

若要指定進階設定，請按一下 **[!UICONTROL More]** 圖示（垂直省略符號），然後按一下 **[!UICONTROL Advanced Settings]**，如下圖所示。

![進階設定功能表](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>如果您使用 [!DNL Adobe Analytics] 作為您的報表來源，則設定是由 [!DNL Analytics] 伺服器管理。進階設定選項無法使用。

![進階設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| 設定 | 說明 |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | 使用此選項時，如果某人先前達到不同的成功量度，則僅將其計算為達到成功量度。 例如，活動轉換可能只有在轉換之前訪客點選了選件，或達到特定頁面時才有效。 您可以提供多個量度上的相依性，並且具有彈性可選擇量度應為達到或未達到時計數才會增加。 定義兩個（或多個）成功量度，之後才可以讓某個量度相依於另一個量度。 此 [!UICONTROL Add Dependency] 選項允許在已達到另一個成功量度或尚未達到時遞增成功量度。 若要新增相依性:<ul><li>新增其他量度後，按一下 [!UICONTROL Advanced Settings].</li><li>按一下 [!UICONTROL Add Dependency] 選項：</li><li>將需要的量度從左窗格拖曳到右窗格，然後按一下 [!UICONTROL Reached] 以切換設定 [!UICONTROL Reached] 和[!UICONTROL  Not Reached].</li><li>您可以在新增相依性之後加以編輯或移除。</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | 有三個選項可控制訪客達到目標量度後會發生什麼事:<ul><li>選取 [!UICONTROL Increment Count & Keep User in Activity] 以指定計數的遞增方式。</li><li>選取 [!UICONTROL Increment Count, Release User & Allow Reentry] 以指定使用者重新進入活動時看到的體驗。</li><li>選取 [!UICONTROL Increment Count, Release User & Bar from Reentry] 以指定使用者看到的內容，而非活動內容。</li></ul> |
| [!UICONTROL How will the count be incremented?] | 計數的遞增方式共有三個選項:<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

請參閱[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)以取得關於進階設定的詳細資訊。

## 其他中繼資料 {#section_2E8917BEFB954480A4206B9E9E917F80}

此 [!UICONTROL Other Metadata] 的區段 [!UICONTROL Goals & Settings] 頁面可讓您指定有關您的活動的任何資訊，這些資訊有助於您自己或其他團隊成員隨時掌握。 註釋窗格可調整大小。|

## 培訓影片

以下影片含有本文章探討之概念的詳細資訊。

### 活動設定(3:02) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於活動設定的資訊。

* 輸入活動的目標
* 設定活動的優先順序層級
* 排程活動開始和結束時間
* 新增報表的對象，以建立報表篩選器
* 輸入活動的備註

(https://video.tv.adobe.com/v/17381?captions=chi_hant)

### 建立A/B測試(8:36) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片示範活動設定如何在建立活動時配合三個步驟引導工作流程。在 5:30 開始討論目標和設定。

* 在 Adobe Target 中建立 A/B 活動
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
