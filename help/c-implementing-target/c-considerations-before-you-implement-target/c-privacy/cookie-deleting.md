---
keywords: cookie;cookie；刪除cookie；刪除目標cookie;google chrome;chrome;mozilla firefox;microsoft edge;safari
description: 瞭解如何刪除您的 [!DNL Target] 瀏覽器Cookie，以便您驗證體驗。
title: 如何刪除 [!DNL Target] Cookie?
feature: 隱私權與安全性
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 4%

---

# 刪除[!DNL Target] Cookie

您可以刪除[!DNL Adobe Target]瀏覽器Cookie(mbox)，以便在測試期間驗證所有體驗。

如果沒有[!DNL Target] Cookie(mbox)，則會將您視為新訪客並顯示新體驗。 有數種方式能夠刪除您的 mbox ，但不會刪除您所有的瀏覽器 Cookie。

>[!NOTE]
>
>下列瀏覽器和版本的指示正確。 搜尋網際網路，以取得您特定瀏覽器或版本的指示。

## 從Google Chrome刪除[!DNL Target] Cookie

84.0.4147.105 版

1. 按一下「**Chrome**&#x200B;功能表> **偏好設定**」。
1. 按一下&#x200B;**隱私和安全**&#x200B;頁籤。
1. 按一下「**Cookie和其他網站資料**」。
1. 按一下「查看所有Cookie和網站資料&#x200B;**」。**
1. 展開`adobe.com`區段，選取&#x200B;**mbox** Cookie，然後按一下刪除圖示(X)。

## 從Mozilla Firefox刪除[!DNL Target] Cookie

79.0 版

### 刪除與`adobe.com`相關的所有Cookie

1. 按一下「**Firefox**&#x200B;功能表> **偏好設定**」。
1. 按一下&#x200B;**隱私和安全**&#x200B;頁籤。
1. 在「**Cookie和網站資料**」下方，按一下「管理資料&#x200B;**」。**
1. 選擇`adobe.com`站點，然後按一下&#x200B;**刪除選定項**。

   >[!NOTE]
   >
   >這會刪除與`adobe.com`網站相關的所有Cookie。 如果您想要刪除網站的個別Cookie，請依照下列指示進行。

### 刪除個別Cookie(mbox)

1. 在Firefox中，按一下「工具&#x200B;**** > **網頁開發人員** > **儲存偵測器**」。
1. 按一下&#x200B;**Advanced**&#x200B;頁籤。
1. 導覽至包含您要刪除之Cookie的網頁。
1. 展開&#x200B;**Cookie**&#x200B;區段，然後按一下`https://experience.adobe.com`。
1. 以滑鼠右鍵按一下&#x200B;**mbox** Cookie，然後按一下&#x200B;**Delete**。

## 從Microsoft Edge刪除[!DNL Target] Cookie

84.0.522.52 版

1. 按一下&#x200B;**Microsoft Edge**&#x200B;菜單> **首選項**。
1. 按一下「**網站權限**」標籤。
1. 按一下「**Cookie和網站資料**」。
1. 按一下「查看所有Cookie和網站資料&#x200B;**」。**
1. 展開`adobe.com`區段，選取&#x200B;**mbox** Cookie，然後按一下刪除圖示(X)。

## 從Apple Safari刪除[!DNL Target] Cookie

13.1.2 版

### 刪除與`adobe.com`相關的所有Cookie

1. 按一下「**Safari**&#x200B;功能表> **偏好設定**」。
1. 按一下&#x200B;**隱私**&#x200B;頁籤。
1. 按一下「管理網站資料」。****
1. 選取您要刪除之Cookie的網站，然後按一下「移除」。****

   >[!NOTE]
   >
   >這會刪除與`adobe.com`網站相關的所有Cookie。 如果您想要刪除網站的個別Cookie，請依照下列指示進行。

### 刪除個別Cookie(mbox)

1. 按一下「**Safari**&#x200B;功能表> **偏好設定**」。
1. 按一下&#x200B;**Advanced**&#x200B;頁籤。
1. 在菜單欄中選擇&#x200B;**顯示開髮菜單選項。**
1. 導覽至包含您要刪除之Cookie的網頁。
1. 按一下「**開發**&#x200B;功能表> **顯示網頁偵測器**」。
1. 按一下&#x200B;**儲存**&#x200B;頁籤。
1. 展開&#x200B;**Cookie**&#x200B;區段，然後按一下`www.adobe.com`。
1. 以滑鼠右鍵按一下&#x200B;**mbox** Cookie，然後按一下&#x200B;**Delete**。
