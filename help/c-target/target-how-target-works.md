---
description: Adobe Target 透過 at.js 或 mbox.js JavaScript 資料庫的方式與您的網頁整合。
keywords: 鎖定目標;Cookie;第一方 Cookie;第一方 Cookie
seo-description: Adobe Target 透過 at.js 或 mbox.js JavaScript 資料庫的方式與您的網頁整合。
seo-title: 鎖定目標如何運作
solution: Target
title: 鎖定目標如何運作
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 鎖定目標如何運作{#how-targeting-works}

Adobe Target 透過 at.js 或 mbox.js JavaScript 資料庫的方式與您的網頁整合。

[!DNL Target Classic] 會在您想在頁面上顯示目標內容或收集資料的每一個區域周圍使用 mbox。[!DNL Target Standard] 中不需要這些 mbox。反之，每一個頁面只需要參照一個 [JavaScript 程式庫](../c-implementing-target/c-considerations-before-you-implement-target/target-implement.md#concept_60B748DE4293488F917E8F1FA4C7E9EB)，就能執行最佳化活動。

每當訪客請求已啟用 功能的頁面時，[!DNL Target]Target 就會使用下列程序來提供選件:

1. 客戶向伺服器請求頁面，並在瀏覽器中顯示該頁面。
1. 客戶的瀏覽器中會設定第一方 Cookie 來設定唯一的訪客 ID。

   如果您使用 Master Marketing Profile，也會設定 [!DNL Experience Cloud visitor ID]。

1. 頁面會透過 [!DNL Target] 檔案或頁面上的 mbox 來呼叫 [!DNL target.js]。
1. [!DNL Target] 會參照與訪客相關聯的設定檔。
1. [!DNL Target] 會執行與該設定檔相關聯的任何設定檔指令碼。
1. [!DNL Target] 會計算其回應。
1. 系統會根據活動或行銷活動的規則來顯示內容。

基本 A/B 測試中顯示的選件是隨機選擇的。因為這樣的隨機流量分割，在平分百分比之前可能需要許多初始流量。例如，如果活動有兩個體驗，則會隨機挑選開始的體驗。如果流量小，該百分比的訪客可能全偏到其中一個體驗。隨著流量增加，百分比會更平均。
