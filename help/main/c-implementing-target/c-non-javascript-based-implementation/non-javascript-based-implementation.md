---
keywords: 實現；at.js非javascript;adbox;redirector;mbox
description: 瞭解如何實施Adobe [!DNL Target] 在非JavaScript方案中，如使用AdBox或重定向器。
title: 如何實施 [!DNL Target] 電子郵件？
feature: Implement Email
role: Developer
exl-id: 3287cf3d-3ed4-471f-aa06-25bb12e23ead
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 78%

---

# 電子郵件：實作 Target

關於在非 JavaScript 案例 (例如，使用 AdBox 或重新導向程式) 中實作 Target 的資訊。

您可以追蹤廣告及其他離站內容的造訪。您也可偵測同位使用者進出您網站的狀況，並根據其網路瀏覽習慣呈現一致的網站體驗。使用單個URL,AdBox允許在不使用JavaScript或 [!DNL at.js]。

AdBox對於沒有 [!DNL at.js]，如關聯公司。 若您的活動需要動態創意素材 (例如，您需要在廣告中展示已從購物車拿掉的產品)，則無法使用 AdBox。

AdBox 廣告與重新導向程式可結合任何種類的活動使用。下表比較 AdBox 和重新導向程式，以及各自的使用時機：

|  | 用途 | 使用時機 | URL 結構 | 選件類型 | 選件內容 |
|--- |--- |--- |--- |--- |--- |
| AdBox | 將不同的影像傳回至廣告 | 變更廣告的內容 | `clientcode&#x200B;.tt.&#x200B;omtrdc&#x200B;.net/&#x200B;m2&#x200B;/&#x200B;clientcode/ubox/&#x200B;image?` | 重新導向選件 | 影像 URL |
| 重新導向程式 | 將訪客重新導向至其他網頁 | 變更廣告的著陸頁面 | `clientcode&#x200B;.tt.omtrdc.net/&#x200B;m2/clientcode&#x200B;/ubox/page?` | 重新導向選件 | 網頁 URL |

## 安全最佳做法 {#security}

請注意，使用重定向器，您可能會面臨「開啟重定向」漏洞的風險。 為避免第三方未經授權使用重定向器連結，建議您使用「授權主機」來允許列出預設重定向URL域。 Target 使用主機來允許列出您要允許重新導向的網域。如需詳細資訊，請參閱[建立允許清單，指定在 *&#x200B;Hosts* &#x200B;中授權傳送 mbox 呼叫至 Target 的主機](/help/main/administrating-target/hosts.md#allowlist)。

## 限制 {#section_38F559DCF1324271926608BCD4AB1227}

* 沒有像標準 mbox 那樣的用戶端逾時。如果 Target 完全故障，則訪客不會看見任何廣告內容，甚至是預設內容。
* 第三方 Cookie 用來追蹤造訪。如果 PCId 不一樣，依預設，訪客的第三方會與任何現有的第一方設定檔合併。
* 若要使用 AdBox 本身的第一方 Cookie，您必須在 URL 中傳遞 mBox 工作階段。請連絡您的帳戶代表來進行這項作業。
* 若要使用第一方 Cookie 來追蹤廣告點按次數，請在 URL 中傳遞 mbox 工作階段。請連絡您的帳戶代表來進行這項作業。
* 若要在相同頁面上使用多個 AdBox，則您必須在 URL 中傳遞 Mbox 作業。請連絡您的帳戶代表來進行這項作業。您在相同頁面上可能擁有一個 AdBox 和一個「重新導向程式」連結 (因為「重新導向程式」實際上位於第二個頁面)。
