---
keywords: faq;常見問題集;analytics for target;a4t;佈建;adobe Experience Cloud
description: 尋找有關為 [!DNL Target] (A4T), which lets you use Analytics reporting for [!DNL Target] 活動布建Analytics的常見問題的解答。
title: 我可以在哪裡找到有關A4T初始布建的資訊？
feature: 目標分析 (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 66%

---

# 初始佈建 - A4T 常見問題集

本主題包含有關將[!DNL Adobe Analytics]設為[!DNL Adobe Target](A4T)報告來源的常見問題的解答。

## 如何設定多頁 A4T 活動?

若要實作基本多頁 A4T 使用案例:

* 在活動登陸 URL/頁面上，實作同時適用於 Target (at.js 或 mbox.js) 和 Analytics 的 JavaScript 資料庫。實作兩種解決方案可拼接 Target 資料與每個訪客的 Analytics 資料。這些資料會保留在 Analytics 中，直到設為 90 天的預設到期期限過後為止。

* 針對網站上只有追蹤 Analytics 量度的其他頁面，請在這些頁面上實作 Analytics。不需要在這些頁面上實作 Target。系統會自動根據上個項目附加至訪客的 Target 資訊，將在這些頁面上擷取的 Analytics 量度，拼接至該使用者最初符合資格的 Target 活動。

## 如何判斷我的[!DNL Target]帳戶是否啟用A4T?{#section_4437D284448F4313BF953D4B6EDBACA6}

定義 Analytics 活動時，在可以選取報表套裝之前，您同時需要 Analytics 使用者帳戶和 Target 使用者帳戶。必須依說明文件所述來設定您的使用者帳戶。請參閱[使用者權限需求](/help/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)。

您是一或多個Experience Cloud群組的成員，可存取Analytics和Target，而且您可存取所有報表套裝，您應在&#x200B;**[!UICONTROL 「建立活動]**」下看到使用Analytics建立A/B測試的選項。

如果發生佈建問題，請檢查 A4T 是否佈建正確。

## 報表套裝為何沒有載入?  {#section_6CC8B2B3568A46C499895EB9811FDC2E}

如發生任何這些問題，請檢查下列事項:

* 請確定您的Analytics和Target帳戶已連結至Experience Cloud。
* 有些客戶在同一家Experience Cloud公司中使用多個Analytics公司登入。 如果您使用多次登入，請確定您最後登入的Analytics公司是系結至整合的Target帳戶的公司。
* 如果已登入 Experience Cloud 數小時，Analytics 工作階段有時會到期。請登出再登入來再試一次。

## 在 Target 中為何看不到 Analytics 選項?  {#section_EDD996AFB08B4DB196DD934BE55BF48D}

請參閱「為什麼我的報表套裝未載入」? 超過. 此問題的根本原因是相同的。

## 在 Analytics 中為何看不到 A4T 報表?  {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

請參閱「為什麼我的報表套裝未載入」? above.此問題的根本原因是相同的。

## 為什麼[!DNL Target]中的報表是空的？{#section_3837104757464CB488C5A83014A669A1}

請參閱「為什麼我的報表套裝未載入」? above.此問題的根本原因是相同的。
