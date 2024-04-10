---
keywords: Target 文件變更記錄；文件更新；新主題；編輯；更新；更新
description: 掌握 [!DNL Adobe Target] 文件的重要新增與變更。
title: 我可以在哪裡查看  [!DNL Target] 文件更新？
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 45576f31f055a83bcdc106771fb0fa25357d226a
workflow-type: tm+mt
source-wordcount: '1613'
ht-degree: 76%

---

# 文件變更

本頁列出 [!DNL Adobe Target] 產品文件的重要變更。

## [!DNL Target] Standard/Premium 24.3.1 （2024年3月4至6日）

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 4 月 9 日 | [疑難排解相關問題 [!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md) | 已更新下列部分：<ul><li>我的頁面未在 VEC 中顯示 (僅限 VEC)</li></ul>新增下列新小區段：<ul><li>中由CSS衝突造成的問題 [!UICONTROL Visual Experience Composer]</li></ul> |
|  | [個人化前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md) | 更新考量事項區段。 |
| 3 月 22 日 | [允許清單 Target 邊緣節點](https://experienceleague.adobe.com/en/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank} | 已移除對邊緣節點31到38的參照，因為此節點已不存在。 確保您的允許清單為最新。 |
|  | [第三方Cookie淘汰對Target (at.js)的影響](https://experienceleague.adobe.com/docs/target-dev/assets/third_party_cookie_deprecation){target=_blank} | 新部落格，說明Google預計淘汰第三方Cookie對您有何影響 [!DNL Adobe Target] at.js實作。 |
| 3 月 14 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增的版本注意事項 [!DNL Adobe Experience Platform Visual Editing Helper] 的 [!DNL Google Chrome]. |
| 3 月 13 日 | [[!UICONTROL Time Frame]](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | 新增說明以重新儲存時間型對象的資訊，以說明日光節約時間(DST)。 |
| 3 月 6 日 | [瀏覽器](/help/main/c-target/c-audiences/c-target-rules/browser.md) | 更新以下章節的資訊：「更新 [!DNL iPad] 和 [!DNL iPhone] 在 [!UICONTROL Browser] 對象屬性（2024年4月30日）」。 |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 更新整個區段：「更新 `Browser:iPad` 和 `Browser:iPhone` 在 [!UICONTROL Browser] 對象屬性（2024年4月30日）」。 |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 24.1.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 24.1.1 (2024 年 1 月 22、23 和 25 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 2 月 28 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 已新增關於 [!DNL Target] Standard/Premium 24.3.1 （2024年3月4至6日）版本。 |
| 2 月 26 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 新增即將推出的資訊 [!UICONTROL Adobe Target Community] 咖啡會（2024年2月28日）。 |
| 2 月 23 日 | [使用的IP位址 [!DNL Recommendations] 摘要處理伺服器](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | 新增下列重要注意事項以及您應加入允許清單的新IP位址。<P>**重要**：此 [!DNL Target] 群組目前正在更新要下載的NAT閘道位址 [!DNL Recommendations] 摘要。 如果您實施IP允許清單，請確定您允許清單下列新的AWS主機。 現有主機預計於2024年6月30日停止服務。 為確保順利轉換，請將所有九個地址加入允許清單。 移除現有位址並不緊迫。 |
| 2 月 8 日 | [預先擷取](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/prefetch.html){target=_blank} | 增加新部份：「使用 Analytics for Target (A4T) 時透過 clickTrack 指標預先擷取 mbox」 |
| 2 月 5 日 | [建立使用 Analytics 作為報告來源的活動](/help/main/c-integrating-target-with-mac/a4t/campaign-creation.md) | 新增文字，指定在使用時，不能對來自不同工作區的兩個活動使用相同的活動名稱 [!UICONTROL Analytics for Target] (A4T)做為報表來源。 |
|  | [活動設定 - A4T 常見問題](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | 新增文字，指定在使用時，不能對來自不同工作區的兩個活動使用相同的活動名稱 [!UICONTROL Analytics for Target] (A4T)做為報表來源。 |
|  | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 新增有關 2024 年 1 月 7 日 Adobe Target 社群咖啡會的資訊。 |
| 1 月 24 日 | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 已新增 at.js 版本 2.11.4 的發行說明。 |
|  | [瀏覽器](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | 宣布這兩個新設定檔還不能使用。當這些設定檔可用時，這些註釋將會更新。 |
|  | [at.js 常見問題](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-faq.html){target=_blank} | 已新增有關 Ionic 應用程式環境中的 at.js 常見問題。此實作未經測試或推薦。 |
| 1 月 22 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 新增從以下位置棄用iPad和iPhone的重要資訊： [!UICONTROL Browser] 需要您在2024年4月30日之前變更的對象屬性。 |
|  | [瀏覽器](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | 新增區段： <ul><li>瀏覽器對象屬性停止支援 iPad 和 iPhone (2024 年 4 月 30 日)</li></ul> |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 24.1.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.11.1 (2023 年 11 月 13 和 14 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 1 月 18 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 已新增未來 [!DNL Target Standard/Premium] 24.1.1 版的搶鮮版注意事項。 |
| 12 月 13 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 已新增 [!DNL Adobe Target] 2024 年個人化成熟度網路研討會系列的相關資訊。 |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html){target=_blank} | 已新增兩個新的可選設定： <ul><li>aepSandboxId</li><li>aepSandboxName</li></ul> |
| 12 月 4 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 新增「機器學習和 AI 報告與分析」[!DNL Adobe Target Community] 咖啡會的報名資訊：2023 年 12 月 6 日星期三。 |
| 12 月 1 日 | [Adobe Target 設定檔更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank} | 舊版 API 文件已移至以下文章：<ul><li>[Adobe Target 設定檔 API 概觀](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank}</li><li>[Adobe Target 單一設定檔更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-single-api.html){target=_blank}</li><li>[Adobe Target 大量設定檔更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-bulk-api.html?){target=_blank}</li></ul> |
| 11 月 29 日 | [大量設定檔更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html){target=_blank} | 澄清關於如何進行 [!DNL Target] 為使用者建立設定檔時處理客戶屬性 [!DNL Target] 使用時尚未看到 [!UICONTROL Bulk Profile Update API] v2而非v1。 |
| 11 月 21 日 | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 已新增 at.js 2.11.3 的發行說明。 |
| 11 月 17 日 | [管理員入門](/help/main/administrating-target/start-target.md) | 新增下列重要附註:<ul><li>使用者 [!UICONTROL Product Admin] 或 [!UICONTROL System Admin] 中的許可權 [!DNL Adobe Admin Console] 可以編輯或變更 [!UICONTROL Administration] 第頁，共頁 [!DNL Target]，無論使用者身分是 [!DNL Target] 角色。 不支援此專案的使用者： [!UICONTROL Product Admin] 或 [!UICONTROL System Admin] 中的許可權 [!DNL Adobe Admin Console] 必須具有特定 [!DNL Target] 進行這些變更的角色。1</li></ul> |
|  | [限制](/help/main/r-troubleshooting-target/target-limits.md#in-mbox) | 更新了有關 [!DNL Target] 如何處理 at.js 2 中截斷資訊的部分。*x* 和 [!DNL Adobe Experience Platform Web SDK]。 |
|  | [傳遞 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html){target=_blank} | 新增了對目前傳遞 API 文件的重新導向，並取代了舊文件 (`http://developers.adobetarget.com/api/delivery-api/`)。請視需要更新書籤。 |
| 11 月 16 日 | [大量設定檔更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html){target=_blank} | 新增了以下警告：「更新通常會在一小時內完成，但可能需要 24 小時後才會反映出來。」 |
| 11 月 13 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.11.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.10.2 (2023 年 10 月 24 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 11 月 10 日 | [Recommendations API 參考](https://developer.adobe.com/target/administer/recommendations-api/){target=_blank} | [!DNL Adobe Target][!DNL Recommendations] API 已移至 [!DNL Adobe Developer] 網站。請視需要更新您的書籤。 |
|  | [時間範圍](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | 已新增[!DNL Target]時間對象不考慮日光節約時間 (DST) 變動的備註。您必須手動更新對象以因應 DST 變動。 |
| 11 月 8 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 已新增未來 [!DNL Target Standard/Premium] 23.11.1 版的搶鮮版注意事項。 |
| 10 月 28 日 | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 已新增關於 at.js 2.11.2 版的詳細資料。 |
| 10 月 25 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增關於 [!UICONTROL Activities] 頁面使用者介面重新整理（2023年10月25日） |
| 10 月 24 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.10.2 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.9.1 (2023 年 9 月 6-11 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 10 月 17 日 | [報表常見問題](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B) | 已更新以下常見問題：「我的活動報表為何未提供資料？」 |
| 10 月 11 日 | [[!DNL Adobe Analytics] 當作  [!DNL Adobe Target] (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 的報告來源 | 已更新 [!DNL Adobe Experience Platform Web SDK] 的 A4T 支援相關資訊。 |
| 10 月 10 日 | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 已新增 at.js 版本 2.11.0 的發行說明。 |
| 10 月 6 日 | [回應權杖](/help/main/administrating-target/response-tokens.md) | 已更新所有程式碼範例。 |
|  | [在中設定A4T報表 [!DNL Analysis Workspace] 的 [!UICONTROL Auto-Allocate] 活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} | 更新中的整個教學課程 *[!UICONTROL Adobe Target Tutorials]* 指南。 |
| 10 月 4 日 | [活動](/help/main/c-activities/activities.md) | 已更新文字和影像以反映 [!DNL Target] 23.9.4 版包含的 UI 重新整理。 |
|  | [摘要](/help/main/c-recommendations/c-products/feeds.md) | 已更新文字和影像以反映 [!DNL Target] 23.9.4 版包含的 UI 重新整理。 |
| 10 月 2 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.3 版的發行說明。 |
|  | [[!DNL Recommendations] 實作模式](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank} | 這個新的「*使用 at.js 的 Recommendations 實作模式*」文章可協助您在使用 at.js JavaScript 程式庫時理解並建立您的 [!DNL Adobe Target Recommendations] 實作。<P>有關 [!DNL Target] 模式的一般資訊，請參閱 *Adobe Target 開發人員指南*&#x200B;中的[實作模式概觀](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html){target=_blank}。<P>新的 Recommendations 實作模式由以下文章組成：<ul><li>[使用 at.js 的 Recommendations 實作模式概觀](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank}</li><ul><li>[初始化 SDK](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html){target=_blank}</li><li>[設定資料收集](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html){target=_blank}</li><li>[呈現體驗](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=zh-Hant){target=_blank}</li><li>[通知 [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=zh-Hant){target=_blank}</li></ul></ul> |
| 9 月 29 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.3 版的搶鮮版注意事項。 |
|  | [初始化 Java SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html){target=_blank} | 已新增以下新參數至表格：<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
| 9 月 22 日 | [疑難排解相關問題 [!UICONTROL Enhanced Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF) | 已更新允許清單的 IP 位址清單。 |
| 9 月 18 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.3 版的發行說明。 |
| 9 月 15 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.3 版的搶鮮版注意事項。 |
| 9 月 12 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.2 版的發行說明。 |
|  | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 新增 at.js 版本 2.10.3 的發行說明。 |
| 9 月 11 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.2 版的搶鮮版注意事項。 |
| 9 月 6 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.8.1 (2023 年 8 月 9 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 9 月 1 日 | [環境](/help/main/administrating-target/environments.md##section_4F8539B07C0C45E886E8525C344D5FB0) | 已更新「設定報告的預設環境」下的註釋。 |
| 8 月 30 日 | [隱私權](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/privacy.html#aep){target=_blank} | 新增章節：「使用 Adobe Experience Platform Web SDK 時的資料流層級 IP 模糊化」 |
|  | [活動設定 - A4T 常見問題](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md#section_9F8092BE4225442896F926540292F221) | 更正了以下常見問題中報告資料顯示的預期時間範圍：「我剛剛建立了一項活動。為何沒看到任何資料進入？」 |
| 8 月 29 日 | [裝置上決策的支援功能](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/supported-features.html){target=_blank} | 新增使用裝置上決策 (ODD) 用戶端時，支援目標定位的地理位置屬性列表。 |
|  | [裝置上決策概觀](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html){target=_blank} | 新增使用裝置上決策 (ODD) 伺服器端時，支援目標定位的地理位置屬性列表。 |
|  | [在具有 Web 檢視的原生應用程式中使用 AEP Mobile SDK 實施 Target](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/native-app.html){target=_blank} | 新文章。 |
|  | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 新增關於即將舉行的 Adobe Target 社群咖啡會 (2023 年 8 月 30 日) 的資訊：「制定策略以發揮 ROI 的最大效益，為旺季做好準備」網路研討會後續追蹤。 |
| 8 月 14 日 | [活動 QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | 新增資訊說明您的網站載入含有空值的頁面，在使用 at.js 2 版本時&#x200B;*不會*&#x200B;從瀏覽器刪除 QA cookie。*X* 已部署。 |
|  | [A/Bn 測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | 已更新「可信度」的定義。 |
|  | [選件](/help/main/c-experiences/c-manage-content/manage-content.md) | 新增附註來說明影像選件並非 [!UICONTROL Enterprise User Permissions] 模型。 |
| 8 月 9 日 | [Target 行動裝置預覽](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html){target=_blank} | 已更新主題，包含有關 [!DNL Adobe Experience Platform Mobile SDK] 目前版本的資訊。 |
| 8 月 9 日 | [Target 行動裝置預覽](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html){target=_blank} | 已更新主題，包含有關 [!DNL Adobe Experience Platform Mobile SDK] 目前版本的資訊。 |
|  | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 已新增以下排定於 2023 年 8 月 17 日舉行的網路研討會的相關資訊：*制定策略以發揮 ROI 的最大效益，為旺季做好準備*。 |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.8.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.7.1 (2023 年 7 月 24-26 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
|  | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 已新增以下排定於 2023 年 8 月 17 日舉行的網路研討會的相關資訊：*制定策略以發揮 ROI 的最大效益，為旺季做好準備*。 |
| 8 月 7 日 | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 澄清了有關 at.js 支援版本的資訊。 |
| 7 月 25 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md#edge) | 有關預計於 2023 年 8 月 9 日進行已規劃的邊緣基礎設施升級新增資訊。 |
|  | [允許清單 Target 邊緣節點](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | 邊緣部署 41-48 的已更新 NAT 和 IP 位址/網域。 |
| 7 月 24 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.7.1 版的發行說明。 |
