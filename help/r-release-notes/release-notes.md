---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強；增強；修正；錯誤修正；更新
description: 目前版本包含哪些新功能？
title: 發行說明（目前）
feature: Release Notes
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 40%

---


# Target 版本說明 (最新)

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 將不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## Target Standard/Premium 21.1.1 (2021 年 1 月 19 日)

此維護髮行包含下列增強功能、修正和變更。

括號內的問題編號供 [!DNL Adobe] 內部使用。

* 在[!UICONTROL Auto-Target]活動中使用[!UICONTROL Analytics作為報告來源](A4T)時，新增在選取[!DNL Adobe Analytics]度量時的警告。 [!UICONTROL 自動定位] 模型已最佳化，可搭配二進位（轉換型）量度運作。選擇連續度量（例如收入）可能會有次優結果，而[!UICONTROL 個人化洞察]報表可能不準確。 (TGT-38926)
* 在[!UICONTROL Auto-Target Summary]報表中為使用A4T的[!UICONTROL Auto-Target]活動新增狀態圖示。 在報表中，每個體驗旁的綠色勾號圖示表示已為該體驗產生個人化機器學習模型。時鐘圖示表示提供的流量還不足以建立模型。(TGT-38925)
* 產生使用A4T和[!DNL Analytics]轉換度量的[!UICONTROL 自動化區段]和[!UICONTROL 重要屬性]活動的[!UICONTROL 自動目標]報表，其外觀與使用[!DNL Target]作為報表來源時相同。 (TGT-38931)
* 在[!UICONTROL Recommendations] [!UICONTROL Collections]清單中新增環境篩選選項。 (TGT-38353)
* 修正在[!UICONTROL Recommendations]系列中顯示錯誤產品計數的問題。 (TGT-39162)
* 新增[!UICONTROL 上次更新]篩選至[!UICONTROL Recommendations] [!UICONTROL 目錄搜尋]。 (TGT-38340)
* 修正[!UICONTROL Recommendations]中，在變更產業垂直後造成[!UICONTROL 建立序列]頁面擱置的問題。 (TGT-38160)
* 修正啟用Device Co-op且使用者從[!DNL Target]作為報告來源變更為[!DNL Analytics](A4T)時，無法儲存活動的問題。 (TGT-38163)
* 修正使用者無法從[!UICONTROL 自動個人化](AP)活動中的選件中移除對象的問題。 (TGT-39058)
* 修正部分客戶的「對象資訊」卡顯示錯誤時段（開始和結束日期）的問題。 (TGT-39150)
* 修正某些客戶無法在[!UICONTROL 預設工作區]中看到活動清單的問題。 (TGT-38526)

## at.js 2.4.0（2021年1月14日）

此版本的at.js是維護髮行，包含下列修正：

* 新增對傳送API customerId的統一設定檔／平台ID支援。
* 修正無效樣式標籤插入。

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參 [閱Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |
