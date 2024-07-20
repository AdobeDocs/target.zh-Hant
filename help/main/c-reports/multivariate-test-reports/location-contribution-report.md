---
keywords: mvt;多變數測試;位置貢獻報表
description: 瞭解如何針對Adobe [!DNL Target] [!UICONTROL Experience Targeting]活動使用位置貢獻報表，以顯示每個元素和每個選件的效能。
title: 如何將[!UICONTROL Location Contribution]報告用於[!UICONTROL Multivariate Test]活動？
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: 6f70ff18cfbee5c02e6bb2bd345acbd2e1b2006f
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 39%

---

# [!UICONTROL Location Contribution]報告(MVT)

[!UICONTROL Location Contribution]報表顯示每個元素和每個選件的效能。

報表頂端會顯示報表中使用的量度、開始和結束日期，以及對象。您可以變更任何係數。

>[!NOTE]
>
>使用[!UICONTROL Location Contribution]報告時，請記住下列資訊：
>
>* 對象和量度選擇器僅在將[!DNL Analytics]用作報表來源(A4T)時才可用。
>
>* 已從[!DNL Target]後端擷取[!UICONTROL Location Contribution]報告的資料，即使活動設定為使用[!UICONTROL Analytics as the reporting source] (A4T)亦然。
>
>* 即使在[!DNL Target]帳戶層級定義了不同的預設環境，「生產」環境也會擷取[!UICONTROL Location Contribution]報告的資料。

[!UICONTROL Location Contribution]報告包含兩個資料表。

第一個表格顯示每一個元素的相對影響。此表格顯示您已新增選件的元素中，哪些元素的轉換次數最多。

![Adobe Target中的位置貢獻報表](/help/main/c-reports/assets/locationcontributiontop.png)

第二個表格提供選件層級報表。這指出每一個元素中每一個選件的轉換率、提升度和信賴度。此表格可協助您判斷哪些選件最成功。 第二欄顯示選件的所選量度 (轉換率、RPV、AOV、訂購或參與量度) 的值，以及一個標準化。

![Adobe Target中的位置貢獻報表](/help/main/c-reports/assets/locationcontributionbottom.png)

## 訓練影片：建立MVT測試![教學課程徽章](/help/main/assets/tutorial.png)

此影片示範如何使用 Target 三個步驟引導工作流程來建立多變數測試。8:45 開始說明「位置貢獻」報表。

>[!VIDEO](https://video.tv.adobe.com/v/17395)
