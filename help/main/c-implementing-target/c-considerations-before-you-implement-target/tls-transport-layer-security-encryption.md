---
keywords: tls;tls 1.0；傳輸層安全性；加密；tls 1.1;tls 1.2
description: 瞭解如何 [!DNL Target] 使用TLS（傳輸層安全性）協定來維護最高的安全標準並提升客戶資料的安全性。
title: 如何 [!DNL Target] 使用TLS提供安全性？
feature: Privacy & Security
role: Developer
exl-id: 964a642a-830a-4556-a92a-d300670cd2fa
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 54%

---

# TLS (傳輸層安全性) 加密變更

有關更改方式的資訊 [!DNL Adobe] 和 [!DNL Adobe Target] 使用TLS（傳輸層安全性）來維護最高的安全標準並提升客戶資料的安全性。

傳輸層安全性 (TLS) 是目前針對須透過網路安全交換資料的網頁瀏覽器和其他應用程式，部署最廣泛的安全通訊協定。Adobe 安全性法規遵循標準規定須結束支援舊版通訊協定，並強制採用 TLS 1.2，以使用最新、最安全的版本。

>[!IMPORTANT]
>
>2020年3月1日之後，Adobe Target將不再支援Visual Experience Composer(VEC)、Enhanced Experience Composer(EEC)、活動傳遞、API等的TLS 1.1加密。 請在2020年3月1日之前升級到TLS 1.2以避免任何問題。

我們預計這不會對客戶資料或報告造成重大影響。

## 具有已啟用增強體驗撰寫器 (EEC) 的可視化體驗撰寫器 (VEC) {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

自2020年3月1日起，TLS 1.2為預設值，不再支援TLS 1.1。

Adobe 會分階段將客戶轉移至 TLS 1.2。對於那些已經符合 1.2 規範之網域的使用者，我們會將其轉移至 TLS 1.2，無需進行任何變更。大多數客戶域已支援TLS 1.2;但是，如果您的域不支援TLS 1.2，我們將像今天一樣（直到2020年3月）將這些域保持在TLS 1.1上。

在此移轉階段，您應該不會遇到任何問題。如果 VEC 已停止載入之前尚能運作的網站，[請開啟「客戶服務」票證](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，說明移轉作業可能為背後原因。

但是，如果您是TSL 1.1上的客戶之一，而不支援TLS 1.2，則您應計畫將域/基礎架構移動到TLS 1.2。我們將繼續支援TLS 1.1協定，直到2020年3月1日。 從2020年3月1日起，Target將不支援通過增強體驗作曲家功能用於VEC的TLS 1.1協定。

雖然我們強烈建議大家繼續使用 TLS 1.2，不過如果您是新客戶但&#x200B;*不*&#x200B;支援 TLS 1.2，請聯絡客戶服務，告知他們您需要針對增強體驗撰寫器使用 TLS 1.1。但是，請計畫轉到TLS 1.2，因為您在2020年3月1日之後將不受支援。

## 活動交付 {#section_46CA5943E4354B259014C2BF340AECD6}

從2020年3月1日起，目標伺服器將不再支援TLS 1.1。通過此更改，目標伺服器將不再接受使用舊設備或不支援TLS 1.2（或更高版本）的Web瀏覽器的訪問者的請求。 因此，僅支援 TLS 1.1 (或預設支援 TLS 1.1) 的舊裝置和瀏覽器將不會從 Adobe Target 接收活動內容。將呈現該網站的預設內容。

一些受影響的舊裝置和瀏覽器包括:

* GoogleChrome(Chrome for Android)29版及更早版本
* Opera Browser(Opera Mobile)12.17版及更低版本
* Mozilla Firefox(Firefox for Mobile)26版及更早版本
* Android 4.3 和之前版本
* Windows 7 上的 Internet Explorer 8-10 和之前版本
* Windows Phone 8.0 上的 Internet Explorer 10
* Safari 6.0.4/OS X10.8.4 和之前版本

在計畫進行此更改時，請考慮以下事項（請注意，2020年3月1日的截止日期會影響所有這些項目）:

* 確保預設網站適用於相容裝置和瀏覽器。
* 請注意，Target 報表中的訪客數量可能顯著下降。
* 您可能需要更改專門為不支援TLS 1.2的較舊設備或瀏覽器建立的訪問群體。向這些設備和瀏覽器提供服務將不再有效。

有關支援的瀏覽器及其版本的詳細資訊，請參見 [支援的瀏覽器](/help/main/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)。

## Adobe [!DNL Target] API {#section_88797FA5434049EC89F908853CC76903}

從2020年3月1日起，目標API將不再支援TLS 1.1加密。 存取該 API 的客戶應確認他們不會受到影響。

* 使用具有預設設定之 Java 7 的 API 用戶端將需要修改以支援 TLS 1.2。如需詳細資訊，請參閱 Java 網站上的[變更用戶端端點的預設 TLS 通訊協定版本: TLS 1.0 到 TLS 1.2](https://www.java.com/en/configure_crypto.html)。
* 使用 Java 8 的 API 用戶端已預設為 TLS 1.2，應該不會受到影響。
* 使用其他架構的 API 用戶端需聯絡其供應商，以瞭解 TLS 1.2 支援的詳細資訊。

## 訪問Experience Cloud解決方案介面 {#section_748870ADE77B4CBEB18518DC784E64E5}

由於 Target Standard/Premium 介面要求使用[最新的網頁瀏覽器](/help/main/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)，我們並未預見任何問題。如果您無法連接到 Target，則應該將瀏覽器升級到最新版本。

## 如何檢查瀏覽器使用的TLS版本 {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

要使用GoogleChrome檢查您網站上的TLS版本：

1. 在Chrome中開啟受影響的網站。
1. 在「鉻色」菜單（三個垂直橢圓）中，按一下「更多工具」>「開發人員工具」。

   ![Chrome Developer Tool](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. 開啟「安全」頁籤，然後檢查「連接：

   ![TLS版本詳細資訊](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>這些說明在發佈時是最新的，可能會發生更改。 如果這些說明發生變化，快速進行網際網路搜索應會有所幫助。  其他瀏覽器也有類似的步驟。

## 支援1.2以下TLS版本的瀏覽器的預期行為 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

本節介紹僅在使用at.js實現時，支援1.2以下TLS版本的瀏覽器所期望的。 為了進行比較，本節還介紹支援TLS 1.2的瀏覽器的預期。

### 中心端點

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| at.js | 啟用TLS 1.0或TLS 1.1時：<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已下載 at.js 檔案。</li></ul> |

### 邊端點

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | 啟用TLS 1.0或TLS 1.1時：<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li><li>已提供預設內容。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已提供選件內容。</li></ul> |
| at.js | 啟用TLS 1.0或TLS 1.1時：<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li><li>已提供預設內容。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已提供選件內容。</li></ul> |

### 針對瀏覽器版本訪問群體的活動（Internet Explorer、6、7或8版）

>[!NOTE]
>
>對象停止運作。

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | 早於10版的Internet Explorer版本不支援平台SDK。 |
| at.js | 版本 10 以前的 Internet Explorer 版本不支援 at.js。 |
