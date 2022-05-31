---
keywords: at.js;瀏覽器使用者代理;使用者代理;用戶端提示;使用者代理
description: 了解  [!DNL Adobe Target]  使用者如何利用使用者代理和用戶端提示來決定訪客的細分和個人化資格。
title: 使用者代理和用戶端提示
feature: at.js
role: Developer
exl-id: 22d29bfe-e022-44b2-913f-c8c32c65bc48
source-git-commit: c351044163a6fb32ca72fa015724d3b0388c059a
workflow-type: ht
source-wordcount: '1332'
ht-degree: 100%

---

# 使用者代理和用戶端提示

[!DNL Adobe Target] 使用者如何利用使用者代理來決定訪客是否細分和個人化的資格。

>[!NOTE]
>
>本文資訊適用於 [at.js 2.9.0 版](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) (或更新版本)。


每次網頁瀏覽器向伺器發出請求時，請求標題會包含關於瀏覽器和執行瀏覽器環境的資訊。 從網際網路早期開始，這些資料一直都彙總在名為使用者代理的單一字串中。

以下文字是使用 Safari 瀏覽器 Mac OS X 系統電腦的使用者代理範本：

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

從這個使用者代理中，接收請求的伺服器可以識別關於瀏覽器和作業系統的以下資訊：

| 資訊 | 詳細資料 |
| --- | --- |
| 軟體名稱 | Chrome |
| 軟體版本 | 101 |
| 完整軟體版本 | 101.0.4951.41 |
| 版面引擎名稱 | AppleWebKit |
| 版面引擎版本 | 537.36 |
| 作業系統 | Android |
| 作業系統版本 | Android 12 (Snow Cone) |
| 裝置 | SM-S908E (Samsung Galaxy S22 Ultra) |

這些年來，使用者代理字串所含的瀏覽器和裝置的數量一直在增加。

## 使用者代理的使用案例

長期以來，使用者代理一直被用來為行銷和開發團隊提供有關瀏覽器和作業系統的重要解析。 和裝置顯示器網站內容，以及使用者如何與網站互動。 使用者代理也可用來封鎖垃圾郵件並過濾機器人，這些都會為各種其他目的而編目網站。

然而近年來，有些網站所有者和行銷供應商會使用用戶代理以及請求標題中的其他資訊來建立數位指紋，這可以在用戶不知情的情況下用作識別用戶的一種手段。 盡管使用者代理服務對網站主有很重要目的，瀏覽器開發商已經決定改變使用者代理的操作方式，以限制網站訪客潛在的隱私問題。

使用者代理用戶端提示是瀏覽器開發人員已開發的解決方案。 用戶端提示仍然允許網站收集必要的瀏覽器、作業系統和裝置的資訊，同時還提供更強防護以防止變相的追蹤方法 (如指紋)。

## 用戶端提示

使用者代理用戶端提示讓網站主能夠存取使用者代理中提供的大部分相同資訊，但是採用更能保護隱私的方式來存取這些資訊。 當現代瀏覽器向網頁伺服器傳送使用者代理時，無論是否需要，系統都會針對每個請求傳送完整的使用者代理。 另一方面，用戶端提示會強制實施模型，即伺服器必須要求瀏覽器提供伺服器想知道關於用戶端的更多資訊。 在收到這個請求後，瀏覽器可以套用本身原則或使用者設定來確定要傳回哪些資料。 現在，所有請求的存取管理都可以明確及可審核方式來進行，而不需依預設來公開整個使用者代理。

使用者代理用戶端提示已可在 89 版以後的 Chrome 系統中使用。 Chromium 系統的最新版本瀏覽器，如 Microsoft Edge、Opera、Brave、Chrome Android、Opera Android 和 Samsung Internet 也支持用戶端提示的 API。

瀏覽器向網頁伺服器發送的第一個請求標題內含有用戶端提示，其中資訊含有瀏覽器品牌、瀏覽器的主要版本，以及一個用戶端是否是為行動裝置的指標。 每一段資料都有自己的標題值，而不是被分組為單一的使用者代理字串，如下面的範例所示：

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

以下範例是相同瀏覽器的使用者代理：

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

雖然資訊類似，但對伺服器發送的第一個請求含有用戶端提示，其中只包含使用者代理字串適用的一個子集。 請求中沒有作業系統架構、完整的作業系統版本、版面引擎名稱、版面引擎版本和完整的瀏覽器版本。 然而，在後續的請求中，用戶端提示 API 會允許網頁伺服器要求更多關於裝置的高平圴資訊量細節。 當伺服器請求這些高平圴資訊量值時，則視瀏覽器原則或使用者設定而定，瀏覽器回應可能包含該資訊。

以下範例是當請求高平圴資訊量值時，用戶端提示 API 會傳回的一個 JSON 物件：

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

高平圴資訊量值包括一些預設用戶端提示資訊中不適用的額外資訊。 下表含有預設請求內適用的資料細節，與高平圴資訊量使用者代理資訊細節。 

| HTTP 標題 | JavaScript | 使用者代理 | 用戶端提示 | 高平圴資訊量的用戶端提示 |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | 品牌 | 是 | 是 | 無 |
| Sec-CH-UA-Platform | 平台 | 是 | 是 | 無 |
| Sec-CH-UA-Mobile | 行動 | 是 | 是 | 無 |
| Sec-CH-UA-Platform-Version | platformVersion | 是 | 無 | 是 |
| Sec-CH-UA-Arch | 架構 | 是 | 無 | 是 |
| Sec-CH-UA-Model | 模式 | 是 | 無 | 是 |
| Sec-CH-UA-Bitness | 位元 | 是 | 無 | 是 |
| Sec-CH-UA-Full-Version-List | fullVersionList | 是 | 無 | 是 |

## 移轉至用戶端提示

目前，Chromium 系統的瀏覽器會繼續發送使用者代理，連同發送位於網頁伺服器請求標題內的用戶端提示。 然而，從 2022 年 4 月起一直持續至 2023 年 2 月底，使用者代理字串所含的資料量將會減少。 其他瀏覽器如 Safari 和 Firefox 將繼續運用使用者代理字串；然而，這些瀏覽器也會減少其中所含的資訊量。

## 需要用戶端提示的 [!DNL Target] 使用案例

以下 Target 使用案例需要用戶端提示：

### 對象屬性

如果您使用 [!DNL Target] 對象和使用任何以下的對象屬性，[!DNL Target] 就會要求用戶端提示以執行正確的分段：

* 瀏覽器
* 作業系統
* 行動

### 設定檔指令碼

如果您使用設定檔指令碼和參照 `user.browser` 屬性 (指使用者代理)，您可能需要更新設定檔指令碼才能同時查看一個或多個用戶端提示。 您還可使用`user.clientHint('sec-ch-ua-xxxxx')` 功能來存取任何用戶端提示。 用戶端提示標題的名稱必須全為小寫。

下例顯示如何在設定檔指令碼中正確檢測 Windows 作業系統：

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

以下部分將顯示用戶端提示標題及其對應的設定檔指令碼使用語義。

#### Sec-CH-UA

平均資訊量：低
文件：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA){target=_blank}
對象屬性：瀏覽器
設定檔指令碼使用情形：`user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

平均資訊量：高
文件：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch){target=_blank}
對象屬性：透過設定檔指令碼向使用者公開。
設定檔指令碼使用情形：`user.clientHint('sec-ch-ua-arch')`

#### Sec-CH-UA-Bitness

平均資訊量：高
文件：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness){target=_blank}
對象屬性：透過設定檔指令碼向使用者公開。
設定檔指令碼使用情形：`user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-Full-Version-List

平均資訊量：高
文件：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List){target=_blank}
對象屬性：瀏覽器
設定檔指令碼使用情形：`user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

平均資訊量：低
文件：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile){target=_blank}
對象屬性：手機
設定檔指令碼使用情形：`user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

平均資訊量：高
文件：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model){target=_blank}
對象屬性：手機
設定檔指令碼使用情形：`user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

平均資訊量：低
文件：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform){target=_blank}
對象屬性：作業系統
設定檔指令碼使用情形：`user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-Platform-Version

平均資訊量：高
文件：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version){target=_blank}
對象屬性：透過設定檔指令碼向使用者公開。
設定檔指令碼使用情形：`user.clientHint('sec-ch-ua-platform-version')`

## 如何將用戶端提示傳遞至 [!DNL Adobe Target]

以下部分包含如何傳遞用戶端提示的更多資訊，具體取決於您的 [!DNL Target] 實施方法。

### at.js 2.9.0 版 (或更新)

從 at.js 2.9.0 版開始，使用者代理用戶端提示會從瀏覽器自動收集，並且在系統呼叫 `getOffer/getOffers()` 時傳送至 [!DNL Target]。 依預設，at.js 只會收集「低平均資訊量」的用戶端提示。 如果根據前面章節中被歸類為「高平均資訊量」的資訊來執行對象細分或使用設定檔指令碼，您需要設定 at.js 以便透過 `targetGlobalSettings` 從瀏覽器收集「高平均資訊量」的用戶端提示。

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### 伺服器端 SDK

有關如何透過伺服器端 SDK 傳遞用戶端提示的更多資訊，請參閱 *Adobe Target SDK* 文件中的「[用戶端提示](https://adobetarget-sdks.gitbook.io/docs/core-principles/audience-targeting#client-hints){target=_blank}。
