---
keywords: 客戶關懷；cname;certificate program;canonican name;cookies;certificate;amc;adobe托管證書；digicert；域控制驗證；dcv
description: 使用 [!DNL Adobe] 在中實現CNAME（規範名稱）支援的客戶端注意 [!DNL Adobe Target] 處理廣告攔截問題。
title: 如何在目標中使用CNAME?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 1%

---

# CNAME 和 [!DNL Target]

使用說明 [!DNL Adobe] 在中實現CNAME（規範名稱）支援的客戶端注意 [!DNL Adobe Target]。 使用CNAME處理廣告阻止問題或與ITP相關（智慧跟蹤防範）Cookie策略。 使用CNAME ，將呼叫到客戶所擁有的域，而不是由客戶所擁有的域 [!DNL Adobe]。

## 請求中的CNAME支援 [!DNL Target]

1. 確定SSL證書所需的主機名清單（請參閱下面的常見問題）。

1. 對於每個主機名，在DNS中建立一個CNAME記錄，該記錄指向您的常規 [!DNL Target] 主機名 `clientcode.tt.omtrdc.net`。

   例如，如果您的客戶端代碼是「cnamecustomer」，而您建議的主機名是 `target.example.com`，您的DNS CNAME記錄看起來類似：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >[!DNL Adobe]在完成此步驟之前，&#39;s證書頒發機構DigiCert無法頒發證書。 所以， [!DNL Adobe] 在完成此步驟之前，無法滿足您對CNAME實施的請求。

1. [填寫此表單](/help/main/assets/FPC_Request_Form.xlsx) 當你 [開啟 [!DNL Adobe] 請求CNAME支援的客戶端保護票證](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * [!DNL Adobe Target] 客戶代碼:
   * SSL證書主機名(示例： `target.example.com target.example.org`):
   * SSL證書購買者([!DNL Adobe] 強烈推薦，請參閱常見問題):Adobe/客戶
   * 如果客戶正在購買證書，又稱「自帶證書」(BYOC)，請填寫以下附加詳細資訊：
      * 證書組織(示例：示例公司):
      * 證書組織單位(可選，例如：營銷):
      * 證書國家（地區）(示例：美國):
      * 證書狀態/區域(示例：加利福尼亞):
      * 證書所在城市(示例：聖何塞):

1. 如果 [!DNL Adobe] 購買證書， [!DNL Adobe] 與DigiCert協作，在 [!DNL Adobe]生產伺服器。

   如果客戶正在購買證書(BYOC), [!DNL Adobe] Client Care向您發送證書籤名請求(CSR)。 在通過您選擇的證書頒發機構購買證書時使用CSR。 在證書頒發後，將證書副本和任何中間證書發送到 [!DNL Adobe] 客戶端注意部署。

   [!DNL Adobe] Client Care會在實施就緒時通知您。

1. 更新 `serverDomain` ([文檔](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)){target=_blank}到新CNAME主機名並設定 `overrideMboxEdgeServer` 至 `false` ([文檔](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)){target=_blank}。

## 常見問題

以下資訊回答了有關請求和實施CNAME支援的常見問題 [!DNL Target]:

### 我能否提供自己的證書（帶來您自己的證書或BYOC）?

您可以提供自己的證書。 但是， [!DNL Adobe] 不推薦這種做法。 SSL證書生命週期的管理對於兩者都更容易 [!DNL Adobe] 如果 [!DNL Adobe] 購買並控制證書。 SSL證書必須每年續訂。 所以， [!DNL Adobe] 客戶服務部門必須每年聯繫您，以便及時獲得新證書。 有些客戶可能難以及時生成更新的證書。 您 [!DNL Target] 當證書因瀏覽器拒絕連接而過期時，實現將受到威脅。

>[!IMPORTANT]
>
>如果您請求 [!DNL Target] 提供您自己的證書CNAME實施，您負責為 [!DNL Adobe] 每年都有客戶照顧。 允許CNAME證書在 [!DNL Adobe] 可以部署更新的證書，導致您的特定 [!DNL Target] 執行。

### 我的新SSL證書到期的時間是多長？

全部 [!DNL Adobe] — 購買的證書有效期為一年。 請參閱 [DigiCert關於1年證書的文章](https://www.digicert.com/blog/position-on-1-year-certificates) 的子菜單。

### 我應選擇哪些主機名？ 應選擇每個域的主機名數？

[!DNL Target] CNAME實現在SSL證書和客戶的DNS中每個域只需要一個主機名。 [!DNL Adobe] 建議每個域一個主機名。 有些客戶需要每個域的更多主機名以用於自己的目的（例如，在轉移中測試），這是受支援的。

大多數客戶選擇主機名 `target.example.com`。 [!DNL Adobe] 建議遵循這種做法，但最終由你做出選擇。 不要請求現有DNS記錄的主機名。 這樣會導致衝突並延遲解決 [!DNL Target] CNAME請求。

### 我已為 [!DNL Adobe Analytics]，是否可以使用相同的證書或主機名？

不， [!DNL Target] 需要單獨的主機名和證書。

### 我當前的實施 [!DNL Target] 受ITP 2.x影響？

Apple智慧跟蹤防護(ITP)2.3版引入了其CNAME遮蓋防護功能，該功能能夠檢測到 [!DNL Adobe Target] CNAME實現並將cookie的過期時間減少到七天。 當前 [!DNL Target] 沒有解決ITP的CNAME遮蓋緩解的方法。 有關ITP的詳細資訊，請參見 [Apple智慧跟蹤預防(ITP)2.x](https://developer.adobe.com/target/before-implement/privacy/apple-itp-2x/)。

### 部署CNAME實施時，我可以期待哪種服務中斷？

部署證書（包括證書續訂）時不會發生服務中斷。

但是，在更改 [!DNL Target] 實施代碼(P)`serverDomain` 在at.js中)到新CNAME主機名(`target.example.com`)，網路瀏覽器將返回的訪問者視為新訪問者。 返回訪問者的配置檔案資料丟失，因為以前的cookie在舊主機名下無法訪問(`clientcode.tt.omtrdc.net`)。 由於瀏覽器安全模型，以前的cookie無法訪問。 此中斷僅在初始切換到新CNAME時發生。 證書續訂沒有相同的效果，因為主機名不會更改。

### 我的CNAME實現使用了什麼密鑰類型和證書籤名算法？

預設情況下，所有證書都是RSA SHA-256 ，密鑰是RSA 2048位。 當前不支援大於2048位的密鑰大小。

### 如何驗證我的CNAME實現是否已準備好進行通信？

使用以下命令集(在macOS或Linux命令行終端中，使用bash和curl >=7.49):

1. 將此bash函式複製並貼上到您的終端中，或將該函式貼上到您的bash啟動指令碼檔案中(通常 `~/.bash_profile` 或 `~/.bashrc`)，因此該功能可在終端會話中使用：

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

   如果實施已就緒，則會看到以下輸出。 重要部分是所有驗證狀態行都顯示 `✅` 而 `🚫`。 每個 [!DNL Target] 邊CNAME分片應顯示 `CN=target.example.com`，與請求的證書上的主主機名匹配（此輸出中不打印證書上的其他SAN主機名）。

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
   >如果此驗證命令在DNS驗證時失敗，但您已經做了必要的DNS更改，則可能需要等待DNS更新完全傳播。 DNS記錄具有關聯 [TTL（生存時間）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) 這表示這些記錄的DNS答復的快取過期時間。 因此，您可能至少需要等待TTL。 您可以使用 `dig target.example.com` 命令或 [G套件工具箱](https://toolbox.googleapps.com/apps/dig/#CNAME) 查看特定TTL。 要檢查DNS在全球的傳播，請參見 [whatsmydns.net](https://whatsmydns.net/#CNAME)。

### 如何使用具有 CNAME 的退出連結

如果使用CNAME，則opt-out連結應包含&quot;client=`clientcode` 參數，例如：
`https://my.cname.domain/optout?client=clientcode`。

替換 `clientcode` 將文本或影像添加到 [選擇 — 退出URL](https://developer.adobe.com/target/before-implement/privacy/privacy/)。

## 已知限制

* QA模式在您有CNAME和at.js 1.x時不會粘滯，因為它基於第三方cookie。 解決方法是將預覽參數添加到導航到的每個URL。 QA模式在您有CNAME和at.js 2.x時是粘滯的。
* 使用CNAME時，更可能是 [!DNL Target] 呼叫增加。 [!DNL Adobe] 建議將cookie大小保持在8 KB以下。
