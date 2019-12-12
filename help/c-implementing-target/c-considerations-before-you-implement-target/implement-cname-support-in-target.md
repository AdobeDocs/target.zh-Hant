---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: 有關使用 Adobe 客戶服務在 Adobe Target 中實作 CNAME (規範名稱) 支援的資訊。
title: CNAME 與 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: a2e4a4d1036d2c56d752d808054f6f4b4ab1d411

---


# CNAME 與 Adobe Target {#cname-and-adobe-target}

Instructions about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 為了最好地處理廣告封鎖問題或ITP相關Cookie政策，會使用CNAME，以便對客戶所擁有的網域進行呼叫，而非對Adobe所擁有的網域進行呼叫。

## 要求CNAME支援

Perform the following steps to request CNAME support in [!DNL Target]:

1. Adobe的認證授權機構(DigiCert)需要確認Adobe是否已授權在您的網域下產生認證。

   DigiCert會呼叫此 [程式「網域控制驗證](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) (DCV)」，在此程式完成之前，Adobe將不得在您的網域下產生憑證。

   DCV使用一些方法，在開啟Adobe Client Care票證（步驟3）之前，您可以先執行一些動作，以協助加速DCV程式：

   * DigiCert將先試用電子郵件方法，在方法中，他們會傳送電子郵件至網域的WHOIS資訊中找到的位址，以及預先決定的電子郵件地址(管理員、管理員、網站管理員、主機和郵遞員 `@[domain_name]`)。 如需詳細 [資訊，請參閱DCV方法檔案](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) 。

      為加速DCV電子郵件程式，DigiCert提供下列建議：

      「請確認您的註冊/WHOIS提供者未蒙蔽或移除相關 [的電子郵件地址]。 如果是，請瞭解他們是否提供方式（例如匿名電子郵件地址、網頁表格）讓您允許認證授權機構 [] ，存取您網域的WHOIS資料。」

   * 如果DCV電子郵件方法不適合您，則下一個方法是DNS TXT方法，您在該方法中使用散列值將DNS TXT記錄添加到域。 此TXT記錄會向DigiCert指出Adobe已授權產生憑證。 如果您需要使用此方法，請在開啟票證時讓Adobe Client Care知道（步驟3）。 這將有助於加速DCV程式。

1. 在網域的DNS上建立指向一般主機名稱的CNAME記錄 `clientcode.tt.omtrdc.net`。 例如，如果您的客戶代碼是客戶代碼，而您建議的主機名 `target.example.com`稱是，則您的DNS CNAME記錄應該如下所示：

   ```
   target.example.com  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. 開啟 [Adobe Client Care票證，要求您呼叫的CNAME](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) 支 [!DNL Target] 援。

   Adobe將與DigiCert合作，在Adobe的生產伺服器上購買及部署您的憑證。 DigiCert將啟動DCV程式，當您的實作準備就緒時，Adobe Client Care會通知您。

1. 完成上述工作後，Adobe Client care已通知您實作已就緒，您必須在at.js中將 `serverDomain` 更新為新的CNAME。

## 常見問題

以下資訊可回答有關要求及實作CNAM支援的常見問題： [!DNL Target]

### 我可以提供自己的憑證嗎？ 如果是，程式是什麼？

是的，您可以提供您自己的憑證，以便：

1. 略過上述步驟1，但完成步驟2和3。 當您開啟Adobe Client Care票證（步驟3）時，請通知他們您將提供您自己的憑證。

   Adobe會產生並傳送憑證簽署要求(CSR)給您。

1. 使用CSR透過您選擇的認證授權機構(CA)購買認證。

1. 傳送新的公開憑證至Adobe。 Adobe代表將會將公開憑證部署在其生產伺服器上。

1. 在Adobe Client Care通知您實作已就緒後，完成步驟4。

### 我已經有CNAME實作，我 [!DNL Adobe Analytics]們可以使用相同的憑證或主機名稱嗎？

否，需 [!DNL Target] 要個別的主機名和證書。

### 我目前的Target實作是否受ITP 2.1或2.2影響？

在Safari瀏覽器中，導覽至您有Target javaScript程式庫的網站。 If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

只需Analytics CNAME，就可解決Target的ITP問題。 只有在廣告封鎖藍本遭封鎖時，您才需要個別的Target CNAME。

如需ITP的詳細資訊，請 [參閱Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### 如何驗證我的CNAME實作已準備好進行流量？

使用下列命令集（在MacOs或Linux命令列終端中，使用bash和curl 7.49+）:

1. 首先將此bash函式貼上到終端：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..33}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 下一步貼上此命令(以您的 `target.example.com` 主機名稱取代):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果實作已就緒，您應該會看到如下輸出。 重要部分是所有行都顯示，這符 `CN=target.example.com`合我們所需的主機名。 如果其中任何一 `CN=*.tt.omtrdc.net`個顯示，實 **作** 尚未準備。

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
   mboxedge33.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. 使用另一個捲曲請求驗證您的新DNS CNAME，該請求也應顯示 `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >如果此命令失敗，但上 `validateEdgeFpsslSni` 述命令成功，您可能需要等待DNS更新完全傳播。
