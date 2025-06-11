---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新、目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 65ac352a1de7ad532f8c39781054fb09fa62c0fa
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 27%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 25.6.1 （2025年6月6日）

此版本包含下列修正和更新：

* 修正QA連結未針對關聯活動提供正確體驗的問題。 (TGT-52163 和 TGT-52790)
* 修正QA連結遺失相關對象ID的問題。 (TGT-52722)
* 修正問題，以確保只有在已設定的頁面傳送URL條件完全符合時，才會傳送體驗。 (TGT-52696)
* 修正客戶無法建立[!DNL Recommendations]設計範本的問題。 嘗試建立範本時觸發了錯誤：「指令碼內應至少使用1個實體變數。」 (TGT-52395)
* 修正無法使用Velocity陣列儲存[!DNL Recommendations]設計的問題。 錯誤訊息「指令碼內應至少使用1個實體變數」未正確觸發。 (TGT-52734)
* 修正當頁面無法載入內部網頁時，[!UICONTROL Visual Experience Composer] (VEC)中無法存取修改的問題。 (TGT-52488 &amp;TGT-52470)
* 修正VEC中較小熒幕大小無法顯示[!UICONTROL Modifications]面板的問題。 (TGT-52470)
* 修正已更新VEC中，從[!UICONTROL Browse]模式切換回[!UICONTROL Design]模式時，造成主控台錯誤及無法進一步互動的問題。 (TGT-52532)
* 修正VEC中按一下某些元素而無意識地擴大其大小的問題。 (TGT-52497)
* 修正某些頁面元素無法載入或在VEC中辨識的問題，以防止選取按鈕或橫幅等互動，並中斷活動中的準確事件追蹤。 (TGT-52663)
* 已修正導致客戶無法在[!UICONTROL Automated Personalization] (AP)活動中刪除或移除優惠的問題。 (TGT-52690)
* 修正造成多頁活動中活動資格行為不一致的問題。 (TGT-52694)
* 修正造成活動的[!UICONTROL Overview]頁面顯示[!UICONTROL Activity Location]無效URL的問題。 (TGT-52695)
* 修正更新的[!DNL Target] UI中，造成活動位置出現重複專案的問題。 (TGT-52693)
* 修正觸發`getAudiencesV3`錯誤，導致客戶無法編輯或複製活動的問題。 (TGT-52709)
* 修正將[!UICONTROL Experience Fragments]或HTML選件新增至活動時，造成無效裝載錯誤的問題。 (TGT-52779 和 TGT-52773)
* 修正更新的[!DNL Target] UI中，由於無效的輸入錯誤，E[!UICONTROL xperience Fragments]無法正確顯示的問題。 (TGT-52701)
* 修正由於無效的使用者錯誤，導致客戶無法編輯[!UICONTROL Form-based Experience Composer]中活動的問題。 (TGT-52470)
* 修正先前翻譯使用基本多語言平面以外的字元時，韓文本地化的問題。 更新的翻譯會使用適當的字元，以準確傳達預期的意義。 (TGT-52508 和 TGT-52509)
* 修正韓文中，為活動選取開始和結束日期時，「日期」的翻譯不一致的問題。 (TGT-52510)

## Target UI版本切換淘汰（2025年5月23日） {#toggle}

新[!DNL Target]使用者介面的轉出將於&#x200B;**2025年5月27日**&#x200B;完成。 到那時，所有客戶都有權存取最新的UI版本。

自&#x200B;**2025年6月22日**&#x200B;起，將移除UI版本切換。 所有使用者將永久轉換至新介面，沒有回覆至先前版本的選項。

>[!NOTE]
>
>在6月22日之後，有特殊情況需要保持切換的客戶可以聯絡Adobe客戶服務以尋求協助。

### 關於UI版本切換的重要資訊

我們提供暫時功能，可讓您使用切換按鈕，在更新的[!DNL Target] UI和舊版之間切換。 此選項僅在UI轉出的最後階段可用。

![目標UI版本切換](/help/main/r-release-notes/assets/toggle.png)

轉出完成後，切換將會移除，所有使用者將於&#x200B;**2025年6月22日**&#x200B;永久轉換為更新的UI。 Adobe建議提前規劃，因為這項功能將很快淘汰。

### UI切換行為的限制

* **新活動的可見性**：如果您切換回舊版使用者介面，在更新的UI中建立的活動將不可見。
* **編輯現有活動**：使用更新的UI時，對現有活動所做的變更（原本是在舊版UI中建立的）將會發佈至您的網站。 不過，如果您切換回去，這些更新將不會顯示在舊版UI中；那裡只會顯示舊版UI進行的最後更新。
* **活動詳細資料的一致性**：無論您使用哪種UI，最新變更都會反映在您已上線的網站上。 不過，舊版UI將只會顯示該版本中執行的最新變更。 如果在更新的UI中編輯的活動看起來與您在舊版UI中看到的不同，這可能會導致混淆。

### 有關已更新UI的更多資訊

* [[!DNL Target Standard/Premium] 25.2.1 （2025年2月17日）發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的關鍵UI變更摘要。

* [[!DNL Target Standard/Premium] 25.1.1 （2025年1月9日）發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!DNL Target]中[!UICONTROL Offers Library]主要UI變更的摘要。

* [瞭解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供簡短的總覽，協助您熟悉[!DNL Target]，並提供連結，以取得更深入的資訊和逐步指示。

* [[!UICONTROL Visual Experience Composer]個變更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）推出更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文說明VEC舊版和更新版本之間的差異。

* [[!UICONTROL Visual Experience Composer]選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文說明更新的VEC UI及其選項。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
