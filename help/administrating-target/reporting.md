---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: 指定Adobe Target Visual Experience Composer(VEC)的一般設定、行動檢視埠設定和CSS選擇器，以設定Adobe Target Visual Experience Composer(VEC)。
title: 在Adobe Target中設定報表
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 9b57d5554884b06d278c3baef3b2c1d5f37bdeb5
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 33%

---


# 在Target中設定報表

設定一般設定，以用於套用至整個[!DNL Target]帳戶的[!DNL Adobe Target]報表。

要訪問[!UICONTROL Reporting]配置頁，請按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Reporting]。**

您可以在此頁面上指定下列設定：

* 用於報告的Adobe Experience Cloud解決方案
* 用於報告的時區
* 用於報告的貨幣
* 要排除在報告之外的IP位址
* 是否在報告中顯示預估的收入提升
* 是否啟用細粒度的優先順序

>[!NOTE]
>
>請注意，排除設定的時區、貨幣和IP位址會套用至使用[!DNL Target]報告的活動。 這些設定不適用於使用[Analytics for Target(A4T)]作為報告來源(/help/c-integrating-target-with-mac/a4t/a4t.md)的活動。

![報告頁面](/help/administrating-target/assets/reporting.png)

## Reporting Cloud解決方案

設定可決定用於您的結果和報表資料的選項。

選取您的活動的報表來源，可以是 [!DNL Target] 或 [!DNL Adobe Analytics]. 您也可以選擇根據活動選取您的報表來源。

選擇報表來源時，請考量下列資訊:

* 如果在此將報表來源設為&#x200B;**[!DNL Target]**「」，便不得啟用將「」當作報表來源的活動。[!DNL Analytics]您必須將活動中的報告源更改為[!DNL Target]，或將報告源更改為&#x200B;**[!UICONTROL 管理] >報告[!UICONTROL 中的**[!UICONTROL &#x200B;選擇每個活動&#x200B;]**。]**
* 如果報告源設定為&#x200B;**[!DNL Analytics]**，則不允許激活使用[!DNL Target]作為報告源的活動（報告源指定為&#x200B;**[!UICONTROL 每活動]目標）**。 您必須將活動中的報告源更改為[!DNL Analytics]，或將報告引擎更改為&#x200B;**[!UICONTROL 管理] >報告[!UICONTROL 中的**[!UICONTROL  Select per activity ]**。]**
* 如果將報表來源設為&#x200B;**[!UICONTROL Select per activity]**，您可以建立、啟用和停用所選報表來源支援的活動。 如需支援活動的矩陣，請參閱&#x200B;*Adobe Analytics中的[支援的活動類型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)作為Adobe Target(A4t)*&#x200B;的報表來源。
* [!UICONTROL 不論選取的報告來源為何] ，都允許自動個人化(AP)活動的建立、啟動和停用。當您選擇[Adobe Analytics作為Adobe Target(A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md)的報表來源時，不支援自動個人化活動。 即使您指定[!DNL Analytics]作為報告來源，[!DNL Target]也會用作「自動個人化」活動的報告來源。 如需詳細資訊，請參閱&#x200B;*Adobe Analytics中的[支援的活動類型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)作為Adobe Target(A4t)*&#x200B;的報表來源。

## 報告時區

指定用於報告的時區。

## 報告貨幣

指定用於報告的貨幣。

## 要從Target報表資料中排除的IP

指定要從報告資料中排除的任何IP位址。 例如，排除內部公司地址是確保報告資料反映網站上客戶互動的好方法。

在新行上輸入每個IP地址。

## 顯示預估提升收益

如果您輸入目標的貨幣值，您可以選擇顯示預計的收入提升。 [!DNL Target]如果所有使用者要瞭解成功的藍圖， 可以估計您可能獲得的收入增益。預估提升度功能依預設會停用。

只有[!DNL Experience Cloud]管理員使用者可以啟用或停用此功能。 如果已停用預估的提升度，則介面中不會出現對應的欄位。停用功能不會造成資料遺失，包括用於預估的資料。預估是根據收集的資料，而無論功能是否已啟用。

如需詳細資訊，請參閱 [預估收入中的提升度](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 啟用微調優先順序

若為介於 0 到 999 的優先順序，則允許數值項目。

視您的設定而定，優先順序的 UI 和選項可能有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。

如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。
