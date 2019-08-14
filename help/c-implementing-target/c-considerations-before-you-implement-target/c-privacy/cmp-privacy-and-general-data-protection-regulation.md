---
description: 有關歐盟通用資料保護規則(GDPR)、加州消費者隱私權法案(CCPA)及其他國際隱私權規定的資訊，以及這些規定對貴組織和Adobe Target的影響。
keywords: gdpr；eu；歐盟；隱私權；常見問題；常見問題；加州消費者隱私權法案；ccpa；隱私權；資料保護；選擇退出；選擇退出；政府；規則
seo-description: 有關歐盟通用資料保護規則(GDPR)、加州消費者隱私權法案(CCPA)及其他國際隱私權規定的資訊，以及這些規定對貴組織和Adobe Target的影響。
seo-title: 有關歐盟通用資料保護規則(GDPR)、加州消費者隱私權法案(CCPA)及其他國際隱私權規定的資訊，以及這些規定對貴組織和Adobe Target的影響。
solution: Target
title: 隱私權與資料保護條例
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: d21838bdf17327b394f6e3106ea5ce4bc72605e6

---


# 隱私權與資料保護條例 {#privacy-and-general-data-protection-regulation-gdpr}

有關歐盟通用資料保護規則(GDPR)、加州消費者隱私權法案(CCPA)及其他國際隱私權規定的資訊，以及這些規定對貴組織和Adobe Target的影響。

## Privacy and General Data Protection Regulation (GDPR) overview {#topic_DE567ECB6C944695AEE5073889F1AEA9}

歐盟的GDPR於2018年月25日生效。如需與您自身相關的詳細資訊，請參閱 [GDPR 與您的業務](https://www.adobe.com/privacy/general-data-protection-regulation.html)。

When [!DNL Adobe] is providing software and services to an enterprise, [!DNL Adobe] is acting as a Data Processor for any personal data it processes and stores as part of providing these services. As a Data Processor, [!DNL Adobe] processes personal data in accordance with your company's permission and instructions (for example, as set out in your agreement with [!DNL Adobe]).

As the Data Controller, you determine the personal data that [!DNL Adobe] processes and stores on your behalf. If you use [!DNL Adobe Experience Cloud] solutions, [!DNL Adobe] might host personal data for you, depending on the solutions you use and the information you choose to send to your [!DNL Adobe Experience Cloud] account. 如需詳細的範例清單，請參閱 [Adobe Experience Cloud 隱私權](https://www.adobe.com/privacy/marketing-cloud.html#collect)。

[!DNL Adobe Experience Cloud] 為資料控制器提供適用於GDPR的API，可讓他們完成下列工作：

* 存取儲存在 中的資料主體資訊[!DNL Target]
* 刪除儲存在 中的資料主體資訊[!DNL Target]

如需詳細資訊，請參閱:

* [Adobe 一般資料保護規範 API 網站](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [GDPR 文件](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## California Consumer Privacy Act(CCPA)概觀

加州消費者隱私權法案(CCPA)為加州消費者提供有關其個人資訊的新權利，並為在加州經營業務的特定實體賦予資料保護責任。CCPA將於2020年月日生效。

在高層級，法律賦予加州居民幾項主要權利，包括：

* 要求資訊(資料存取)
* 選擇退出銷售個人資訊(提供與第三方分享資訊的廣泛定義權利)
* 已刪除個人資訊
* 得知個人資訊已揭露或銷售

如果您在去年忙於準備歐洲隱私權法律(GDPR)，其中有些權利可能會很熟悉，而且您的大部分工作可能會被重新利用。

## Adobe Target and [!DNL Experience Platform Launch] opt-in {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] 提供選擇加入功能支援 [!DNL Launch] ，協助支援您的許可管理策略。Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. To enable the ability to use Opt-In in the [!DNL Target] at.js library, you should use `targetGlobalSettings` and add the `optinEnabled=true` setting. In [!DNL Launch] you'll need to select "enable" from the [!UICONTROL GDPR Opt-In] drop-down list in the [!DNL Launch] extension installation view. 如需詳細資訊，請參閱 [Launch 文件](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。

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
>Using [!DNL Experience Platform Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide selected elements of your page prior to [!DNL Target] firing that are helpful to leverage as part of your consent strategy.

使用「選擇加入」時，該考慮三種情況:

1. **[!DNL Target]標記會經過[!DNL Launch]預先核准(或先前核准的[!DNL Target]資料主體)：**[!DNL Target] 標籤不會受同意，且如預期般運作。
1. **[!DNL Target]標記「不會」預先核准且`bodyHidingEnabled`為「FALSE」:** 標記僅在向客戶取得同意後觸發。[!DNL Target]取得同意前，僅可使用預設內容。After consent is received, [!DNL Target] is called and personalized content is available to the data subject (visitor). 由於收到同意前只能使用預設內容，因此運用適當策略非常重要，例如遮住整個頁面或可個人化內容的啟動顯示畫面。這可確保資料主體 (訪客) 的體驗一致。
1. **[!DNL Target]標記「不會」預先核准且`bodyHidingEnabled`為「TRUE」:** 標記僅在向客戶取得同意後觸發。[!DNL Target]取得同意前，僅可使用預設內容。但由於 `bodyHidingEnabled` 設為 True，`bodyHiddenStyle` 會指定在觸發 標記前隱藏的頁面內容 (或資料主體拒絕選擇加入，而顯示預設內容)。[!DNL Target]`bodyHiddenStyle` 預設為 `body { opacity:0;`}，會隱藏 HTML 內文標記。建議的頁面設定如下，將頁面內容放入一個容器，並將同意管理程式對話方塊放入另一個容器，即可隱藏頁面所有內容，而不是同意管理程式對話方塊。This setup configures [!DNL Target] so that it hides the page content container only. 如需如何設定上述設定的詳細資訊，請參閱 [ Launch 文件](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html)。

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

關於歐盟通用資料保護規則(GDPR)、加州消費者隱私權法(CCPA)及其他特定Target的國際隱私權要求的常見問題。

### Adobe對於這些法規的政策為何？ {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe]身為資料處理者， 已符合相關規範或致力於履行我們的義務。在2018年月期限之前，我們已針對經過認證的安全性和隱私權控制奠定了堅實的基礎，並已完成產品增強功能。企業客戶有責任實作這些增強功能，以及更新任何必要的政策和程序。

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each [!DNL Adobe Experience Cloud] solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, [!DNL Adobe] is providing a central way to help Data Controllers meet their GDPR and CCPA requirements. 資料控管者無需直接處理每一個解決方案。

[!DNL Experience Cloud] 所有解決方案的GDPR和CCPA要求，包括 [!DNL Target]，將透過目前稱為GDPR API的中央Adobe API進行。The API will then complete the request across the Data Controller's [!DNL Experience Cloud] solution suite.

### What information will [!DNL Adobe] enable our customers to delete in response to a data subject/user request? {#section_4B51D00924EC4166B2442218B69214F0}

The information related to an individual visitor within [!DNL Target] is contained within the [!DNL Target] Visitor Profile. [!DNL Target] 會讓客戶刪除與其訪客設定檔中之 ID 相關的所有資料。如需設定檔資料 [!DNL Target] 儲存區的範例，請參閱 [「訪客資料](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)」。

不會識別特定個人的彙總或匿名資料 (例如報告資料)，或與特定個人不相關的資料 (例如內容資料)，則不在使用者刪除要求的範圍之內。

[!DNL Target]長達 90 天未使用的 訪客設定檔會依預設刪除，您無需採取任何動作。

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] 支援下列 ID 類型，以便找出客戶設定檔:

| 使用者 ID | 命名空間 ID 類型 | 命名空間 ID | 定義 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID，先前稱為訪客 ID 或 Marketing Cloud ID。您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| TnT ID/Cookie ID(TNTID) | Standard | 9 | 在訪客的瀏覽器中設為 Cookie 的 Target 識別碼。您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| 第三方 ID/CRM ID(THIRDPARTYID) | Target 專用 | 不適用 | 此情況為您向 Target 提供您的 CRM 或客戶的其他唯一識別碼資訊。 |

>[!NOTE]
>
>[!DNL Target] 雖然支援第一方和第三方跨網域Cookie，但僅建議將第一方 [!DNL Target] Cookie用於GDPR和CCPA。

### How does [!DNL Target] handle consent management? {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR和CCPA不會在您需要同意時變更，但您要如何取得。每個客戶的同意策略會根據其資料收集和使用實務，以及其隱私權政策來訂定。Consent management isn’t supported by and shouldn’t be achieved via [!DNL Target] for GDPR and CCPA.

[!DNL Adobe] 目前並未提供同意管理解決方案，但市場中已開發各種工具，可有效應付新需求中的部分內容。For more information on privacy tools in general, including consent managers, see the [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) on the *International Association of Privacy Professionals (iaap)* website.

[!DNL Target] 提供選擇加入功能支援 [!DNL Launch] ，以支援您的同意管理策略。Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. Using [!DNL Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide select elements of your page prior to the [!DNL Target] firing that might be helpful to leverage as part of your consent strategy.

For more information on GDPR, CCPA, and [!DNL Launch], see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Also, see the *Adobe Target and Experience Platform Launch opt-in* section above.

### AdobePrivacy.js 會將資訊提交至 GDPR API 嗎? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *不會*&#x200B;將此資訊提交至 API。此動作必須由客戶來執行。本程式庫僅會提供儲存在該特定訪客所使用之瀏覽器中的 ID。

### removeIdentities 會移除哪些內容? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities]*僅會*[!DNL Adobe]從瀏覽器移除身分資料，而此動作完全取決於 解決方案是否已實作此程式碼。

For example, [!DNL Target] deletes the cookies storing its IDs, but [!DNL Adobe Audience Manager] (AAM) does not delete the demdex ID that is stored in a third-party cookie.

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

In addition to the requirements from Central Privacy Service, a valid GDPR or CCPA message for [!DNL Target] contains:

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

Responses to access data requests contain a summary of the [!DNL Target] profile for the visitor in question. Note that this return is sent to the [!DNL Experience Cloud] GDPR API, which in turn sends Data Controllers a response.

A sample [!DNL Target] access API response could look like this:

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

當有多個值可用來識別設定檔時，每個有效的識別碼都會有一個設定檔檔案。The profile file(s) are sent to the central GDPR Azure Blob through the GDPR Central API, in the format of [!DNL Target] Profile JSON response.

[!DNL Target] 範例Profile JSON可能類似下列範例：

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
| Sample_Parameter | [!DNL Target] 資料中許多部分的資訊由資料掌控者上傳或直接提供。In this example, a parameter was uploaded into the [!DNL Target] profile using the Profile Update API. 如需詳細資訊，請參閱 [「方法將資料放入Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)」。 |
| user.ReturnTimeOfDay | 此標準欄位包含使用者最近回訪的時間。 |
| firstSessionStart | 此標準欄位包含使用者首次工作階段開始的時間。 |
| user.sessionCountScript | [!DNL Target] 資料中許多部分的資訊由資料掌控者上傳或直接提供。在此範例中，設定檔指令碼會遞增此訪客針對資料管控者網站執行工作階段的次數。如需詳細資訊，請參閱[設定檔指令碼屬性](/help/c-target/c-visitor-profile/profile-parameters.md)。 |

>[!NOTE]
>
>This is a shortened version of a [!DNL Target] profile JSON for the purpose of illustration. [!DNL Target] 大部份的設定檔欄位並非標準。傳回的內容取決於特定訪客設定檔中的資訊。

### Target 支援 IP 模糊化功能嗎?   {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] 支援IP模糊化，如果您選擇將它用作GDPR或CCPA實施策略的一部分。For more information, see [Privacy](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
