---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: 有關使用 Adobe 客戶服務在 Adobe Target 中實作 CNAME (規範名稱) 支援的資訊。
title: CNAME 與 Adobe Target
feature: privacy and security
translation-type: tm+mt
source-git-commit: 677d5ed16377fc32b4506ca736084319e5643e67
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 2%

---


# CNAME 與 Adobe Target {#cname-and-adobe-target}

與Adobe Client Care合作以在[!DNL Adobe Target]中實作CNAME（標準名稱）支援的指示。 為了最好地處理廣告封鎖問題或ITP相關Cookie政策，會使用CNAME，以便對客戶所擁有的網域進行呼叫，而非對Adobe所擁有的網域進行呼叫。

## 要求CNAME支援

請執行下列步驟以要求[!DNL Target]中的CNAME支援：

1. 確定您的SSL憑證需要的主機名稱清單（請參閱常見問答集）。

1. 對於每個主機名稱，在DNS中建立指向一般[!DNL Target]主機名稱`clientcode.tt.omtrdc.net`的CNAME記錄。

   例如，如果您的客戶代碼是「客戶」，而您建議的主機名稱是`target.example.com`，則您的DNS CNAME記錄應該如下所示：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >Adobe的認證授權機構DigiCert必須等到此步驟完成後，才能核發認證。 因此，Adobe必須等到此步驟完成後，才能完成您對CNAME實作的要求。

1. [請填寫此](https://experienceleague.adobe.com/docs/core-services/assets/FPC_Request_Form.xlsx?lang=en) 表格，並在您開啟要求CNAME [支援的Adobe Client Care票證時加入此表格](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe [!DNL Target]用戶端代碼：
   * SSL憑證主機名稱(範例：`target.example.com target.example.org`):
   * SSL憑證購買者（強烈建議使用Adobe，請參閱常見問答集）:Adobe/客戶
   * 如果客戶購買憑證（亦即BYOC），請填寫下列其他詳細資訊：
      * 憑證組織(範例：範例公司):
      * 證書組織單位(可選，例如：行銷):
      * 憑證國家(範例：美國):
      * 憑證狀態／地區(範例：加州):
      * 認證城市(範例：聖荷西):

1. 如果Adobe要購買憑證，Adobe將與DigiCert合作，在Adobe的生產伺服器上購買及部署您的憑證。

   如果客戶購買憑證(BYOC),Adobe客戶服務會傳送憑證簽署要求(CSR)給您，當您透過您選擇的憑證授權機構購買憑證時，需要使用此要求。 在核發憑證後，您必須將憑證副本和任何中間憑證傳回Adobe Client Care以進行部署。

   當您的實作準備就緒時，Adobe Client Care會通知您。

1. 完成上述工作後，Adobe Client Care已通知您實作已就緒，您必須將`serverDomain`更新為at.js中的新CNAME。

## 常見問題

以下資訊可回答有關在[!DNL Target]中請求及實作CNAME支援的常見問題：

### 我是否可提供我自己的憑證（又稱為攜帶您自己的憑證或BYOC）?

是的，您可以提供您自己的憑證；但不建議使用。 Adobe和您在購買及控制憑證時，SSL憑證生命週期的管理會變得更輕鬆。 SSL憑證必須每年更新一次，這表示Adobe Client Care必須每年與您聯絡，以便及時傳送新憑證給Adobe。 有些客戶可能每年都無法及時產生續約的憑證，這會危及其[!DNL Target]實作，因為當憑證過期時，瀏覽器會拒絕連線。

>[!IMPORTANT]
>
>請注意，如果您要求[!DNL Target]攜帶您自己的憑證CNAME實作，您有責任每年向Adobe Client Care提供續約的憑證。 若您的CNAME憑證在Adobe部署續約的憑證之前到期，將會導致您的特定[!DNL Target]實作中斷。

### 新SSL憑證到期的時間？

2020年9月1日前核發的證書為兩年期證書。 2020年9月1日或之後簽發的證書為一年期證書。 您可閱讀更多有關移至一年期憑證[的資訊，請參閱](https://www.digicert.com/position-on-1-year-certificates)。

### 我應選擇哪些主機名？ 我應選擇每個網域的主機名？

[!DNL Target] CNAME實作在SSL憑證和客戶的DNS中，每個網域只需要一個主機名稱，因此我們建議您這麼做。有些客戶可能會要求每個網域額外的主機名稱，以用於自己的用途（例如在測試階段中測試），這是受支援的。

大多數客戶都選擇像`target.example.com`這樣的主機名稱，因此我們建議這麼做，但最終選擇的是您。 請務必不要請求現有DNS記錄的主機名稱，因為這會導致[!DNL Target] CNAME請求的解決衝突和延遲時間。

### 我已經有[!DNL Adobe Analytics]的CNAME實作，我們是否可以使用相同的憑證或主機名稱？

否，[!DNL Target]需要個別的主機名和證書。

### 我目前的Target實作是否受ITP 2.x影響？

在Safari瀏覽器中，導覽至您有Target JavaScript程式庫的網站。 如果您在CNAME（例如`analytics.company.com`）的內容中看到Target Cookie設定，則不會受到ITP 2.x的影響。

只需Analytics CNAME，就可解決Target的ITP問題。 只有在廣告封鎖藍本遭封鎖時，您才需要個別的Target CNAME。

如需ITP的詳細資訊，請參閱[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### 部署CNAME實作時，我可能會預期發生何種服務中斷？

在部署憑證時（包括憑證續約），不會中斷服務。 不過，當您將[!DNL Target]實作程式碼（at.js中的`serverDomain`）中的主機名稱變更為新的CNAME主機名稱(`target.example.com`)時，網頁瀏覽器會將舊訪客視為新訪客，其描述檔資料將會遺失，因為舊主機名稱(`clientcode.tt.omtrdc.net`)下的舊Cookie將因瀏覽器安全性模型而無法存取。 只有在初次切換新CNAME時，才會發生一次中斷。 憑證續約沒有相同的效果，因為主機名稱並未變更。

### 我的CNAME實作會使用何種金鑰類型和憑證簽名演算法？

預設情況下，所有證書都是RSA SHA-256 ，密鑰是RSA 2048位。 目前不支援大於2048位元的金鑰大小。

### 如何驗證我的CNAME實作已準備好進行流量？

使用下列命令集（在MacOs或Linux命令列終端中，使用bash和curl 7.49+）:

1. 首先將此bash函式貼上到終端：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 下一步貼上此命令（將`target.example.com`取代為您的主機名稱）:

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果實作已就緒，您應該會看到如下輸出。 重要部分是所有行都顯示`CN=target.example.com` ，這與我們所需的主機名匹配。 如果其中任何一個顯示`CN=*.tt.omtrdc.net`，則實施為&#x200B;**not**&#x200B;就緒。

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
   >如果此命令失敗，但上述`validateEdgeFpsslSni`命令成功，則可能需要等待DNS更新完全傳播。 DNS記錄具有關聯的[TTL（存留時間）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)，該&lt;a1/>規定了這些記錄的DNS回覆的快取過期時間，因此您至少需要等待TTL。 您可以使用`dig target.example.com`命令或[G套件工具箱](https://toolbox.googleapps.com/apps/dig/#CNAME)來查找特定TTL。

## 已知限制

* 當您有CNAME和at.js 1.x時，QA模式將不會自黏，因為它是以第三方Cookie為基礎。 因應措施是將預覽參數新增至您導覽至的每個URL。 當您有CNAME和at.js 2.x時，QA模式會很嚴格。
* 目前，當使用at.js 1.8.2和at.js 2.3.1之前的at.js版本時，`overrideMboxEdgeServer`設定無法與CNAME搭配運作。如果您使用舊版at.js，應將此設定為`false`以避免請求失敗。 或者，您應考慮將at.js[更新為較新、支援的版本。](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)
* 使用CNAME時，Target呼叫的Cookie標題大小可能會增加。 我們建議將Cookie大小維持在8KB以下。
