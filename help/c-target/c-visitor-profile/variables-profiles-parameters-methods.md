---
keywords: variables;profiles;parameters;built in profiles;methods;url variables;geo profiles;third party profiles;mbox variables;campaign variables;customer attributes
description: 此頁面列出在設定檔指令碼中很實用的設定檔、變數和參數。
title: 設定檔和變數字彙表
feature: null
topic: Standard
uuid: 9286467c-cbb5-42be-99c0-6687ffab0969
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 93%

---


# 設定檔和變數字彙表{#profile-and-variable-glossary}

此頁面列出在設定檔指令碼中很實用的設定檔、變數和參數。

## 內建的描述檔 {#section_2B694370003C4F8E8E29E0B2F6E52045}

| 描述檔 | 附註 |
|--- |--- |
| user.activeActivities<br>user.activeCampaigns | 即便他/她並未在目前的工作階段中與促銷活動/活動互動，仍傳回使用者所在所有促銷活動/活動的促銷活動 ID。 |
| user.pcId |  |
| user.sessionId |  |
| user.categoryAffinity |  |
| user.categoryAffinities | 傳回訪客已填入的相似性陣列 |
| user.isFirstSession |  |
| user.isNewSession |  |
| user.daysSinceLastVisit |  |
| user.browser | 使用者代理程式 |
| user.header | 所有 `user.header` 描述檔皆是由 mbox 請求標頭資料內建 |
| user.header(&#39;x-cluster-client-ip&#39;)<br><br>oruser.header(&#39;x-forwarded-for&#39;) | 訪客所在網路連線的公開顯示的 IP 位址。<br>您可以以數個方式取得該資訊，例如 [whatismyip.com](https://www.whatismyip.com/)。IP 位址不是 NAT 位址 (內部位址)，其開頭為 10.、192.168. 或 172。 |
| user.header(&#39;host&#39;) | 網站主機名稱 |
| user.header(&#39;cookie&#39;) | 訪客 cookie 資料 |
| user.header(&#39;user-agent&#39;) | 訪客瀏覽器使用者代理程式 |
| user.header(&#39;accept-language&#39;) | 訪客語言 |
| user.header(&#39;accept-encoding&#39;) | 訪客字元編碼 |
| user.header(&#39;accept&#39;) | 訪客語言和字元編碼 |
| user.header(&#39;connection&#39;) | 伺服器連線。例如: keep-live |
| user.header(&#39;referrer&#39;) | 訪客目前頁面的網站 URL。不適用於 Internet Explorer。 |
| user.getLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.setLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | 持續保存透過設定檔指令碼建立的設定檔屬性。另請參考「系統」設定檔，例如地理位置、造訪計數等。 |
| profile.get(&#39;param_name&#39;) | 要獲得要在配置檔案指令碼中使用的配置檔案參數，正確的方法是profile.get(&#39;param_name&#39;)方法。 |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | 對 Mbox 參數持續保存是因為其profile.  首碼。 |
| profile.browserTime | 訪客的本機瀏覽器時間。如需系統時間，請在描述檔指令碼中建立新的日期物件 |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount  |  |
| parameter= | 使用 mbox 傳遞之其他值的一般詞語，通常為名稱/值配對的形式。除非使用 `profile.parameter` 或 `user.parameter`，否則不會持續保存。 |

## URL 變數 {#section_8F25958273164EBAA6DC659302993FD3}

| `landing` | `referrer` | `page` |
|---|---|---|
| `landing.url` | `referrer.url` | `page.url` |
| `landing.domain` | `referrer.domain` | `page.domain` |
| `landing.protocol` | `referrer.protocol` | `page.protocol` |
| `landing.param` | `referrer.param` | `page.param` |
| `landing.query` | `referrer.query` | `page.query` |

## 地理和行動電信業者設定檔 {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`
* `profile.geolocation.latitude`
* `profile.geolocation.longitude`

## Mbox 變數 {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

| 變數 | 附註 |
|--- |--- |
| `mbox.name` |  |
| mbox.param(&#39;param_name&#39;) |  |
| 自動和每個請求一併傳遞的參數:<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |
| 與訂單 mbox 一併傳遞的參數:<ul><li>mbox.param(&#39;orderId&#39;)</li><li>mbox.param(&#39;orderTotal&#39;)</li><li>mbox.param(&#39;productPurchasedId&#39;)</li></ul> |
| mbox3rdPartyId | mbox 參數，用來將客戶 ID 同步至 Target 的 mboxPCID。客戶 ID 為您的公司用來追蹤訪客的 ID，例如 CRM ID、會員 ID 或類似的項目。然後此 ID 可用來新增資訊，透過設定檔 API 和[客戶屬性](/help/c-target/c-visitor-profile/working-with-customer-attributes.md)。 |
| mboxPageValue | 在每個 mbox 呼叫中，會指定一個值給頁面。 |
| mboxDebug | 僅用於除錯資訊。新增至頁面 URL，mbox.js 會在此頁面尋找它。 |
| mboxOverride.browserIp | 設定和實際位置不同的地理區域，讓您可以測試某個項目在其他位置看起來如何。<br>**注意:**只有在測試活動並且不在生產中時，才應該使用 mboxOverride 參數。使用任何 mboxOverride 參數可能造成使用[Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T) 時的報表差異。在測試時，您應該使用[活動 QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)，以在將活動推送至您的即時環境之前，確保您的活動可如預期般運作。 |

## 客戶屬性 {#section_62B4821EB6564FF4A14159A837AD4EDB}

可在描述檔指令碼中參考客戶屬性 ，格式為 `crs.get('<Datasource Name>.<Attribute name>')`。

這些屬性也可做為描述檔指令碼中的代號，以及直接用在選件中，不需要先使用描述檔指令碼。代號的格式為: `${crs.datasourceName.attributeName}`。請注意，應從任 `datasourceName` 何API呼叫中移除空格。
