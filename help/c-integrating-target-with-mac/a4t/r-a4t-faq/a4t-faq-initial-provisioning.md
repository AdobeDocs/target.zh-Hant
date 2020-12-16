---
keywords: faq;frequently asked questions;analytics for target;a4t;provisioning;provisioning;adobe Experience Cloud
description: 此主題包含經常詢問關於佈建 Analytics 做為 Target 報表來源 (A4T) 問題的回答。
title: 初始佈建 - A4T 常見問題集
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 100%

---


# 初始佈建 - A4T 常見問題集{#initial-provisioning-a-t-faq}

此主題包含經常詢問關於佈建 Analytics 做為 Target 報表來源 (A4T) 問題的回答。

## 如何設定多頁 A4T 活動?

若要實作基本多頁 A4T 使用案例:

* 在活動登陸 URL/頁面上，實作同時適用於 Target (at.js 或 mbox.js) 和 Analytics 的 JavaScript 資料庫。實作兩種解決方案可拼接 Target 資料與每個訪客的 Analytics 資料。這些資料會保留在 Analytics 中，直到設為 90 天的預設到期期限過後為止。

* 針對網站上只有追蹤 Analytics 量度的其他頁面，請在這些頁面上實作 Analytics。不需要在這些頁面上實作 Target。系統會自動根據上個項目附加至訪客的 Target 資訊，將在這些頁面上擷取的 Analytics 量度，拼接至該使用者最初符合資格的 Target 活動。

## 如何判斷我的 Target 帳戶是否已啟用 A4T? {#section_4437D284448F4313BF953D4B6EDBACA6}

定義 Analytics 活動時，在可以選取報表套裝之前，您同時需要 Analytics 使用者帳戶和 Target 使用者帳戶。必須依說明文件所述來設定您的使用者帳戶。請參閱[使用者權限需求](/help/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)。

只要您是可存取 Analytics 和 Target 的 Experience Cloud 群組的成員，且擁有所有報表套裝的存取權，您在&#x200B;**[!UICONTROL 「建立活動」]**&#x200B;下即會看見使用 Analytics 建立 A/B 測試的選項。

如果發生佈建問題，請檢查 A4T 是否佈建正確。

## 報表套裝為何沒有載入?  {#section_6CC8B2B3568A46C499895EB9811FDC2E}

如發生任何這些問題，請檢查下列事項:

* 確定 Experience Cloud 中已連結您的 Analytics 和 Target 帳戶。
* 如果您在相同體驗 Experience Cloud 公司使用多個 Analytics 公司登入，請確定您上次登入的 Analytics 公司已繫結至整合的 Target 帳戶。
* 如果已登入 Experience Cloud 數小時，Analytics 工作階段有時會到期。請登出再登入來再試一次。

## 在 Target 中為何看不到 Analytics 選項?  {#section_EDD996AFB08B4DB196DD934BE55BF48D}

請參閱「為什麼我的報表套裝未載入」? above.此問題的根本原因是相同的。

## 在 Analytics 中為何看不到 A4T 報表?  {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

請參閱「為什麼我的報表套裝未載入」? above.此問題的根本原因是相同的。

## 我的報表在 Target 中為何空白?  {#section_3837104757464CB488C5A83014A669A1}

請參閱「為什麼我的報表套裝未載入」? above.此問題的根本原因是相同的。
