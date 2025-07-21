---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b91abbd3b7418fd4d1444d96f160c3d9017f3bf8
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 34%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期： 2025年7月21日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.7.3 （2025年7月24日）

由於最近發現的問題（主要與複雜的客戶自訂有關），此版本包含以下修正和更新：

**活動**

+++查看詳細資料
* 修正Builder類別中的`buildViews`方法不正確將`viewMaxLocalId`設定為檢視總次數，而非指派的最高值`viewLocalId`的問題。 (TGT-53207)

+++

**表單式體驗撰寫器**

+++查看詳細資料
* 修正[!UICONTROL Form-Based Experience Composer]中，在建立或編輯&#x200B;**[!UICONTROL Manage Content]** (AP)活動時，在按一下![圖示（ ](/help/main/assets/icons/Experience.svg)管理內容圖示[!UICONTROL Automated Personalization] ）後導致編輯器當機的問題。 (TGT-53047)

+++

**推薦**

+++查看詳細資料
* 修正捲動至清單底部時，[!UICONTROL Catalog Search]無法載入其他結果的問題，恢復與舊版UI一致的行為。 (TGT-53088)
* 修正更新[!UICONTROL Number of Products] UI中[!UICONTROL Collections]頁面缺少[!DNL Target]欄的問題。 欄現在可正確顯示，並恢復預期的功能。 (TGT-53168)
* 修正[!UICONTROL Collection]規則未根據規則正確篩選的問題。 (TGT-53254)
* 修正封鎖從[!UICONTROL Criteria Details]對話方塊刪除專案的問題。 (TGT-53245)
* 修正無法開啟或無法與無名稱產品互動的問題。 選擇傳回未命名結果的環境時，會發生此問題，導致無法存取產品詳細資料。 (TGT-53007)
* 修正導致[!UICONTROL Catalog Search]頁面當機並在選取特定產品時顯示空白畫面的問題。 (TGT-53087)

+++

**可視化體驗撰寫器 (VEC)**

+++查看詳細資料

* 修正VEC中，將修改套用至檢視時造成重複並觸發「無效使用者輸入」錯誤的問題。 (TGT-52886)
* 修正在VEC中設定影像選件時，[!UICONTROL Undo]和[!UICONTROL Insert Before]選項的[!UICONTROL Insert After]功能問題。

  先前，在影像選件上復原[!UICONTROL Insert Before]或[!UICONTROL Insert After]動作會導致不一致的行為或無法正確回覆修改，尤其是在舊版[!DNL Target] UI中建立的活動中。 此問題已解決，以確保復原動作現在能可靠地用於這些修改。 (TGT-52809)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
