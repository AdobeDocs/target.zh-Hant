---
keywords: 報表；報表；報表；experience cloud解決方案；時區；時區；貨幣；排除IP；預估收入成長；收入；收入成長；微調優先順序；微調
description: 使用 [!DNL Target] 或Adobe Analytics做為報表來源，指定預設時區和貨幣格式、新增要從報表中排除的IP位址等。
title: 如何在Target中設定報表？
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 31%

---

# 在Target中設定報表

設定一般設定以用於 [!DNL Adobe Target] 套用至整個報表的報表 [!DNL Target] 帳戶。

若要存取 [!UICONTROL 報告] 設定頁面，按一下 **[!UICONTROL 管理]** > **[!UICONTROL 報告].**

您可以在此頁面指定下列設定：

* 用於報表的Adobe Experience Cloud解決方案
* 用於報告的時區
* 用於報告的貨幣
* 要從報告排除的IP位址
* 是否要在報表中顯示預估收入成長
* 是否啟用微調優先順序

>[!NOTE]
>
>請注意，要排除設定的時區、貨幣和IP位址適用於使用的活動 [!DNL Target] 報告。 這些設定不適用於使用的活動 [Analytics for Target (A4T)] 作為報表來源(/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

![報告頁面](/help/main/administrating-target/assets/reporting.png)

## Reporting Cloud解決方案

設定可決定用於您的結果和報表資料的選項。

選取您的活動的報表來源，可以是 [!DNL Target] 或 [!DNL Adobe Analytics]. 您也可以選擇根據活動選取您的報表來源。

選擇報表來源時，請考量下列資訊:

* 如果在此將報表來源設為&#x200B;**[!DNL Target]**「」，便不得啟用將「」當作報表來源的活動。[!DNL Analytics]您必須將報表來源變更為 [!DNL Target] 將報表來源變更為 **[!UICONTROL 為每個活動選取]** 在 **[!UICONTROL 管理] > [!UICONTROL 報告]**.
* 如果報表來源設為 **[!DNL Analytics]** 在此，您無權啟動使用下列專案的活動： [!DNL Target] 作為報表來源(報表來源指定為 **[!UICONTROL 每個活動的目標])**. 您必須將報表來源變更為 [!DNL Analytics] 將報告引擎變更為 **[!UICONTROL 為每個活動選取]** 在 **[!UICONTROL 管理] > [!UICONTROL 報告]**.
* 如果報表來源設為 **[!UICONTROL 為每個活動選取]** 在這裡，您可以建立、啟用和停用所選報表來源支援的活動。 如需支援活動的矩陣，請參閱 [支援的活動型別](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 在 *Adobe Analytics作為Adobe Target (A4t)的報表來源*.
* [!UICONTROL Automated Personalization] (AP)無論選取的報表來源為何，都允許建立、啟用和停用活動。 當您選擇時，不支援Automated Personalization活動 [Adobe Analytics作為Adobe Target (A4T)的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md). 即使您指定 [!DNL Analytics] 作為您的報表來源， [!DNL Target] 會用作Automated Personalization活動的報表來源。 如需詳細資訊，請參閱 [支援的活動型別](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 在 *Adobe Analytics作為Adobe Target (A4t)的報表來源*.

## 報表的時區

指定用於報告的時區。

## 報表的貨幣

指定用於報表的貨幣。

## 要從中排除的IP [!DNL Target] 報告資料

指定您要從報表資料排除的任何IP位址。 例如，排除內部公司地址是確保報表資料反映客戶在您網站上的互動的良好方式。

在新行中輸入每個IP位址。

## 顯示預估提升收益

如果您為目標輸入貨幣值，則可以選擇顯示預估提升收入。 [!DNL Target]如果所有使用者要瞭解成功的藍圖， 可以估計您可能獲得的收入增益。預估提升度功能依預設會停用。

僅限 [!DNL Experience Cloud] 管理員使用者可以啟用或停用此功能。 如果已停用預估的提升度，則介面中不會出現對應的欄位。停用功能不會造成資料遺失，包括用於預估的資料。預估是根據收集的資料，而無論功能是否已啟用。

如需詳細資訊，請參閱 [預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 啟用微調優先順序

若為介於 0 到 999 的優先順序，則允許數值項目。

視您的設定而定，優先順序的 UI 和選項可能有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。

如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。
