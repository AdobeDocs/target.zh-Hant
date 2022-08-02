---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bc4b04ae0be1fade2456eb42ade7ee87c0f14b16
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 100%

---

# Target 發行說明 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2022 年 7 月 20 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] 平台發行版本 (2022 年 7 月 20 日)

此版本包含以下功能、增強功能和修正：

| 功能 | 說明 |
| --- | --- |
| 透過 IPv6 支援提高對象評估準確性並降低最終使用者延遲 (TNT-43364、TNT-44692) | 訪客的地理位置現在由 IPv6 位址決定 (如果可用)，而不是僅由 IPv4 位址決定。 傳送 API 也支援 IPv6 輸入參數。 篩選和加入允許清單同時支援 IPv4 和 IPv6 位址。 此版本中的 IPv6 支援代表訪客將更準確地包含在對象中 (更準確地符合活動資格或包含在篩選條件中)。 同時改善了資料延遲，因為 IPv6 用戶端將直接路由，避免 IPv6 到 IPv4 閘道的額外負荷。 |
| 修正 A4T 用戶端裝載處理問題 (TNT-44926) | 透過 A4T 伺服器端整合，如果 Adobe Target 將請求識別為來自機器人，則不會將裝載轉送到 Analytics，並且 [!DNL Target] 日誌中不會記錄 mod_stats 事件。 在此版本中，A4T 用戶端記錄已增強，因此有關 A4T 裝載的行為與 A4T 伺服器端相同：被識別為機器人的訪客會排除在 [!DNL Target] 計數/報告之外。 (請注意，討論中的問題僅限於使用用戶端裝載處理的實施；伺服器端不受影響。 在此版本中，伺服器端和用戶端負載處理的行為現在是一致的。) |


## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
