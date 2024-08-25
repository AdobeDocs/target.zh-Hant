---
keywords: 報表；報表；報表；Experience Cloud解決方案；時區；貨幣；排除IP；預估收入成長；收入；收入成長；微調優先順序；微調
description: 使用 [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] 作為報表來源、指定預設時區和貨幣格式、新增要從報表中排除的IP位址等等。
title: 如何在 [!DNL Target]中設定報告？
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: ea9513c4310d13e1e7899aa7e228b4d7ecdf0748
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 22%

---

# 在[!DNL Target]中設定報告

設定一般設定，以用於套用至您整個[!DNL Target]帳戶的[!DNL Adobe Target]報告。

若要存取[!UICONTROL Reporting]設定頁面，請按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

您可以在此頁面指定下列設定：

* 用於報表的Adobe Experience Cloud解決方案
* 用於報告的時區
* 用於報告的貨幣
* 要從報告排除的IP位址
* 是否要在報表中顯示預估收入成長
* 是否要啟用微調優先順序

>[!NOTE]
>
>請注意，要排除設定的時區、貨幣和IP位址會套用至使用[!DNL Target]報表的活動。 這些設定不適用於使用[Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)或[!DNL Customer Journey Analytics]作為報表來源的活動。

![報告頁面](/help/main/administrating-target/assets/reporting.png)

## Reporting Cloud解決方案 {#solution}

設定可決定用於您的結果和報表資料的選項。

選取活動的報告來源： [!DNL Target]、[!DNL Adobe Analytics]或[!DNL Adobe Customer Journey Analytics]。 在建立活動時，您也可以選擇根據活動選取報表來源，作為三步驟引導式工作流程的一部分。

選擇報表來源時，請考量下列資訊:

* **[!DNL Adobe Target]**：如果在此將報表來源設為&#x200B;**[!DNL Target]**，便不允許建立或啟用使用[!DNL Analytics]或[!DNL Customer Journey Analytics]作為報表來源的活動。 您必須將報表來源變更為&#x200B;**[!UICONTROL Select per activity]**。
* **[!DNL Adobe Analytics]**：如果在此將報表來源設為&#x200B;**[!DNL Analytics]**，便不允許建立或啟用使用[!DNL Target]或[!DNL Customer Journey Analytics]作為報表來源的活動。 您必須將報表來源變更為&#x200B;**[!UICONTROL Select per activity]**。
* **[!DNL Adobe Customer Journey Analytics]**：如果在此將報表來源設為&#x200B;**[!DNL Customer Journey Analytics]**，便不允許建立或啟用使用[!DNL Target]或[!DNL Analytics]作為報表來源的活動。 您必須將報表來源變更為&#x200B;**[!UICONTROL Select per activity]**。
* **為每個活動選取**：如果在此將報表來源設為&#x200B;**[!UICONTROL Select per activity]**，您可以建立並啟用所選報表來源支援的活動。

在決定您的報表來源時，請考慮下列資訊：

* **[!DNL Analytics]**：如需使用[!DNL Analytics]作為報告來源(A4T)之支援活動的矩陣，請參閱&#x200B;*Adobe Analytics中的[支援的活動型別](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)作為Adobe Target (A4t)*&#x200B;的報告來源。

  無論選取的報表來源為何，都允許建立和啟用[!UICONTROL Automated Personalization] (AP)活動。 當您選擇[Adobe Analytics做為Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的報表來源時，[!UICONTROL Automated Personalization]活動不受支援。

  即使您指定[!DNL Analytics]作為您的報表來源，[!DNL Target]也會用作[!DNL Automated Personalization]活動的報表來源。

* **[!DNL Customer Journey Analytics]**：如需在[!DNL Customer Journey Analytics]中使用[!DNL Target]報告的支援活動的矩陣，請參閱&#x200B;[!DNL Adobe Customer Journey Analytics]*中*[!DNL Target]&#x200B;報告中的[支援的活動型別](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities)。

  無論選取的報表來源為何，[!UICONTROL Automated Personalization] (AP)、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動皆可建立及啟動。 當您選擇[Adobe Customer Journey Analytics做為報表來源](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)時，不支援這些活動。

  即使您指定[!DNL Customer Journey Analytics]作為您的報表來源，[!DNL Target]也會用作[!DNL Automated Personalization]活動的報表來源。

  如果您指定[!DNL Customer Journey Analytics]作為[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target]活動的報表來源，則可以使用[!DNL Target]或[!DNL Analytics]作為報表來源。

## 報表的時區

指定用於報告的時區。

## 報表的貨幣

指定用於報表的貨幣。

## 要從[!DNL Target]報告資料排除的IP

指定您要從報表資料排除的任何IP位址。 例如，排除內部公司地址是確保報表資料反映客戶在您網站上的互動的好方法。

在新行中輸入每個IP位址。

## 顯示預估提升收益

如果您為目標輸入貨幣值，您可以選擇顯示預估提升收入。 [!DNL Target]如果所有使用者要瞭解成功的藍圖， 可以估計您可能獲得的收入增益。預估提升度功能依預設會停用。

只有[!DNL Experience Cloud]個管理員使用者可以啟用或停用此功能。 如果已停用預估的提升度，則介面中不會出現對應的欄位。停用功能不會造成資料遺失，包括用於預估的資料。預估是根據收集的資料，而無論功能是否已啟用。

如需詳細資訊，請參閱 [預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 啟用微調優先順序

若為介於 0 到 999 的優先順序，則允許數值項目。

視您的設定而定，優先順序的UI和選項可能有所不同。 您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。

如果將多個活動指派至具有相同客群的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。
