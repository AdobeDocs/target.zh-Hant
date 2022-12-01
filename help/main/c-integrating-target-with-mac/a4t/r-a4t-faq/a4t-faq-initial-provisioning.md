---
keywords: faq;常見問題集;analytics for target;a4t;佈建;adobe Experience Cloud
description: 尋找經常詢問關於布建Analytics的問題的解答 [!DNL Target] (A4T)，這可讓您對 [!DNL Target] 活動。
title: 我可以在哪裡找到A4T初始布建的相關資訊？
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 47%

---

# 初始佈建 - A4T 常見問題集

本主題包含經常詢問關於布建問題的回答 [!DNL Adobe Analytics] 作為的報表來源 [!DNL Adobe Target] (A4T)。

## 如何設定多頁 A4T 活動?

+++若要實作基本多頁A4T使用案例，請回答：

* 在活動登陸URL/頁面上，為Target和Analytics實作JavaScript程式庫。 實作兩種解決方案可拼接 Target 資料與每個訪客的 Analytics 資料。這些資料會保留在 Analytics 中，直到設為 90 天的預設到期期限過後為止。

* 針對網站上只有追蹤 Analytics 量度的其他頁面，請在這些頁面上實作 Analytics。不需要在這些頁面上實作 Target。系統會自動根據上個項目附加至訪客的 Target 資訊，將在這些頁面上擷取的 Analytics 量度，拼接至該使用者最初符合資格的 Target 活動。

+++

## 如何判斷我的 [!DNL Target] 帳戶？ {#section_4437D284448F4313BF953D4B6EDBACA6}

+++答案定義Analytics活動時，在可以選取報表套裝之前，您同時需要Analytics使用者帳戶和Target使用者帳戶。 必須依說明文件所述來設定您的使用者帳戶。請參閱[使用者權限需求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)。

如果您是可存取Analytics和Target的Experience Cloud群組的成員，且擁有所有報表套裝的存取權，您應會在下方看到使用Analytics建立A/B測試的選項 **[!UICONTROL 建立活動]**.

如果發生佈建問題，請檢查 A4T 是否佈建正確。

+++

## 報表套裝為何沒有載入? {#section_6CC8B2B3568A46C499895EB9811FDC2E}

+++回答如果發生以下任何問題，請檢查：

* 請確定您的Analytics和Target帳戶已在Experience Cloud中連結。
* 有些客戶在同一家Experience Cloud公司中使用多個Analytics公司登入。 如果您使用多個登入，請確定您最後登入的Analytics公司是系結至整合的Target帳戶的公司。
* 如果已登入 Experience Cloud 數小時，Analytics 工作階段有時會到期。請登出再登入來再試一次。

+++

## 在 Target 中為何看不到 Analytics 選項? {#section_EDD996AFB08B4DB196DD934BE55BF48D}

+++答案請參閱「為何我的報表套裝未載入？」 超過. 此問題的根本原因是相同的。

+++

## 在 Analytics 中為何看不到 A4T 報表? {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

+++答案請參閱「為何我的報表套裝未載入？」 above.此問題的根本原因是相同的。

+++

## 我的報表為何位於 [!DNL Target] 空的？ {#section_3837104757464CB488C5A83014A669A1}

+++答案請參閱「為何我的報表套裝未載入？」 above.此問題的根本原因是相同的。

+++
