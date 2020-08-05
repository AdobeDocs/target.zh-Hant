---
description: 刪除 Target 瀏覽器 Cookie，如此才可驗證所有的體驗。
title: 刪除Adobe Target Cookie
topic: Standard
uuid: 6e95ee4d-dbf2-4432-8abe-cfd9bc928f0c
translation-type: tm+mt
source-git-commit: 79bcd452a9faa0883272d2e686efd7c4ddfa34a2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%

---


# 刪除 Target Cookie{#delete-the-target-cookie}

您可以刪除瀏 [!DNL Target] 覽器Cookie(mbox)，以便在測試期間驗證所有體驗。

If there is no [!DNL Target] cookie (mbox), you are considered a new visitor and shown a new experience. There are several ways to delete your [!DNL Target] cookies without deleting all of your browser cookies.

>[!NOTE]
>
>下列瀏覽器和版本的指示正確。 搜尋網際網路，以取得您特定瀏覽器或版本的指示。

## 從Google Chrome刪除Target Cookie

84.0.4147.105 版

1. 按一下「 **Chrome** 」選單>「 **偏好設定」**。
1. 按一下「 **隱私與安全** 」標籤。
1. 按一 **下Cookie和其他網站資料**。
1. 按一 **下查看所有Cookie和網站資料**。
1. 展開 `adobe.com` 區段，選取 **mbox** Cookie，然後按一下刪除圖示(X)。

## 從Mozilla Firefox刪除Target Cookie

79.0 版

1. 按一下「 **Firefox** 」選單>「 **偏好設定**」。
1. 按一下「 **隱私與安全** 」標籤。
1. 在「 **Cookie和網站資料」下**，按一 **下「管理資料」**。
1. 選取網 `adobe.com` 站，然後按一下「 **移除選取的**」。

   >[!NOTE]
   >
   >這會刪除與網站相關的所有 `adobe.com` Cookie。 如果您想要刪除或編輯網站的個別Cookie，可以在開發人員工具的儲 [存偵測器中這麼做](https://developer.mozilla.org/en-US/docs/Tools/Storage_Inspector)。 您應刪除的特定Cookie名為「mbox」。

## 從Microsoft Edge刪除目標Cookie

84.0.522.52 版

1. 按一下「 **Microsoft Edge** 」功能表>「 **偏好設定**」。
1. Click the **Site Permissions** tab.
1. 按一 **下Cookie和網站資料**。
1. 按一 **下查看所有Cookie和網站資料**。
1. 展開 `adobe.com` 區段，選取 **mbox** Cookie，然後按一下刪除圖示(X)。

## 從Apple Safari刪除Target Cookie

13.1.2 版

1. 按一下「 **Safari** 」功能表> **偏好設定**。
1. Click the **Privacy** tab.
1. 按一 **下「管理網站資料**」。
1. 選取您要刪除之Cookie的網站，然後按一下「移除 **」**。

>[!NOTE]
>
>這會刪除與網站相關的所有 `adobe.com` Cookie。 如果您要刪除網站的個別Cookie，請依照下列指示進行：

1. 按一下「 **Safari** 」功能表> **偏好設定**。
1. Click the **Advanced** tab.
1. 在菜單欄 **中選擇「顯示開發」菜單** 。
1. 導覽至包含您要刪除之Cookie的網頁。
1. 按一下「 **開發** 」功能表> **「顯示網頁偵測器**」。
1. Click the **Storage** tab.
1. 展開「 **Cookie** 」區段，然後按一下 `www.adobe.com`。
1. 以滑鼠右鍵按一 **下mbox** Cookie，然後按一 **下刪除**。