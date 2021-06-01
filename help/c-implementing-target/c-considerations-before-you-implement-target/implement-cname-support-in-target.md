---
keywords: 用戶端服務；cname；憑證程式；規範名稱；cookie；憑證；amc;adobe托管憑證；digicert；網域控制驗證
description: 與Adobe客戶服務合作，在Adobe [!DNL Target] 中實作CNAME（規範名稱）支援，以處理廣告封鎖問題或ITP相關的Cookie原則。
title: 如何在Target中使用CNAME?
feature: 隱私權與安全性
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 1f27ebfb7fb4203558f4d10e5e98cced04a82f2b
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 1%

---

# CNAME和Target

與[!DNL Adobe]客戶服務合作以在[!DNL Adobe Target]中實作CNAME（規範名稱）支援的相關指示。 使用CNAME處理廣告封鎖問題或ITP相關（智慧型追蹤預防）Cookie原則。 若使用CNAME，會呼叫客戶擁有的網域，而非[!DNL Adobe]擁有的網域。

## 在Target中要求CNAME支援

1. 決定您SSL憑證所需的主機名稱清單（請參閱下方的常見問題集）。

1. 對於每個主機名稱，在DNS中建立CNAME記錄，指向一般的[!DNL Target]主機名稱`clientcode.tt.omtrdc.net`。

   例如，如果您的用戶端代碼為「cnamecustomer」，而您建議的主機名稱為`target.example.com`，則您的DNS CNAME記錄看起來類似：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Adobe的憑證授權單位DigiCert必須完成此步驟，才能核發憑證。 因此，在此步驟完成之前，[!DNL Adobe]無法完成您的CNAME實作要求。

1. [請填寫下](/help/assets/FPC_Request_Form.xlsx) 清單格，並在您開啟Adobe [客戶服務票證要求CNAME支援時加入](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe[!DNL Target]客戶端代碼：
   * SSL憑證主機名稱(範例：`target.example.com target.example.org`):
   * SSL憑證購買者(強烈建議使用Adobe，請參閱常見問題集):Adobe/客戶
   * 如果客戶購買憑證(也稱為「自攜憑證」(BYOC))，請填寫以下額外詳細資訊：
      * 憑證組織(範例：範例Company Inc):
      * 憑證組織單位(選用，範例：行銷):
      * 憑證國家（地區）(範例：美國):
      * 憑證狀態/地區(範例：加州):
      * 憑證城市(範例：聖荷西):

1. 如果[!DNL Adobe]購買憑證，[!DNL Adobe]會與DigiCert合作，購買憑證並部署至Adobe的生產伺服器。

   如果客戶購買憑證(BYOC),[!DNL Adobe]客戶服務會將憑證簽署請求(CSR)傳送給您。 透過您選擇的憑證授權單位購買憑證時，請使用CSR。 核發憑證後，請將憑證副本和任何中繼憑證傳送至[!DNL Adobe]客戶服務以進行部署。

   [!DNL Adobe] 客戶服務會在您的實作準備就緒時通知您。

1. 將`serverDomain`更新為at.js中的新CNAME。

## 常見問題

以下資訊回答了在[!DNL Target]中請求和實作CNAME支援的常見問題：

### 我可以提供自己的憑證（自攜憑證或BYOC）嗎？

您可以提供自己的憑證。 不過，[!DNL Adobe]不建議此作法。 對於[!DNL Adobe]和您（如果[!DNL Adobe]購買並控制憑證），管理SSL憑證生命週期會更輕鬆。 SSL憑證必須每年續約。 因此，[!DNL Adobe]客戶服務必須每年聯絡您，以及時取得新憑證。 有些客戶無法及時產生續約的憑證。 憑證過期時，由於瀏覽器拒絕連線，導致[!DNL Target]實作受到損害。

>[!IMPORTANT]
>
>若您要求[!DNL Target]自攜憑證CNAME實作，您每年須負責為[!DNL Adobe]客戶服務提供續約憑證。 若允許您的CNAME憑證在[!DNL Adobe]可部署續約的憑證之前過期，將導致您的特定[!DNL Target]實作中斷。

### 我的新SSL憑證要到期多久？

2020年9月1日之前簽發的證書為兩年證書。 2020年9月1日或之後簽發的證書為一年期證書。 您可以在[此處](https://www.digicert.com/position-on-1-year-certificates)閱讀更多有關移至一年期憑證的資訊。

### 我應選擇哪些主機名稱？ 我應選擇每個網域的主機名稱數？

[!DNL Target] CNAME實作在SSL憑證和客戶的DNS中，每個網域僅需一個主機名稱。Adobe建議一個主機名。 有些客戶為了自己的目的（例如在測試環境中進行測試），需要每個網域更多主機名稱，這是受支援的。

大部分客戶選擇主機名，如`target.example.com`。 Adobe建議您遵循此作法，但最終由您選擇。 請不要求現有DNS記錄的主機名。 這樣會導致衝突並延遲[!DNL Target] CNAME請求的解決時間。

### 我已有[!DNL Adobe Analytics]的CNAME實作，可以使用相同的憑證或主機名稱嗎？

否， [!DNL Target]需要單獨的主機名和證書。

### 我目前的[!DNL Target]實作是否受到ITP 2.x影響？

在 Safari 瀏覽器中，導覽至您擁有 [!DNL Target] JavaScript 程式庫的網站。如果您在CNAME的內容中看到[!DNL Target] Cookie設定（例如`analytics.company.com`），則表示您未受到ITP 2.x的影響。

[!DNL Target]只需[!DNL Analytics] CNAME，即可解決ITP問題。 在[!DNL Target]遭到封鎖的廣告封鎖案例中，您僅需要個別的[!DNL Target] CNAME。

如需ITP的詳細資訊，請參閱[Apple智慧型追蹤預防(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### 部署CNAME實作時，我會預期會發生哪種服務中斷？

部署憑證時不會造成服務中斷（包括憑證續約）。

不過，當您將[!DNL Target]實作程式碼中的主機名稱（at.js中的`serverDomain`）變更為新的CNAME主機名稱(`target.example.com`)後，網頁瀏覽器會將再度訪問的訪客視為新訪客。 舊訪客的設定檔資料遺失，因為舊主機名稱(`clientcode.tt.omtrdc.net`)下無法存取先前的Cookie。 由於瀏覽器安全模型，無法存取先前的Cookie。 此中斷僅發生在新CNAME的初始切換上。 憑證續約沒有相同的效果，因為主機名稱不會變更。

### 我的CNAME實作使用哪種金鑰類型和憑證簽名演算法？

預設情況下，所有憑證均為RSA SHA-256，金鑰為RSA 2048位元。 目前不支援大於2048位元的金鑰大小。

### 如何驗證CNAME實作是否已準備好迎接流量？

使用下列命令集（在macOS或Linux命令列終端中，使用bash和curl 7.49+）:

1. 將此bash函式貼入您的終端機：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 貼上此命令（將`target.example.com`替換為主機名）:

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果實作已就緒，您會看到如下的輸出。 重要部分是所有行都包含`CN=target.example.com`，這些行與所需的主機名匹配。 如果有任何行包含`CN=*.tt.omtrdc.net`，則實施為&#x200B;**not**&#x200B;就緒。

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge36.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. 使用另一個curl請求驗證您的新DNS CNAME，該請求也應顯示`CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >如果此命令失敗，但上述`validateEdgeFpsslSni`命令成功，請等待DNS更新完全傳播。 DNS記錄具有關聯的[TTL（存留時間）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)，它規定這些記錄的DNS答復的快取過期時間。 因此，您至少需要等候TTL。 您可以使用`dig target.example.com`命令或[G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME)來尋找您的特定TTL。

### 如何搭配CNAME使用選擇退出連結

如果您使用CNAME，選擇退出連結應包含&quot;client=`clientcode`參數，例如：
`https://my.cname.domain/optout?client=clientcode`。

將`clientcode`取代為您的用戶端代碼，然後新增要連結至[選擇退出URL](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC)的文字或影像。

## 已知限制

* 如果您有CNAME和at.js 1.x,QA模式就不會有黏性，因為它是以協力廠商Cookie為基礎。 因應措施是將預覽參數新增至您導覽至的每個URL。 如果您有CNAME和at.js 2.x,QA模式就會有黏性。
* 目前，使用at.js 1.8.2和at.js 2.3.1之前的at.js版本時，`overrideMboxEdgeServer`設定無法正常運作。如果您使用的是舊版at.js，應將此設定設為`false`，以避免請求失敗。 或者，您也應該考慮將at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)更新至較新的支援版本。[
* 使用CNAME時，[!DNL Target]呼叫的Cookie標題大小可能會增加。 [!DNL Adobe] 建議將cookie大小保持在8 KB以下。
