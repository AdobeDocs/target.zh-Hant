---
keywords: 用戶端服務；cname；憑證程式；規範名稱；cookie；憑證；amc;adobe托管憑證；digicert；網域控制驗證
description: 使用 [!DNL Adobe] Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target] 處理廣告封鎖問題。
title: 如何在Target中使用CNAME?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 3e15b8d06cb8185be27a8e0210ecfcfc5002b7e7
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 1%

---

# CNAME 和 [!DNL Target]

使用說明 [!DNL Adobe] 客戶服務以在中實作CNAME（規範名稱）支援 [!DNL Adobe Target]. 使用CNAME處理廣告封鎖問題或ITP相關（智慧型追蹤預防）Cookie原則。 若使用CNAME，會呼叫客戶擁有的網域，而非 [!DNL Adobe].

## 請求中的CNAME支援 [!DNL Target]

1. 決定您SSL憑證所需的主機名稱清單（請參閱下方的常見問題集）。

1. 請針對每個主機名稱，在DNS中建立CNAME記錄，指向您的一般 [!DNL Target] 主機名 `clientcode.tt.omtrdc.net`.

   例如，如果您的用戶端代碼為「客戶」，而您建議的主機名稱為 `target.example.com`，您的DNS CNAME記錄看起來類似：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >[!DNL Adobe]完成此步驟後，憑證授權單位DigiCert才能核發憑證。 因此， [!DNL Adobe] 完成此步驟後，才能完成您對CNAME實作的要求。

1. [填這張表](/help/assets/FPC_Request_Form.xlsx) 並在您 [開啟 [!DNL Adobe] 要求CNAME支援的客戶服務票證](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * [!DNL Adobe Target] 客戶代碼:
   * SSL憑證主機名稱(範例： `target.example.com target.example.org`):
   * SSL憑證購買者([!DNL Adobe] 強烈建議，請參閱常見問題集):Adobe/客戶
   * 如果客戶購買憑證(也稱為「自攜憑證」(BYOC))，請填寫以下額外詳細資訊：
      * 憑證組織(範例：範例Company Inc):
      * 憑證組織單位(選用，範例：行銷):
      * 憑證國家（地區）(範例：美國):
      * 憑證狀態/地區(範例：加州):
      * 憑證城市(範例：聖荷西):

1. 若 [!DNL Adobe] 在購買證書， [!DNL Adobe] 與DigiCert合作，在 [!DNL Adobe]的生產伺服器。

   如果客戶購買憑證(BYOC), [!DNL Adobe] 客戶服務傳送憑證簽署要求(CSR)給您。 透過您選擇的憑證授權單位購買憑證時，請使用CSR。 核發憑證後，請將憑證副本和任何中繼憑證傳送至 [!DNL Adobe] 部署的客戶服務。

   [!DNL Adobe] 客戶服務會在您的實作準備就緒時通知您。

1. 更新 `serverDomain` ([檔案](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#serverDomain))新CNAME主機名稱並設定 `overrideMboxEdgeServer` to `false` ([檔案](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#overridemboxedgeserver))。

## 常見問題

下列資訊可回答以下中有關要求和實作CNAME支援的常見問題 [!DNL Target]:

### 我可以提供自己的憑證（自攜憑證或BYOC）嗎？

您可以提供自己的憑證。 不過， [!DNL Adobe] 不建議此作法。 兩者皆可更輕鬆管理SSL憑證生命週期 [!DNL Adobe] 若 [!DNL Adobe] 購買並控制憑證。 SSL憑證必須每年續約。 因此， [!DNL Adobe] 客戶服務必須每年聯絡您，才能及時取得新憑證。 有些客戶無法及時產生續約的憑證。 您的 [!DNL Target] 憑證過期時，由於瀏覽器拒絕連線，實作會受到影響。

>[!IMPORTANT]
>
>如果您要求 [!DNL Target] 自攜憑證CNAME實作，您必須負責為 [!DNL Adobe] 客戶服務。 允許您的CNAME憑證在 [!DNL Adobe] 可部署續約的憑證，導致您特定 [!DNL Target] 實作。

### 我的新SSL憑證要到期多久？

全部 [!DNL Adobe]-purchased證書的有效期為一年。 請參閱 [DigiCert關於1年證書的文章](https://www.digicert.com/blog/position-on-1-year-certificates) 以取得更多資訊。

### 我應選擇哪些主機名稱？ 我應選擇每個網域的主機名稱數？

[!DNL Target] CNAME實作在SSL憑證和客戶的DNS中，每個網域僅需一個主機名稱。 [!DNL Adobe] 建議每個域一個主機名。 有些客戶為了自己的目的（例如在測試環境中進行測試），需要每個網域更多主機名稱，這是受支援的。

大部分客戶都選擇主機名稱，例如 `target.example.com`. [!DNL Adobe] 建議您遵循此作法，但最終由您選擇。 請不要求現有DNS記錄的主機名。 這樣會造成衝突，並延遲解決 [!DNL Target] CNAME要求。

### 我已有 [!DNL Adobe Analytics]，可以使用相同的憑證或主機名稱嗎？

不， [!DNL Target] 需要獨立的主機名稱和憑證。

### 我目前的實作 [!DNL Target] 受ITP 2.x影響？

Apple智慧型追蹤預防(ITP)2.3版推出其CNAME隱匿緩解功能，可偵測 [!DNL Adobe Target] CNAME實作並將Cookie的有效期縮短為7天。 目前 [!DNL Target] 無法解決ITP的CNAME隱匿問題。 如需ITP的詳細資訊，請參閱 [Apple智慧型追蹤預防(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### 部署CNAME實作時，我會預期會發生哪種服務中斷？

部署憑證時不會造成服務中斷（包括憑證續約）。

不過，在變更 [!DNL Target] 實作代碼(`serverDomain` 在at.js中)新增至新CNAME主機名稱(`target.example.com`)，則網頁瀏覽器會將再度訪問的訪客視為新訪客。 舊訪客的設定檔資料遺失，因為舊主機名稱下無法存取先前的Cookie(`clientcode.tt.omtrdc.net`)。 由於瀏覽器安全模型，無法存取先前的Cookie。 此中斷僅發生在新CNAME的初始切換上。 憑證續約沒有相同的效果，因為主機名稱不會變更。

### 我的CNAME實作使用哪種金鑰類型和憑證簽名演算法？

預設情況下，所有憑證均為RSA SHA-256，金鑰為RSA 2048位元。 目前不支援大於2048位元的金鑰大小。

### 如何驗證CNAME實作是否已準備好迎接流量？

使用下列命令集(在macOS或Linux命令列終端中，使用bash和curl >=7.49):

1. 將此bash函式複製並貼到您的終端機，或將函式貼到您的bash啟動指令碼檔案(通常是 `~/.bash_profile` 或 `~/.bashrc`)，讓函式可在終端工作階段間使用：

   ```
   function adobeTargetCnameValidation {
     local hostname="$1"
     if [ -z "$hostname" ]; then
       echo "ERROR: no hostname specified"
       return 1
     fi
   
     local service="Adobe Target CNAME implementation"
     local edges="31 32 34 35 36 37 38"
     local edgeDomain="tt.omtrdc.net"
     local edgeFormat="mboxedge%d%s.$edgeDomain"
     local shardFormat="-alb%02d"
     local shards=5
     local shardsFoundCount=0
     local shardsFound
     local shardsFoundOutput
     local curlRegex="subject:.*CN=|expire date:|issuer:"
     local curlValidation="SSL certificate verify ok"
     local curlResponseValidation='"OK"'
     local curlEndpoint="/uptime?mboxClient=uptime3"
     local url="https://$hostname$curlEndpoint"
     local sslLabsUrl="https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=$hostname"
     local success="✅"
     local failure="🚫"
     local info="🔎"
     local rule="="
     local horizontalRule="$(seq ${COLUMNS:-30} | xargs printf "$rule%.0s")"
     local miniRule="$(seq 5 | xargs printf "$rule%.0s")"
     local curlVersion="$(curl --version | head -1 | cut -d' ' -f2 )"
     local curlVersionRequired=">=7.49"
     local edgeCount="$(wc -w <<< "$edges" | tr -d ' ')"
     local edge
     local shard
     local currEdgeShard
     local dnsOutput
     local cnameExists
     local endToEndTestSucceeded
     local curlResult
   
     for shard in $(seq $shards); do
       if [ "$shardsFoundCount" -eq 0 ]; then
         for edge in $edges; do
           if [ "$shard" -eq 1 ]; then
             currEdgeShard="$(printf "$edgeFormat" "$edge" "")"
           else
             currEdgeShard="$(
               printf "$edgeFormat" "$edge" "$(
                 printf -- "$shardFormat" "$shard"
               )"
             )"
           fi
           curlResult="$(curl -vsm20 --connect-to "$hostname:443:$currEdgeShard:443" "$url" 2>&1)"
           if grep -q "$curlValidation" <<< "$curlResult"; then
             shardsFound+=" $currEdgeShard"
             if grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundCount=$((shardsFoundCount+1))
               shardsFoundOutput+="\n\n$miniRule $success $hostname [edge shard: $currEdgeShard] $miniRule\n"
             else
               shardsFoundOutput+="\n\n$miniRule $failure $hostname [edge shard: $currEdgeShard] $miniRule\n"
             fi
             shardsFoundOutput+="$(grep -E "$curlRegex" <<< "$curlResult" | sort)"
             if ! grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundOutput+="\nERROR: unexpected HTTP response from this shard using $url"
             fi
           fi
         done
       fi
     done
   
     echo
     echo "$horizontalRule"
     echo
     echo "$service validation for hostname $hostname:"
     dnsOutput="$(dig -t CNAME +short "$hostname" 2>&1)"
     if grep -qFi ".$edgeDomain" <<< "$dnsOutput"; then
       echo "$success $hostname passes DNS CNAME validation"
       cnameExists=true
     else
       echo -n "$failure $hostname FAILED DNS CNAME validation -- "
       if [ -n "$dnsOutput" ]; then
         echo -e "$dnsOutput is not in the subdomain $edgeDomain"
       else
         echo "required DNS CNAME record pointing to <target-client-code>.$edgeDomain not found"
       fi
     fi
   
     curlResult="$(curl -vsm20 "$url" 2>&1)"
     if grep -q "$curlValidation" <<< "$curlResult"; then
       if grep -q "$curlResponseValidation" <<< "$curlResult"; then
         echo -en "$success $hostname passes TLS and HTTP response validation"
         if [ -n "$cnameExists" ]; then
           echo
         else
           echo " -- the DNS CNAME is not pointing to the correct subdomain for ${service}s with Adobe-managed certificates" \
             "(bring-your-own-certificate implementations don't have this requirement), but this test passes as configured"
         fi
         endToEndTestSucceeded=true
       else
         echo -n "$failure $hostname FAILED HTTP response validation --" \
           "unexpected response from $url -- "
         if [ -n "$cnameExists" ]; then
           echo "DNS is NOT pointing to the correct shard, notify Adobe Client Care"
         else
           echo "the required DNS CNAME record is missing, see above"
         fi
       fi
     else
   
       echo -n "$failure $hostname FAILED TLS validation -- "
       if [ -n "$cnameExists" ]; then
         echo "DNS is likely NOT pointing to the correct shard or there's a validation issue with the certificate or" \
           "protocols, see curl output below and optionally SSL Labs ($sslLabsUrl):"
         echo ""
         echo "$horizontalRule"
         echo "$curlResult" | sed 's/^/    /g'
         echo "$horizontalRule"
         echo ""
       else
         echo "the required DNS CNAME record is missing, see above"
       fi
     fi
   
     if [ "$shardsFoundCount" -ge "$edgeCount" ]; then
       echo -n "$success $hostname passes shard validation for the following $shardsFoundCount edge shards:"
       echo -e "$shardsFoundOutput"
       echo
   
       if [ -n "$cnameExists" ] && [ -n "$endToEndTestSucceeded" ]; then
         echo "$horizontalRule"
         echo ""
         echo "  For additional TLS/SSL validation, including detailed browser/client support,"
         echo "  see SSL Labs (click the first IP address if prompted):"
         echo ""
         echo "    $info  $sslLabsUrl"
         echo ""
         echo "  To check DNS propagation around the world, see whatsmydns.net:"
         echo ""
         echo "    $info  DNS A records:     https://whatsmydns.net/#A/$hostname"
         echo "    $info  DNS CNAME record:  https://whatsmydns.net/#CNAME/$hostname"
       fi
     else
       echo -n "$failure $hostname FAILED shard validation -- shards found: $shardsFoundCount," \
         "expected: $edgeCount"
       if bc -l <<< "$(cut -d. -f1,2 <<< "$curlVersion") $curlVersionRequired" 2>/dev/null | grep -q 0; then
         echo -n " -- insufficient curl version installed: $curlVersion, but this script requires curl version" \
           "$curlVersionRequired because it uses the curl --connect-to flag to bypass DNS and directly test" \
           "each Adobe Target edge shards' SNI confirguation for $hostname"
       fi
       if [ -n "$shardsFoundOutput" ]; then
         echo -e ":\n$shardsFoundOutput"
       fi
       echo
     fi
     echo
     echo "$horizontalRule"
     echo
   }
   ```

1. 貼上此命令(替換 `target.example.com` ):

   ```
   adobeTargetCnameValidation target.example.com
   ```

   如果實作已就緒，您會看到如下的輸出。 重要部分是，所有驗證狀態行均顯示 `✅` 而非 `🚫`. 每個 [!DNL Target] 邊緣CNAME分卡應顯示 `CN=target.example.com`，此名稱會符合要求之憑證的主要主機名稱（此輸出中不會列印憑證上的其他SAN主機名稱）。

   ```
   $ adobeTargetCnameValidation target.example.com
   
   ==========================================================
   
   Adobe Target CNAME implementation validation for hostname target.example.com:
   ✅ target.example.com passes DNS CNAME validation
   ✅ target.example.com passes TLS and HTTP response validation
   ✅ target.example.com passes shard validation for the following 7 edge shards:
   
   ===== ✅ target.example.com [edge shard: mboxedge31-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge32-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge34-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge35-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge36-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge37-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge38-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ==========================================================
   
     For additional TLS/SSL validation, including detailed browser/client support,
     see SSL Labs (click the first IP address if prompted):
   
       🔎  https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=target.example.com
   
     To check DNS propagation around the world, see whatsmydns.net:
   
       🔎  DNS A records:     https://whatsmydns.net/#A/target.example.com
       🔎  DNS CNAME record:  https://whatsmydns.net/#CNAME/target.example.com
   
   ==========================================================
   ```

   >[!NOTE]
   >
   >如果此驗證命令在DNS驗證時失敗，但您已進行了必要的DNS更改，則可能需要等待DNS更新完全傳播。 DNS記錄具有關聯 [TTL（存留時間）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) 這會指定這些記錄的DNS回覆的快取過期時間。 因此，您至少需要等候TTL。 您可以使用 `dig target.example.com` 命令或 [G Suite工具箱](https://toolbox.googleapps.com/apps/dig/#CNAME) 查看您的特定TTL。 要檢查DNS在全球的傳播，請參閱 [whatsmydns.net](https://whatsmydns.net/#CNAME).

### 如何使用具有 CNAME 的退出連結

如果您使用CNAME，選擇退出連結應包含「client=`clientcode` 參數，例如：
`https://my.cname.domain/optout?client=clientcode`.

取代 `clientcode` 使用您的用戶端代碼，然後新增要連結至 [退出URL](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC).

## 已知限制

* 如果您有CNAME和at.js 1.x,QA模式就不會有黏性，因為它是以協力廠商Cookie為基礎。 因應措施是將預覽參數新增至您導覽至的每個URL。 如果您有CNAME和at.js 2.x,QA模式就會有黏性。
* 使用CNAME時，Cookie標題的大小 [!DNL Target] 呼叫數增加。 [!DNL Adobe] 建議將cookie大小保持在8 KB以下。
