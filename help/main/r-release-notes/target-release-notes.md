---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 71f88ad173599b3a582a1d2c261ba8a562cf734a
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 28%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年6月20日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.6.3 （2025年6月20日）

此版本包含下列修正和更新：

* 已將[!UICONTROL Rearrange]選項新增至更新的[!UICONTROL Visual Experience Composer] (VEC) UI，以符合舊版VEC中可用的功能。 (TGT-46957)
* 修正將活動從一個工作區複製到另一個工作區時，會觸發錯誤（例如「不得為空」或「發生錯誤」）的問題。 (TGT-52474)
* 修正未針對某些活動產生[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]報告的問題。 (TGT-52904)
* 已修正更新VEC中，[!UICONTROL Automated Personalization] (AP)活動中的預設內容處理與舊版UI不符的問題。 系統現在會在未明確新增群組時，自動新增名為「預設內容」的預設`optionGroup`搭配`optionGroupLocalId = 0`。 此群組包含預設選項（例如，`optionLocalId: 0`）。 如果移除預設內容，則也會移除對應的選項群組。 (TGT-52651)
* 修正[!UICONTROL Multivariate Test] (MVT)活動中不允許從先前移除的體驗中重複使用`experienceLocalId`的問題。 (TGT-52672)
* 修正活動位置中的URL因斜線(/)等無效字元而無法顯示查詢引數的問題。 (TNT52845)
* 已透過後端API改善[!DNL A/B Test]活動更新的驗證錯誤訊息。 出現重複的位置名稱時，訊息現在會清楚指出： `locations.selectors`的「不允許重複名稱」。 (TGT-52589)
* 修正更新已上線[!UICONTROL Recommendations]活動時，由於要求裝載中有無法辨識的屬性而發生的錯誤。 系統現在可以正確處理「無效的JSON」。 無法辨識的屬性名稱」錯誤。 (TGT-52723)
* 修正無法建立[!DNL Recommendations]設計的問題。 按一下[!UICONTROL Create]觸發訊息：「指令碼內應至少使用1個實體變數。」 (TGT-52395 和 TGT-52899)
* 修正無法在不修改的情況下重新儲存[!DNL Recommendations]設計的問題。 (TGT-52879)
* 修正儲存[!UICONTROL Recommendations]活動時，造成「400錯誤請求」錯誤的後端驗證錯誤。 (TGT-52716)
* 修正在[!UICONTROL Form-Based Experience Composer]中，將滑鼠游標暫留在[!UICONTROL Location]下拉式清單中具有特殊字元的mbox上，導致編輯器變為空白並觸發「無法在&#39;Element&#39;上執行&#39;querySelector&#39;」的問題。 」錯誤。(TGT-52717)
* 使用新的「PARTIALLY_IMPORTED」指標改善摘要狀態準確度。 先前，即使檔案中並非所有列都已匯入，摘要仍會標示為「success」，這是誤導性的。 (TGT-52892)
* 修正移轉至AP V2後，對`/admin/rest/ui/v1/campaigns`的特定API呼叫傳回使用者端錯誤(HTTP 4xx)的錯誤。 (TGT-52721)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
