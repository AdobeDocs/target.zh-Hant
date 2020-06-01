---
keywords: target documentation change log;documentation updates;new topics;edits;updates
description: 本頁列出依發行順序對Adobe Target檔案所做的重要變更。
title: Adobe Target 產品文件中的文件變更。
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: 1d0aa67027d76c659ca634f679c2341cafa52b09
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 34%

---


# 文件變更{#documentation-changes}

This page lists important changes made to the [!DNL Adobe Target] product documentation.

## Adobe Target Standard/Premium 20.4.1 (2020 年 5 月 6 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 6月1日 | [回應式體驗的行動檢視區](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) | 更新Apple iPhone 11、Apple iPhone SE和Google Pixel 2 XL機型的檢視區尺寸和解析度。 |
| 28 年 5 月 | [報表常見問題集](/help/c-reports/reporting-frequently-asked-questions.md) | 新增下列新常見問答： <ul><li>「新訪客」和「舊訪客」量度的計數方式為何？</li></ul> |
| 27 年 5 月 | [Target 版本說明 (發行前)](/help/r-release-notes/target-release-notes.md) | 已新增有關Analytics for Target(A4T)支援自動配置活動的資訊。 |
| 26 年 5 月 | [設定檔屬性](/help/c-target/c-visitor-profile/profile-parameters.md) | 已新增下列資訊： 「停用指令碼後，參數仍保留在描述檔中。 如果使用者的設定檔已包含用於活動對象的參數，則該活動將符合該使用者的資格。」 |
| 21 年 5 月 | [白名單目標邊緣節點](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | 已新 `mboxedge30.tt.omtrdc.net` 增至清單。 |
| 20 年 5 月 | [Target 版本說明 (發行前)](/help/r-release-notes/target-release-notes.md) | 已新增有關即將發行的Target Standard/Premium 20.6.1（2020年6月10日）版本的資訊。 |
|  | [主機](/help/administrating-target/hosts.md) | 在「安全性最佳實務」一節中新增附註。 |
| 14 年 5 月 | [Target 版本說明 (最新)](/help/r-release-notes/release-notes.md) | 已新增有關描述檔批次狀態API v2變更的資訊。 |
| 13 年 5 月 | [CNAME 與 Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 新增「已知限制」區段。 |
| 11 年 5 月 | [主機](/help/administrating-target/hosts.md) | 已新增有關使用包含重新導向和白名單的ubox功能的資訊。 |
|  | [使用重新導向程式](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | 已新增有關使用主機以避免「開啟重新導向弱點」的資訊。 |
|  | [將 Recommendations 與電子郵件整合](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | 已新增有關使用主機以避免「開啟重新導向弱點」的資訊。 |
|  | [電子郵件: 實作 Target](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | 已新增有關使用主機以避免「開啟重新導向弱點」的資訊。 |
| 7 年 5 月 | [Target 版本說明 (最新)](/help/r-release-notes/release-notes.md) | 隨著mbox.js即將於2020年8月30日淘汰，Adobe Target產品經理David Son最近主持了開發人員聊天，討論將mbox.js移轉至at.js的優點。 您可以透過連結觀看未來30天的網路研討會。 |
|  | [活動 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 更新「考量事項」區段。 |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 已更新「設定」下的「overrideMboxEdgeServer」列。 |
| 6 年 5 月 | [Apple 智慧型追蹤預防 (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | 已新增有關ITP 2.3的資訊。 |
|  | [版本說明](/help/r-release-notes/release-notes.md): 20.4.1 | 此版本包含增強功能和修正。您可以閱讀相關內容，並從版本說明連結至文件。此版本也包括許多對整個說明中的文件更新。 |

## Adobe Target Standard/Premium 20.2.1 (2020 年 2 月 19 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 4 年 5 月 | [報表常見問題集](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | 新增常見問答： 「為什麼我的A/B或MVT活動中體驗之間的流量分割不均？」 |
| 29 年 4 月 | [已知問題和已解決的問題](/help/r-release-notes/known-issues-resolved-issues.md) | 已新增極端訂單報告的已知問題。 |
| 28 年 4 月 | [設定檔和變數字彙表](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 已刪除有關使用較 `user.header('x-forwarded-for')` 新的AWS邊緣來檢索用戶IP地址的資訊。 此命令現在適用於較新的AWS邊緣。 |
|  | [Target 版本說明 (發行前)](/help/r-release-notes/target-release-notes.md) | 將Target Standard/Premium發行(20.4.1)的日期變更為5月6日。 |
| 23 年 4 月 | [CNAME 與 Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 更新了主題。 |
| 22 年 4 月 | [Target 版本說明 (發行前)](/help/r-release-notes/target-release-notes.md) | 新增區段： *描述檔批次狀態API v2變更（2020年5月4日）。* |
| 20 年 4 月 | [Target 版本說明 (最新)](/help/r-release-notes/release-notes.md) | 新增區段： *Adobe Target Skill Builder: 開發人員聊天，將Adobe Target的mbox.js移轉至at.js。* |
| 14 年 4 月 | [白名單目標邊緣主機](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | 新主題。 |
| 10 年 4 月 | [實作單頁應用程式](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | 新增區段： 「實作最佳實務。」 |
| 7 年 4 月 | [提升度和可信度 - A4T 常見問題集](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | 更新「為什麼我看不到計算量度的提升度和可信度？」的文字 |
| 2 年 4 月 | [設定檔和變數字彙表](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 已添加有關使用 `user.header('x-forwarded-for')` 較新的AWS邊緣來檢索用戶IP地址的資訊。 |
|  | [從 at.js 1.*x* 升級為 at.js 2.*x *](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | 已新增下列備註:<ul><li>安裝 ECID 資料庫 v4.3.0+ 和 at.js 2.*x* 後，您將能建立橫跨多個唯一網域的活動以及追蹤使用者。請務必注意，此功能只有在工作階段過期後才能運作。</li></ul> |
| 3月30日 | [已知問題和已解決的問題](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | 已新增影響at.js 2.2.0之前版本的已知問題。 當Adobe Analytics代碼不存在於頁面元素時，此問題會導致點按追蹤無法報告Analytics for Target(A4T)中的轉換。 |
|  | [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 已將下列資訊新增至at.js 2.2.0版詳細資訊：<ul><li>修正當Adobe Analytics代碼不存在於頁面元素時，點按追蹤無法報告Analytics for Target(A4T)轉換的問題。</li></ul> |
| 3月25日 | [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 已新增下列at.js新版本的相關資訊：<ul><li>at.js 2.3.0版</li><li>at.js 1.8.1版</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 在「設定」區段中新增下列新列：<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>新增下列新小節:<ul><li>內容安全性原則</li></ul> |
| 3月24日 | [Apple 智慧型追蹤預防 (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | 已新增有關下列影響的資訊：<ul><li>基於3rdPartyID的描述檔指令碼</li><li>iOS裝置中的QA/預覽URL</li></ul> |
| 3月20日 | [發行說明 (最新)](/help/r-release-notes/release-notes.md) | 已指出Target Standard/Premium 20.2.1版本將於2020年3月23日發行。 |
| 3月13日 | [限制](/help/r-troubleshooting-target/target-limits.md) | 更新「觀眾，每個帳戶可重複使用」的數量。 |
| 3月12日 | [發行說明（目前）](/help/r-release-notes/release-notes.md#summit) | 已新增註冊資訊，以免費存取線上數位峰會。 |
| 3月9日 | [隱私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | 已在「取代IP位址的最後八位元」區段中新增更多資訊。 |
|  | [使用多值屬性](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | 更新JavaScript中 *傳遞多值參數的程式碼範例*。 |
|  | [自訂實體屬性](/help/c-recommendations/c-products/custom-entity-attributes.md) | 在「使用API」的「實 *作多值屬性* 」 *下方新增程式碼範例*。 |
| 3月4日 | [設定檔屬性](/help/c-target/c-visitor-profile/profile-parameters.md) | 更新整個主題，並對「最佳實務」一節進行廣泛修訂。 |
| 2月21日 | [發行說明 (最新)](/help/r-release-notes/release-notes.md) | 已新增有關新Adobe Experience Cloud導覽的資訊。 |
| 2月20日 | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Updated the description for the `enabled` setting. 已新增下列設定的資訊： `pageLoadEnabled` 和 `viewsEnabled`。 |
| 2 月 19 日 |  [版本說明](/help/r-release-notes/release-notes.md) | 已新增有關即將淘汰mbox.js程式庫的資訊。 |
|  | [地理](/help/c-target/c-audiences/c-target-rules/geo.md) | 已新增 `mboxOverride.browserIp` at.js 1支援的附註。*x* 版。 |
|  | [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 已釐清文字，說明Target團隊支援哪些版本的at.js。 |
|  | [版本說明](/help/r-release-notes/release-notes.md): 20.2.1 | 此版本包含增強功能和修正。您可以閱讀相關內容，並從版本說明連結至文件。此版本也包括許多對整個說明中的文件更新。 |

## Adobe Target Standard/Premium 20.1.1 (2020 年 2 月 4 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 2月4日 | [版本說明](/help/r-release-notes/release-notes.md): 20.1.1 | 此版本包含增強功能和修正。您可以閱讀相關內容，並從版本說明連結至文件。此版本也包括許多對整個說明中的文件更新。 |
