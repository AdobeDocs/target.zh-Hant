---
keywords: 實現；javascript library;js;atjs；設備上決策；設備上決策；at.js；設備上；設備上；故障排除；故障排除
description: 瞭解如何通過at.js庫排除設備上的決策故障。
title: 如何通過at.js JavaScript庫排除設備上決策故障？
feature: at.js
role: Developer
exl-id: 76bb9393-1560-455b-9d95-91576faee1f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 1%

---

# 針對 at.js 的裝置上決策疑難排解

完成以下步驟以排除中的設備上決策故障 [!DNL Adobe Target] 帶有at.js JavaScript庫：

## 步驟1:為at.js啟用控制台日誌

附加URL參數 `mboxDebug=1` 啟用at.js在瀏覽器控制台中打印消息。

所有消息都包含前置詞&quot;AT:&quot;，以方便概述。 為確保已成功載入項目，控制台日誌應包含類似以下內容的消息：

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

下圖在控制台日誌中顯示了這些消息：

![包含項目消息的控制台日誌](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## 步驟2:驗證在瀏覽器的「網路」頁籤中下載的規則項目

開啟瀏覽器的「網路」頁籤。

例如，要在GoogleChrome中開啟DevTools:

1. 按Ctrl+Shift+J(Windows)或Command+Option+J(Mac)。
1. 導航到「網路」頁籤。
1. 按關鍵字「rules.json」篩選調用以確保只顯示項目規則檔案。

   此外，您可以按「/delivery|rules.json/」篩選以顯示所有 [!DNL Target] 調用和項目rules.json。

   ![GoogleChrome中的網路頁籤](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## 第3步：使用at.js自定義事件驗證規則項目下載

at.js庫派送兩個新的自定義事件以支援設備上的決策。

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

您可以訂閱在應用程式中偵聽這些自定義事件，以便在項目規則檔案下載成功或失敗時執行操作。

以下示例顯示了一個代碼樣例，用於偵聽項目下載成功和失敗事件：

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
