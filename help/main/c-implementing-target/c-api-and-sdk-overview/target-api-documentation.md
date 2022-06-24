---
keywords: API; Adobe I/O
description: 瞭解如何從Adobe過渡 [!DNL Target] 傳統舊API到新API的Adobe I/O。
title: 如何從舊式API過渡到Adobe I/O?
feature: Implement Server-side
role: Developer
exl-id: 4b4274a9-b91a-4a79-9b40-8b1909a2d1d1
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 81%

---

# 從 [!DNL Target] 舊API到Adobe I/O

可協助您從 Target 舊版 API 使用轉變到 Adobe I/O 上的新 API 的資訊。

停用 Adobe Target Classic 之後，連接到 Target Classic 帳戶的 API 也已無法使用。本文協助您從舊版 API 型整合移轉至 Adobe I/O 所支援的 Target API。

如需有關 Target API 文件的詳細資訊，請參閱 [目標API和NodeJS SDK](https://developer.adobe.com/target/implement/server-side/){target=_blank}。

## 術語 {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

| 術語 | 說明 |
|--- |--- |
| 舊版 API | 連結至 Target Classic 帳戶的 API。這些 API 呼叫是根據使用者名稱和密碼式驗證，並使用主機名稱 `testandtarget.omniture.com`。如果您的 API 呼叫在要求 URL 中包含使用者名稱和密碼，您必須轉變為 Adobe I/O API。 |
| Adobe I/O | : Adobe I/O 是 Target API 的新入口。這些 API 會連接至您的 Target Standard/Premium 帳戶。Adobe I/O 上的 Target API 採用 JWT 型驗證，這是安全企業 API 方面的業界標準。 |

## 時間表 {#section_A478EBF637554A2DB5A31661955121ED}

我們停止支援 Target Classic 時，也就停止支援舊版 API。

| 日期 | 詳細資料 |
|--- |--- |
| 2017 年 10 月 17 日 | 已停止支援執行寫入作業的所有 API 方法 (`saveCampaign`、`copyCampaign`、`saveHTMLOfferContent` 以及 `setCampaignState`)。<br>這是所有 Target Classic 使用者帳戶設為唯讀狀態的相同日期。 |
| 2017 年 11 月 14 日 | 其餘 API 已停用。這是 Target Classic 使用者介面停用的日期。 |

此時間表不影響 Recommendations 傳統版 API。

## 對等方法 {#section_DDB42CCC172545B09CB728D794CC466B}

下表列出與舊版 API 方法對等的新版 Target API 方法。相較於舊版 API 所提供的 XML 回應，新版 API 會傳回 JSON。

新版 API 方法會連結至 API 說明文件網站中對應的區段。每一個 API 方法都有範例。您也可以使用 Admin Postman Collection，其中包含 Adobe I/O 上的所有新版 Adobe API 方法的 API 呼叫範例。

| 分組 | 舊版 API 方法 | 新版 API 方法 | 附註 |
|--- |--- |--- |--- |
| 行銷活動/活動 | 行銷活動建立 | [建立 AB 活動](https://developers.adobetarget.com/api/#create-ab-activity)<br>[建立 XT 活動](https://developers.adobetarget.com/api/#create-xt-activity) | 新版 API 對 AB 和 XT 提供不同的建立方法 |
|  | 行銷活動更新 | [更新 AB 活動](https://developers.adobetarget.com/api/#update-ab-activity)<br>[更新 XT 活動](https://developers.adobetarget.com/api/#update-xt-activity) |  |
|  | 複製行銷活動 | 不適用 | 使用活動建立 API |
|  | 促銷活動清單 | [列出活動](https://developers.adobetarget.com/api/#list-activities) |  |
|  | 行銷活動狀態 | [更新活動狀態](https://developers.adobetarget.com/api/#update-activity-state) |  |
|  | 促銷活動檢視 | [依 ID 取得 AB 活動](https://developers.adobetarget.com/api/#get-ab-activity-by-id)<br>[依 ID 取得 XT 活動](https://developers.adobetarget.com/api/#get-xt-activity-by-id) |  |
|  | 第三方行銷活動 ID | 不適用 | 如果您使用 thirdpartyID，則可使用相關的活動方法 |
| 選件 | 選件建立 | [建立選件](https://developers.adobetarget.com/api/#create-offer) |  |
|  | 選件取得 | [依 ID 取得選件](https://developers.adobetarget.com/api/#get-offer-by-id) |  |
|  | 選件清單 | [列出選件](https://developers.adobetarget.com/api/#list-offers) |  |
|  | 資料夾清單 | 不適用 | Target Standard/Premium 中不支援資料夾 |
| 報表 | 行銷活動效能報表 | [取得 AB 效能報表](https://developers.adobetarget.com/api/#get-ab-performance-report)<br>[取得 XT 效能報表](https://developers.adobetarget.com/api/#get-xt-performance-report) |  |
|  | 稽核報表 | [取得稽核報表](https://developers.adobetarget.com/api/#get-audit-report) |  |
|  | 1-1 內容報表 | [取得 AP 效能報表](https://developers.adobetarget.com/api/#get-ap-activity-performance-report) |  |
| 帳戶設定 | 取得主機群組 | [列出環境](https://developers.adobetarget.com/api/#list-environments) |  |

## 例外 {#section_09CF9A0E289149279783B4801D1B6D4C}

如果需要例外狀況，請聯絡您的「客戶成功經理」。

## 說明 {#section_591F850E2B7A4342B1C233693425415C}

如果您有任何疑問，或需要協助您移轉至 Adobe I/O 上的新版 Target API，請聯絡 Adobe Target 客戶服務 (tt-support@adobe.com)。
