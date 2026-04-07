---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: cad8c365028b28bd9349d2d283370e2c8a750180
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 34%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

如需詳細資訊，請參閱[[!DNL Target] UI更新常見問題](/help/main/c-intro/updated-ui-faq.md)。


## [!DNL Target Standard/Premium] 26.4.1 （2026年4月2日）

**活動**

+++檢視詳細資料

* **在「活動」檢視中顯示的對象屬性。**&#x200B;修正從&#x200B;**[!UICONTROL Activity]**&#x200B;檢視的對象規則詳細資料，未顯示從&#x200B;**[!UICONTROL Audiences]**&#x200B;區段開啟相同對象時顯示之某些屬性的問題。 (TGT-54742)

* **套用至其他檢視時保留自訂程式碼。**&#x200B;修正套用至一個&#x200B;**[!UICONTROL View]**&#x200B;的自訂程式碼在同一&#x200B;**[!UICONTROL View]**&#x200B;中新增或儲存另一個&#x200B;**[!UICONTROL Activity]**&#x200B;的自訂程式碼時，可能會遭到移除的問題。 (TGT-53933)

* 在「活動」和「對象」清單頁面上&#x200B;**匯出CSV。**&#x200B;已新增&#x200B;**[!UICONTROL Export CSV]**&#x200B;動作，因此您可以從使用者介面匯出活動清單（包括套用篩選器的時間），而不需要仰賴API進行例行匯出。 (TGT-51466)

* 找不到選取器時標籤的&#x200B;**體驗修改。**&#x200B;體驗修改現在會執行選擇器存在性檢查；當頁面上找不到選擇器時，修改會標籤為無效。 (TGT-54815)

* **[!UICONTROL Automated personalization]個活動。**&#x200B;修正介面和活動載入問題，此問題會讓使用者無法可靠地建立、編輯或管理Automated Personalization活動，進而封鎖行銷活動設定，並延遲個人化使用案例。 (TGT-54421)

+++

**客群**

+++檢視詳細資料

* **從活動建立對象時顯示的對象名稱和說明。**&#x200B;修正從活動流程建立或編輯對象時，對象&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**&#x200B;欄位與直接在&#x200B;**[!UICONTROL Audiences]**&#x200B;下建立對象相比，未明確顯示的問題。 (TGT-54837)

+++

**深入分析**

+++檢視詳細資料

* **[!UICONTROL Live Activities]計入深入分析。**&#x200B;修正前瞻分析控制面板上的&#x200B;**[!UICONTROL Live Activities]**&#x200B;量度報告的總計可能高於&#x200B;**[!UICONTROL All Activities]**&#x200B;中顯示為已上線的活動數的問題。 (TGT-54788)

+++

**推薦**

+++檢視詳細資料

* **中的[!UICONTROL Global Exclusions]長ID清單。**&#x200B;修正在&#x200B;**[!UICONTROL Global Exclusions]**&#x200B;中貼上或輸入長清單ID時，在更新介面中可能比舊版截斷，導致排除清單不完整的問題。 (TGT-54422)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++檢視詳細資料

* **在[!UICONTROL Visual Experience Composer]中的增強體驗撰寫器(EEC)狀態指標。** EEC指標表示是否已啟用增強體驗撰寫器。 其顯示方式已經過修訂，因此不再類似互動式切換，因為它僅作為非互動式狀態顯示。 (TGT-54828)

* **[!UICONTROL Visual Experience Composer]中的左側邊欄。**&#x200B;現在當活動開啟進行編輯時，可以收合左側邊欄。 這可改善對包含多個對象和頁面的活動（包括在較小的顯示器上）的&#x200B;**[!UICONTROL Components]**&#x200B;和&#x200B;**[!UICONTROL Properties]**&#x200B;存取權。 (TGT-54269)

+++

## [!DNL Target Standard/Premium] 26.3.7 （2026年3月26日）

**客群**

+++檢視詳細資料

* **對象介面中的對象來源標籤準確度。**&#x200B;修正來自Adobe Experience Platform中Adobe Target v2目的地的對象可能以&#x200B;**Adobe Experience Cloud**&#x200B;而非&#x200B;**Adobe Experience Platform**&#x200B;作為來源的問題。 此更新可改善篩選和檢閱對象時來源標籤的一致性。 (TGT-54802)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
