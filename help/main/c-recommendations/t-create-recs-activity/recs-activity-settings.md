---
keywords: Recommendations;設定;名稱;目標;優先順序;持續時間;報表設定;其他中繼資料
description: 瞭解如何進行設定，以說明和控制Adobe Target中的Recommendations活動。
title: 如何設定Recommendations活動設定？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 48%

---

# Recommendations 活動設定

可用於描述和控制設定的相關資訊 [!UICONTROL Recommendations] 中的活動 [!DNL Adobe Target].

![Recommendations 目標和設定頁面](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

以下小節說明 [!UICONTROL Recommendations] 活動。

## 名稱

提供將可幫助您和您的團隊識別活動的描述性名稱。

活動名稱中不允許下列字元:

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

如果您指定 [!UICONTROL Recommendations] 中已有另一個活動的活動名稱 [!UICONTROL Recommendations Classic]，新活動會以新名稱重新同步。 新名稱為原始名稱附加時間戳記的唯一名稱。這個新名稱會顯示在 [!DNL Target Standard/Premium] 和 [!UICONTROL Recommendations Classic] 中。

## 目標

(可選) 描述活動的目標。

## 優先順序

調整滑桿來決定優先順序層級。

如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。

## 持續時間

設定活動的持續時間。

活動可以在啟用後開始，或者您可以設定特定的日期和時間。同樣地，活動可以在停用時結束，或者您可以設定日期和時間。時間選擇器使用 24 小時時鐘，午夜為 00:00。時區會設為瀏覽器中設定的時區。若要使用不同的時區，請將您的瀏覽器設定為其他時區並重新啟動瀏覽器。

## 報表設定

* **報表來源：** 指定收集來源的解決方案資料：

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  如果您已在以下專案中指定報表解決方案： [帳戶設定](/help/main/administrating-target/reporting.md)，則會使用指定的解決方案，並且此設定不會顯示。

  為了讓報表保持一致，在活動上線後，您無法變更您的報表來源。

  **[!DNL Adobe Analytics]**：請參閱 [[!DNL Adobe Analytics] 做為的報表來源 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 以瞭解報告解決方案之間的差異和各自的優點。

  當選取 [!DNL Analytics] 做為的報表來源 [!DNL Target] (A4T)，您選取 [!DNL Analytics] 要接收的報表套裝 [!DNL Target] 活動資料。 若要這麼做，請先從下列任一 [!DNL Analytics] 您的帳戶繫結的公司，然後為活動選取適當的報表套裝。 僅限布建為可連線的報表套裝 [!DNL Target] 可供選取。 如果您沒有看到預期的報表套裝，請先嘗試登出並重新登入 [!DNL Adobe Experience Cloud] 再試一次。 如果清單中仍缺少報表套裝，請聯絡 [客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

  [!DNL Analytics for Target] (A4T)需要追蹤伺服器才能正確回報結果。 預設追蹤伺服器會顯示在 [!UICONTROL Tracking Server] 欄位。 如果您使用多個追蹤伺服器，請確定您在此欄位中包含正確的追蹤伺服器。 另請參閱 [使用Analytics追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 以取得詳細資訊。

  **[!DNL Adobe Customer Journey Analytics]**：請參閱 [[!DNL Target] 報告位置 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) 以取得關於以下各項整合的詳細資訊： [!DNL Adobe Customer Journey Analytics] 和 [!DNL Target].

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
