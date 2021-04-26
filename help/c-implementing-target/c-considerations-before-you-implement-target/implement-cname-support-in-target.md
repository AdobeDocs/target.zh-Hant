---
keywords: client care;cname;certificate program；正則名稱；cookies;certificate;amc;adobe受管理證書；digicert；域控制驗證；dcv
description: 與AdobeClient Care合作，在Adobe [!DNL Target] 中實作CNAME（標準名稱）支援，以處理廣告封鎖問題或與ITP相關的Cookie政策。
title: 如何在Target中使用CNAME?
feature: 隱私權與安全性
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
translation-type: tm+mt
source-git-commit: 85a17944c7d5924edb1bbabb7531274249ceaaa8
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 2%

---

# CNAME 與 Adobe Target

使用[!DNL Adobe] Client Care在[!DNL Adobe Target]中實作CNAME（標準名稱）支援的指示。 使用CNAME來處理廣告封鎖問題或ITP相關（智慧追蹤防範）Cookie政策。 使用CNAME，會呼叫客戶所擁有的網域，而非[!DNL Adobe]所擁有的網域。

## 在Target中要求CNAME支援

1. 確定您的SSL憑證需要的主機名稱清單（請參閱以下常見問答集）。

1. 對於每個主機名稱，在DNS中建立指向一般[!DNL Target]主機名稱`clientcode.tt.omtrdc.net`的CNAME記錄。

   例如，如果您的客戶代碼是「客戶」，而您建議的主機名稱是`target.example.com`，則您的DNS CNAME記錄看起來類似：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Adobe的認證授權機構DigiCert在完成此步驟之前無法核發認證。 因此，[!DNL Adobe]在此步驟完成前無法完成您對CNAME實作的要求。

1. [填寫此](/help/assets/FPC_Request_Form.xlsx) 表格，並在您開啟Adobe [客戶服務票證以要求CNAME支援時加入](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe[!DNL Target]客戶端代碼：
   * SSL憑證主機名稱(範例：`target.example.com target.example.org`):
   * SSL憑證購買者(強烈建議Adobe，請參閱常見問答集):Adobe/客戶
   * 如果客戶購買的憑證也稱為「攜帶您自己的憑證」(BYOC)，請填寫下列其他詳細資訊：
      * 憑證組織(範例：範例公司):
      * 證書組織單位(可選，例如：行銷):
      * 憑證國家(範例：美國):
      * 憑證狀態／地區(範例：加州):
      * 認證城市(範例：聖荷西):

1. 如果[!DNL Adobe]正在購買憑證，[!DNL Adobe]會與DigiCert合作，在Adobe的生產伺服器上購買和部署憑證。

   如果客戶購買憑證(BYOC),[!DNL Adobe]客戶服務會傳送憑證簽署要求(CSR)給您。 透過您選擇的認證授權機構購買認證時，請使用CSR。 核發憑證後，請將憑證副本和任何中介憑證傳送至[!DNL Adobe] Client Care以進行部署。

   [!DNL Adobe] 當您的實作準備就緒時，Client Care會通知您。

1. 將`serverDomain`更新為at.js中的新CNAME。

## 常見問題

以下資訊可回答有關在[!DNL Target]中請求及實作CNAME支援的常見問題：

### 我是否可提供我自己的憑證（攜帶您自己的憑證或BYOC）?

您可以提供您自己的憑證。 但是，[!DNL Adobe]不建議使用此作法。 對於[!DNL Adobe]和您（如果[!DNL Adobe]購買並控制憑證），管理SSL憑證生命週期會更輕鬆。 SSL憑證必須每年更新一次。 因此，[!DNL Adobe]客戶服務部門必須每年與您聯絡，才能及時取得新的憑證。 有些客戶可能無法及時產生更新的憑證。 當憑證過期時，由於瀏覽器拒絕連線，您的[!DNL Target]實作會受到影響。

>[!IMPORTANT]
>
>如果您要求[!DNL Target]攜帶您自己的憑證CNAME實作，您每年都有責任為[!DNL Adobe]客戶服務提供續約的憑證。 允許您的CNAME憑證在[!DNL Adobe]部署續約的憑證前過期，會導致您特定[!DNL Target]實作中斷。

### 新SSL憑證到期的時間？

2020年9月1日前簽發的證書為兩年期證書。 2020年9月1日或之後簽發的證書為一年期證書。 您可閱讀更多有關移至一年期憑證[的資訊，請參閱](https://www.digicert.com/position-on-1-year-certificates)。

### 我應選擇哪些主機名？ 我應選擇每個網域的主機名？

[!DNL Target] CNAME實作在SSL憑證和客戶的DNS中，每個網域只需一個主機名稱。Adobe建議使用一個主機名。 有些客戶需要每個網域的主機名稱，以用於自己的用途（例如在測試階段中測試），這是受支援的。

大多數客戶都選擇像`target.example.com`這樣的主機名。 Adobe建議採用這種做法，但最終選擇由您決定。 請勿請求現有DNS記錄的主機名。 這麼做會造成衝突，並拖延解決[!DNL Target] CNAME要求的時間。

### 我已經有[!DNL Adobe Analytics]的CNAME實作，我們是否可以使用相同的憑證或主機名稱？

否，[!DNL Target]需要個別的主機名和證書。

### 我目前[!DNL Target]的實作是否受ITP 2.x影響？

在 Safari 瀏覽器中，導覽至您擁有 [!DNL Target] JavaScript 程式庫的網站。如果您在CNAME的內容中看到設定[!DNL Target] Cookie，例如`analytics.company.com`，則不會受到ITP 2.x的影響。

ITP問題可以在[!DNL Target]只有[!DNL Analytics] CNAME的情況下解決。 您只需在[!DNL Target]被封鎖的廣告封鎖藍本中使用個別的[!DNL Target] CNAME。

如需ITP的詳細資訊，請參閱[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### 部署CNAME實作時，我可能會預期發生何種服務中斷？

在部署憑證時（包括憑證續約），不會中斷服務。

不過，在您將[!DNL Target]實作程式碼（at.js中的`serverDomain`）中的主機名稱變更為新的CNAME主機名稱(`target.example.com`)後，網頁瀏覽器會將舊訪客視為新訪客。 舊訪客的描述檔資料會遺失，因為舊主機名稱(`clientcode.tt.omtrdc.net`)下無法存取先前的Cookie。 由於瀏覽器安全性模型，先前的Cookie無法存取。 此中斷僅發生在初次切換至新CNAME時。 憑證續約不會有相同的效果，因為主機名稱不會變更。

### 我的CNAME實作使用哪些金鑰類型和憑證簽名演算法？

預設情況下，所有證書都是RSA SHA-256 ，密鑰是RSA 2048位。 目前不支援大於2048位元的金鑰大小。

### 我要如何驗證我的CNAME實作是否已準備好進行流量？

使用下列命令集（在macOS或Linux命令列終端中，使用bash和curl 7.49+）:

1. 將此bash函式貼上到終端：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 貼上此命令（以您的主機名稱取代`target.example.com`）:

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果實作已就緒，您會看到如下輸出。 重要部分是所有行都包含`CN=target.example.com` ，它們與所需的主機名匹配。 如果有行包含`CN=*.tt.omtrdc.net`，則實施為&#x200B;**not**&#x200B;就緒。

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

1. 使用另一個捲動請求驗證您的新DNS CNAME，該請求也應顯示`CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >如果此命令失敗，但上述`validateEdgeFpsslSni`命令成功，請等待DNS更新完全傳播。 DNS記錄具有相關的[TTL（存留時間）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)，該指定了這些記錄的DNS回覆的快取過期時間。 因此，您可能需要等待至少TTL的時間。 您可以使用`dig target.example.com`命令或[G套件工具箱](https://toolbox.googleapps.com/apps/dig/#CNAME)來查找特定TTL。

## 已知限制

* 當您擁有CNAME和at.js 1.x時，QA模式不嚴格，因為它是以第三方Cookie為基礎。 因應措施是將預覽參數新增至您導覽至的每個URL。 當您有CNAME和at.js 2.x時，QA模式會很嚴格。
* 目前，當使用at.js 1.8.2和at.js 2.3.1之前的at.js版本時，`overrideMboxEdgeServer`設定無法與CNAME一起正常運作。如果您使用舊版at.js，應將此設定設為`false`，以避免請求失敗。 或者，您應考慮將at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)更新為較新、支援的版本。[
* 使用CNAME時，[!DNL Target]呼叫的Cookie標題大小可能會增加。 [!DNL Adobe] 建議將Cookie大小保持在8 KB以下。
