---
keywords: tls;tls 1.0;transport layer security;encryption
description: Adobe 和 Target 如何使用 TLS (傳輸層安全性) 維持最高安全性標準，提升客戶資料安全性的相關變更資訊。
title: TLS (傳輸層安全性) 加密變更
topic: Standard
uuid: d222b966-ee73-4254-87b7-68099583e0dd
translation-type: tm+mt
source-git-commit: 1a502cc9c235ee765f24f04acf60b6fd75c369dc

---


# TLS (傳輸層安全性) 加密變更{#tls-transport-layer-security-encryption-changes}

Adobe 和 Target 如何使用 TLS (傳輸層安全性) 維持最高安全性標準，提升客戶資料安全性的相關變更資訊。

傳輸層安全性 (TLS) 是目前針對須透過網路安全交換資料的網頁瀏覽器和其他應用程式，部署最廣泛的安全通訊協定。[!DNL Adobe] 安全性法規遵循標準規定須結束支援舊版通訊協定，並強制採用 TLS 1.2，以使用最新、最安全的版本。

>[!IMPORTANT]
>
>在2020年2月之後，Adobe target將不再支援Visual Experience Composer(VEC)、Enhanced Experience Composer(EEC)、活動傳送、API等的TLS 1.1加密。 請在2002年2月之前升級至TLS 1.2，以避免任何問題。

我們預計這不會對客戶資料或報告造成重大影響。

## 具有已啟用增強體驗撰寫器 (EEC) 的可視化體驗撰寫器 (VEC){#section_B374B62DEC3344C194AC7BECC2EE0AA0}

到目前為止，Adobe Target 的[增強體驗撰寫器](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) (EEC) 預設使用 TLS 1.0。在2020年2月之後，Target依預設會移至TLS 1.2。

Adobe 會分階段將客戶轉移至 TLS 1.2。對於那些已經符合 1.2 規範之網域的使用者，我們會將其轉移至 TLS 1.2，無需進行任何變更。大多數客戶網域已支援 TLS 1.2；但如果您的網域不支援 TLS 1.2，我們會像今天一樣，將這些網域保留在 TLS 1.0 上 (直到 2020 年 2 月)。

在此移轉階段，您應該不會遇到任何問題。如果 VEC 已停止載入之前尚能運作的網站，[請開啟「客戶服務」票證](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，說明移轉作業可能為背後原因。

但是，如果您屬於不支援 TLS 1.2 的 TSL 1.0 客戶，那麼您應該計劃將網域/基礎架構轉移到 TLS 1.2。我們將繼續支援 TLS 1.0 通訊協定，直到 2020 年 2 月為止。自 2020 年 2 月起，Target 將不支援透過增強體驗撰寫器功能用於 VEC 的 TLS 1.0 通訊協定。

雖然我們強烈建議大家繼續使用 TLS 1.2，不過如果您是新客戶但&#x200B;*不*&#x200B;支援 TLS 1.2，請聯絡客戶服務，告知他們您需要針對增強體驗撰寫器使用 TLS 1.0。但是，請務必計劃轉移到 TLS 1.2，因為 2020 年 2 月之後將不再為 TLS 1.0 提供支援。

## Activity delivery {#section_46CA5943E4354B259014C2BF340AECD6}

自 2020 年 2 月起，Target 伺服器將不再支援 TLS 1.0。透過此變更，Target 伺服器將不再接受來自使用舊裝置或不支援 TLS 1.1 或更新版本之網頁瀏覽器的一般使用者請求。因此，僅支援 TLS 1.0 (或預設支援 TLS 1.0) 的舊裝置和瀏覽器將不會從 Adobe Target 接收活動內容。將呈現該網站的預設內容。

一些受影響的舊裝置和瀏覽器包括:

* Android 4.3 和之前版本
* Windows 7 上的 Internet Explorer 8-10 和之前版本
* Windows Phone 8.0 上的 Internet Explorer 10
* Safari 6.0.4/OS X10.8.4 和之前版本

在您計劃此變更時，請考慮以下事項 (請注意，2020 年 2 月截止日期會影響所有這些項目):

* 確保預設網站適用於相容裝置和瀏覽器。
* 請注意，Target 報表中的訪客數量可能顯著下降。
* 您可能需要對專門為鎖定舊裝置為目標或不支援 TLS 1.0 的瀏覽器所建立的對象進行變更 - 傳送到這些裝置和瀏覽器的內容將無法再運。

如需有關支援瀏覽器及其版本的詳細資訊，請參閱[受支援的瀏覽器](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)。

## Adobe Target API {#section_88797FA5434049EC89F908853CC76903}

自 2020 年 2 月起，Target API 不再支援 TLS 1.0 加密。存取該 API 的客戶應確認他們不會受到影響。

* 使用具有預設設定之 Java 7 的 API 用戶端將需要修改以支援 TLS 1.2。如需詳細資訊，請參閱 Java 網站上的[變更用戶端端點的預設 TLS 通訊協定版本: TLS 1.0 到 TLS 1.2](https://www.java.com/en/configure_crypto.html)。
* 使用 Java 8 的 API 用戶端已預設為 TLS 1.2，應該不會受到影響。
* 使用其他架構的 API 用戶端需聯絡其供應商，以瞭解 TLS 1.2 支援的詳細資訊。

## Access to Experience Cloud Solutions interfaces {#section_748870ADE77B4CBEB18518DC784E64E5}

由於 Target Standard/Premium 介面要求使用[最新的網頁瀏覽器](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)，我們並未預見任何問題。如果您無法連接到 Target，則應該將瀏覽器升級到最新版本。

## How to check which TLS version your browser uses {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

若要使用Google Chrome檢查您網站上的TLS版本：

1. 在Chrome中開啟受影響的網站。
1. 從「色彩」選單（三個垂直橢圓）中，按一下「更多工具>開發人員工具」。

   ![Chrome Developer Tool](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. 開啟「安全性」標籤，然後檢查「連線：

   ![TLS版本詳細資訊](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>這些指示目前已發佈，可能會有所變更。 如果這些指示改變，快速網際網路搜尋應該會有所幫助。  其他瀏覽器也有類似的步驟。

## Expected behavior with browsers supporting TLS 1.0 Only {#section_B5DA97A34EF248EB927610A5DA71EF2F}

本節說明使用 at.js 或 mbox.js 實作時，僅支援 TLS 1.0 的瀏覽器會造成什麼情況。為了進行比較，本節也說明支援TLS 1.2的瀏覽器有何期待。

### 中央端點

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| at.js | 啟用 TLS 1.0 的瀏覽器:<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已下載 at.js 檔案。</li></ul> |
| mbox.js | 啟用 TLS 1.0 的瀏覽器:<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已下載 mbox.js 檔案。</li></ul> |

### 邊緣端點

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| at.js | 啟用 TLS 1.0 的瀏覽器:<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li><li>已提供預設內容。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已提供選件內容。</li></ul> |
| mbox.js | 啟用 TLS 1.0 的瀏覽器:<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li><li>已提供預設內容。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已提供選件內容</li></ul> |

### 以瀏覽器版本對象為目標的活動（Internet Explorer、6、7或8版）

>[!NOTE]
>
>對象停止運作。

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| at.js | 版本 10 以前的 Internet Explorer 版本不支援 at.js。 |
| mbox.js | 啟用 TLS 1.0 的瀏覽器:<ul><li>已提供預設內容。</li><li>未觸發任何 Target 要求。</li><li>未顯示任何主控台錯誤。</li><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已提供選件內容。</li></ul> |