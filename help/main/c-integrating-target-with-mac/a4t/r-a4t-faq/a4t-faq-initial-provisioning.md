---
keywords: faq;常見問題集;analytics for target;a4t;佈建;adobe Experience Cloud
description: 查找有關為 [!DNL Target] (A4T)，用於使用Analytics報告 [!DNL Target] 活動。
title: 在何處可以找到有關A4T初始置備的資訊？
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 61%

---

# 初始佈建 - A4T 常見問題集

本主題包含有關設定的常見問題的答案 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。

## 如何設定多頁 A4T 活動?

若要實作基本多頁 A4T 使用案例:

* 在活動登錄URL/頁面上為「目標」和「分析」實現JavaScript庫。 實作兩種解決方案可拼接 Target 資料與每個訪客的 Analytics 資料。這些資料會保留在 Analytics 中，直到設為 90 天的預設到期期限過後為止。

* 針對網站上只有追蹤 Analytics 量度的其他頁面，請在這些頁面上實作 Analytics。不需要在這些頁面上實作 Target。系統會自動根據上個項目附加至訪客的 Target 資訊，將在這些頁面上擷取的 Analytics 量度，拼接至該使用者最初符合資格的 Target 活動。

## 如何判斷A4T是否在 [!DNL Target] 賬戶？ {#section_4437D284448F4313BF953D4B6EDBACA6}

定義 Analytics 活動時，在可以選取報表套裝之前，您同時需要 Analytics 使用者帳戶和 Target 使用者帳戶。必須依說明文件所述來設定您的使用者帳戶。請參閱[使用者權限需求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)。

在您是一個或多個Experience Cloud組的成員，這些test組有權訪問分析和目標，並且您有權訪問所有報告套件後，您應看到以下選項：使用分析建立A/B: **[!UICONTROL 建立活動]**。

如果發生佈建問題，請檢查 A4T 是否佈建正確。

## 報表套裝為何沒有載入? {#section_6CC8B2B3568A46C499895EB9811FDC2E}

如發生任何這些問題，請檢查下列事項:

* 確保分析帳戶和目標帳戶在Experience Cloud中連結。
* 一些客戶在同一Experience Cloud公司中使用多個Analytics公司登錄名。 如果您使用多次登錄，請確保您登錄的最後一個分析公司是與目標帳戶綁定以進行整合的公司。
* 如果已登入 Experience Cloud 數小時，Analytics 工作階段有時會到期。請登出再登入來再試一次。

## 在 Target 中為何看不到 Analytics 選項? {#section_EDD996AFB08B4DB196DD934BE55BF48D}

請參閱「為什麼我的報表套裝未載入」? 超過. 此問題的根本原因是相同的。

## 在 Analytics 中為何看不到 A4T 報表? {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

請參閱「為什麼我的報表套裝未載入」? above.此問題的根本原因是相同的。

## 為什麼我的報告 [!DNL Target] 空的？ {#section_3837104757464CB488C5A83014A669A1}

請參閱「為什麼我的報表套裝未載入」? above.此問題的根本原因是相同的。
