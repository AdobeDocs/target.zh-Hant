---
keywords: 最佳化；個人化；adobe journey optimizer；ajo；使用案例；案例；新增內容；隱藏內容；新增元件；隱藏元件
description: 瞭解如何使用 [!DNL Adobe Journey Optimizer]新增或隱藏網頁上的元件。
title: 新增或隱藏元件至 [!DNL Adobe Journey Optimizer]中的網頁
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: b68ee55246f46f59bc0117e7702b06589fc1e58c
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 1%

---

# 新增或隱藏網頁元件

此使用案例可協助您解除鎖定秘密，以在[!DNL Adobe Journey Optimizer]中有效A/B測試內容變更。

此使用案例示範如何使用[!DNL Journey Optimizer]而非[!DNL Adobe Target]來執行熟悉的工作，例如使用[A/B測試活動](/help/main/c-activities/t-test-ab/test-ab.md)進行A/B測試。

此使用案例旨在示範如何使用[!DNL Adobe Target]、使用[A/B測試活動](/help/main/c-activities/t-test-ab/test-ab.md)但使用[!DNL Journey Optimizer]的A/B測試來執行您熟悉的工作。

## 優點與價值

* **增強使用者參與度**：以強調相關資訊（例如促銷活動）的最佳化頁面設計吸引使用者的注意力。
* **改善可發現性**：策略性地在網頁或行動應用程式上放置新元件或內容，以簡化動作並增強導覽。
* **增加其他接觸點**：有效引導使用者進行轉換事件和目標以加速業務影響。

## 可能的情況

* 一家金融服務公司計畫在其首頁上新增一個動態磚，以便快速存取貸款計算器，減少搜尋時間並增加貸款申請。

* 一家服裝公司透過在網頁上新增號召性用語按鈕來提高轉換率。

## 步驟

>[!NOTE]
>
>本節中的指示會強調變更影像及使用設定檔屬性個人化文字訊息的必要步驟。 如需[!DNL Journey Optimizer]網頁設計工具中可用選項的詳細資訊，請參閱&#x200B;*Journey Optimizer檔案*&#x200B;中的[編輯網頁內容](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank}。
>
>頁面底部的影片特別實用。

執行以下步驟來新增元件或隱藏網頁上的元件：

1. 在[!DNL Adobe Journey Optimizer]中，按一下左側邊欄中的&#x200B;**促銷活動**&#x200B;以顯示[!UICONTROL Campaigns]頁面。

   ![醒目提示「行銷活動」索引標籤的Adobe Journey Optimizer登陸頁面。](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. 按一下[!UICONTROL Campaigns]頁面右上角的&#x200B;**[!UICONTROL Create Campaign]**。

1. 選取「**[!UICONTROL Scheduled - Marketing]**」（預設），然後按一下「**建立**」以顯示[!UICONTROL Campaign]詳細資料頁面。

   在Adobe Journey Optimizer中的![行銷活動詳細資訊頁面](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;區段中，為行銷活動提供描述性名稱和選擇性說明。

1. （視條件而定）在&#x200B;**[!UICONTROL Audience]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Select Audience]**&#x200B;並選擇所要的對象。

   針對此使用案例，您可以啟動[!UICONTROL All Visitors]的行銷活動（預設）。

1. 在&#x200B;**[!UICONTROL Action]**&#x200B;區段中，從&#x200B;**[!UICONTROL Action]**&#x200B;下拉式清單中選擇&#x200B;**[!UICONTROL Web]**，然後選取或建立新的網頁組態。

   Web設定（或頻道介面）是由系統管理員定義的設定。 網頁設定包含所有用於傳送訊息的技術引數，例如標頭引數、子網域、行動應用程式等。

   如需詳細資訊，請參閱&#x200B;*Journey Optimizer檔案*&#x200B;中的[設定頻道介面](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank}。

1. 在&#x200B;**[!UICONTROL Action]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Edit Content]**&#x200B;以在[!DNL Journey Optimizer]網頁設計工具中開啟您的網站。

   ![LUMA網站上的瑜伽登陸頁面](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. 若要新增隱藏元素，請按一下右側邊欄中的&#x200B;**[!UICONTROL Edit Web Page]**。

1. 按一下您要隱藏的元素，然後按一下右側邊欄中的[!UICONTROL Hide]按鈕。

   右側欄會顯示您可以對所選元素執行的選項。 這些選項會因選取的元素而異。

   ![隱藏元素按鈕](/help/main/c-integrating-target-with-mac/ajo/assets/hide-element.png)

1. 按一下左上角的返回箭頭可返回網頁設計工具。

   ![後退箭號](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. 按一下「**[!UICONTROL Review to Activate]**」，確定一切如預期般顯示，然後按一下「**啟動**」。

## 檢視報表

按一下[!UICONTROL Reports]按鈕，然後按一下所需的報告期間：

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

如需詳細資訊，請參閱&#x200B;*Journey Optimizer檔案*&#x200B;中的[開始使用新的報表介面](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank}。

>[!MORELIKETHIS]
>
>在&#x200B;*Journey Optimizer檔案*&#x200B;中[編輯網頁內容](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank}
>[*Journey Optimizer檔案*&#x200B;中的作法影片](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content#video){target=_blank}
>[在&#x200B;*Journey OptimizerTutorials*&#x200B;中建立行銷活動](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank}