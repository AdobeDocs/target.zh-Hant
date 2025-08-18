---
keywords: 最佳化；個人化；adobe journey optimizer；ajo；使用案例；案例；內容變更/ab測試；設定檔屬性；變更影像；交換影像
description: 在Adobe Journey Optimizer中解鎖有效A/B測試內容變更的秘密
title: 透過 [!DNL Adobe Journey Optimizer]中的A/B測試變更內容
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: e5aed7cd-7701-4133-ac7c-98e528c8a763
source-git-commit: b66abe9649f8c257891c1cd8e5736b7f91501c13
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# 透過[!DNL Adobe Journey Optimizer]中的A/B測試變更內容

此使用案例可協助您解除鎖定秘密，以在[!DNL Adobe Journey Optimizer]中有效A/B測試內容變更。

此使用案例示範如何使用[而非](/help/main/c-activities/t-test-ab/test-ab.md)來執行熟悉的工作，例如在[!DNL Adobe Target]中對[!DNL Journey Optimizer]A/B測試活動[!DNL Adobe Target]進行A/B測試。

## 優點與價值

* **最佳化內容成效**：探索哪些內容變數和元素最能引起客戶的共鳴，進而提高參與度和轉換率。
* **資料導向式決策**：運用資料，針對您的內容策略做出明智的決策，確保影響最大化。
* **個人化使用者體驗**：量身打造內容，以符合所有受眾區段的不重複偏好設定和需求。

## 可能的情況

* 服裝公司透過測試各種影像並在call-to-action文字中使用者的名字來個人化行銷活動登陸頁面，以提高轉換率。

* 一家電子商務公司發現其「金會員忠誠度」會員的轉換率較高，這是因為他們在行銷活動登陸頁面上測試各種產品說明和影像，導致銷售額上升。

## 步驟

>[!NOTE]
>
>本節中的指示會強調變更影像及使用設定檔屬性個人化文字訊息的必要步驟。 如需[!DNL Journey Optimizer]網頁設計工具中可用選項的詳細資訊，請參閱[Journey Optimizer檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}中的&#x200B;*使用網頁設計工具*。
>
>頁面底部的影片特別實用。

若要使用設定檔指令碼測試各種影像並以使用者的名字個人化訊息，以最佳化網頁：

1. 在[!DNL Journey Optimizer]中，按一下左側邊欄中的&#x200B;**促銷活動**&#x200B;以顯示[!UICONTROL Campaigns]頁面。

1. 按一下&#x200B;**[!UICONTROL Create Campaign]**&#x200B;頁面右上角的[!UICONTROL Campaigns]。

1. 選取「**[!UICONTROL Scheduled - Marketing]**」（預設），然後按一下「**建立**」以顯示[!UICONTROL Campaign]詳細資料頁面。

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;區段中，為行銷活動提供描述性名稱和選擇性說明。

1. （視條件而定）在&#x200B;**[!UICONTROL Audience]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Select Audience]**&#x200B;並選擇所要的對象。

   針對此使用案例，您可以啟動[!UICONTROL All Visitors]的行銷活動（預設）。

1. 在&#x200B;**[!UICONTROL Action]**&#x200B;區段中，從&#x200B;**[!UICONTROL Web]**&#x200B;下拉式清單中選擇&#x200B;**[!UICONTROL Action]**，然後選取或建立新的網頁組態。

   Web設定（或頻道介面）是由系統管理員定義的設定。 網頁設定包含所有用於傳送訊息的技術引數，例如標頭引數、子網域、行動應用程式等。

   如需詳細資訊，請參閱[Journey Optimizer檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank}中的&#x200B;*設定頻道介面*。

1. 在&#x200B;**[!UICONTROL Action]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Edit Content]**&#x200B;以在[!DNL Journey Optimizer]網頁設計工具中開啟您的網站。

   A/B測試需要兩個或多個實驗。 您可以使用現有的首頁做為第一個實驗。 後續步驟將說明如何設定第二個實驗。

   ![LUMA網站上的瑜伽登陸頁面](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. 若要建立實驗，以判斷哪些內容效果較佳，請按一下&#x200B;**[!UICONTROL Create Experiment]**。

   內容實驗可讓您變更訊息內容、主旨或寄件者，以定義多種處理方式，並為您的對象確定最佳組合。 如需詳細資訊，請參閱[Journey Optimizer檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank}中的&#x200B;*建立內容實驗*。

1. 選取成功量度並按一下動作。

   按一下「說明」圖示，即可取得詳細資訊和相關文章的連結。

1. 按一下&#x200B;**[!UICONTROL Add Treatment]**，然後按一下&#x200B;**[!UICONTROL Create]**。

   對於此使用案例，您可以將每個實驗的分佈保留為50%。

1. 在[!UICONTROL Campaign]詳細資訊頁面的&#x200B;**[!UICONTROL Action]**&#x200B;底下，按一下&#x200B;**[!UICONTROL Edit Content]**。

1. 按一下「處理B」下的「網頁」。

   針對此使用案例，請維持[!UICONTROL Treatment A]不變，以使用原始體驗作為A/B測試中的第一個體驗。

1. 按一下右側邊欄中的&#x200B;**[!UICONTROL Edit Web Page]**。

   ![在瑜伽登陸頁面上編輯內容頁面](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. 若要變更主圖影像，請按一下您要變更的影像，然後按一下&#x200B;**[!UICONTROL Choose Image]**&#x200B;按鈕。

   ![選擇影像按鈕](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. 瀏覽並選取想要的影像，然後按一下&#x200B;**[!UICONTROL Use This Image]**。

   ![瑜伽頁面上的新主圖影像](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. 若要使用設定檔屬性以使用者的名字個人化郵件，請按一下您要個人化的文字，然後按一下&#x200B;**[!UICONTROL Add Personalization]**&#x200B;以顯示[!UICONTROL Add Personalization]頁面。

   ![新增Personalization按鈕。](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   如需設定檔屬性的詳細資訊，請參閱[Journey Optimizer檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank}中的&#x200B;*開始使用個人化編輯器*。

1. 搜尋並按一下加號以新增「名字」設定檔屬性，視需要調整文字，然後按一下&#x200B;**[!UICONTROL Save]**。

   ![為名稱](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)新增設定檔屬性

   如需詳細資訊，請參閱[Journey Optimizer檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank}中的&#x200B;*開始使用個人化編輯器*。

1. 按一下左上角的返回箭頭可返回網頁設計工具。

   ![後退箭號](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. 按一下「**[!UICONTROL Review to Activate]**」，確定一切如預期般顯示，然後按一下「**啟動**」。

## 檢視報告

按一下[!UICONTROL Reports]按鈕，然後按一下所需的報告期間：

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

如需詳細資訊，請參閱[Journey Optimizer檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank}中的&#x200B;*開始使用新的報表介面*。

>[!MORELIKETHIS]
>
>[在](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}Journey Optimizer檔案&#x200B;*中使用網頁設計工具*
>>[在](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank}Journey Optimizer教學課程&#x200B;*中建立行銷活動*
