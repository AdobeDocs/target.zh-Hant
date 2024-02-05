---
keywords: Target 文件變更記錄；文件更新；新主題；編輯；更新；更新
description: 掌握 [!DNL Adobe Target] 文件的重要新增與變更。
title: 我可以在哪裡查看  [!DNL Target] 文件更新？
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '1328'
ht-degree: 92%

---

# 文件變更

本頁列出 [!DNL Adobe Target] 產品文件的重要變更。

## [!DNL Target] Standard/Premium 24.1.1 (2024 年 1 月 22、23 和 25 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 2 月 5 日 | [建立使用 Analytics 作為報告來源的活動](/help/main/c-integrating-target-with-mac/a4t/campaign-creation.md) | 新增文字，指定在使用時，不能對來自不同工作區的兩個活動使用相同的活動名稱 [!UICONTROL 目標分析] (A4T)做為報表來源。 |
|  | [活動設定 - A4T 常見問題](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | 新增文字，指定在使用時，不能對來自不同工作區的兩個活動使用相同的活動名稱 [!UICONTROL 目標分析] (A4T)做為報表來源。 |
| 1 月 24 日 | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 已新增 at.js 版本 2.11.4 的發行說明。 |
|  | [瀏覽器](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | 宣佈尚未提供這兩個新的設定檔。 當這些設定檔可供使用時，將會更新這些附註。 |
|  | [at.js常見問題](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-faq.html){target=_blank} | 新增離子應用程式環境中at.js的常見問題集。 此實作未經測試或未建議。 |
| 1 月 22 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 新增了有關[!UICONTROL 瀏覽器]對象屬性停止支援 iPad 和 iPhone 的重要資訊，需要您在 2024 年 4 月 30 日之前進行變更。 |
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
| 11 月 29 日 | [大量設定檔更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html){target=_blank} | 澄清 [!DNL Target] 為 [!DNL Target]使用[!UICONTROL 批次設定檔更新 API] v2 與 v1 時還沒看到的使用者建立設定檔時處理客戶屬性方式的差異。 |
| 11 月 21 日 | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 已新增 at.js 2.11.3 的發行說明。 |
| 11 月 17 日 | [管理員入門](/help/main/administrating-target/start-target.md) | 新增下列重要附註:<ul><li>在 [!DNL Adobe Admin Console] 中具有[!UICONTROL 產品管理員]或[!UICONTROL 系統管理員]權限的使用者可以編輯或變更 [!DNL Target] [!UICONTROL 管理]頁面上的所有設定，無論其 [!DNL Target] 角色為何。在 [!DNL Adobe Admin Console] 中沒有[!UICONTROL 產品管理員]或[!UICONTROL 系統管理員]權限的使用者必須具有特定 [!DNL Target] 角色才能進行這些變更。1</li></ul> |
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
| 10 月 25 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增關於[!UICONTROL 活動]頁面使用者介面重新整理的相關資訊 (2023 年 10 月 25 日) |
| 10 月 24 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.10.2 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.9.1 (2023 年 9 月 6-11 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 10 月 17 日 | [報表常見問題](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B) | 已更新以下常見問題：「我的活動報表為何未提供資料？」 |
| 10 月 11 日 | [[!DNL Adobe Analytics] 當作  [!DNL Adobe Target] (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 的報告來源 | 已更新 [!DNL Adobe Experience Platform Web SDK] 的 A4T 支援相關資訊。 |
| 10 月 10 日 | [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 已新增 at.js 版本 2.11.0 的發行說明。 |
| 10 月 6 日 | [回應權杖](/help/main/administrating-target/response-tokens.md) | 已更新所有程式碼範例。 |
|  | [在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動分配]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} | 已更新 *[!UICONTROL Adobe Target 教學課程]*&#x200B;指南中的整個教學課程。 |
| 10 月 4 日 | [活動](/help/main/c-activities/activities.md) | 已更新文字和影像以反映 [!DNL Target] 23.9.4 版包含的 UI 重新整理。 |
|  | [摘要](/help/main/c-recommendations/c-products/feeds.md) | 已更新文字和影像以反映 [!DNL Target] 23.9.4 版包含的 UI 重新整理。 |
| 10 月 2 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.3 版的發行說明。 |
|  | [[!DNL Recommendations] 實作模式](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank} | 這個新的「*使用 at.js 的 Recommendations 實作模式*」文章可協助您在使用 at.js JavaScript 程式庫時理解並建立您的 [!DNL Adobe Target Recommendations] 實作。<P>有關 [!DNL Target] 模式的一般資訊，請參閱 *Adobe Target 開發人員指南*&#x200B;中的[實作模式概觀](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html){target=_blank}。<P>新的 Recommendations 實作模式由以下文章組成：<ul><li>[使用 at.js 的 Recommendations 實作模式概觀](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank}</li><ul><li>[初始化 SDK](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html){target=_blank}</li><li>[設定資料收集](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html){target=_blank}</li><li>[呈現體驗](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=zh-Hant){target=_blank}</li><li>[通知 [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=zh-Hant){target=_blank}</li></ul></ul> |
| 9 月 29 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.9.3 版的搶鮮版注意事項。 |
|  | [初始化 Java SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html){target=_blank} | 已新增以下新參數至表格：<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
| 9 月 22 日 | [排解[!UICONTROL 增強體驗撰寫器的相關問題]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF) | 已更新允許清單的 IP 位址清單。 |
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
|  | [選件](/help/main/c-experiences/c-manage-content/manage-content.md) | 新增註釋解影像選件不屬於[!UICONTROL 企業使用者權限]模型。 |
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
