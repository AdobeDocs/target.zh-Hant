---
keywords: gdpr;eu;european union;privacy;faq;frequently asked questions;california consumer privacy act;ccpa;privacy;data protection;opt-out;opt out;government;regulation
description: 歐盟一般資料保護規範 (GDPR)、加州消費者隱私保護法 (CCPA) 及其他國際隱私權要求的相關資訊，以及這些規範對您的組織和 Adobe Target 有何影響。
title: 隱私權與資料保護規範
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '2248'
ht-degree: 91%

---


# 隱私權與資料保護規範

有關歐盟通用資料保護規則(GDPR)、加州消費者隱私法(CCPA)和其他國際隱私權要求的資訊，以及這些規定對您的組織和[!DNL Adobe Target]有何影響。

## 隱私權與資料保護規範 (GDPR) 概覽 {#topic_DE567ECB6C944695AEE5073889F1AEA9}

自 2018 年 5 月 25 日起，歐盟的 GDPR 已正式生效。如需與您自身相關的詳細資訊，請參閱 [GDPR 與您的業務](https://www.adobe.com/privacy/general-data-protection-regulation.html)。

當 [!DNL Adobe] 向企業提供軟體和服務時，為了提供這些服務，[!DNL Adobe] 會以資料處理者的角色處理和儲存任何個人資料。身為資料處理者，[!DNL Adobe] 會根據貴公司的權限和指示 (例如，依照您與 [!DNL Adobe] 的合約規定) 處理個人資料。

身為資料控管者，您可以決定由 [!DNL Adobe] 代表您處理和儲存的個人資料。如果使用 [!DNL Adobe Experience Cloud] 解決方案，則 [!DNL Adobe] 可能會根據您使用的解決方案，以及您選擇傳送到 [!DNL Adobe Experience Cloud] 帳戶的資訊，為您託管個人資料。如需詳細的範例清單，請參閱 [Adobe Experience Cloud 隱私權](https://www.adobe.com/privacy/marketing-cloud.html#collect)。

[!DNL Adobe Experience Cloud] 為資料控管者提供 GDPR 完備的 API，可讓資料控管者完成下列工作:

* 存取儲存在 [!DNL Target] 中的資料主體資訊
* 刪除儲存在 [!DNL Target] 中的資料主體資訊

如需詳細資訊，請參閱:

* [Adobe 一般資料保護規範 API 網站](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [GDPR 文件](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## 加州消費者隱私保護法 (CCPA) 概覽

加州消費者隱私保護法 (CCPA) 為加州消費者提供關於其個人資訊的新權利，並對在加州執行業務的某些實體施加資料保護責任。CCPA 將於 2020 年 1 月 1 日生效。

整體來說，此法律賦予加州人多項重要權利，包括下列權利:

* 要求資訊 (資料存取)
* 選擇退出個人資訊銷售 (這是一項定義非常廣泛的權利，可選擇退出與協力廠商分享資訊)
* 要求刪除個人資訊
* 在個人資訊已公開或銷售時收到通知

如果您去年忙著為歐洲的隱私權法律 (GDPR) 做好準備，您可能很熟悉這裡的其中一些權利，而您已完成的許多工作可能可以另作他用。

>[!NOTE]
>
>訪問和刪除適用於CCPA的資料時，會遵循與GDPR相同的流程。

## Adobe Target 和 [!DNL Experience Platform Launch] 選擇加入 {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] 透過 [!DNL Launch] 支援選擇加入功能，有助於支援同意管理策略。選擇加入功能可讓客戶控制引發 [!DNL Target] 標記的方法和時機。也可選擇透過 [!DNL Launch] 預先核准 [!DNL Target] 標記。若要啟用在 [!DNL Target] at.js 資料庫中使用選擇加入的功能，您應使用 `targetGlobalSettings` 並新增 `optinEnabled=true` 設定。在 [!DNL Launch] 中，您會需要以 [!DNL Launch] 擴充程式安裝檢視，從 [!UICONTROL GDPR 選擇加入]下拉式清單中選取「啟用」。如需詳細資訊，請參閱 [Launch 文件](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。

下列程式碼片段會向您示範如何啟用 `optinEnabled=true` 設定:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>at.js 1.7.0 版和 at.js 2.1.0 或更新版本可支援選擇加入功能。at.js 2.0.0 版和 2.0.1 版不支援選擇加入。
>
>建議使用 [!DNL Experience Platform Launch] 管理選擇加入。[!DNL Launch] 中可更仔細控制，可在 [!DNL Target] 引發前隱藏選取的頁面元素，當作同意策略十分實用。

使用「選擇加入」時，該考慮三種情況:

1. **[!DNL Target] 標記是透過 [!DNL Launch] 預先核准 (或資料主體先前核准 [!DNL Target]):**[!DNL Target] 標記不會為同意保留，並照常運作。
1. **[!DNL Target] 標記「不會」預先核准且 `bodyHidingEnabled` 為「FALSE」:**[!DNL Target] 標記僅在向客戶取得同意後觸發。取得同意前，僅可使用預設內容。收到同意後，系統會呼叫 [!DNL Target]，資料主體 (訪客) 即可使用個人化內容。由於收到同意前只能使用預設內容，因此運用適當策略非常重要，例如遮住整個頁面或可個人化內容的啟動顯示畫面。這可確保資料主體 (訪客) 的體驗一致。
1. **[!DNL Target] 標記「不會」預先核准且 `bodyHidingEnabled` 為「TRUE」:**[!DNL Target] 標記僅在向客戶取得同意後觸發。取得同意前，僅可使用預設內容。但由於 `bodyHidingEnabled` 設為 True，`bodyHiddenStyle` 會指定在觸發 [!DNL Target] 標記前隱藏的頁面內容 (或資料主體拒絕選擇加入，而顯示預設內容)。依預設，`bodyHiddenStyle`設為`body { opacity:0;}`，會隱藏HTML內文標籤。 建議的頁面設定如下，將頁面內容放入一個容器，並將同意管理程式對話方塊放入另一個容器，即可隱藏頁面所有內容，而不是同意管理程式對話方塊。這項設定會將 [!DNL Target] 設定為只隱藏頁面內容容器。如需如何設定上述設定的詳細資訊，請參閱 [ Launch 文件](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html)。

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

## 隱私權與資料保護規範常見問題集 {#concept_41F88DE95D2943178BEC382736B5C038}

歐盟一般資料保護規範 (GDPR)、加州消費者隱私保護法 (CCPA) 及 Target 專用之其他國際隱私權要求的相關常見問題集。

### Adobe 針對這些規範採取什麼原則? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] 身為資料處理者， 已符合相關規範或致力於履行我們的義務。我們在經認證的安全性與設計的隱私權控制方面擁有穩固的基礎，並已於 2018 年 5 月的截止日期前持續增強產品功能。企業客戶有責任實作這些增強功能，以及更新任何必要的政策和程序。

### 我們公司身為資料控管者，需要針對每個使用的 [!DNL Adobe Experience Cloud]解決方案提交 GDPR 或 CCPA 要求嗎? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

不需要，[!DNL Adobe]會以集中的方式協助資料控管者符合其 GDPR 和 CCPA 的規範要求。資料控管者無需直接處理每一個解決方案。

[!DNL Experience Cloud]解決方案 (包括 [!DNL Target]) 的所有 GDPR 和 CCPA 要求，將透過目前稱為 GDPR API 的中央 Adobe API 來執行。此 API 便會完成資料控管者的 [!DNL Experience Cloud] 解決方案套裝上的所有要求。

### [!DNL Adobe] 提交資料主體/使用者要求後， 會讓客戶刪除哪些資訊? {#section_4B51D00924EC4166B2442218B69214F0}

有關 [!DNL Target] 中的個別訪客資訊會包含在 [!DNL Target] 訪客設定檔中。[!DNL Target] 會讓客戶刪除與其訪客設定檔中之 ID 相關的所有資料。如需設定檔資料 [!DNL Target] 儲存的範例，請參閱[訪客設定檔](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)。

不會識別特定個人的彙總或匿名資料 (例如報告資料)，或與特定個人不相關的資料 (例如內容資料)，則不在使用者刪除要求的範圍之內。

[!DNL Target] 長達 90 天未使用的 訪客設定檔會依預設刪除，您無需採取任何動作。

### 哪些 ID 受到支援，並且可協助客戶完成針對 [!DNL Target] 的 GDPR 或 CCPA 存取及刪除要求? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] 支援下列 ID 類型，以便找出客戶設定檔:

| 使用者 ID | 命名空間 ID 類型 | 命名空間 ID | 定義 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID，先前稱為訪客 ID 或 Marketing Cloud ID。您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| TnT ID/Cookie ID(TNTID) | 標準 | 9 | 在訪客的瀏覽器中設為 Cookie 的 Target 識別碼。您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| 第三方 ID/CRM ID(THIRDPARTYID) | Target 專用 | 不適用 | 此情況為您向 Target 提供您的 CRM 或客戶的其他唯一識別碼資訊。 |

>[!NOTE]
>
>雖然 [!DNL Target] 對第一方和協力廠商跨網域 Cookie 均有支援，但只建議將第一方 [!DNL Target] Cookie 用於 GDPR 和 CCPA。

### [!DNL Target] 如何處理同意管理? {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR 和 CCPA 並未變更您必須取得同意的時間，而是改變您取得同意的方式。每個客戶的同意策略會根據其資料收集和使用實務，以及其隱私權政策來訂定。[!DNL Target] 不支援 GDPR 和 CCPA 的同意管理，也不應作為達成此功能的工具。

[!DNL Adobe] 目前並未提供同意管理解決方案，但市場中已開發各種工具，可有效應付新需求中的部分內容。有關一般隱私權工具的詳細資訊，包括同意管理員，請參閱&#x200B;*國際隱私專業人士協會(iaap)*&#x200B;網站上的[2017年隱私權技術廠商報告](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf)。

[!DNL Target] 透過 [!DNL Launch] 支援選擇加入功能，以支援同意管理策略。選擇加入功能可讓客戶控制引發 [!DNL Target] 標記的方法和時機。也可選擇透過 [!DNL Launch] 預先核准 [!DNL Target] 標記。建議使用 [!DNL Launch] 管理選擇加入。[!DNL Launch] 中可更仔細控制，可在 [!DNL Target] 引發前隱藏特定頁面元素，當作同意策略十分實用。

如需有關GDPR、CCPA和[!DNL Launch]的詳細資訊，請參閱[ The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html)。 另請參閱上方的 *Adobe Target 和 Experience Platform Launch 選擇加入*&#x200B;一節。

### AdobePrivacy.js 會將資訊提交至 GDPR API 嗎? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *不會*&#x200B;將此資訊提交至 API。此動作必須由客戶來執行。本程式庫僅會提供儲存在該特定訪客所使用之瀏覽器中的 ID。

### removeIdentities 會移除哪些內容? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] *僅會*[!DNL Adobe]從瀏覽器移除身分資料，而此動作完全取決於 解決方案是否已實作此程式碼。

例如，[!DNL Target] 會刪除儲存訪客 ID 的 Cookie，但 [!DNL Adobe Audience Manager] (AAM) 不會刪除儲存在協力廠商 Cookie 中的 demdex ID。

### Target GDPR 或 CCPA 要求需要包含哪些資訊? {#section_D29A4744AE6344E68AD7710B185FD6D0}

除了集中隱私權服務的需求，[!DNL Target] 接受的有效 GDPR 或 CCPA 訊息包含:

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

### 透過 GDPR API，我應該可以得到哪些回應類型?    {#section_F67263D2A72B4641A47CE36729CCAE8F}

| 要求狀態 | Target 回應訊息 | 藍本 |
|--- |--- |--- |
| 正在處理 | 正在處理 | Target 已收到 GDPR 或 CCPA 要求，且正在處理中。 |
| 完成 | 不適用 - 公司環境不適用 | GDPR 或 CCPA 要求中的 IMS ID 未對應到任何 Target 用戶端。<br>請注意，某些公司擁有多個 IMS ID。您必須在佈建 Target 之處提交 IMS ID。 |
| 完成 | 不適用 - 使用者環境不適用 | Target 設定檔存放區中沒有在 GDPR 或 CCPA 要求中提供的特定訪客或資料主體的 ID。<br>請注意，如果您企圖提交 Target 不支援的名稱空間 ID 類型 (請參閱上方提及支援的 ID 部分)，也會傳回這樣的結果。 |
| 錯誤 | 錯誤訊息 (詳細資訊會視錯誤類型而定) | 擷取或刪除要求的資料主體設定檔時發生錯誤。<br>因應存取要求上傳至 Azure 時發生錯誤。 |

### Target 針對存取要求傳送至 GDPR API 的回應是什麼? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

存取資料要求的回應包含特定訪客的 [!DNL Target] 設定檔摘要。請注意，此傳回內容會傳送至 [!DNL Experience Cloud] GDPR API，並傳送回應給資料控管者。

[!DNL Target] 存取 API 回應的範例看起來可能會像這樣:

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
| jobId | 表示中央 GDPR API 中的 GDPR 或 CCPA 工作 ID。 |
| imsOrgID | 為您的公司提供唯一識別碼。 |
| namespace | 亦稱為資料來源。請參閱「哪些 ID 受到支援，並且可協助客戶完成針對 Target 的 GDPR 或 CCPA 存取及刪除要求?」GDPR 存取及刪除要求?」 |
| type | 您要求 GDPR 或 CCPA 資料存取權限的 ID 類型。Target 接受多種 ID 類型，部分為標準型，有些則為 Target 專用型。請參閱「哪些 ID 受到支援，並且可協助客戶完成針對 Target 的 GDPR 或 CCPA 存取及刪除要求?」GDPR 存取及刪除要求?」 |
| value | namespace/資料來源的 ID。請參閱「哪些 ID 受到支援，並且可協助客戶完成針對 Target 的 GDPR 或 CCPA 存取及刪除要求?」，以瞭解接受的值。 |
| 整合程式碼 | 整合程式碼為易記的資料來源名稱，比起使用資料來源 ID，可協助您更輕鬆地追蹤資料來源。 |

當有多個值可用來識別設定檔時，每個有效的識別碼都會有一個設定檔檔案。設定檔檔案會透過 GDPR 中央 API，以 [!DNL Target] 設定檔的 JSON 回應格式傳送至集中的 GDPR Azure Blob。

[!DNL Target] 設定檔 JSON 的範例看起來可能像下面的例子:

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
| Sample_Parameter | [!DNL Target] 設定檔中的許多資訊都是由資料控管者上傳或直接提供。在此範例中，參數是使用設定檔更新 API 上傳到 [!DNL Target] 設定檔中。如需詳細資訊，請參閱[將資料傳入 Target 的方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)。 |
| user.ReturnTimeOfDay | 此標準欄位包含使用者最近回訪的時間。 |
| firstSessionStart | 此標準欄位包含使用者首次工作階段開始的時間。 |
| user.sessionCountScript | [!DNL Target] 設定檔中的許多資訊都是由資料控管者上傳或直接提供。在此範例中，設定檔指令碼會遞增此訪客針對資料管控者網站執行工作階段的次數。如需詳細資訊，請參閱[設定檔指令碼屬性](/help/c-target/c-visitor-profile/profile-parameters.md)。 |

>[!NOTE]
>
>此為 [!DNL Target] 設定檔 JSON 的簡短版本，以供說明使用。[!DNL Target] 設定檔的許多欄位並非標準欄位。傳回的內容取決於特定訪客設定檔中的資訊。

### Target 支援 IP 模糊化功能嗎?    {#section_428907B0CD9842D9B245B38C66A53C6A}

如果您選擇使用 [!DNL Target] 作為 GDPR 或 CCPA 實作策略, Target 則支援 IP 模糊化功能。如需詳細資訊，請參閱[隱私權](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0)。

### 我是否需要採取措施來防止我的資料被分享或出售給第三方？

Target無法允許客戶直接從Target分享或銷售資料給第三方，因此不會選擇退出Target銷售。
