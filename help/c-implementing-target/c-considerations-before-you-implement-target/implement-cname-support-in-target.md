---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: 有關使用 Adobe 客戶服務在 Adobe Target 中實作 CNAME (規範名稱) 支援的資訊。
title: CNAME 與 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 8267de6c27566ec397651d3bfc88aad0818ed8d2

---


# CNAME 與 Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 為了最好地處理廣告封鎖問題或ITP相關Cookie政策，會使用CNAME，以便對客戶所擁有的網域進行呼叫，而非對Adobe所擁有的網域進行呼叫。

## 要求CNAME支援

Perform the following steps to request CNAME support in [!DNL Target]:

1. Adobe的認證授權機構(DigiCert)需要確認Adobe是否已授權在您的網域下產生認證。

   DigiCert會呼叫此程式 [網域控制驗證(DCV)](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/)，而且在至少下列其中一個DCV方法完成此程式之前，Adobe將不得在您的網域下產生憑證：

   * 最快速的DCV方法是 __DNS CNAME方法__，您可在其中新增DNS CNAME記錄（包含Token）至指向DigiCert DCV主機名稱(dcv.digicert.com)的網域。 此CNAME記錄會向DigiCert指出Adobe已獲得授權，可產生憑證。 Adobe Client Care會將指示與必要的DNS記錄一併傳送給您。 例如：

      ```
      3b0332e02daabf31651a5a0d81ba830a.target.example.com.  IN  CNAME  dcv.digicert.com.
      ```

      >[!NOTE]
      >
      >這些DCV Token會在30天後到期，Adobe Client Care會隨時與您聯絡更新的Token。 為了盡快解決您的CNAME要求，請在提交您的要求前，先準備對所有要求的網域進行這些DNS變更。

      >[!NOTE]
      >
      >如果您的網域有 [DNS CAA記錄](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization)，則您需要新增 `digicert.com` （如果尚未新增）。 此DNS記錄會指出哪些認證授權機構已授權為網域發行認證。 產生的DNS記錄如下所示： `example.com. IN CAA 0 issue "digicert.com"`。 您可以使 [用G Suite工具箱](https://toolbox.googleapps.com/apps/dig/#CAA) ，判斷您的根網域是否有現有的CAA記錄。 您可以在這裡閱讀更多有關DigiCert如何處理CAA記 [錄](https://docs.digicert.com/manage-certificates/dns-caa-resource-record-check)。

   * DigiCert也會嘗試電子郵件方 __法__，在此方法中，他們會傳送電子郵件至網域的WHOIS資訊中找到的位址，以及預先決定的電子郵件地址(管理員、管理員、網站管理員、主機管理員和郵遞員 `@[domain_name]`)。 如需詳細 [資訊，請參閱DCV方法檔案](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) 。

      為加速DCV電子郵件程式，DigiCert提供下列建議：

      「請確認您的註冊/WHOIS提供者未蒙蔽或移除相關 [的電子郵件地址]。 如果是，請瞭解他們是否提供方式（例如匿名電子郵件地址、網頁表格）讓您允許認證授權機構 [] ，存取您網域的WHOIS資料。」

1. 在網域的DNS上建立指向一般主機名稱的CNAME記錄 `clientcode.tt.omtrdc.net`。 例如，如果您的客戶代碼是客戶代碼，而您建議的主機名 `target.example.com`稱是，則您的DNS CNAME記錄應該如下所示：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. 開啟 [Adobe Client Care票證，要求您呼叫的CNAME](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) 支 [!DNL Target] 援。

   Adobe將與DigiCert合作，在Adobe的生產伺服器上購買及部署您的憑證。 DigiCert將啟動DCV程式，當您的實作準備就緒時，Adobe Client Care會通知您。

1. 完成上述工作後，Adobe Client Care已通知您實作已就緒，您必須在at.js中將 `serverDomain` 更新為新的CNAME。

## 常見問題

下列資訊可回答有關在中要求和實作CNAME支援的常見問題 [!DNL Target]:

### 我是否可提供我自己的憑證（又稱攜帶您自己的憑證，亦稱BYOC）? 如果是，程式是什麼？

是的，您可以提供您自己的憑證，但 __不建議使用__。 當Adobe購買並控制憑證時，Adobe和客戶都能更輕鬆地管理SSL憑證生命週期。 SSL憑證需要每年更新一次，這表示Adobe Client Care必須每年與您聯絡，才能及時傳送新憑證給Adobe。 有些客戶可能每年都無法及時產生更新的憑證，這會危及其實作，因為當憑證過期時， [!DNL Target] 瀏覽器會拒絕連線。

>[!NOTE]
>
>請注意，如果您要求實 [!DNL Target] 施攜帶自有憑證的CNAME，您每年將負責為Adobe Client Care提供續約憑證。 若您的CNAME憑證在Adobe部署續約的憑證之前到期，將會導致您的特定實作中斷 [!DNL Target] 運作。

1. 略過上述步驟1，但完成步驟2和3。 當您開啟Adobe Client Care票證（步驟3）時，請通知他們您將提供您自己的憑證。

   Adobe會產生並傳送憑證簽署要求(CSR)給您。

1. 使用CSR透過您選擇的認證授權機構(CA)購買認證。

1. 傳送新的公開憑證至Adobe。 Adobe代表將會將公開憑證部署在其生產伺服器上。

1. 在Adobe Client Care通知您實作已就緒後，完成步驟4。

### 新SSL憑證到期的時間？

2020年9月1日前核發的證書為2年期證書。 2020年9月1日及之後簽發的證書為1年證書。 您可以在這裡閱讀更多有關改用1年證書的 [資訊](https://www.digicert.com/position-on-1-year-certificates)。

### 我應選擇哪些主機名？ 我應選擇每個網域的主機名？

[!DNL Target] CNAME實作在SSL憑證和客戶的DNS中，每個網域只需要一個主機名稱，因此我們建議您這麼做。 有些客戶可能會要求每個網域額外的主機名稱，以用於自己的用途（例如在測試階段中測試），這是受支援的。

大部分客戶都會選擇類似 `target.example.com`的主機名稱，因此我們建議您選擇，但最終選擇是您自己。 請務必不要請求現有DNS記錄的主機名稱，因為這會導致CNAME請求的解決衝突和延遲 [!DNL Target] 時間。

### 我已經有CNAME實作，我 [!DNL Adobe Analytics]們可以使用相同的憑證或主機名稱嗎？

否，需 [!DNL Target] 要個別的主機名和證書。

### 我目前的Target實作是否受ITP 2.1或2.2影響？

在Safari瀏覽器中，導覽至您有Target JavaScript程式庫的網站。 If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

只需Analytics CNAME，就可解決Target的ITP問題。 只有在廣告封鎖藍本遭封鎖時，您才需要個別的Target CNAME。

如需ITP的詳細資訊，請 [參閱Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### Adobe/DigiCert是否可將DCV電子郵件傳送至其他電子郵件地址 `<someone>@example.com`?

否，DigiCert（或任何認證機構）將不允許只有網域下有電子郵件地址的任何人授權該網域下的SSL憑證，除非該電子郵件地址也包含在網域的WHOIS資訊或預先確定的位址清單中（請參閱上文）。 這可確保只有經過授權的個人才能核准特定網域的DCV。 如果這對您不可行，我們建議使用DNS CNAME DCV方法（請參閱上文）。

### 如何驗證我的CNAME實作已準備好進行流量？

使用下列命令集（在MacOs或Linux命令列終端中，使用bash和curl 7.49+）:

1. 首先將此bash函式貼上到終端：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..32},34,35,37,38}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 下一步貼上此命令(以您的 `target.example.com` 主機名稱取代):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果實作已就緒，您應該會看到如下輸出。 重要部分是所有行都會顯示，這 `CN=target.example.com`些行與我們所需的主機名稱相符。 如果其中任何一 `CN=*.tt.omtrdc.net`個顯示，實 **作** 尚未準備。

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge17.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge21.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge22.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge26.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge28.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge29.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge30.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. 使用另一個捲曲請求驗證您的新DNS CNAME，該請求也應顯示 `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >如果此命令失敗，但 `validateEdgeFpsslSni` 上述命令成功，您可能需要等待DNS更新完全傳播。 DNS記錄具有關聯的 [TTL（存留時間）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) ，它規定這些記錄的DNS回覆的快取到期時間，因此您至少需要等待TTL。 您可以使用 `dig target.example.com` 命令 [](https://toolbox.googleapps.com/apps/dig/#CNAME) 或G套裝工具箱來查閱您的特定TTL。
