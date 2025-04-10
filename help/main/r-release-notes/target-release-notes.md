---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7e23eea48abdebd60f37ad1bf453813a63779d33
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 27%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年4月10日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## Target許可權更新（2025年4月22日）

此未來更新加強了組織對[!DNL Target]執行個體設定的控制，防止了可能影響跨各種測試和個人化團隊的活動傳送的意外更新。

自2025年4月22日起，只有[!UICONTROL Product]和[!UICONTROL Solutions]管理員能更新[!UICONTROL Administration]區段中的設定，無論他們在[!DNL Target]工作區中的角色為何。 沒有此許可權的使用者將擁有[!UICONTROL Administration]區段的唯讀存取權。

如需詳細資訊，請參閱[管理Target](/help/main/administrating-target/start-target.md)。

## [!DNL Target Standard/Premium] 25.4.4 （2025年4月15日）

此版本包含下列修正和更新：

* 新增錯誤訊息，以引導使用者解決活動中的重複選項。 (TGT-51927)
* 修正刪除具有重新導向選件的頁面或體驗時，未移除ClickTrack選取器的問題。 (TGT-51952)
* 修正[!DNL Target]在活動URL中無法正確偵測「#」字元的問題。 (TGT-52093)
* 修正在[!UICONTROL Automated Personalization] (AP)活動中編輯選件層級鎖定目標時，無法顯示對象定義的問題。 (TGT-52148)
* 修正在UI中反轉對象細分和活動鎖定對象的問題。 (TGT-52158)

## [!DNL Target Standard/Premium] 25.4.3 （2025年4月10日）

此版本包含下列修正和更新：

* 修正導致客戶無法開啟特定[!UICONTROL Experience Targeting] (XT)活動的對象資訊快顯視窗的錯誤。 (TGT-52049)
* 修正客戶無法在預設工作區中插入[!UICONTROL Experience Fragment]的問題。 (TGT-52073)
* 修正了針對[!UICONTROL Automated Personalization] (AP)活動，選件顯示為「找不到內容」且未顯示在[!UICONTROL Offers]頁面的問題。 (TGT-52150)
* 新增在活動中允許重複受眾的功能。 (TGT-51200)
* 修正編輯後XT活動的[!UICONTROL Goals & Settings]頁面上顯示錯誤mbox名稱的問題。 (TGT-52026)
* 修正`defaultContent`不在`experiences/optionLocations`中卻顯示在選項中的問題。 (TGT-52036)
* 修正確保空白字串未轉換為Null值的問題。 (TGT-52037)
* 已修正要求客戶在編輯[!UICONTROL Goals & Settings]頁面上的[!UICONTROL Reporting Settings]中重新設定[!UICONTROL Optimization Goal]的問題。 (TGT-52071)
* 修正無頁面傳送規則的活動在[!UICONTROL Overview]頁面上顯示多個規則的問題。 (TGT-52084)
* 新增錯誤訊息，說明使用者嘗試以基本多語言平面以外的字元（例如表情符號）儲存優惠方案。 (TGT-52105)
* 修正開啟活動觸發錯誤訊息的問題：「此活動使用一或多個在來源中刪除的對象。」 (TGT-52120)
* 修正在編輯期間ClickTrack量度未顯示在更新的[!UICONTROL Visual Experience Composer] (VEC)中的問題。 (TGT-52152)
* 修正具有查詢引數作為活動位置的URL未在活動的[!UICONTROL Overview]頁面上顯示查詢引數的問題。 (TGT-51635)
* 修正無法在[!UICONTROL Visual Experience Composer] (VEC)的[!UICONTROL Browse mode]中顯示整個體驗URL的問題。 (TGT-52101)
* 修正編輯活動導致頁面傳送在URL結尾新增「/」使其無效的問題。 (TGT-52114)
* 修正[!UICONTROL Form-Based Experience Composer]中的[!UICONTROL Activity QA]連結不正確地重新導向至[!DNL Adobe Experience Cloud]首頁的問題。 (TGT-52055)
* 修正儲存及重新開啟後，新增至[!UICONTROL A/B Test]活動的其他頁面未保留的問題。 (TGT-51994)
* 已修正導致客戶無法刪除內嵌樣式區段中的樣式的問題。 (TGT-52070)
* 已還原存取[!UICONTROL Activity QA]對話方塊中的[對象定義卡](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)，類似於舊版UI。 (TGT-52056)
* 更新後的UI未儲存頁面或對象而未經修改。 如果客戶將新頁面或對象新增至活動，但未進行變更，[!DNL Target]會在儲存時捨棄未修改的對象。 已在相關位置新增通知，以通知使用者此行為。 (TGT-52104)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
