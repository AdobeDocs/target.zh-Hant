---
keywords: tls;tls 1.0；傳輸層安全性；加密；tls 1.1;tls 1.2
description: 了解如何 [!DNL Target] 使用TLS（傳輸層安全性）通訊協定來維持最高的安全標準，並提升客戶資料的安全性。
title: 如何 [!DNL Target] 使用TLS來提供安全性？
feature: 隱私權與安全性
role: Developer
exl-id: 964a642a-830a-4556-a92a-d300670cd2fa
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 54%

---

# TLS (傳輸層安全性) 加密變更

[!DNL Adobe]和[!DNL Adobe Target]如何使用TLS（傳輸層安全性）來維持最高安全標準並提升客戶資料安全性的相關變更資訊。

傳輸層安全性 (TLS) 是目前針對須透過網路安全交換資料的網頁瀏覽器和其他應用程式，部署最廣泛的安全通訊協定。Adobe 安全性法規遵循標準規定須結束支援舊版通訊協定，並強制採用 TLS 1.2，以使用最新、最安全的版本。

>[!IMPORTANT]
>
>2020年3月1日後，Adobe Target將不再支援可視化體驗撰寫器(VEC)、增強體驗撰寫器(EEC)、活動傳送、API等的TLS 1.1加密技術。 請在2020年3月1日之前升級至TLS 1.2，以避免出現任何問題。

我們預計這不會對客戶資料或報告造成重大影響。

## 具有已啟用增強體驗撰寫器 (EEC) 的可視化體驗撰寫器 (VEC) {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

自2020年3月1日起，預設為TLS 1.2，我們將不再支援TLS 1.1。

Adobe 會分階段將客戶轉移至 TLS 1.2。對於那些已經符合 1.2 規範之網域的使用者，我們會將其轉移至 TLS 1.2，無需進行任何變更。大部分的客戶網域已支援TLS 1.2;不過，若您的網域不支援TLS 1.2，我們將像今天一樣將這些網域保留在TLS 1.1上（直到2020年3月）。

在此移轉階段，您應該不會遇到任何問題。如果 VEC 已停止載入之前尚能運作的網站，[請開啟「客戶服務」票證](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，說明移轉作業可能為背後原因。

不過，若您是使用TSL 1.1但不支援TLS 1.2的客戶之一，則您應計畫將網域/基礎架構移動至TLS 1.2。我們將持續支援TLS 1.1通訊協定，直到2020年3月1日為止。 自2020年3月1日起，Target將不支援要透過增強體驗撰寫器功能用於VEC的TLS 1.1通訊協定。

雖然我們強烈建議大家繼續使用 TLS 1.2，不過如果您是新客戶但&#x200B;*不*&#x200B;支援 TLS 1.2，請聯絡客戶服務，告知他們您需要針對增強體驗撰寫器使用 TLS 1.1。不過，請計畫改用TLS 1.2，因為2020年3月1日以後將不再支援您。

## 活動傳送 {#section_46CA5943E4354B259014C2BF340AECD6}

自2020年3月1日起，Target伺服器將不再支援TLS 1.1。隨著此變更正式發佈，若訪客使用不支援TLS 1.2（或更新版本）的較舊裝置或網頁瀏覽器，Target伺服器將不再接受其要求。 因此，僅支援 TLS 1.1 (或預設支援 TLS 1.1) 的舊裝置和瀏覽器將不會從 Adobe Target 接收活動內容。將呈現該網站的預設內容。

一些受影響的舊裝置和瀏覽器包括:

* Google Chrome（Android專用Chrome）29版及舊版
* Opera Browser(Opera Mobile)12.17版及舊版
* Mozilla Firefox（行動版Firefox）26版及舊版
* Android 4.3 和之前版本
* Windows 7 上的 Internet Explorer 8-10 和之前版本
* Windows Phone 8.0 上的 Internet Explorer 10
* Safari 6.0.4/OS X10.8.4 和之前版本

在您計畫進行此變更時，請考量下列事項（請注意，2020年3月1日的截止日期會影響所有這些項目）:

* 確保預設網站適用於相容裝置和瀏覽器。
* 請注意，Target 報表中的訪客數量可能顯著下降。
* 您可能需要變更專為鎖定不支援TLS 1.2之舊裝置或瀏覽器而建立的對象。傳送至這些裝置和瀏覽器的功能將無法繼續運作。

如需深入了解所支援的瀏覽器及其版本，請參閱[支援的瀏覽器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)。

## Adobe[!DNL Target] API {#section_88797FA5434049EC89F908853CC76903}

自2020年3月1日起，Target API將不再支援TLS 1.1加密技術。 存取該 API 的客戶應確認他們不會受到影響。

* 使用具有預設設定之 Java 7 的 API 用戶端將需要修改以支援 TLS 1.2。如需詳細資訊，請參閱 Java 網站上的[變更用戶端端點的預設 TLS 通訊協定版本: TLS 1.0 到 TLS 1.2](https://www.java.com/en/configure_crypto.html)。
* 使用 Java 8 的 API 用戶端已預設為 TLS 1.2，應該不會受到影響。
* 使用其他架構的 API 用戶端需聯絡其供應商，以瞭解 TLS 1.2 支援的詳細資訊。

## 存取Experience Cloud解決方案介面 {#section_748870ADE77B4CBEB18518DC784E64E5}

由於 Target Standard/Premium 介面要求使用[最新的網頁瀏覽器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)，我們並未預見任何問題。如果您無法連接到 Target，則應該將瀏覽器升級到最新版本。

## 如何檢查您的瀏覽器使用的TLS版本 {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

若要使用Google Chrome檢查您網站上的TLS版本：

1. 在Chrome中開啟受影響的網站。
1. 從Chrome功能表（三個垂直的點），按一下「更多工具>開發人員工具」。

   ![Chrome Developer Tool](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. 開啟「安全性」標籤，然後檢查「連線：

   ![TLS版本詳細資訊](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>這些指示在發佈時為最新狀態，可能會有所變更。 如果這些指示發生更改，快速網際網路搜索應該會有所幫助。  其他瀏覽器則有類似步驟。

## 支援1.2以下TLS版本的瀏覽器的預期行為 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

本節說明只有使用at.js實作時，才支援1.2以下TLS版本的瀏覽器會有何期望。 為了比較目的，本節也說明支援TLS 1.2的瀏覽器有何期望。

### 中央端點

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| at.js | 啟用TLS 1.0或TLS 1.1時：<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已下載 at.js 檔案。</li></ul> |

### 邊緣端點

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | 啟用TLS 1.0或TLS 1.1時：<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li><li>已提供預設內容。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已提供選件內容。</li></ul> |
| at.js | 啟用TLS 1.0或TLS 1.1時：<ul><li>若使用瀏覽器開發人員工具，你將會在「網路」標籤上看到「200 OK」。這表示要求已成功。</li><li>使用者會看到「無法安全地連線至此頁面」訊息。此訊息說明這可能是由於網站使用了過期或不安全的 TLS 安全性設定。</li><li>未顯示任何主控台錯誤。</li><li>已提供預設內容。</li></ul>啟用 TLS 1.2 的瀏覽器:<ul><li>已提供選件內容。</li></ul> |

### 以瀏覽器版本對象為目標的活動（Internet Explorer、6、7或8版）

>[!NOTE]
>
>對象停止運作。

| Target JavaScript 實作 | 詳細資料 |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | Internet Explorer 10版之前的版本不支援Platform SDK。 |
| at.js | 版本 10 以前的 Internet Explorer 版本不支援 at.js。 |
