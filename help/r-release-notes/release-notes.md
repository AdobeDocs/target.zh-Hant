---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
title: 'Adobe Target 版本說明 (最新) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 322b14629d420601b763fed7597c43a8458b7dbf
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 28%

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!NOTE]
>
>* **mbox.js淘汰**: 自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請 [參閱At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[和Adobe Target技能產生器： 開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**: 請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。 如需詳細資訊，請參閱 [Target公告](/help/r-release-notes/target-announcements.md)。


括號內的問題編號供 [!DNL Adobe] 內部使用。

## Target Standard/Premium 20.5.1 (2020 年 6 月 17 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| 目標分析 (A4T) 對自動分 [!UICONTROL 配活動的支援] | [!UICONTROL 自動配置活動] ，現在支援 [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)。<br>此整合可讓您使用 [!UICONTROL Auto-Allocate] multi-firled Bandit功能，將流量驅動至成功體驗，同時使用 [!UICONTROL Adobe Analytics] 目標量度及／或  Adobe Analytics報告與分析功能。<br>如果您已實作 [A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) ，以便與A/B測試和體驗定位活動搭配使用，一切就緒！<br>如需詳細資訊，請 [參閱「活動建立」中自動配置活動的Analytics for Target(A4T)](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)*支援*。 |
| 用於自動定位和自動個人化活動的流量分配方法的回應Token | 已 [將兩個回應Token新增至](/help/administrating-target/response-tokens.md) Auto-Target [!UICONTROL 和] Automated Personalization  （自動個人化）活動，以判斷訪客是因為被指派至「控制」或「目標」流量而收到特定體驗。<ul><li>`experience.trafficAllocationId` 如果訪客從「控制」流量中收到體驗，則會傳回0；如果訪客從「已定位」流量分佈中收到體驗，則會傳回1。</li><li>`experience.trafficAllocationType` 將會傳回「控制」或「已定位」。</li></ul>如需控制與目標流量的詳細資訊，請參 [閱選取「自動個人化」或「自動目標」活動的控制項](/help/c-activities/t-automated-personalization/experience-as-control.md)。 |
| [!UICONTROL 發佈者] 角色 | 此新角色類似於當前的 [!UICONTROL Observer] 角色（可以查看活動，但不能建立或編輯活動）。 不過，「發 [!UICONTROL 布者] 」角色具有啟動活動的額外權限。<br>如需詳細資訊，請參閱: <ul><li>**Target Standard使用者**: [在「使用者」中指定角色](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 和 *權限*。</li><li>**Target Premium使用者**: [步驟6: 在「設定企業權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) 」中 *指定角色和權限*。</li></ul> |
| 2020年6月25日 [!DNL Analysis Workspace]<br>提供A4T支援 | [!UICONTROL Analytics for Target] (A4T)現在支援 [!DNL Analysis Workspace]。 「 [!UICONTROL Analytics for Target(A4T)」面板] ，可讓您分析 [!DNL Adobe Target] 中的活動和體驗 [!DNL Analysis Workspace]。<br>如需詳細資訊，請 [參閱「A4T報表」和「](/help/c-integrating-target-with-mac/a4t/reporting.md) Analytics工具指南」中「Analytics中的報表」(位於 *A4T報表和Analytics for Target* (A4T)面板) [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html)**。 |

### 增強功能、修正和變更

* 修正造成「訪客」量度儲存在活動定義而非「獨特訪客」中的問題。 (TGT-37098)
* 修正UI中導致 [!DNL Target] 垂直捲軸在「觀眾」頁面上無法正確運 [!UICONTROL 作的問題] 。 (TGT-36968)

## at.js 1.8.2和at.js 2.3.1版本（2020年6月15日）

已在at.js程式庫中進行下 [!DNL Target] 列改進和修正：

| 功能/增強功能 | 說明 |
| --- | --- |
| at.js 1.8.2 | 此版本的at.js是維護髮行，包含下列修正：<ul><li>修正使用CNAME和Edge Override(at.js 1)時的問題。*x可能* 會錯誤建立伺服器網域，導致請求 [!DNL Target] 失敗。 (TNT-35064)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| at.js 2.3.1 | 此 at.js 版本為維護版本，包含下列增強功能和修正:<ul><li>透過targetGlobalSettings `deviceIdLifetime` 可覆蓋 [設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。 (TNT-36349)</li><li>修正使用CNAME和Edge Override(at.js 2)時的問題。*x可能* 會錯誤建立伺服器網域，導致請求 [!DNL Target] 失敗。 (TNT-35065)</li><li>已修正使用擴充功能v2 [!DNL Target] 和擴充功能時， [!DNL Launch] 延遲 [!DNL Adobe Analytics] 呼叫的問 [!DNL Launch][!DNL Target][!DNL Analytics]`sendBeacon` 題。 (TNT-36407、TNT-35990、TNT-36000)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |

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
