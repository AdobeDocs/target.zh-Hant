---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: 指定Adobe Target Visual Experience Composer(VEC)的一般設定、行動檢視埠設定和CSS選擇器，以設定Adobe Target Visual Experience Composer(VEC)。
title: 在Adobe Target中設定報表
topic: Standard
translation-type: tm+mt
source-git-commit: 44d9024cb9c1f6a1e28845f9545fed0d56fe176a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 在Target中設定報表

設定一般設定，以用於套用至整個帳戶的Target報 [!DNL Target] 告。

>[!NOTE]
>
>本主題中的資訊已更新，讓您在Target Standard/Premium 20.6.1版（2020年7月）即將推出的UI變更中搶先登峰造極。 本主題中顯示的大部分資訊都適用於目前的使用者介面； 不過，選項可能位於稍微不同的位置。

若要存取「報 [!UICONTROL 告] 」設定頁面，請按一 **[!UICONTROL 下「管理]** > **[!UICONTROL 報告]」。**

您可以在此頁面上指定下列設定：

* 用於報告的Adobe Experience Cloud解決方案
* 用於報告的時區
* 用於報告的貨幣
* 要排除在報告之外的IP位址
* 是否在報告中顯示預估的收入提升
* 是否啟用細粒度的優先順序

![報告頁面](/help/administrating-target/assets/reporting.png)

## Reporting Cloud解決方案

設定可決定用於您的結果和報表資料的選項。

選取您的活動的報表來源，可以是 [!DNL Target] 或 Adobe Analytics。您也可以選擇根據活動選取您的報表來源。

選擇報表來源時，請考量下列資訊:

* 無論選取的報表來源為何，均可建立、啟用和停用[!UICONTROL 「自動分配」]、[!UICONTROL 「自動鎖定目標」]和[!UICONTROL 「自動個人化」] (AP) 活動。選擇 [Adobe Analytics 當作 Adobe Target (A4T) 的報表來源](/help/c-integrating-target-with-mac/a4t/a4t.md)時，不支援前述活動類型。即便指定 Analytics 當作報表來源，前述活動類型也會使用 [!DNL Target] 當作報表來源。
* 如果在此將報表來源設為「Analytics」，便不得啟用將 [!DNL Target] 作為報表來源的活動 (根據活動，報表來源指定為 Target)。您必須在活動中將報表來源變更為「Analytics」，或在「設定 > 偏好設定」中將報表引擎變更為「根據活動選取」。
* 如果在此將報表來源設為[!DNL Target]「」，便不得啟用將「Analytics」當作報表來源的活動。您必須在活動中將報表來源變更為[!DNL Target]「」，或在「設定 > 偏好設定」中將報表來源變更為「根據活動選取」。
* 如果在此將報表來源設為「根據活動選取」，您就可建立、啟用和停用所選報表來源支援的活動。如需支援活動的表格，請參閱 [](/help/c-integrating-target-with-mac/a4t/a4t.md)Adobe Analytics 作為 Adobe Target (A4T) 的報表來源。
* 從「A/B 手動」切換為[!UICONTROL 「自動分配」]或[!UICONTROL 「自動鎖定目標」]時，如果[!UICONTROL 「自動分配」]或[!UICONTROL 「自動鎖定目標」]活動不支援「A/B 手動」活動的報表來源，所有量度和報表對象都會消失。

## 報告時區

指定用於報告的時區。

## 報告貨幣

指定用於報告的貨幣。

## 要從Target報表資料中排除的IP

指定要從報告資料中排除的任何IP位址。 例如，排除內部公司地址是確保報告資料反映網站上客戶互動的好方法。

在新行上輸入每個IP地址。

## 顯示預估提升收益

如果您輸入目標的貨幣值，您可以選擇顯示預計的收入提升。 [!DNL Target]如果所有使用者要瞭解成功的藍圖， 可以估計您可能獲得的收入增益。預估提升度功能依預設會停用。

只有 Experience Cloud 管理員使用者可以啟用或停用此功能。如果已停用預估的提升度，則介面中不會出現對應的欄位。停用功能不會造成資料遺失，包括用於預估的資料。預估是根據收集的資料，而無論功能是否已啟用。

如需詳細資訊，請參閱 [預估收入中的提升度](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 啟用微調優先順序

若為介於 0 到 999 的優先順序，則允許數值項目。

視您的設定而定，優先順序的 UI 和選項可能有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。

如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。
