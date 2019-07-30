---
description: 關於 Target 中報表常見問題的清單。
keywords: 疑難排解;量度差異;FAQ;報表
seo-description: Adobe Target中報告報告的常見問題清單。
seo-title: Adobe Target的報告常見問答集
solution: Target
title: 報表常見問題集
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: a6f2eceaddf67653b36a1687ba071f7226169516

---


# 報表常見問題集{#reporting-faq}

關於 [!DNL Target] 中報表常見問題的清單。

## Why do my [!UICONTROL Experience Targeting] (XT) reports contain metrics for control experiences?

XT活動應一律具有控制體驗。If you are using an XT activity in a similar manner to an [!UICONTROL A/B Test] activity, which is a fairly common scenario, the control experience data is useful. 如果您發現報表中沒有有用的資料，可以忽略控制體驗資料。

## Why are the number of visits lower in [!DNL Target] than in other [!DNL Adobe Experience Cloud] solutions? {#section_7E626FDB417E41B8B58BBF30FB207409}

由於下列原因，[!DNL Target] 所報告的量度數字 (例如造訪) 一律低於其他 [!DNL Experience Cloud] 解決方案中所報告的數字:

* [!DNL Target] 只會計算活動合格訪客的造訪次數。其他解決方案會針對顯示頁面的訪客來計算造訪次數，而不在乎將他們帶到頁面的活動。
* 有時不同的活動會在同一位置競爭(互斥)。因此，訪客在網頁上會看到不同內容，因而影響 [!DNL Target] 所報告的量度數字。

## 活動的報表為何沒有資料可用? {#section_E4722F6445884130951DF79981C8289B}

If an activity's content was successfully delivered to users but its report contains no data, ensure that you have the correct environment ([host group](/help/administrating-target/hosts.md)) selected in the report's settings.

如果您已選取開發環境，可能會看到下列錯誤訊息:「沒有可用於所選報表設定的資料」。

若要變更活動報表的環境:

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，從清單中按一下所需的活動，然後按一下&#x200B;**「報表」]標籤。[!UICONTROL **
1. 按一下齒輪圖示進行報表設定。

   ![A/B設定對話框](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >The gear icon is not available for [!UICONTROL Automated Personalization] (AP) reports.

1. 從&#x200B;**[!UICONTROL 「環境」]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 「生產」]**。

   如果您選取了開發環境，則可能沒有報表資料可用。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

如需環境的詳細資訊，請參閱[主機](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。
