---
keywords: gdpr;eu;歐盟;隱私權;常見問題集;常見問題集;加州消費者隱私保護法;ccpa;隱私權;資料保護;選擇退出;選擇退出;政府;規範
description: 瞭解 [!DNL Target] 以及歐盟一般資料保護條例(GDPR)、加利福尼亞消費者隱私法(CCPA)和其他隱私要求。
title: 如何 [!DNL Target] 處理隱私和資料保護法規？
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2193'
ht-degree: 54%

---

# 隱私權與資料保護規範

有關歐盟一般資料保護條例(GDPR)、加利福尼亞消費者隱私法(CCPA)和其他國際隱私要求的資訊。 瞭解這些管理法規如何影響您的組織和 [!DNL Adobe Target]。

## 隱私權與資料保護規範 (GDPR) 概覽 {#topic_DE567ECB6C944695AEE5073889F1AEA9}

自 2018 年 5 月 25 日起，歐盟的 GDPR 已正式生效。有關此條例對您意味著什麼的詳細資訊，請參見 [GDPR和您的業務](https://business.adobe.com/privacy/general-data-protection-regulation.html)。

當 [!DNL Adobe] 向企業提供軟體和服務時，為了提供這些服務，[!DNL Adobe] 會以資料處理者的角色處理和儲存任何個人資料。身為資料處理者，[!DNL Adobe] 會根據貴公司的權限和指示 (例如，依照您與 [!DNL Adobe] 的合約規定) 處理個人資料。

身為資料控管者，您可以決定由 [!DNL Adobe] 代表您處理和儲存的個人資料。如果使用 [!DNL Adobe Experience Cloud] 解決方案，則 [!DNL Adobe] 可能會根據您使用的解決方案，以及您選擇傳送到 [!DNL Adobe Experience Cloud] 帳戶的資訊，為您託管個人資料。如需詳細的範例清單，請參閱 [Adobe Experience Cloud 隱私權](https://www.adobe.com/privacy/experience-cloud.html#collect)。

[!DNL Adobe Experience Cloud] 為資料控制器提供GDPR就緒API，允許它們完成以下任務：

* 存取儲存在 [!DNL Target] 中的資料主體資訊
* 刪除儲存在 [!DNL Target] 中的資料主體資訊

如需詳細資訊，請參閱:

* [Adobe 一般資料保護規範 API 網站](https://www.adobe.io/apis/experienceplatform/gdpr.html)
* [GDPR 文件](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en)

## 加州消費者隱私保護法 (CCPA) 概覽

加州消費者隱私保護法 (CCPA) 為加州消費者提供關於其個人資訊的新權利，並對在加州執行業務的某些實體施加資料保護責任。《保護婦女兒童公約》於2020年1月1日起實施。

整體來說，此法律賦予加州人多項重要權利，包括下列權利:

* 要求資訊 (資料存取)
* 選擇不銷售個人資訊（一種廣義的權利，即選擇不與第三方共用資訊）
* 要求刪除個人資訊
* 在個人資訊已公開或銷售時收到通知

如果你去年忙於準備歐洲隱私法(GDPR)，這些權利中的一些可能已經熟悉，而你所做的大部分工作可以重新利用。

>[!NOTE]
>
>訪問和刪除資料時，資料應用於CCPA的過程與GDPR的過程相同。

## Adobe [!DNL Target] 和 [!DNL Adobe Experience Platform] 選擇加入 {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] 通過標籤插入提供選擇加入功能支援 [!DNL Adobe Experience Platform] 幫助支援您的同意管理策略。 選擇加入功能可讓客戶控制引發 [!DNL Target] 標記的方法和時機。也可選擇透過 [!DNL Adobe Experience Platform] 預先核准 [!DNL Target] 標記。若要啟用在 [!DNL Target] at.js 資料庫中使用選擇加入的功能，您應使用 `targetGlobalSettings` 並新增 `optinEnabled=true` 設定。在 [!DNL Adobe ExperiencePlatform]，從 [!UICONTROL GDPR選擇加入] 下拉清單。 請參閱 [實施 [!DNL Target] 使用 [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 的子菜單。

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
>建議使用 [!DNL Adobe Experience Platform] 管理選擇加入。在 [!DNL Adobe Experience Platform] 要隱藏頁面的選定元素，請在 [!DNL Target] 這有助於你的同意策略。

使用「選擇加入」時，該考慮三種情況:

1. **[!DNL Target] 標記是透過 [!DNL Adobe Experience Platform] 預先核准 (或資料主體先前核准 [!DNL Target]):**[!DNL Target] 標記不會為同意保留，並照常運作。
1. **[!DNL Target] 標記「不會」預先核准且 `bodyHidingEnabled` 為「FALSE」:**[!DNL Target] 標記僅在向客戶取得同意後觸發。取得同意前，僅可使用預設內容。收到同意後，系統會呼叫 [!DNL Target]，資料主體 (訪客) 即可使用個人化內容。因為只有預設內容在同意前才可用，所以使用適當的策略非常重要，例如包含頁面任何部分或可能個性化的內容的閃屏頁面。 此過程確保資料主題（訪問者）的體驗保持一致。
1. **[!DNL Target] 標記「不會」預先核准且 `bodyHidingEnabled` 為「TRUE」:**[!DNL Target] 標記僅在向客戶取得同意後觸發。取得同意前，僅可使用預設內容。但由於 `bodyHidingEnabled` 設為 True，`bodyHiddenStyle` 會指定在觸發 [!DNL Target] 標記前隱藏的頁面內容 (或資料主體拒絕選擇加入，而顯示預設內容)。預設情況下， `bodyHiddenStyle` 設定為 `body { opacity:0;}`，它隱藏HTML體標籤。 Adobe建議的頁面配置位於下面，以便將頁面的內容放在一個容器中，將同意管理器對話框放在單獨的容器中，從而隱藏頁面的整個正文（不包括同意管理器對話框）。 這項設定會將 [!DNL Target] 設定為只隱藏頁面內容容器。查看 [Privacy Service概述](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en)。

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

關於歐盟一般資料保護條例(GDPR)、加利福尼亞消費者隱私法(CCPA)和其他特定於 [!DNL Target]。

### 是什麼 [!DNL Adobe] 這些條例的政策？ {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] 已履行或正在履行其作為資料處理器的義務。 Adobe通過設計，為經過認證的安全和隱私控制奠定了堅實的基礎，並在2018年5月的最後期限之前對產品進行了增強。 企業客戶有責任實施這些增強功能並更新任何必要的策略和程式。

### 必須將GDPR或CCPA請求提交給每個公司，即資料控制器 [!DNL Adobe Experience Cloud] 解決方案？ {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

不， [!DNL Adobe] 提供了幫助資料控制器滿足其GDPR和CCPA要求的中心方法。 資料控制器不需要直接訪問每個解決方案。

跨所有GDPR和CCPA請求 [!DNL Experience Cloud] 解決方案，包括 [!DNL Target]，通過中心 [!DNL Adobe] API，當前稱為GDPR API。 然後，API將完成跨資料控制器的請求 [!DNL Experience Cloud] 解決方案套件。

### 資訊是什麼 [!DNL Adobe] 是否允許客戶根據資料主題/用戶請求刪除？ {#section_4B51D00924EC4166B2442218B69214F0}

有關 [!DNL Target] 中的個別訪客資訊會包含在 [!DNL Target] 訪客設定檔中。[!DNL Target] 允許客戶刪除其訪問者配置檔案中與ID關聯的所有資料。 如需設定檔資料 [!DNL Target] 儲存的範例，請參閱[訪客設定檔](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)。

不會識別特定個人的彙總或匿名資料 (例如報告資料)，或與特定個人不相關的資料 (例如內容資料)，則不在使用者刪除要求的範圍之內。

[!DNL Target] 長達 90 天未使用的 訪客設定檔會依預設刪除，您無需採取任何動作。

### 哪些 ID 受到支援，並且可協助客戶完成針對 [!DNL Target] 的 GDPR 或 CCPA 存取及刪除要求? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] 支援下列 ID 類型，以便找出客戶設定檔:

| 使用者 ID | 命名空間 ID 類型 | 命名空間 ID | 定義 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | [!UICONTROL Adobe Experience CloudID]，以前稱為訪問者ID或Experience CloudID。 您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| TnT ID/Cookie ID(TNTID) | 標準 | 9 | [!DNL Target]在訪客的瀏覽器中設為 Cookie 的 識別碼。您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| 第三方 ID/CRM ID(THIRDPARTYID) | [!DNL Target]-特定 | 不適用 | 如果您提供 [!DNL Target] 您的客戶的CRM或其他唯一標識符資訊。 |

>[!NOTE]
>
>雖然 [!DNL Target] 對第一方和協力廠商跨網域 Cookie 均有支援，但只建議將第一方 [!DNL Target] Cookie 用於 GDPR 和 CCPA。

### [!DNL Target] 如何處理同意管理?  {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR和CCPA在您必須獲得同意時不會更改，而是您如何獲得同意。 每個客戶的同意策略取決於其資料收集和使用實踐及其隱私策略。 [!DNL Target] 不支援 GDPR 和 CCPA 的同意管理，也不應作為達成此功能的工具。

[!DNL Adobe] 目前並未提供同意管理解決方案，但市場中已開發各種工具，可有效應付新需求中的部分內容。有關一般隱私工具（包括許可管理者）的詳細資訊，請參閱 [2017隱私技術供應商報告](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) 的 *國際隱私專業人士協會* 的子菜單。

[!DNL Target] 通過 [!DNL Adobe Experience Platform] 支援您的同意管理策略。 選擇加入功能可讓客戶控制引發 [!DNL Target] 標記的方法和時機。也可選擇透過 [!DNL Adobe Experience Platform] 預先核准 [!DNL Target] 標記。建議使用 [!DNL Adobe Experience Platform] 管理選擇加入。在 [!DNL Adobe Experience Platform] 隱藏頁面的選定元素 [!DNL Target] 開槍可能有助於你的同意策略。

有關GDPR、CCPA和 [!DNL Adobe Experience Platform]，請參閱 [Adobe隱私JavaScript庫和GDPR](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en)。 另請參見 *Adobe Target和Adobe Experience Platform選擇加入* 的上界。

### `AdobePrivacy.js` 會將資訊提交至 GDPR API 嗎? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *不會*&#x200B;將此資訊提交至 API。此動作必須由客戶來執行。本程式庫僅會提供儲存在該特定訪客所使用之瀏覽器中的 ID。

### 什麼是 `removeIdentities` 刪除？ {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`] *僅會*[!DNL Adobe]從瀏覽器移除身分資料，而此動作完全取決於 解決方案是否已實作此程式碼。

例如，[!DNL Target] 會刪除儲存訪客 ID 的 Cookie，但 [!DNL Adobe Audience Manager] (AAM) 不會刪除儲存在協力廠商 Cookie 中的 demdex ID。

### 必須包含哪些資訊 [!DNL Target] GDPR還是CCPA請求？ {#section_D29A4744AE6344E68AD7710B185FD6D0}

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

### 我期望從哪些類型的響應 [!DNL Target] 通過GDPR API嗎？ {#section_F67263D2A72B4641A47CE36729CCAE8F}

| 要求狀態 | [!DNL Target] 響應消息 | 藍本 |
|--- |--- |--- |
| 正在處理 | 正在處理 | [!DNL Target] 已收到 GDPR 或 CCPA 要求，且正在處理中。 |
| 完成 | 不適用 - 公司環境不適用 | GDPR或CCPA請求中的IMS ID未映射到任何 [!DNL Target] 客戶端。<br>一些公司擁有多個IMS ID。 提交IMS ID，其中 [!DNL Target] 已設定。 |
| 完成 | 不適用 - 使用者環境不適用 | GDPR或CCPA請求中為特定訪問者或資料主題提供的ID不在 [!DNL Target] 配置檔案儲存。<br>如果嘗試提交不受支援的命名空間ID類型，則此結果也會返回 [!DNL Target] （有關支援的ID，請參見上文）。 |
| 錯誤 | 錯誤訊息 (詳細資訊會視錯誤類型而定) | 擷取或刪除要求的資料主體設定檔時發生錯誤。<br>因應存取要求上傳至 Azure 時發生錯誤。 |

### 什麼響應 [!DNL Target] 發送到GDPR API以獲取訪問請求？ {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

存取資料要求的回應包含特定訪客的 [!DNL Target] 設定檔摘要。此返回將發送到 [!DNL Experience Cloud] GDPR API ，它反過來向資料控制器發送響應。

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
| namespace | 亦稱為資料來源。請參閱「支援哪些ID以幫助客戶完成GDPR或CCPA訪問和刪除請求 [!DNL Target]?&quot; GDPR 存取及刪除要求?」 |
| type | 您要求 GDPR 或 CCPA 資料存取權限的 ID 類型。[!DNL Target] 接受多種ID類型，其中有些是標準類型，有些是特定於 [!DNL Target]。 請參閱「支援哪些ID以幫助客戶完成GDPR或CCPA訪問和刪除請求 [!DNL Target]?&quot; GDPR 存取及刪除要求?」 |
| value | namespace/資料來源的 ID。請參閱「支援哪些ID以幫助客戶完成GDPR或CCPA訪問和刪除請求 [!DNL Target]?&quot; ，以瞭解接受的值。 |
| 整合程式碼 | 整合程式碼為易記的資料來源名稱，比起使用資料來源 ID，可協助您更輕鬆地追蹤資料來源。 |

當有多個值可用來識別設定檔時，每個有效的識別碼都會有一個設定檔檔案。一個或多個配置檔案通過GDPR Central API以格式發送到中央GDPR Azure Blob [!DNL Target] 配置檔案JSON響應。

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
| Sample_Parameter | [!DNL Target] 設定檔中的許多資訊都是由資料控管者上傳或直接提供。在此範例中，參數是使用設定檔更新 API 上傳到 [!DNL Target] 設定檔中。如需詳細資訊，請參閱[將資料傳入 的方法 [!DNL Target]](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)。 |
| user.ReturnTimeOfDay | 此標準欄位包含使用者最近回訪的時間。 |
| firstSessionStart | 此標準欄位包含使用者首次工作階段開始的時間。 |
| user.sessionCountScript | [!DNL Target] 設定檔中的許多資訊都是由資料控管者上傳或直接提供。在此範例中，設定檔指令碼會遞增此訪客針對資料管控者網站執行工作階段的次數。如需詳細資訊，請參閱[設定檔指令碼屬性](/help/main/c-target/c-visitor-profile/profile-parameters.md)。 |

>[!NOTE]
>
>此代碼示例是 [!DNL Target] 配置檔案JSON用於插圖。 [!DNL Target] 設定檔的許多欄位並非標準欄位。傳回的內容取決於特定訪客設定檔中的資訊。

### 是 [!DNL Target] 是否支援IP混淆？ {#section_428907B0CD9842D9B245B38C66A53C6A}

如果您選擇使用 [!DNL Target] 作為 GDPR 或 CCPA 實作策略, Target 則支援 IP 模糊化功能。如需詳細資訊，請參閱[隱私權](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0)。

### 我是否應該採取措施防止共用資料或將其出售給第三方？

[!DNL Target] 不允許客戶直接從 [!DNL Target] 第三方，因此並無可選擇 [!DNL Target]。
