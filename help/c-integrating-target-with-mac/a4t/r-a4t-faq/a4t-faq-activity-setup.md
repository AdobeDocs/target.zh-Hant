---
keywords: faq;frequently asked questions;analytics for target;a4T;activity setup
description: 此主題包含經常詢問關於活動設定和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。
title: 活動設定 - A4T 常見問題集
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 89%

---


# 活動設定 - A4T 常見問題集{#activity-settings-a-t-faq}

此主題包含經常詢問關於活動設定和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。

## Analytics 作為報表來源 (A4T) 時支援哪些活動類型?{#section_5E4F58CD25A5424E869E6FE0803968EF}

如需完整清單，請參閱 [Adobe Analytics 作為 Adobe Target (A4T) 的報表來源](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)中的「支援的活動類型」。

## 我剛才建立了活動。為何沒看到任何資料進入? {#section_9F8092BE4225442896F926540292F221}

建立活動時，Target 會將分類檔案傳送至 Analytics。雖然 Analytics 會擷取並處理資料，但要等到分類檔案更新之後，資料才會出現在報表中。這可能需要 24 小時。如果 48 小時之後沒看到資料，請[聯絡客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。或者，如果您已知將會啟動活動，您可以提前幾天建立活動，在儲存活動時即會傳送分類。於是，啟動後資料即會立即出現在報表中。請注意，Analytics 中處理資料需要 45-90 分鐘。

## 建立新活動時，為何無法選取 Analytics 作為報表來源? {#section_9F4F69C3085F4C2480AF439127EB27CD}

您可以在「管理」中變更「報表設定」選項。

1. In Adobe Target, click **[!UICONTROL Administration]**.
1. 在&#x200B;**[!UICONTROL 「用於報表的 Experience Cloud 解決方案」]**&#x200B;下拉式清單中，按一下&#x200B;**[!UICONTROL 「為每個活動選取」]**。

![](assets/select-per-activity.png)

**[!UICONTROL 「目標與設定」]**&#x200B;畫面中會啟用&#x200B;**[!UICONTROL 「報表來源」下拉式清單，以供您建立和編輯活動。]**

To always use Analytics as the reporting source, select **[!UICONTROL Adobe Analytics]** from the drop-down list in Administration.
