---
keywords: 推薦;設定;名稱;目標;優先順序;持續時間;報表設定;其他中繼資料
description: 瞭解如何進行設定，以說明和控制Adobe Target中的Recommendations活動。
title: 如何設定Recommendations活動設定？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
TQID: 'https://experienceleague.adobe.com/pfMAvl6MmLCtH3PZfOR4Ve-WFIc3e2iN2Bh-cIzjeC0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 13%
---
# 推薦活動設定 {#recs-activity-settings}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解描述和控制[!DNL Adobe Target]中[!DNL Recommendations]活動的設定。

>[!ENDSHADEBOX]

活動設定會識別[!DNL Recommendations]活動、控制其顯示的時間和位置，並定義其結果的報告方式。

## 名稱

按一下「更多動作」圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallListVert.svg) ），然後按一下「**[!UICONTROL 重新命名]**」，為活動提供有助於識別它的描述性名稱。

活動名稱中不允許下列字元： `/`、`?`、`#`、`:`、`=`、`+`、`-`和`@`。

如果[!UICONTROL Recommendations Classic]中的另一個活動已存在[!DNL Recommendations]活動的名稱，則會以新名稱重新同步新活動。 新名稱是原始名稱，會附加時間戳記，使其成為唯一名稱。 它會顯示在[!DNL Target Standard/Premium]和[!UICONTROL Recommendations Classic]中。

## 目標

(可選) 描述活動的目標。

## 優先順序

調整滑桿以設定優先等級。

當多個活動指派至具有相同對象的相同位置時，就會使用優先順序。 如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。

## 持續時間

設定活動的持續時間。

活動可以在啟動時開始，或在特定的日期和時間開始。 同樣地，它可以在停用時或在特定日期和時間結束。

時間選擇器使用 24 小時時鐘，午夜為 00:00。 時區是瀏覽器中設定的時區。 若要使用不同的時區，請將瀏覽器設定為該時區，然後重新啟動瀏覽器。

## 報表設定

以下設定會定義活動結果的報告方式。

* **[!UICONTROL 報告Source]：**&#x200B;指定資料收集來源的解決方案： [!DNL Adobe Target]、[!DNL Adobe Analytics]或[!DNL Adobe Customer Journey Analytics]。

  如果在[帳戶設定](/help/main/administrating-target/reporting.md)中指定了報表解決方案，則會使用該解決方案，而且此設定不會顯示。 為保持報表的一致性，在活動上線後無法變更報表來源。

  **[!DNL Adobe Analytics]**：請參閱[[!DNL Adobe Analytics] 作為 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的報告來源，以瞭解報告解決方案之間的差異與各自的優點。 如需選取[!DNL Analytics]報表套裝和追蹤伺服器，請參閱[報告Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source)。

  **[!DNL Adobe Customer Journey Analytics]**：如需有關[!DNL Adobe Customer Journey Analytics]與[!DNL Target]之間整合的詳細資訊，請參閱[[!DNL Target] 在 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中報告。

* **[!UICONTROL 目標量度]：**&#x200B;選取判斷活動是否成功的成功量度。
* **[!UICONTROL 其他度量]：**&#x200B;設定報告的其他成功度量。
* **[!UICONTROL 報表對象]：**&#x200B;定義可用來篩選報表的對象。

## 其他中繼資料

輸入有關活動的附註。

## 訓練影片：活動設定(3:02) ![教學課程徽章](/help/main/assets/tutorial.png)

本影片涵蓋下列活動設定：

* 輸入活動的目標。
* 設定活動的優先等級。
* 排程開始和結束時間。
* 新增報表對象以建立報表篩選器。
* 輸入活動的附註。

>[!VIDEO](https://video.tv.adobe.com/v/17381)
