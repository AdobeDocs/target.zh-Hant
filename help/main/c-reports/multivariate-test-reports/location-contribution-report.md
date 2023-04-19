---
keywords: mvt;多變數測試;位置貢獻報表
description: 了解如何使用「位置貢獻」報表進行Adobe [!DNL Target] [!UICONTROL 體驗鎖定] 顯示每個元素和每個選件之效能的活動。
title: 如何使用 [!UICONTROL 位置貢獻] 報表 [!UICONTROL 多變數測試] 活動？
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: 6f70ff18cfbee5c02e6bb2bd345acbd2e1b2006f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL 位置貢獻報表 (MVT)]

此 [!UICONTROL 位置貢獻] 報表會顯示每個元素和每個選件的效能。

報表頂端會顯示報表中使用的量度、開始和結束日期，以及對象。您可以變更任何係數。

>[!NOTE]
>
>使用時，請記住下列資訊 [!UICONTROL 位置貢獻] 報告：
>
>* 對象和量度選擇器僅在 [!DNL Analytics] 會作為報表來源(A4T)。
>
>* 資料 [!UICONTROL 位置貢獻] 報表會從中擷取 [!DNL Target] 後端，即使活動設定為使用 [!UICONTROL Analytics作為報表來源] (A4T)。
>
>* 資料 [!UICONTROL 位置貢獻] 即使在中定義了不同的預設環境，系統仍會為「生產」環境擷取報表 [!DNL Target] 帳戶層級。


此 [!UICONTROL 位置貢獻] 報表包含兩個表格。

第一個表格顯示每一個元素的相對影響。此表格顯示已新增選件的元素中，哪些元素會產生最多的轉換。

![位置貢獻報表在Adobe Target](/help/main/c-reports/assets/locationcontributiontop.png)

第二個表格提供選件層級報表。這指出每一個元素中每一個選件的轉換率、提升度和信賴度。此表格可協助您判斷哪些選件最成功。 第二欄顯示選件的所選量度 (轉換率、RPV、AOV、訂購或參與量度) 的值，以及一個標準化。

![位置貢獻報表在Adobe Target](/help/main/c-reports/assets/locationcontributionbottom.png)

## 訓練影片：建立MVT測試 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片示範如何使用 Target 三個步驟引導工作流程來建立多變數測試。8:45 開始說明「位置貢獻」報表。

>[!VIDEO](https://video.tv.adobe.com/v/17395)
