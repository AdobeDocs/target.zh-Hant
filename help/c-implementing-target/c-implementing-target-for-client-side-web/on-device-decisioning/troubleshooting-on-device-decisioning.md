---
keywords: 實施；javascript library;js;atjs；裝置上決策；裝置上決策；at.js；裝置上；裝置上；疑難排解；故障排除
description: 瞭解如何使用at.js程式庫疑難排解裝置上的決策。
title: 如何使用at.js JavaScript程式庫疑難排解裝置上決策？
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: 85a17944c7d5924edb1bbabb7531274249ceaaa8
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# 疑難排解at.js的裝置上決策

完成下列步驟，以疑難排解[!DNL Adobe Target]中使用at.js JavaScript程式庫的裝置上決策問題：

## 步驟1:啟用at.js的主控台記錄檔

附加URL參數`mboxDebug=1`可讓at.js在瀏覽器主控台中列印訊息。

所有訊息都包含首碼&quot;AT:&quot;，以方便概述。 為確保對象已成功載入，控制台日誌應包含類似以下的消息：

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

下圖顯示控制台日誌中的這些消息：

![具有對象消息的控制台日誌](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## 步驟2:在瀏覽器的「網路」索引標籤中驗證規則物件下載

開啟瀏覽器的「網路」標籤。

例如，若要在Google Chrome中開啟DevTools:

1. 按Ctrl+Shift+J(Windows)或Command+Option+J(Mac)。
1. 導航至「網路」頁籤。
1. 依關鍵字&quot;rules.json&quot;篩選呼叫，以確保只顯示對象規則檔案。

   此外，您還可以依&quot;/delivery|rules.json/&quot;篩選，以顯示所有[!DNL Target]呼叫和對象rules.json。

   ![Google Chrome中的「網路」索引標籤](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## 步驟3:使用at.js自訂事件驗證規則物件下載

at.js程式庫會派送兩個新的自訂事件，以支援裝置上的決策。

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

您可以訂閱，以監聽應用程式中的這些自訂事件，以便在對象規則檔案下載成功或失敗時採取動作。

以下範例顯示監聽對象下載成功和失敗事件的程式碼範例：

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
