---
keywords: 報告；報告；體驗雲解決方案；時區；時區；貨幣；排除IPs；估計收入提升；收入提升；細粒度優先順序；細粒度
description: 使用 [!DNL Target] 或Adobe Analytics作為報告源，指定預設時區和貨幣格式，添加要從報告中排除的IP地址，等等。
title: 如何在目標中配置報告？
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 31%

---

# 在目標中配置報告

配置要在中使用的常規設定 [!DNL Adobe Target] 適用於您整個 [!DNL Target] 帳戶。

訪問 [!UICONTROL 報告] 配置頁，按一下 **[!UICONTROL 管理]** > **[!UICONTROL 報告]。**

可以在此頁上指定以下設定：

* 用於報告的Adobe Experience Cloud解決方案
* 用於報告的時區
* 用於報告的幣種
* 要從報告中排除的IP地址
* 是否在報告中顯示收入的估計增長
* 是否啟用細粒度優先順序

>[!NOTE]
>
>請注意，要排除設定的時區、貨幣和IP地址應用於使用 [!DNL Target] 報告。 這些設定不適用於使用 [目標分析(A4T)] 作為報告來源(/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

![報告頁](/help/main/administrating-target/assets/reporting.png)

## 報告雲解決方案

設定可決定用於您的結果和報表資料的選項。

選取您的活動的報表來源，可以是 [!DNL Target] 或 [!DNL Adobe Analytics]. 您也可以選擇根據活動選取您的報表來源。

選擇報表來源時，請考量下列資訊:

* 如果在此將報表來源設為&#x200B;**[!DNL Target]**「」，便不得啟用將「」當作報表來源的活動。[!DNL Analytics]必須將報告源更改為 [!DNL Target] 或將報告源更改為 **[!UICONTROL 按活動選擇]** 在 **[!UICONTROL 管理] > [!UICONTROL 報告]**。
* 如果報告源設定為 **[!DNL Analytics]** 此處，不允許您激活使用 [!DNL Target] 作為報告源(報告源指定為 **[!UICONTROL 每個活動的目標])**。 必須將報告源更改為 [!DNL Analytics] 或將報告引擎更改為 **[!UICONTROL 按活動選擇]** 在 **[!UICONTROL 管理] > [!UICONTROL 報告]**。
* 如果報告源設定為 **[!UICONTROL 按活動選擇]** 在此，您可以建立、激活和停用選定報告源支援的活動。 有關受支援活動的清單，請參見 [支援的活動類型](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 在 *Adobe Analytics為Adobe Target的報告來源(A4t)*。
* [!UICONTROL Automated Personalization] (AP)活動建立、激活和停用是允許的，而不管選擇的報告源是什麼。 選擇時不支援Automated Personalization活動 [Adobe Analytics為Adobe Target(A4T)的報告來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。 即使您指定 [!DNL Analytics] 作為你的報告來源， [!DNL Target] 用作Automated Personalization活動的報告來源。 有關詳細資訊，請參見 [支援的活動類型](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 在 *Adobe Analytics為Adobe Target的報告來源(A4t)*。

## 報告時區

指定用於報告的時區。

## 報告幣種

指定用於報告的幣種。

## 要從中排除的IP [!DNL Target] 報告資料

指定要從報告資料中排除的任何IP地址。 例如，排除公司內部地址是確保報告資料反映您網站上客戶互動的良好方法。

在新行上輸入每個IP地址。

## 顯示預估提升收益

如果為目標輸入貨幣值，則可以選擇顯示估計的收入增幅。 [!DNL Target]如果所有使用者要瞭解成功的藍圖， 可以估計您可能獲得的收入增益。預估提升度功能依預設會停用。

僅 [!DNL Experience Cloud] 管理員用戶可以啟用或禁用此功能。 如果已停用預估的提升度，則介面中不會出現對應的欄位。停用功能不會造成資料遺失，包括用於預估的資料。預估是根據收集的資料，而無論功能是否已啟用。

如需詳細資訊，請參閱 [預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 啟用微調優先順序

若為介於 0 到 999 的優先順序，則允許數值項目。

視您的設定而定，優先順序的 UI 和選項可能有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。

如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。
