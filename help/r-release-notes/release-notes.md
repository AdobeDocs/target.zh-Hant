---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
title: 'Adobe Target 版本說明 (最新) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 2aca4490a70c0f6a1f38fab2e62cdab55b5b7a4f
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 34%

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!NOTE]
>
>* **mbox.js淘汰**: 自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都將失敗，並影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 請參 *閱Adobe Target技能產生器： 開發人員聊天，將Adobe Target的mbox.js移轉至下方的at.js* ，以取得詳細資訊。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。


括號內的問題編號供 [!DNL Adobe] 內部使用。

## Adobe Target Skill Builder: 開發人員聊天，將Adobe Target的mbox.js移轉至at.js {#skill-builder}

隨著mbox.js即將於2020年8月30日淘汰，Adobe Target產品經理David Son最近主持了開發人員聊天，討論將mbox.js移轉至at.js的優點。 在接下來的30天中，您可 [以檢視網路研討會錄制](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。

## Target Standard/Premium 20.4.1 (2020 年 5 月 6 日)

此發行包含下列增強功能、修正和變更：

* 已修正對對象不正確限定裝置和瀏覽器類型的問題。 (TGT-36266)
* 修正在寬度小於963像素的螢幕上檢視報表資料時無法顯示的問題。 (TGT-36549)
* 修正「自動個人化」報表無法正確呈現的問題。 (TGT-36619)
* 修正在使用Analytics for Target(A4t)的「自動分配」和「自動目標」活動中，允許選取不相容量度的問題。 (TGT-36646)
* 修正「視覺體驗撰寫器」(VEC)中某些選項無法正確顯示的問題。 (TGT-36571)
* 修正Target UI中，當使用者在單一體驗中取代內容後，導致其他Recommendations選件預覽顯示已編輯內容的問題。 (TGT-36053 和 TGT-36894)
* 修正部分使用者無法從Recommendations目錄刪除項目的問題。 (TGT-36455)
* 修正使用者無法將Recommendations標準儲存在多頁活動上的問題。 (TGT-36249)
* 修正行為資料來源選項按鈕在連續編輯准則第二次時消失的問題。 (TGT-36796)
* 修正Recommendations演算法在延長期間顯示「擷取結果」的顯示問題。 (TGT-36550 和 TGT-36551)
* 已更新多種語言本地化的UI字串。

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明——目標伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 與Adobe Target伺服器端API相關的發行說明。 |
| [發行說明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 與Adobe Target的Node.js SDK相關的發行說明。 |
| [發行說明——目標Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 與Adobe Target Java SDK相關的發行說明。 |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js JavaScript程式庫各版本變更的詳細資訊。 |
| [mbox.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 本頁面顯示每個 mbox.js 版本的變更。<br>請注意，mbox.js程式庫已不再開發。 所有客戶應該從 mbox.js 移轉至 at.js。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](../r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參 [閱Experience Cloud發行說明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |
