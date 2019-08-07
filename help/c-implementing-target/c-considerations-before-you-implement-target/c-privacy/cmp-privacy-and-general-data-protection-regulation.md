---
description: 有關歐盟通用資料保護規則(GDPR)和加州消費者隱私權法案(CCPA)的資訊，以及這些規定對貴組織和Adobe Target的影響。
keywords: gdpr；eu；歐盟；隱私權；常見問題；常見問題；加州消費者隱私權法案；ccpa
seo-description: 有關歐盟通用資料保護規則(GDPR)和加州消費者隱私權法案(CCPA)的資訊，以及這些規定對貴組織和Adobe Target的影響。
seo-title: 通用資料保護規則(GDPR)、加州消費者隱私權法案(CCPA)和Adobe Target
solution: Target
title: 隱私權與資料保護條例
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: 222fb66f58ea5bcecabfaa2ab966ad9a686dc9ef

---


# 隱私權與資料保護條例 {#privacy-and-general-data-protection-regulation-gdpr}

有關歐盟通用資料保護規則(GDPR)和加州消費者隱私權法案(CCPA)的資訊，以及這些法規對貴組織的影響 [!DNL Adobe Target]。

## 隱私權與一般資料保護規範 (GDPR) 概覽 {#topic_DE567ECB6C944695AEE5073889F1AEA9}

有關 Adobe 會如何與您合作以準備好因應歐盟一般資料保護規範 (GDPR) 的資訊。

### GDPR 概覽 {#section_8C99434A431B4494998B01B869E7EA5D}

歐盟的GDPR於2018年月25日生效。如需與您自身相關的詳細資訊，請參閱 [GDPR 與您的業務](https://www.adobe.com/privacy/general-data-protection-regulation.html)。

當 Adobe 提供軟體和服務給企業時，Adobe 為了提供這些服務，會以資料處理者的角色處理和儲存任何個人資料。身為資料處理者，Adobe 會根據貴公司的權限和指示 (例如，依照您與 Adobe 的合約規定) 處理個人資料。

身為資料控管者，您可以決定 Adobe 代表您處理和儲存的個人資料。如果使用 Adobe Experience Cloud 解決方案，則 Adobe 可能會根據您使用的解決方案，以及您選擇傳送到 Adobe Experience Cloud 帳戶的資訊，為您託管個人資料。如需詳細的範例清單，請參閱 [Adobe Experience Cloud 隱私權](https://www.adobe.com/privacy/marketing-cloud.html#collect)。

Adobe Experience Cloud 將為資料控管者提供符合 GDPR 規範的 API，使其能夠在 GDPR 規範的生效日前完成下列工作:

* 存取儲存在 Target 中的資料主體資訊
* 刪除儲存在 Target 中的資料主體資訊

### Adobe 一般資料保護規範 API 網站 {#section_51B8FA3CBE234E9592BDA7083B5CE4CD}

如需詳細資訊，請參閱:

* [Adobe 一般資料保護規範 API 網站](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [GDPR 文件](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## 加州消費者隱私權法案(CCPA)概觀

加州消費者隱私權法案(CCPA)自2014年月日起生效。根據設計，法律賦予加州法規人員進行調整並釐清細節的機會，這表示您自然有許多問題。如果您有疑問，就不會因為有許多企業正在處理法律中的不確定性，並嘗試瞭解並制定一種解決法律、營運和技術需求的方法。

CCPA提供加州消費者有關其個人資訊的新權利，並為在加州經營業務的特定實體賦予資料保護責任。在高層級，法律賦予加州居民幾項主要權利，包括：(1)要求資訊(資料存取)、(2)選擇退出個人資訊銷售(以廣泛定義的權利拒絕與第三方分享資訊)、(3)刪除個人資訊，並通知(4)個人資訊遭到揭露或販售。

如果您在去年忙於準備歐洲隱私權法律(GDPR)，其中有些權利可能會很熟悉，而且您的大部分工作可能會被重新利用。

## Adobe Target 和 Adobe Launch 選擇加入 {#section_6F7B53F5E40C4425934627B653E831B0}

Target 透過 Adobe Launch 支援選擇加入功能，有助於支援同意管理策略。選擇加入功能可讓客戶控制觸發 Target 標記的方法和時機。也可選擇透過 Adobe Launch 預先核准 Target 標記。若要啟用 Target at.js 中使用選擇加入的功能，您應使用 `targetGlobalSettings` 並新增 `optinEnabled=true` 設定。在 Launch 中，您會需要以 Target Launch 擴充程式安裝檢視，從「GDPR 選擇加入」下拉式清單中選取「啟用」。如需詳細資訊，請參閱 [Launch 文件](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。

下列程式碼片段會向您示範如何啟用 `optinEnabled=true` 設定:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>選擇加入功能在at. js1.7.0和at. js2.1.0或更新版本中受到支援。在at. js2.0.0和2.0.1版中不支援加入。
>
>建議使用 Adobe Launch 管理選擇加入。Adobe Launch 中可更仔細控制，可在 Target 觸發前隱藏選取的頁面元素，當作同意策略十分實用。

使用「選擇加入」時，該考慮三種情況:

1. **Target 標記是透過 Adobe Launch 預先核准 (或資料主體先前核准 Target):** Target 標記不會為同意保留，並照常運作。
1. **Target 標記「不會」預先核准且`bodyHidingEnabled`為「FALSE」:** Target 標記僅在向客戶取得同意後觸發。取得同意前，僅可使用預設內容。收到同意後，系統會呼叫 Target，資料主體 (訪客) 即可使用個人化內容。由於收到同意前只能使用預設內容，因此運用適當策略非常重要，例如遮住整個頁面或可個人化內容的啟動顯示畫面。這可確保資料主體 (訪客) 的體驗一致。
1. **Target 標記「不會」預先核准且`bodyHidingEnabled`為「TRUE」:** Target 標記僅在向客戶取得同意後觸發。取得同意前，僅可使用預設內容。但由於 `bodyHidingEnabled` 設為 True，`bodyHiddenStyle` 會指定在觸發 Target 標記前隱藏的頁面內容 (或資料主體拒絕選擇加入，而顯示預設內容)。`bodyHiddenStyle` 預設為 `body { opacity:0;`}，會隱藏 HTML 內文標記。建議的頁面設定如下，將頁面內容放入一個容器，並將同意管理程式對話方塊放入另一個容器，即可隱藏頁面所有內容，而不是同意管理程式對話方塊。這項設定會將 Target 設定為只隱藏頁面內容容器。如需如何設定上述設定的詳細資訊，請參閱 [Adobe Launch 文件](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html)。

   情況 3 的建議頁面設定如下:

   ```
   <html> 
   <head> 
   //visitor, at.js 
   </head> 
   
   <body> 
   <div id = "consentManagerDialog"> 
   
   //consent manager html dialog goes here 
   </div> 
   
   <div id="pageContent"> 
   // page content goes here 
   </div> 
   
   </body> 
   </html> 
   ```

   假設 `bodyHiddenStyle` 如下:

   ```
   #pageContent { opacity:0;}
   ```

## 隱私權與資料保護法規常見問題 {#concept_41F88DE95D2943178BEC382736B5C038}

一般資料保護規則(GDPR)和加州消費者隱私權法案(CCPA)的常見問題。

### Adobe對於這些法規的政策為何？ {#section_A6849628D6524C80A6E16946DC5D25A9}

身為資料處理者，Adobe 已符合相關規範或致力於履行我們的義務。我們在經認證的安全性與設計的隱私權控制方面擁有穩固的基礎，並將於 2018 年 5 月的截止日期前持續增強產品功能。企業客戶有責任實作這些增強功能，以及更新任何必要的政策和程序。

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each Adobe Experience Cloud solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

否，Adobe提供了一個中心方法，幫助資料掌控者符合其GDPR和CCPA要求。資料控管者無需直接處理每一個解決方案。

所有Experience Cloud解決方案(包括Target)的GDPR和CCPA要求都將透過目前稱為GDPR API的中央Adobe API進行。此 API 便會完成資料控管者的 Experience Cloud 解決方案套裝上的所有要求。

### 提交資料主體/使用者要求後，Adobe 會讓客戶刪除哪些資訊?   {#section_4B51D00924EC4166B2442218B69214F0}

有關 Target 中的個別訪客資訊會包含在 Target 訪客設定檔中。Adobe Target 會讓客戶刪除與其訪客設定檔中之 ID 相關的所有資料。如需 Adobe Target 儲存之設定檔資料的範例，請參閱[訪客資料](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)。

不會識別特定個人的彙總或匿名資料 (例如報告資料)，或與特定個人不相關的資料 (例如內容資料)，則不在使用者刪除要求的範圍之內。

長達 90 天未使用的 Target 訪客設定檔會依預設刪除，您無需採取任何動作。

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for Target? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

Target 支援下列 ID 類型，以便找出客戶設定檔:

| 使用者 ID | 命名空間 ID 類型 | 命名空間 ID | 定義 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID，先前稱為訪客 ID 或 Marketing Cloud ID。您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| TnT ID/Cookie ID(TNTID) | Standard | 9 | 在訪客的瀏覽器中設為 Cookie 的 Target 識別碼。您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| 第三方 ID/CRM ID(THIRDPARTYID) | Target 專用 | 不適用 | 此情況為您向 Target 提供您的 CRM 或客戶的其他唯一識別碼資訊。 |

>[!NOTE]
>
>雖然Adobe Target支援第一方和第三方跨網域Cookie，但僅建議GDPR和CCPA使用第一方Adobe Target Cookie。

### Adobe Target 如何處理同意管理? {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR和CCPA不會在您需要同意時變更，但您要如何取得。每個客戶的同意策略會根據其資料收集和使用實務，以及其隱私權政策來訂定。同意管理不受GDPR和CCPA的支援，且不是透過Target達成的。

Adobe 目前並未提供同意管理解決方案，但市場中已開發各種工具，可有效應付新需求中的部分內容。如需常見隱私權工具的詳細資訊，包括同意管理程式，請參閱國際隱私權專家協會 (IAAP) 網站上的[《2017 年隱私權技術廠商報告》(2017 Privacy Tech Vendor Report)](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf)。

Adobe Target 透過 Adobe Launch 支援選擇加入功能，以支援同意管理策略。選擇加入功能可讓客戶控制觸發 Adobe Target 標記的方法和時機。也可選擇透過 Adobe Launch 預先核准 Adobe Target 標記。建議使用 Adobe Launch 管理選擇加入。Adobe Launch 中可更仔細控制，可在 Adobe Target 觸發前隱藏特定頁面元素，當作同意策略十分實用。

For more information on GDPR, CCPA and Adobe Launch, see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). 另請參閱上方的「Adobe Target 和 Adobe Launch 選擇加入」一節。

### AdobePrivacy.js 會將資訊提交至 GDPR API 嗎? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *不會*&#x200B;將此資訊提交至 API。此動作必須由客戶來執行。本程式庫僅會提供儲存在該特定訪客所使用之瀏覽器中的 ID。

### removeIdentities 會移除哪些內容? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities]*僅會*&#x200B;從瀏覽器移除身分資料，而此動作完全取決於 Adobe 解決方案是否已實作此程式碼。

例如，Target 會刪除儲存訪客 ID 的 Cookie，但 Adobe Audience Manager (AAM) 不會刪除儲存在第三方 Cookie 中的 demdex ID。

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

除了Central隱私權服務的要求外，Target有效的GDPR或CCPA訊息也包含：

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            "namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            "namespace":"TNTID", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"THIRDPARTYID", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
}
```

### 透過 GDPR API，我應該可以得到哪些回應類型?   {#section_F67263D2A72B4641A47CE36729CCAE8F}

| 要求狀態 | Target 回應訊息 | 藍本 |
|--- |--- |--- |
| 正在處理 | 正在處理 | Target收到GDPR或CCPA要求，正在處理中。 |
| 完成 | 不適用 - 公司環境不適用 | GDPR或CCPA請求中的IMS ID未對應至任何Target用戶端。<br>請注意，某些公司擁有多個 IMS ID。您必須在佈建 Target 之處提交 IMS ID。 |
| 完成 | 不適用 - 使用者環境不適用 | GDPR或CCPA要求中針對特定訪客或資料主體提供的ID不存在於Target描述檔商店中。<br>請注意，如果您企圖提交 Target 不支援的名稱空間 ID 類型 (請參閱上方提及支援的 ID 部分)，也會傳回這樣的結果。 |
| 錯誤 | 錯誤訊息 (詳細資訊會視錯誤類型而定) | 擷取或刪除要求的資料主體設定檔時發生錯誤。<br>因應存取要求上傳至 Azure 時發生錯誤。 |

### Target 針對存取要求傳送至 GDPR API 的回應是什麼? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

存取資料要求的回應包含特定訪客的 Target 設定檔摘要。請注意，此傳回內容會傳送至 Experience GDPR API，並傳送回應給資料控管者。

Target 存取 API 回應的範例看起來可能會像這樣:

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            ~"namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            ~"namespace":"tntId", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"thirdPartyId", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
} 
```

| 欄位 | 說明 |
|--- |--- |
| jobId | 指出Central GDPR API中的GDPR或CCPA工作ID。 |
| imsOrgID | 為您的公司提供唯一識別碼。 |
| namespace | 亦稱為資料來源。請參閱「支援哪些ID以協助客戶完成GDPR或CCPA的存取和刪除要求？」GDPR 存取及刪除要求?」 |
| type | 您請求GDPR或CCPA資料存取權的ID類型。Target 接受多種 ID 類型，部分為標準型，有些則為 Target 專用型。請參閱「支援哪些ID以協助客戶完成GDPR或CCPA的存取和刪除要求？」GDPR 存取及刪除要求?」 |
| value | namespace/資料來源的 ID。請參閱「支援哪些ID以協助客戶完成GDPR或CCPA的存取和刪除要求？」，以瞭解接受的值。 |
| 整合程式碼 | 整合程式碼為易記的資料來源名稱，比起使用資料來源 ID，可協助您更輕鬆地追蹤資料來源。 |

當有多個值可用來識別設定檔時，每個有效的識別碼都會有一個設定檔檔案。設定檔檔案會透過 GDPR 中央 API，以 Target 設定檔的 JSON 回應格式傳送至集中的 GDPR Azure Blob。

Target 設定檔 JSON 的範例看起來可能像下面的例子:

```
{"profileAttributes": 
 
"Sample_Parameter":{"value":"Gold Loyalty Status","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"user.ReturnTimeOfDay":{"value":"44.0","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"firstSessionStart":{"value":"1523497450602","modifiedAt":"2018-04-11T21:44:10.000-04:00"}, 
 
"user.sessionCountScript":{"value":"1","modifiedAt":"2018-04-11T21:44:14.000-04:00"} 
   } 
} 
```

下表包含說明性的設定檔 JSON 欄位描述:

| 欄位 | 說明 |
|--- |--- |
| Sample_Parameter | Target 設定檔中的許多資訊都是由資料控管者上傳或直接提供。在此範例中，參數是使用「設定檔更新 API」上傳到 Target 設定檔中。如需詳細資訊，請參閱[將資料傳入 Target 的方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)。 |
| user.ReturnTimeOfDay | 此標準欄位包含使用者最近回訪的時間。 |
| firstSessionStart | 此標準欄位包含使用者首次工作階段開始的時間。 |
| user.sessionCountScript | Target 設定檔中的許多資訊都是由資料控管者上傳或直接提供。在此範例中，設定檔指令碼會遞增此訪客針對資料管控者網站執行工作階段的次數。如需詳細資訊，請參閱[設定檔指令碼屬性](/help/c-target/c-visitor-profile/profile-parameters.md)。 |

>[!NOTE]
>
>此為 Target 設定檔 JSON 的簡短版本，以供說明使用。Target 設定檔的許多欄位並非標準欄位。傳回的內容取決於特定訪客設定檔中的資訊。

## Target 支援 IP 模糊化功能嗎?   {#section_428907B0CD9842D9B245B38C66A53C6A}

如果您選擇將其作為GDPR或CCPA實施策略的一部分使用，Target支援Target中的IP模糊化。For more information, see [Privacy](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
