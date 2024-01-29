---
keywords: 變數;設定檔;參數;內建設定檔;方法;url 變數;地理設定檔;第三方設定檔;mbox 變數;促銷活動變數;客戶屬性
description: 檢視Adobe Target中適用於設定檔指令碼的各種設定檔、變數和引數的清單。
title: 哪些設定檔、變數和引數用於 [!DNL Target]？
feature: Audiences
exl-id: 96ef9a56-fe76-428e-a164-c01829fdf45d
source-git-commit: d3c9a5bfa1e0496387103d82dd811f28581ba8bf
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 70%

---

# 設定檔和變數字彙表

此頁面列出在設定檔指令碼中很實用的設定檔、變數和參數。

## 內建的描述檔 {#section_2B694370003C4F8E8E29E0B2F6E52045}

| 個人資料 | 附註 |
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
| user.header(&#39;x-forwarded-for&#39;) | 訪客所在網路連線的公開顯示的 IP 位址。<br>您可以以數個方式取得該資訊，例如 [whatismyip.com](https://www.whatismyip.com/). IP 位址不是 NAT 位址 (內部位址)，其開頭為 10.、192.168. 或 172。<br>注意： user.header(&#39;x-cluster-client-ip&#39;)已過時。 |
| user.header(&#39;host&#39;) | 網站主機名稱 |
| user.header(&#39;cookie&#39;) | 訪客 cookie 資料 |
| user.header(&#39;user-agent&#39;) | 訪客瀏覽器使用者代理程式 |
| user.header(&#39;accept-language&#39;) | 訪客語言 |
| user.header(&#39;accept-encoding&#39;) | 訪客字元編碼 |
| user.header(&#39;accept&#39;) | 訪客語言和字元編碼 |
| user.header(&#39;connection&#39;) | 伺服器連線。例如: keep-live |
| user.header(&#39;referrer&#39;) | 訪客目前頁面的網站 URL。不適用於 Internet Explorer。 |
| user.getLocal(&#39;param_name&#39;)； | 擷取您使用設定的值 `user.setLocal`. |
| user.setLocal(&#39;param_name&#39;，&#39;value&#39;) | 在設定檔指令碼中建立持續存在的設定檔值。 這些值就像個人資料指令碼一樣持續存在，但您只能在設定它的指令碼中存取它。 |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | 持續保存透過設定檔指令碼建立的設定檔屬性。也會參照「系統」設定檔，例如地理位置、造訪次數等。 |
| profile.get(&#39;param_name&#39;) | 取得要在設定檔指令碼中使用的設定檔引數的正確方式是profile.get(&#39;param_name&#39;)方法。 |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | 對 Mbox 參數持續保存是因為其profile.  首碼。 |
| profile.browserTime | 訪客的本機瀏覽器時間。如需系統時間，請在描述檔指令碼中建立新的日期物件 |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount  |  |
| profile.mobile.isTablet | 訪客裝置是平板電腦。<P>此設定檔會取代已棄用的舊版 [瀏覽器是iPad對象類別](/help/main/c-target/c-audiences/c-target-rules/browser.md). |
| profile.mobile.isMobilePhone | 訪客裝置是行動電話。<P>此設定檔會取代已棄用的舊版 [瀏覽器是iPhone對象類別](/help/main/c-target/c-audiences/c-target-rules/browser.md). |
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
| mbox3rdPartyId | mbox 參數，用來將客戶 ID 同步至 Target 的 mboxPCID。客戶 ID 為您的公司用來追蹤訪客的 ID，例如 CRM ID、會員 ID 或類似的項目。然後，您可以使用此ID透過設定檔API新增資訊，並 [客戶屬性](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html){target=_blank}. |
| mboxPageValue | 在每個 mbox 呼叫中，會指定一個值給頁面。 |
| mboxDebug | 僅用於除錯資訊。新增至頁面URL，at.js會在此頁面尋找它。 |
| mboxOverride.browserIp | 設定和實際位置不同的地理區域，讓您可以測試某個項目在其他位置看起來如何。<br>**注意:** 只有在測試活動並且不在生產中時，才應該使用 mboxOverride 參數。使用任何 mboxOverride 參數可能造成使用 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) 時的報表差異。在測試時，您應該使用[活動 QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)，以在將活動推送至您的即時環境之前，確保您的活動可如預期般運作。 |

## 客戶屬性 {#section_62B4821EB6564FF4A14159A837AD4EDB}

可在描述檔指令碼中參考客戶屬性 ，格式為 `crs.get('<Datasource Name>.<Attribute name>')`。

這些屬性也可做為描述檔指令碼中的代號，以及直接用在選件中，不需要先使用描述檔指令碼。代號的格式為： `${crs.datasourceName.attributeName}`. 請注意， `datasourceName` 應從任何API呼叫中移除。
