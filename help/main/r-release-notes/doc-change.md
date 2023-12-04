---
keywords: Target 文件變更記錄；文件更新；新主題；編輯；更新；更新
description: 掌握 [!DNL Adobe Target] 文件的重要新增與變更。
title: 我可以在哪裡查看  [!DNL Target] 文件更新？
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 537af78695d8c22ec3725dfd86449852182c0b25
workflow-type: tm+mt
source-wordcount: '2337'
ht-degree: 95%

---

# 文件變更

本頁列出 [!DNL Adobe Target] 產品文件的重要變更。

## [!DNL Target] Standard/Premium 23.11.1 (2023 年 11 月 13 和 14 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 12 月 4 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 新增「機器學習與AI Reporting &amp; Analysis」的註冊資訊 [!DNL Adobe Target Community] 咖啡會：2023年12月6日星期三。 |
| 12 月 1 日 | [Adobe Target設定檔更新API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank} | 舊版API檔案已移至下列文章：<ul><li>[Adobe Target設定檔API概述](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank}</li><li>[Adobe Target單一設定檔更新API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-single-api.html){target=_blank}</li><li>[Adobe Target大量設定檔更新API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-bulk-api.html?){target=_blank}</li></ul> |
| 11 月 29 日 | [大量設定檔更新API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html){target=_blank} | 澄清關於如何進行 [!DNL Target] 為使用者建立設定檔時處理客戶屬性 [!DNL Target] 使用時尚未看到 [!UICONTROL 大量設定檔更新API] v2而非v1。 |
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
|  | [初始化 Java SDK](https://experienceleague.corp.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html){target=_blank} | 已新增以下新參數至表格：<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
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

## [!DNL Target] Standard/Premium 23.6.1 (2023 年 6 月 27-29 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 7 月 20 日 | [內容安全性原則 (CSP) 指示](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/content-security-policy.html){target=_blank} | 已新增以下 *Adobe Target 開發者指南* 常見問題集：如何允許或阻止我的網站作為 iFrame 嵌入在外部網域下？ |
| 7 月 10 日 | [考量事項和已知限制](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/known-limitations.html){target=_blank} | 已在 *Target Delivery API* 文件中新增資訊，關於 HTTP/2 強制使用小寫標頭名稱。 |
| 6 月 27 日 | [活動 QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | 活動 QA 現在可用於所有 Target 活動類型，包括 [!UICONTROL Automated Personalization] &#x200B;(AP) 活動。已移除有關預覽連結的資訊。 |
|  | 預覽 URL | 由於現在所有的活動類型都支援活動 QA，因此該主題已刪除並重新導向到[活動 QA](/help/main/c-activities/c-activity-qa/activity-qa.md) 主題。 |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.6.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.5.1 (2023 年 5 月 23-25 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 6 月 26 日 | [適用於行動應用程式的 Target](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/overview.html){target=_blank} | 在行動應用程式教學課程中新增了實施的連結 [!DNL Adobe Experience Cloud]。 |
| 6 月 12 日 | [Adobe Target Cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-target.html){target=_blank} | *Experience Cloud 中央介面元件指南*&#x200B;中的更新文件，說明 [!DNL Target] 所使用的 Cookie。 |
|  | [初始化 Java SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html){target=_blank} | 已新增有關「環境」參數的資訊。 |
|  | [初始化 Python SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/python/initialize-sdk.html){target=_blank} | 已新增有關「環境」參數的資訊。 |
| 6 月 5 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 已更新以下活動的資訊：<ul><li>已更新 [!DNL Adobe Target Recommendations] 咖啡會的註冊連結 (2023 年 6 月 7 日，星期三)</li><li>已新增關於近期網路研討會「經驗證之環境的行動體驗最佳化和個人化」的資訊和錄影連結。</li></ul> |
|  | [套用報表對象至成功量度](/help/main/c-target/apply-reporting-audience-success-metric.md) | 已更新「考量事項」章節並新增「範例」章節。 |
|  | [鎖定目標和對象常見問題](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md#url-targeting) | 已更新「URL 目標定位」章節。 |
| 5 月 30 日 | [[!DNL Target] 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.5.2 版的發行說明。 |
|  | [整合 [!DNL Real-Time Customer Data Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md) | 已更新有關與 [!DNL Target] 分享 [!UICONTROL Real-Time CDP 設定檔屬性]以用於 HTML 和 JSON 商品等資訊的文章。 |
|  | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 已新增下列即將舉行的咖啡會活動相關資訊：<ul><li>[!DNL Adobe Target Recommendations] 咖啡會 (6 月 7 日)</li><li>個人化方案整備度網路研討會後續追蹤 (6 月 21 日)</li></ul> |
| 5 月 23 日 | [允許清單 Target 邊緣節點](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | 已更新重要說明。 |
|  | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 為即將發佈的版本更新了發行前說明。 |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.5.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.4.1 (2023 年 4 月 25-27 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 5 月 22 日 | [整合 [!DNL Real-Time Customer Data Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#videos-blogs) | 已新增下列新影片: <ul><li>在 [!DNL Real-Time Customer Data Platform] 中設定 [!DNL Adobe Target] 目的地</li><li>啟動區段和設定檔屬性</li><li>在 [!DNL Target] 中使用 [!DNL Real-Time CDP] 區段</li><li>在 [!DNL Adobe Target] 中使用 [!DNL Real-Time CDP] 設定檔屬性</li></ul> |
|  | [允許清單 Target 邊緣節點](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | 已更新重要說明。 |
| 5 月 19 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 為即將發佈的版本更新了發行前說明。 |
| 5 月 17 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 新增有關 2023 年 5 月 24 日星期三 [!UICONTROL Adobe Target 社群]問答咖啡會的資訊。 |
| 5 月 16 日 | [實體屬性](/help/main/c-recommendations/c-products/entity-attributes.md) | 表示 `entity.id` 值不允許有「空格」。 |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html){target=_blank} | 更新 `viewsEnabled` 說明。 |
|  | [單次頁面應用程式實施](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/target-atjs-single-page-application.html){target=_blank} | 進行下列更新：<ul><li>在「實作 Adobe Target 檢視」下的步驟 2 後新增說明。</li><li>更新「初始頁面載入操作順序」下的步驟 2「執行 Target 請求」。</li></ul> |
| 5 月 4 日 | [為 Adobe Target API 設定驗證](https://experienceleague.adobe.com/docs/target-dev/developer/api/configure-authentication.html){target=_blank} | 新增解釋需要從 JWT 認證遷移到 OAuth 伺服器到伺服器認證的說明。 |
| 5 月 3 日 | [檢視報告 - A4T 常見問題](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#activity-impressions) | 新增下列常見問題：<ul><li>使用 [!UICONTROL Analytics for Target] (A4T) 時，如何在 [!DNL Analysis Workspace] 中追蹤活動曝光次數？</li></ul> |
| 4 月 26 日 | [AEM [!UICONTROL 體驗片段]和[!UICONTROL 內容片段]概觀](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md) | [!UICONTROL AEM 內容片段]功能現在可供所有 [!DNL Target customers]使用。 |
|  | [[!UICONTROL AEM 內容片段]](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) | [!UICONTROL AEM 內容片段]功能現在可供所有 [!DNL Target customers]使用。 |
|  | [*Adobe Target 開發人員指南*](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html){target=_blank} | *Adobe Target 開發人員指南*&#x200B;已移至 *[!UICONTROL Adobe Experience League]*。移至 *[!UICONTROL Experience League]* 可協助將文字當地語系化為其他語言，在 *Experience League* 中統一搜尋以提供來自 *[!UICONTROL Adobe Target 商務從業者指南]*&#x200B;和 *[!UICONTROL Adobe Target 開發人員指南]*&#x200B;的搜尋結果，並提供額外的好處。<P>您將從先前位置自動重新導向到 *[!UICONTROL Experience League]* 。請視需要更新您的書籤。 |
| 4 月 24 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 新增有關以下 Adobe Target 社群問答咖啡會的資訊：<ul><li>經驗證之環境的行動體驗最佳化和個人化</li></ul> |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.4.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 23.3.1 (2023 年 3 月 28 至 30 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 4 月 19 日 | [[!UICONTROL 位置貢獻]報表 (MVT)](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) | 已更新注意事項中的資訊。 |
| 4 月 13 日 | [[!DNL Target] 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 新增有關 [!DNL Target] Standard/Premium 23.4.1 版 (2023 年 4 月 25-27 日) 的資訊。 |
| 4 月 12 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 註册下列網路研討會的新增連結：<ul><li>每次都提供個人化的客戶體驗！</li></ul> |
|  | [重要屬性報表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md#models-api) | 新增下列常見問題：<ul><li>我看到一個或多個我不希望模型用於訓練的屬性。我可以從訓練模型中刪除這些屬性嗎？</li></ul> |
|  | [企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#multiple-roles) | 新增下列常見問題：<ul><li>如果使用者具有多個角色和權限，會如何？</li></ul> |
|  | [AEM 內容片段](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) | 新主題。請注意，出於測試目的，此功能處於「預先發佈」狀態。 |
| 4 月 5 日 | [使用報價決策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) | 已新增文字，表示 [!UICONTROL Analytics 作為報告來源] (A4t) 不受使用報價決策的活動支援。 |
| 4 月 3 日 | [[!DNL Adobe Target] 公告和活動](/help/main/r-release-notes/target-announcements.md) | 新增有關 2023 年 4 月 12 日星期三 [!UICONTROL Adobe Target 社群]咖啡會的資訊。 |
|  | [允許清單 Target 邊緣節點](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | 新增備註以將所有 [!DNL Adobe Analytics] IP 位址區塊加入允許清單。 |
| 3 月 30 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已更新發行說明，關於發行為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]功能最佳化的 A4T 量度，可讓您在為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動使用 [!UICONTROL A4T] 時，可根據二項式事件選擇量度，或根據連續事件選擇量度。 |
|  | [[!UICONTROL 自動分配和自動鎖定目標活動的 A4T 支援]](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) | 更新「受支援目標量度」一節以包含使用 [!UICONTROL Analytics for Target] (A4T) 之[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動的受支援 (和不受支援) 量度的資訊。 |
|  | [Adobe Target 教學課程](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html){target=_blank} | 已更新下列教學課程：<ul><li>[在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動分配]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li><li>[在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動鎖定目標]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |
|  | [Target 發行說明 (搶鮮版)](/help/main/r-release-notes/target-release-notes.md) | 已新增 [!DNL Adobe Experience Manager] (AEM) 和 [!DNL Adobe Target][!UICONTROL 內容片段]發行資訊。(2023 年 4 月 6 日) |
| 3 月 28 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 23.3.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 22.15.1 (2023 年 3 月 8 日和 9 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
|  | [編輯活動或另存為草稿](/help/main/c-activities/edit-activity.md) | 新增「最佳做法」一節。 |
|  | [修改](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | 在「自訂程式碼疑難排解」一節中新增以下備註：<ul><li>當使用 `{page: false}` 做為選項呼叫 `triggerView()` 時，VEC 中的自訂程式碼選件不會重新呈現。</li></ul> |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增關於 at.js 2.10.2 版的資訊。 |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 22.15.1 版的發行說明。 |

## [!DNL Target] Standard/Premium 22.13.3 (2023 年 1 月 25 日)

| 日期 | 主題 | 變更 |
| --- | --- | --- |
| 2 月 21 日 | [允許清單 Target 邊緣節點](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | 已更新 IP 位址清單，將 [Adobe Target 開發人員指南](https://experienceleague.corp.adobe.com/docs/target-dev/developer/overview.html){target=_blank}中的所有區域加入允許清單。 |
|  | [修改](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | 新增的文字解釋了使用 JQuery 的範例假設客戶的網站在 [!DNL Target] 執行選件時，頁面上有提供 jQuery。 |
| 2 月 10 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 22.14.5 版的發行說明。 |
| 2 月 8 日 | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 at.js 2.10.1 的發行說明。 |
| 2 月 2 日 | [排解視覺化體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md#section_FA2A18E8FD6A4274B2E395DBAA2FB407) | 已更新下列部分：<ul><li>當我使用瀏覽模式時，VEC 似乎損毀</li></ul> |
|  | [在 Target 中建立對象](/help/main/c-target/c-audiences/create-audience.md) | 已新增不可以在對象名稱中使用的字元和字元組合清單。 |
| 1 月 31 日 | [限制](/help/main/r-troubleshooting-target/target-limits.md#mbox-names) | 已新增 mbox 名稱中可使用和不可使用的字元清單。 |
| 1 月 25 日 | [建立 JSON 選件](/help/main/c-experiences/c-manage-content/create-json-offer.md) | 表示現在已可使用表單式體驗撰寫器支援 [!UICONTROL Automated Personalization] (AP) 活動中的 JSON 選件。 |
|  | [Adobe Target 公告和活動](/help/main/r-release-notes/target-announcements.md) | 已新增以下活動的相關資訊：<ul><li>[!DNL Adobe Target] 社群問答咖啡會：體驗最佳化的行動與已驗證使用案例</li></ul> |
|  | [Target 發行說明 (最新)](/help/main/r-release-notes/release-notes.md) | 已新增 [!DNL Target Standard/Premium] 22.13.3 版的發行說明。 |
