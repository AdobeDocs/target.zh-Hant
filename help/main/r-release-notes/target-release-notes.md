---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b09796cd8464b54dcc1945ae1ec00eb914ba218c
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 31%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年4月24日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.4.5 （2025年4月25日）

此版本包含下列修正和更新：

* 修正[!UICONTROL Activity]設定頁面與[!UICONTROL Reporting]概觀頁面之間對象清單不一致的問題。 (TGT-52203)
* 修正由於無效的使用者輸入錯誤而無法新增頁面至活動的問題。 (TGT-52263)
* 修正啟用[!DNL Recommendations]活動後，建議未顯示在客戶網站上的問題。 (TGT-52164)
* 修正當選項保持不變時，`OptionLocalIDs`錯誤地遞增的問題。 (TGT-52187)
* 已修正問題，讓下載的報表檔案可正確顯示報表UI中存在的資料。 (TGT-52068)
* 修正問題，讓批次作業在新增頁面傳送規則後不再失敗。 (TGT-52097)
* 修正導致[!DNL Target]從網站URL中修剪所有查詢引數的問題。 (TGT-52100)
* 解決導致客戶無法在舊版和更新版Target UI中建立活動的主控台錯誤。 (TGT-52181)
* 已修正導致客戶無法新增頁面，進而造成無效使用者輸入錯誤的問題。 (TGT-52258)
* 已修正導致修改在新增其他頁面然後導覽回[!UICONTROL Experiences]索引標籤後消失的問題。 (TGT-52264)
* 修正阻止客戶變更[!UICONTROL Experience Targeting] (XT)活動中對象的問題。 (TGT-52191)
* 修正因不支援的UI規則而無法編輯XT活動的錯誤。 (TGT-52273)
* 修正即使已成功傳遞至網頁，[!DNL Target] UI仍未顯示活動修改的問題。 (TGT-52192)
* 已修正更新[!UICONTROL Visual Experience Composer] (VEC)中，在編輯器底部不一定會顯示階層連結，而造成精確選取元素困難的問題。 (TGT-51169)
* 修正[!UICONTROL Audience]下拉式清單因分頁而無法顯示所有對象的問題。 (TGT-52204)
* 修正在[!UICONTROL Automated Personalization] (AP)活動中新增優惠方案時，造成使用者輸入訊息無效的問題。 (TGT-52210)
* 修正即使客戶沒有A4T的存取權，[!UICONTROL Analytics for Target] (A4T)仍錯誤地選取為報告來源的問題。 (TGT-52226)
* 修正無法儲存具有[!UICONTROL View a Page] URL量度的活動的問題。 (TGT-52260)
* 修正在活動中建立優惠方案時，客戶無法選取工作區的問題。 (TGT-52289)
* 修正切換至另一個體驗時，來自一個體驗的修改未正確顯示的問題。 (TGT-52184)
* 修正開啟活動時，[!DNL Target] UI中錯誤顯示預設選件的問題。 (TGT-52198)

## Target許可權更新（2025年4月22日）

此未來更新加強了組織對[!DNL Target]執行個體設定的控制，防止了可能影響跨各種測試和個人化團隊的活動傳送的意外更新。

自2025年4月22日起，只有[!UICONTROL Product]和[!UICONTROL Solutions]管理員能更新[!UICONTROL Administration]區段中的設定，無論他們在[!DNL Target]工作區中的角色為何。 沒有此許可權的使用者將擁有[!UICONTROL Administration]區段的唯讀存取權。

如需詳細資訊，請參閱[管理Target](/help/main/administrating-target/start-target.md)。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
