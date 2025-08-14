---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c5016d212edafa908b8755044e73d28167e20e8a
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 13%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期： 2025年7月24日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.8.2 （2025年8月13日）

此版本包含下列修正和更新：

**[!UICONTROL Activities]**

+++檢視詳細資料
* 修正更新的[!DNL Target] UI中，某些活動在嘗試編輯時無法載入的問題。 此問題導致客戶將使用者留在無限載入畫面中。 此問題會影響多個活動，且各客戶回報問題的發生方式不一致。 透過此修正，受影響的活動現在可正確載入，允許順暢的編輯並減少活動工作流程的中斷。 (TGT-53209)
* 修正了活動建立程式中，由於後端驗證錯誤而導致客戶無法儲存變更的問題： `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:`在修改活動內的特定元素時，會發生此問題，導致儲存作業失敗。 此修正可確保`optionLocalId`參考現在已正確驗證，允許客戶儲存活動而不會遇到此錯誤。 (TGT-53293)
* 修正活動建立程式中，在編輯期間切換頁面三次，導致UI當機的問題。 無效的選項參考觸發當機，導致主控台錯誤，例如「找不到localId為&#39;7&#39;的選項」。 透過此更新，客戶現在可以在頁面之間切換並套用修改，而不會遇到系統故障或中斷。 (TGT-53295)
* 修正活動建立程式中，客戶因無效的使用者輸入錯誤而無法儲存活動變更的問題。 在更新的UI中修改體驗時發生錯誤，導致無法提交更新。 活動現在可以成功儲存，允許客戶在不中斷的情況下編輯和發佈。 (TGT-53267)
* 修正活動建立程式中，客戶因持續載入畫面而無法編輯更新UI中的活動的問題。 客戶現在可以開啟和修改活動，而不會遇到載入失敗的情況。 (TGT-53415)

+++

**體驗片段(XF)**

+++檢視詳細資料
* 修正活動建立程式中的問題，該問題允許客戶編輯在[!DNL Experience Fragments]內從[!DNL Adobe Experience Manager] (AEM)匯出的[!DNL Target] (XF)的HTML。 這是意外行為，因為從AEM發佈後，XF應該會保持鎖定以便編輯。 此修正可確保「編輯HTML」選項不再適用於AEM匯出的片段，保留內容完整性和預期的控管。 (TGT-53286)

+++

**QA模式**

+++檢視詳細資料
* 修正活動建立程式中，活動URL中的前導空格在儲存時未正確裁剪的問題。 這會導致後端的QA連結無效和格式不正確。 更新後，URL現在已完整儲存，避免連結損毀，並改善客戶QA工作流程的可靠性。 (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++檢視詳細資料
* 修正新[!UICONTROL Catalog Search] UI中，[!UICONTROL Advanced Search]功能無法提供建議的問題。 使用者必須輸入包含精確拼字的確切值，導致搜尋體驗繁瑣且容易出錯。 透過此修正，[!UICONTROL Advanced Search]現在會隨著使用者型別提供相關建議，以提升可用性並減少定位產品時的摩擦。 (TGT-52008)
* 解決幾個問題，包括小熒幕裝置上的條件詳細資料回應不良、在[!UICONTROL Environment]篩選器中選取「所有主機群組」時缺乏結果，以及無法與沒有名稱的實體互動。 這些修正可提升所有熒幕大小的可用性、確保篩選準確且允許與所有產品實體完全互動，進而增強使用者的整體體驗。 (TGT-52992)
* 修正[!DNL Recommendations]活動建立程式中，產品詳細資料畫面遺失產品ID，導致客戶在工作流程期間難以複製或參考產品ID的問題。 產品ID現在會清楚顯示在詳細資料檢視中，不但能改善可見度，還能為客戶提供更有效率的產品管理。 (TGT-51964)
* 修正活動建立程式中，[!UICONTROL Message]檢視中的[!DNL Recommendations]欄未顯示產品資料（即使有訊息）的問題。 客戶必須手動移除並重新新增欄以暫時顯示內容，當捲動或搜尋時，內容通常會再次消失。 此更新可恢復產品訊息的一致可見性，並改善目錄導覽和稽核工作流程。 (TGT-52777)
* 修正活動建立程式中，在[!DNL Recommendations]檢視中選取「所有主機群組」環境未傳回任何結果的問題。 客戶現在可以如預期檢視所有主機群組的產品資料，在活動設定期間提高可見度和篩選準確性。 (TGT-53006)
* 修正活動建立程式中，在活動設定中停用前端促銷活動切換開關在儲存後無法持續的問題。 嘗試移除前端促銷活動的客戶發現，在重新造訪活動時，切換功能會重新啟用，導致無法正確自訂。 此更新可可靠儲存變更，讓客戶完全掌控促銷活動設定。 (TGT-53215)

+++

**可視化體驗撰寫器 (VEC)**

+++檢視詳細資料
* 修正活動建立程式中，某些活動無法載入，導致客戶無法存取修改的問題。 此外，[!UICONTROL Cancel]按鈕無回應，導致客戶無法停止載入程式或退出編輯檢視。 此修正可確保活動現在能以可靠的方式載入，且[!UICONTROL Cancel]按鈕如預期般運作，改善視覺化體驗撰寫器(VEC)(TGT-53218)中的整體穩定性和使用者體驗
* 已修正更新VEC UI中，在體驗鎖定目標(XT)活動中的體驗之間切換時，無法載入修改的問題。 客戶無法編輯超出最初輸入範圍的體驗，且[!UICONTROL Cancel]按鈕遺失或無回應。 此修正可確保修改現在在所有體驗中正確載入，且[!UICONTROL Cancel]按鈕可靠地運作，即使沒有Helper擴充功能也是如此，可改善編輯工作流程並減少挫敗感。 (TGT-53256)
* 修正切換多個體驗時導致白熒幕的問題。 也修正了活動建立程式中，客戶嘗試修改活動內的多個體驗時，遇到白熒幕的問題。 將變更套用至兩個體驗，然後選取第三個體驗（阻止進一步編輯）後，就會發生此問題。 此更新可確保體驗之間順利轉換，讓客戶能夠在不中斷的情況下進行修改。 (TGT-53266)
* 修正在視覺化體驗撰寫器(VEC)中進行的自訂程式碼修改無法可靠地儲存在單次嘗試中的問題。 客戶回報網站和QA URL斷斷續續遺失樣式更新或HTML編輯等變更，即使同時使用[!UICONTROL Edit Content]和最終[!UICONTROL Save]按鈕亦然。 此回歸已解決，確保所有自訂程式碼變更在整個編輯工作階段中都會如預期般持續存在。 (TGT-53418)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
