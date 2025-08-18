---
keywords: 推薦;設定;名稱;目標;優先順序;持續時間;報表設定;其他中繼資料
description: 瞭解如何進行設定，以說明和控制Adobe Target中的Recommendations活動。
title: 如何設定Recommendations活動設定？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 43%

---

# 推薦活動設定

關於您可以用來描述和控制[!UICONTROL Recommendations]中[!DNL Adobe Target]活動的設定資訊。

以下各節說明[!UICONTROL Recommendations]活動可用的設定。

## 名稱

按一下「更多動作」圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallListVert.svg) ），然後按一下「**[!UICONTROL Rename]**」以提供描述性名稱，協助您和您的團隊識別活動。

活動名稱中不允許下列字元:

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

如果您指定的[!UICONTROL Recommendations]活動名稱是[!UICONTROL Recommendations Classic]中另一個已存在活動的名稱，則會以新名稱重新同步新活動。 新名稱為原始名稱附加時間戳記的唯一名稱。這個新名稱會顯示在 [!DNL Target Standard/Premium] 和 [!UICONTROL Recommendations Classic] 中。

## 目標

(可選) 描述活動的目標。

## 優先順序

調整滑桿來決定優先順序層級。

如果將多個活動指派至具有相同客群的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。

## 持續時間

設定活動的持續時間。

活動可以在啟用後開始，或者您可以設定特定的日期和時間。同樣地，活動可以在停用時結束，或者您可以設定日期和時間。時間選擇器使用24小時時鐘，00:00為午夜。 時區會設為瀏覽器中設定的時區。若要使用不同的時區，請將您的瀏覽器設定為其他時區並重新啟動瀏覽器。

## 報表設定

* **報告Source：**&#x200B;指定收集自下列專案的解決方案資料：

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  如果已在您的[帳戶設定](/help/main/administrating-target/reporting.md)中指定報表解決方案，則會使用指定的解決方案，而且此設定不會顯示。

  為了讓報表保持一致，在活動上線後，您無法變更您的報表來源。

  **[!DNL Adobe Analytics]**：檢視[[!DNL Adobe Analytics] 作為 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的報告來源，以瞭解報告解決方案之間的差異和各自的優點。

  選取[!DNL Analytics]做為[!DNL Target] (A4T)的報告來源時，請選取[!DNL Analytics]報告套裝來接收[!DNL Target]活動資料。 若要這麼做，請先從您帳戶繫結的[!DNL Analytics]家公司中選擇任一，接著為該活動選取適當的報表套裝。 只有布建為連線至[!DNL Target]的報表套裝才可供選取。 如果您沒有看到預期的報表套裝，請先嘗試登出並重新登入[!DNL Adobe Experience Cloud]以重試。 如果清單中仍缺少報表套裝，請連絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

  [!DNL Analytics for Target] (A4T)需要追蹤伺服器才能正確回報結果。 預設追蹤伺服器會顯示在[!UICONTROL Tracking Server]欄位中。 如果您使用多個追蹤伺服器，請確定您在此欄位中包含正確的追蹤伺服器。 如需詳細資訊，請參閱[使用Analytics追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

  **[!DNL Adobe Customer Journey Analytics]**：如需有關[[!DNL Target] 與 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)之間整合的詳細資訊，請參閱[!DNL Adobe Customer Journey Analytics]在[!DNL Target]中報告。

* **目標量度:** 選取判斷活動是否成功的成功量度。
* **其他度量:** 設定要在您的報表中使用的其他成功度量。
* **報表對象:** 定義篩選報表時可以使用的對象。

## 其他中繼資料

輸入關於您的活動的備註。

## 訓練影片：活動設定(3:02) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於活動設定的資訊。

* 輸入活動的目標
* 設定活動的優先順序層級
* 排程活動開始和結束時間
* 新增報表的對象，以建立報表篩選器
* 輸入活動的備註

>[!VIDEO](https://video.tv.adobe.com/v/17381)
