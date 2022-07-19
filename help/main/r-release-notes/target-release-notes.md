---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d0b6f81507cc5d5bc17d029c3d8f5b36c2c71a29
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 30%

---

# Target 發行說明 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期: 2022 年 7 月 18 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 22.7.1（2022年7月20日）

此版本包含以下功能、增強和修復：

| 功能 | 說明 |
| --- | --- |
| 通過IPv6支援提高觀眾評估準確性和最終用戶延遲 | 訪問者的地理位置現在由IPv6地址（如果可用）確定，而不是僅由IPv4地址確定。 交付API還支援IPv6輸入參數。 篩選和允許清單支援IPv4和IPv6地址。 此版本中的此IPv6支援意味著訪問者將更準確地包括在受眾中（更準確地說，訪問者有資格參加活動或被包括在過濾標準中）。 它還改善了資料延遲，因為IPv6客戶端將直接路由，避免了IPv6到IPv4網關的開銷。 |
| A4T客戶端負載處理增強 | 通過A4T伺服器端整合，如果Adobe Target將請求標識為來自bot的請求，則它不會將負載轉發到分析，並且目標日誌中沒有記錄modstats事件。 在此版本之前， A4T客戶端整合會將負載轉發到分析，即使它已被標識為bot通信量。 伺服器端與客戶端之間的這種不一致會導致不一致，因為後者的A4T報告包括bot流量。 此外，機器人流量未必被識別或標籤，這意味著無法消除機器人流量的歧義或從其餘流量中刪除機器人流量。 而且，即使客戶自己考慮了bot流量，也未必與Target識別並排除為bot流量的流量集匹配，從而導致分歧或其他問題。 在此版本中，A4T客戶端日誌記錄得到增強，因此與A4T伺服器端相同的是，A4T負載的行為：被標識為bot的訪問者不會從目標計數/報告中，而是不會從伺服器端和客戶端實施中進行。 |

## [!DNL Target Standard/Premium]22.6.2 (2022 年 6 月 30 日)

此版本包含以下功能、增強和修復：

| 功能 | 說明 |
| --- | ---  |
| 產品內通知 | 獲取以下相關的產品內通知：<ul><li>**活動**:當活動被批准或停用時（手動或達到其開始或結束日期時），所有活動類型的通知。 通知包括活動的名稱，其中包含指向活動概述頁的連結。</li><li>**配置檔案指令碼** 在手動或目標激活或停用配置檔案指令碼時通知。</li><li>**Recommendations飼料**:在手動或由Target激活或停用Recommendations源時通知。 當Recommendations饋送失敗時也會發送通知。</li></ul> 預設情況下，產品管理員、發佈者和批准者會接收通知。 通知可在Experience Cloud首選項內配置。<br>有關詳細資訊，請參閱 [通知和公告](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements)。 |
| *Adobe Target開發人員指南* | 的 *Adobe Target開發人員指南* 合併所有 [!DNL Target] 開發人員內容。 指南包括有關實施的資訊 [!DNL Target] 和 [!DNL Recommendations]。 [!DNL Target] SDK和 [!DNL Target] API。<br>有關詳細資訊，請參見 [Adobe Target開發人員指南](https://developer.adobe.com/target/){target=_blank}。 |

* 具有「[!UICONTROL 編輯者]」角色的使用者無法在即時活動中編輯受眾。 (TGT-43582)
* 如果客戶試圖以對象名字的第一個字元 (如 !London) 的嘆號 ( ! ) 來儲存對象，就會出現警告訊號。 (TGT-43643)
* 修正導致一些客戶的對象定義細節卡顯示已結束活動仍然在進行中的問題。 (TGT-43527)

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
