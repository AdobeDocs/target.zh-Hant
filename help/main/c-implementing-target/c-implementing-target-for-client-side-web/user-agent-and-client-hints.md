---
keywords: at.js；瀏覽器用戶代理；用戶代理；客戶端提示；用戶代理
description: 瞭解如何 [!DNL Adobe Target] 使用用戶代理和客戶端提示來限定訪問者進行分段和個性化。
title: 用戶代理和客戶端提示
feature: at.js
role: Developer
source-git-commit: 2527608fc781913024d5d6ffee49aff9eb6c2f42
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 3%

---

# 用戶代理和客戶端提示

[!DNL Adobe Target] 使用用戶代理來限定訪問者進行分段和個性化。

每次Web瀏覽器向伺服器發出請求時，請求的標題中都包含有關瀏覽器和瀏覽器運行環境的資訊。 自Internet早期以來，此資料已聚合到一個名為user-agent的字串中。

以下文本是使用Safari瀏覽器的基於MacOS X的電腦的示例用戶代理：

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

從此用戶代理中，接收請求的伺服器可以識別有關瀏覽器和作業系統的以下資訊：

| 資訊 | 詳細資料 |
| --- | --- |
| 軟體名稱 | Chrome |
| 軟體版本 | 101 |
| 完整軟體版本 | 101.0.4951.41 |
| 佈局引擎名稱 | AppleWebKit |
| 佈局引擎版本 | 537.36 |
| 作業系統 | Android |
| 作業系統版本 | Android 12（雪錐） |
| 裝置 | SM-S908E(三星Galaxy S22Ultra) |

多年來，用戶 — 代理字串中包含的瀏覽器和設備資訊量已增長。

## 用戶代理使用案例

長期以來，用戶代理一直被用來向市場營銷和開發人員團隊提供瀏覽器、作業系統的重要見解。 設備顯示網站內容，以及用戶如何與網站交互。 用戶代理還用於阻止垃圾郵件和過濾為各種其他目的爬網站點的機器人。

但是，近年來，一些網站所有者和營銷供應商使用用戶代理以及請求標頭中包含的其他資訊來建立數字指紋，這些指紋可以用作在不知情的情況下識別用戶的手段。 儘管用戶代理為站點所有者服務有著重要的目的，但瀏覽器開發人員決定對用戶代理的操作方式進行更改，以限制站點訪問者的潛在隱私問題。

User-Agent Client Hints是開發者開發的解決方案瀏覽器。 客戶端提示仍然允許站點收集必要的瀏覽器、作業系統和設備資訊，同時還可以增強對隱蔽跟蹤方法（如指紋）的保護。

## 客戶端提示

用戶代理客戶端提示使網站所有者能夠訪問用戶代理中提供的大部分相同資訊，但是以更加保護隱私的方式。 當現代瀏覽器向Web伺服器發送用戶代理時，無論是否需要，每個請求都會發送整個用戶代理。 而客戶端提示則強制實施一個模型，伺服器必須在該模型中詢問瀏覽器要瞭解的有關客戶端的其他資訊。 在接收到此請求後，瀏覽器可以應用其自己的策略或用戶配置來確定返回哪些資料。 現在，不必在所有請求上預設顯示整個用戶代理，而是以顯式和可審核的方式管理訪問。

自89版以來，Chrome中提供了用戶代理客戶端提示。 基於鉻的瀏覽器的最新版本，如MicrosoftEdge、Opera、Brave、Chrome Android、Opera Android和三星Internet，也支援客戶端提示API。

瀏覽器向Web伺服器發出的第一個請求的標題中包含的客戶端提示包含瀏覽器品牌、瀏覽器的主要版本以及客戶端是否是移動設備的指示器。 每個資料都有其自己的標頭值，而不是按以下示例所示將其分組為單個用戶代理字串：

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

以下示例是同一瀏覽器的用戶代理：

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

儘管資訊相似，但對伺服器的第一個請求包含的客戶端提示僅包含用戶代理字串中可用內容的子集。 請求中缺少的是作業系統體系結構、完整作業系統版本、佈局引擎名稱、佈局引擎版本和完整瀏覽器版本。 但是，在後續請求中，客戶端提示API確實允許Web伺服器請求有關該設備的附加、高熵的詳細資訊。 當根據瀏覽器策略或用戶設定請求這些高熵值時，瀏覽器響應可以包括該資訊。

以下示例是請求高熵值時由客戶端提示API返回的JSON對象：

```
{ 

    "architecture":"x86", 
    "bitness":"64", 
    "brands":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100" 
        } 
    ], 
    "fullVersionList":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99.0.0.0" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100.0.4896.127" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100.0.4896.127" 
        } 
    ], 
    "mobile":false, 
    "model":"", 
    "platformVersion":"12.2.1" 
} 
```

高熵值包括預設「客戶機提示」資訊中不可用的幾個附加資訊。 下表包含預設請求中可用資料與高熵User-Agent客戶端提示資訊的詳細資訊。

| HTTP頭 | JavaScript | 用戶代理 | 客戶端提示 | 高熵客戶端提示 |
| --- | --- | --- | --- | --- |
| 秒 — 甲 — 阿 | 品牌 | 是 | 是 | 無 |
| Sec-CH-UA — 平台 | 平台 | 是 | 是 | 無 |
| Sec-CH-UA-Mobile | 行動 | 是 | 是 | 無 |
| Sec-CH-UA — 平台版本 | 平台版本 | 是 | 無 | 是 |
| 塞克 — 舒阿拱門 | 體系結構 | 是 | 無 | 是 |
| Sec-CH-UA — 模型 | model | 是 | 無 | 是 |
| 秒 — CH-UA — 比特 | 比特 | 是 | 無 | 是 |
| Sec-CH-UA — 完整版本清單 | 完整版本清單 | 是 | 無 | 是 |

## 遷移到客戶端提示

當前，基於Cr的瀏覽器繼續在向Web伺服器發出的請求的報頭中發送用戶代理和客戶端提示。 但是，從2022年4月開始，一直持續到2023年2月，用戶 — 代理字串中包含的資料量將減少。 其他瀏覽器，如Safari和Firefox，將繼續利用用戶代理字串；但是，它們也將減少其中所載資訊量。

## [!DNL Target] 使用需要客戶提示的案例

目標中的以下使用情形需要客戶端提示：

### 受眾屬性

如果您使用 [!DNL Target] 並使用以下任一受眾屬性， [!DNL Target] 需要客戶端提示執行正確的分段：

* 瀏覽器
* 作業系統
* 行動

### 設定檔指令碼

如果使用配置檔案指令碼並引用 `user.browser` 屬性（指用戶代理），您可能需要更新配置檔案指令碼以同時檢查一個或多個客戶端提示。 您可以使用該函式訪問任何客戶端提示 `user.clientHint('sec-ch-ua-xxxxx')`。 客戶端提示標頭名稱必須全部小寫。

以下示例說明如何正確檢測配置檔案指令碼中的Windows OS:

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

以下各節顯示「客戶端提示」標題及其相應的配置檔案指令碼使用語義。

#### 秒 — 甲 — 阿

熵：低文檔： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA){target=_blank}受眾屬性：瀏覽器配置檔案指令碼用法： `user.clientHint('sec-ch-ua')`

#### 塞克 — 舒阿拱門

熵：高文檔： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch){target=_blank}受眾屬性：配置檔案指令碼用法： `user.clientHint('sec-ch-ua-arch')`

#### 秒 — CH-UA — 比特

熵：高文檔： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness){target=_blank}受眾屬性：配置檔案指令碼用法： `user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA — 完整版本清單

熵：高文檔： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List){target=_blank}受眾屬性：瀏覽器配置檔案指令碼用法： `user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

熵：低文檔： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile){target=_blank}受眾屬性：移動配置檔案指令碼用法： `user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA — 模型

熵：高文檔： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model){target=_blank}受眾屬性：移動配置檔案指令碼用法： `user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA — 平台

熵：低文檔： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform){target=_blank}受眾屬性：作業系統配置檔案指令碼用法： `user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA — 平台版本

熵：高文檔： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version){target=_blank}受眾屬性：配置檔案指令碼用法： `user.clientHint('sec-ch-ua-platform-version')`

## 如何將客戶端提示傳遞給 [!DNL Adobe Target]

以下各節包含有關如何傳遞客戶端提示的詳細資訊，具體取決於 [!DNL Target] 執行。

### at.js版本2.9.0（或更高版本）

從at.js 2.9.0開始，將自動從瀏覽器收集用戶代理客戶端提示併發送到 [!DNL Target] 何時 `getOffer/getOffers()` 。 預設情況下， at.js僅收集「低熵」客戶端提示。 如果根據前面各節中分類為「高熵」的資料執行受眾分段或使用配置檔案指令碼，則需要配置at.js以通過以下方式從瀏覽器收集「高熵」客戶端提示 `targetGlobalSettings`。

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### 伺服器端SDK

有關如何通過伺服器端SDK傳遞客戶端提示的詳細資訊，請參見 [客戶端提示](https://adobetarget-sdks.gitbook.io/docs/core-principles/audience-targeting#client-hints){target=_blank} *Adobe TargetSDK* 文檔。












