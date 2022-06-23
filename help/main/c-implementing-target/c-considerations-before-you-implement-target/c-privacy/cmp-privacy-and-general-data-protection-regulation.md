---
keywords: gdpr;eu;歐盟;隱私權;常見問題集;常見問題;加州消費者隱私保護法;ccpa;隱私權;資料保護;選擇退出;退出;政府;規範
description: 了解 [!DNL Target] 和歐盟一般資料保護規範 (GDPR)、加州消費者隱私保護法 (CCPA) 及其他隱私規定。
title: ' [!DNL Target] 如何處理隱私權與資料保護規範？'
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '2229'
ht-degree: 98%

---

# 隱私權與資料保護規範

有關歐盟一般資料保護規範 (GDPR)、加州消費者隱私保護法 (CCPA) 及其他國際隱私規定的資訊。 了解這些規範如何影響貴組織和 [!DNL Adobe Target]。

## 隱私權與一般資料保護規範 (GDPR) 總覽 {#topic_DE567ECB6C944695AEE5073889F1AEA9}

自 2018 年 5 月 25 日起，歐盟的 GDPR 已正式生效。 如需有關此規範對您有何意義的詳細資訊，請參閱 [GDPR 和您的企業](https://business.adobe.com/privacy/general-data-protection-regulation.html)。

當 [!DNL Adobe] 向企業提供軟體和服務時，為了提供這些服務，[!DNL Adobe] 會以資料處理者的角色處理和儲存任何個人資料。身為資料處理者，[!DNL Adobe] 會根據貴公司的權限和指示 (例如，依照您與 [!DNL Adobe] 的合約規定) 處理個人資料。

身為資料控管者，您可以決定由 [!DNL Adobe] 代表您處理和儲存的個人資料。如果使用 [!DNL Adobe Experience Cloud] 解決方案，則 [!DNL Adobe] 可能會根據您使用的解決方案，以及您選擇傳送到 [!DNL Adobe Experience Cloud] 帳戶的資訊，為您託管個人資料。如需範例的詳細清單，請參閱 [Adobe Experience Cloud 隱私權](https://www.adobe.com/privacy/experience-cloud.html#collect)。

[!DNL Adobe Experience Cloud] 為資料控管者提供 GDPR 就緒的 API，好讓他們完成下列工作：

* 存取儲存在 [!DNL Target] 中的資料主體資訊
* 刪除儲存在 [!DNL Target] 中的資料主體資訊

如需詳細資訊，請參閱：

* [Adobe Privacy Service 總覽](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=-blank}
* [Privacy Service API 指南](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target=_blank}
* [Privacy Service UI 總覽](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target=_blank}

## 加州消費者隱私保護法 (CCPA) 總覽

加州消費者隱私保護法 (CCPA) 為加州消費者提供關於其個人資訊的新權利，並對在加州執行業務的某些實體施加資料保護責任。CCPA 已於 2020 年 1 月 1 日生效。

整體來說，此法律賦予加州人多項重要權利，包括下列權利:

* 要求資訊 (資料存取)
* 選擇退出個人資訊銷售 (這是一項定義非常廣泛的權利，可選擇退出與第三方分享資訊)
* 要求刪除個人資訊
* 在個人資訊已公開或銷售時收到通知

如果您去年忙著為歐洲的隱私權法律 (GDPR) 做準備，您可能很熟悉這裡的其中一些權利，您已完成的大部分工作都可以重新利用。

>[!NOTE]
>
>存取和刪除適用於 CCPA 的資料會遵循與 GDPR 相同的流程。

## Adobe [!DNL Target] 和 [!DNL Adobe Experience Platform] 選擇加入 {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] 透過 [!DNL Adobe Experience Platform] 中的標記支援選擇加入功能，可協助支援您的知情同意管理策略。 選擇加入功能可讓客戶控制引發 [!DNL Target] 標記的方法和時機。也可選擇透過 [!DNL Adobe Experience Platform] 預先核准 [!DNL Target] 標記。若要啟用在 [!DNL Target] at.js 程式庫中使用選擇加入的功能，您應使用 `targetGlobalSettings` 並新增 `optinEnabled=true` 設定。在 [!DNL Adobe ExperiencePlatform] 中，從延伸模組安裝檢視中的 [!UICONTROL GDPR 選擇加入]下拉式清單中選取「啟用」。 如需詳細資訊，請參閱[實作  [!DNL Target]  - 使用  [!DNL Adobe Experience Platform]。](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/)

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
>建議使用 [!DNL Adobe Experience Platform] 管理選擇加入。[!DNL Adobe Experience Platform] 中有進一步精細控制的功能，可在 [!DNL Target] 引發前隱藏選取的頁面元素，可能利於用於知情同意策略的一部分。

使用「選擇加入」時，該考慮三種情況:

1. **[!DNL Target] 標記是透過 [!DNL Adobe Experience Platform] 預先核准 (或資料主體先前核准 [!DNL Target]):**[!DNL Target] 標記不會為同意保留，並照常運作。
1. **[!DNL Target] 標記「不會」預先核准且 `bodyHidingEnabled` 為「FALSE」:**[!DNL Target] 標記僅在向客戶取得同意後觸發。取得同意前，僅可使用預設內容。收到同意後，系統會呼叫 [!DNL Target]，資料主體 (訪客) 即可使用個人化內容。由於知情同意前只能使用預設內容，因此使用適當的策略很重要，例如蓋住頁面任何部分的啟動顯示畫面或可個人化的內容。 此程序可確保資料主體 (訪客) 的體驗保持一致。
1. **[!DNL Target] 標記「不會」預先核准且 `bodyHidingEnabled` 為「TRUE」:**[!DNL Target] 標記僅在向客戶取得同意後觸發。取得同意前，僅可使用預設內容。但由於 `bodyHidingEnabled` 設為 True，`bodyHiddenStyle` 會指定在觸發 [!DNL Target] 標記前隱藏的頁面內容 (或資料主體拒絕選擇加入，而顯示預設內容)。根據預設，`bodyHiddenStyle` 設定為 `body { opacity:0;}`，這會隱藏 HTML 內文標記。 Adobe 建議的頁面設定如下，以便將頁面內容放入一個容器，並將知情同意管理程式對話框放入另一個容器，即可隱藏頁面的整個內文，而不是知情同意管理程式對話框。 此設定會將 [!DNL Target] 設定為只隱藏頁面內容容器。 請參閱 [Privacy Service 總覽](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant)。

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

有關歐盟一般資料保護規範 (GDPR)、加州消費者隱私保護法 (CCPA) 及 [!DNL Target] 特有的其他國際隱私規定的常見問題集。

### [!DNL Adobe] 針對這些規範採取什麼政策？ {#section_A6849628D6524C80A6E16946DC5D25A9}

身為資料處理者，[!DNL Adobe] 已符合相關規範或致力於履行我們的義務。 Adobe 在設計上擁有經過認證的安全性與隱私權控制的堅實基礎，並已於 2018 年 5 月的截止日期前對產品做了強化。 企業客戶有責任實作這些增強功能，並更新任何必要的政策和程序。

### 我們公司身為資料控管者，必須對每個使用的 [!DNL Adobe Experience Cloud] 解決方案提交 GDPR 或 CCPA 要求嗎？ {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

不需要，[!DNL Adobe] 會以集中的方式協助資料控管者符合其 GDPR 和 CCPA 規定。 資料控管者無需直接處理每個解決方案。

各種 [!DNL Experience Cloud] 解決方案 (包括 [!DNL Target]) 中的所有 GDPR 和 CCPA 要求都是透過目前稱為 GDPR API 的中央 [!DNL Adobe] API 來執行。 此 API 接著會完成資料控管者的 [!DNL Experience Cloud] 解決方案套件上的要求。

### [!DNL Adobe] 會讓客戶刪除哪些資訊來回應資料主體/使用者要求？ {#section_4B51D00924EC4166B2442218B69214F0}

有關 [!DNL Target] 中的個別訪客資訊會包含在 [!DNL Target] 訪客資料中。 [!DNL Target] 可讓客戶刪除與其訪客資料中之 ID 相關的所有資料。 如需個人資料 [!DNL Target] 存放區的範例，請參閱[訪客個人資料](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)。

不會識別特定個人的彙總或匿名資料 (例如報告資料)，或與特定個人不相關的資料 (例如內容資料)，則不在使用者刪除要求的範圍之內。

[!DNL Target] 長達 90 天未使用的訪客個人資料會依預設刪除，您無需採取任何動作。

### 哪些 ID 受到支援，並且可協助客戶完成針對 [!DNL Target] 的 GDPR 或 CCPA 存取及刪除要求? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] 支援下列 ID 類型，以便找出客戶個人資料:

| 使用者 ID | 命名空間 ID 類型 | 命名空間 ID | 定義 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | [!UICONTROL Adobe Experience Cloud ID]，先前稱為訪客 ID 或 Experience Cloud ID。 您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| TnT ID/Cookie ID(TNTID) | 標準 | 9 | 在訪客的瀏覽器中設為 Cookie 的 [!DNL Target] 識別碼。 您可以使用 JavaScript API 找到此 ID (請參閱下方的詳細資料)。 |
| 第三方 ID/CRM ID(THIRDPARTYID) | [!DNL Target] 特有 | 不適用 | 如果您向 [!DNL Target] 提供您的 CRM 或客戶的其他唯一識別碼資訊。 |

>[!NOTE]
>
>雖然 [!DNL Target] 對第一方和第三方跨網域 Cookie 都有支援，但只建議將第一方 [!DNL Target] Cookie 用於 GDPR 和 CCPA。

### [!DNL Target] 如何處理知情同意管理？ {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR 和 CCPA 不會改變您必須取得同意的時間，而是改變您取得同意的方式。 每個客戶的知情同意策略會依據其資料收集和使用做法以及其隱私權政策而定。 [!DNL Target] 不支援 GDPR 和 CCPA 的同意管理，也不應作為達成此功能的工具。

[!DNL Adobe] 目前並未提供同意管理解決方案，但市場中已開發各種工具，可有效應付新需求中的部分內容。如需一般隱私工具的詳細資訊，包括知情同意管理程式，請參閱&#x200B;*國際隱私權專家協會 (iaap)* 網站上的 [2017 年隱私技術廠商報告](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf)。

[!DNL Target] 透過 [!DNL Adobe Experience Platform] 支援選擇加入功能，可協助支援您的知情同意管理策略。 選擇加入功能可讓客戶控制引發 [!DNL Target] 標記的方法和時機。也可選擇透過 [!DNL Adobe Experience Platform] 預先核准 [!DNL Target] 標記。建議使用 [!DNL Adobe Experience Platform] 管理選擇加入。[!DNL Adobe Experience Platform] 中有更精細的控制功能，可在 [!DNL Target] 引發前隱藏選取的頁面元素，可能利於用於知情同意策略的一部分。

如需有關 GDPR、CCPA 和 [!DNL Adobe Experience Platform] 的詳細資訊，請參閱 [Adobe 隱私權 JavaScript 程式庫和 GDPR](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en)。 另請參閱上面的 *Adobe Target 和 Adobe Experience Platform 選擇加入*&#x200B;一節。

### `AdobePrivacy.js` 會將資訊提交至 GDPR API 嗎？ {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *不會*&#x200B;將此資訊提交至 API。此動作必須由客戶來執行。本程式庫僅會提供儲存在該特定訪客所使用之瀏覽器中的 ID。

### `removeIdentities` 會移除哪些內容？ {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`] *僅會*[!DNL Adobe]從瀏覽器移除身分資料，而此動作完全取決於 解決方案是否已實作此程式碼。

例如，[!DNL Target] 會刪除儲存訪客 ID 的 Cookie，但 [!DNL Adobe Audience Manager] (AAM) 不會刪除儲存在協力廠商 Cookie 中的 demdex ID。

### [!DNL Target] GDPR 或 CCPA 要求中必須包含哪些資訊？ {#section_D29A4744AE6344E68AD7710B185FD6D0}

除了中央 Privacy Service 的需求，[!DNL Target] 的有效 GDPR 或 CCPA 訊息也包含：

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

### 透過 GDPR API，我應該可以從 [!DNL Target] 得到哪些類型的回應？ {#section_F67263D2A72B4641A47CE36729CCAE8F}

| 要求狀態 | [!DNL Target] 回應訊息 | 藍本 |
|--- |--- |--- |
| 正在處理 | 正在處理 | [!DNL Target] 已收到 GDPR 或 CCPA 要求，且正在處理中。 |
| 完成 | 不適用 - 公司環境不適用 | GDPR 或 CCPA 要求中的 IMS ID 未對應到任何 [!DNL Target] 用戶端。<br>某些公司有多個 IMS ID。 在已佈建 [!DNL Target] 的地方提交 IMS ID。 |
| 完成 | 不適用 - 使用者環境不適用 | GDPR 或 CCPA 要求中針對特定訪客或資料主體提供的 ID 不在 [!DNL Target] 個人資料存放區中。<br>如果您試圖提交 [!DNL Target] 不支援的命名空間 ID 類型 (請參閱上面所述的支援的 ID)，也會傳回這樣的結果。 |
| 錯誤 | 錯誤訊息 (詳細資訊會視錯誤類型而定) | 擷取或刪除要求的資料主體個人資料時發生錯誤。<br>因應存取要求上傳至 Azure 時發生錯誤。 |

### [!DNL Target] 針對存取要求傳送至 GDPR API 的回應是什麼？ {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

存取資料要求的回應包含特定訪客的 [!DNL Target] 個人資料摘要。 此傳回內容會傳送至 [!DNL Experience Cloud] GDPR API，接著傳送回應給資料控管者。

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
| namespace | 亦稱為資料來源。請參閱「哪些 ID 受到支援，並且可協助客戶完成針對 [!DNL Target] 的 GDPR 或 CCPA 存取及刪除要求？」GDPR 存取及刪除要求?」 |
| type | 您要求 GDPR 或 CCPA 資料存取權限的 ID 類型。[!DNL Target] 接受多種 ID 類型，部分為標準型，有些則為 [!DNL Target] 專用型。 請參閱「哪些 ID 受到支援，並且可協助客戶完成針對 [!DNL Target] 的 GDPR 或 CCPA 存取及刪除要求？」GDPR 存取及刪除要求?」 |
| value | namespace/資料來源的 ID。請參閱「哪些 ID 受到支援，並且可協助客戶完成針對 [!DNL Target] 的 GDPR 或 CCPA 存取及刪除要求？」，以瞭解接受的值。 |
| 整合程式碼 | 整合程式碼為易記的資料來源名稱，比起使用資料來源 ID，可協助您更輕鬆地追蹤資料來源。 |

當有多個值可用來識別個人資料時，每個有效的識別碼都會有一個個人資料檔案。一個或多個個人資料檔案會透過 GDPR 中央 API，以 [!DNL Target] 個人資料 JSON 回應格式傳送至中央 GDPR Azure Blob。

[!DNL Target] 個人資料 JSON 的範例看起來可能像下面的例子:

```
{"profileAttributes": 
 
"Sample_Parameter":{"value":"Gold Loyalty Status","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"user.ReturnTimeOfDay":{"value":"44.0","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"firstSessionStart":{"value":"1523497450602","modifiedAt":"2018-04-11T21:44:10.000-04:00"}, 
 
"user.sessionCountScript":{"value":"1","modifiedAt":"2018-04-11T21:44:14.000-04:00"} 
   } 
} 
```

下表包含說明性的個人資料 JSON 欄位描述:

| 欄位 | 說明 |
|--- |--- |
| Sample_Parameter | [!DNL Target] 個人資料中的許多資訊都是由資料控管者上傳或直接提供。在此範例中，參數是使用個人資料更新 API 上傳到 [!DNL Target] 個人資料中。有關詳細資訊，請參見 [將資料獲取到的方法 [!DNL Target]](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/)。 |
| user.ReturnTimeOfDay | 此標準欄位包含使用者最近回訪的時間。 |
| firstSessionStart | 此標準欄位包含使用者首次工作階段開始的時間。 |
| user.sessionCountScript | [!DNL Target] 個人資料中的許多資訊都是由資料控管者上傳或直接提供。在此範例中，個人資料指令碼會遞增此訪客針對資料管控者網站執行工作階段的次數。如需詳細資訊，請參閱[設定檔指令碼屬性](/help/main/c-target/c-visitor-profile/profile-parameters.md)。 |

>[!NOTE]
>
>此程式碼範例是說明用的簡短版 [!DNL Target] 個人資料 JSON。 [!DNL Target] 個人資料的許多欄位並非標準欄位。傳回的內容取決於特定訪客個人資料中的資訊。

### [!DNL Target] 是否支援 IP 模糊化功能？ {#section_428907B0CD9842D9B245B38C66A53C6A}

如果您選擇使用 [!DNL Target] 作為 GDPR 或 CCPA 實作策略, Target 則支援 IP 模糊化功能。如需詳細資訊，請參閱[隱私權](https://developer.adobe.com/target/before-implement/privacy/privacy/)。

### 我應該採取某個行動來避免我的資料被分享或賣給第三方嗎？

[!DNL Target] 不允許客戶直接從 [!DNL Target] 分享或銷售資料給第三方，所以不需要針對 [!DNL Target] 選擇退出銷售。
