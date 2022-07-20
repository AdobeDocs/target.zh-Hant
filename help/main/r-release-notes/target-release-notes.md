---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bc4b04ae0be1fade2456eb42ade7ee87c0f14b16
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 37%

---

# Target 發行說明 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期: 2022 年 7 月 20 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] 平台版本（2022年7月20日）

此版本包含以下功能、增強和修復：

| 功能 | 說明 |
| --- | --- |
| 通過IPv6支援(TNT-43364、TNT-44692)提高了受眾評估準確性並減少了最終用戶延遲 | 訪問者的地理位置現在由IPv6地址（如果可用）確定，而不是僅由IPv4地址確定。 交付API還支援IPv6輸入參數。 篩選和允許清單支援IPv4和IPv6地址。 本版本中的IPv6支援意味著訪問者將更準確地包括在觀眾中（更準確地說，訪問者有資格參加活動或被包括在過濾標準中）。 它還改善了資料延遲，因為IPv6客戶端將直接路由，避免了IPv6到IPv4網關的開銷。 |
| 已修復A4T客戶端有效載荷處理問題(TNT-44926) | 通過A4T伺服器端整合，如果Adobe Target將請求標識為來自bot的請求，則它不會將負載轉發到Analytics，並且中沒有記錄modstats事件 [!DNL Target] 日誌。 在此版本中，A4T客戶端日誌記錄得到增強，因此與A4T伺服器端相同的是，A4T負載的行為：被標識為bot的訪問者不在 [!DNL Target] 計數/報告。 (注意，所討論的問題僅限於使用客戶端負載處理的實施；伺服器端未受到影響。 在此版本中，現在伺服器端和客戶端負載處理的行為是一致的。) |


## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
