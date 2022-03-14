---
keywords: 客戶關係管理；客戶記錄服務；crs;crm;mbox3rdpartyid；客戶屬性；目標；csv;crm;adobe經驗雲人員
description: 瞭解如何使用客戶關係管理(CRM)資料庫中的企業客戶資料，以在 [!DNL Adobe Target]。
title: 什麼是客戶屬性以及如何使用這些屬性？
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 34%

---

# 客戶屬性

有關使用Customer Relationship Management(CRM)資料庫中的企業客戶資料以在 [!DNL Adobe Target] 在 [!DNL Adobe Enterprise Cloud People] 服務。

通過多個源收集並儲存在CRM資料庫中的企業客戶資料可用於 [!DNL Target] 戰略性地向客戶提供最相關的內容，特別是重點放在返回的客戶上。 中的受眾和客戶屬性 [!DNL People] 服務（以前是配置式和受眾）將資料收集和分析與測試和優化結合起來，使資料和洞見具有可操作性。

## 客戶屬性概述 {#section_B4099971FA4B48598294C56EAE86B45A}

[客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) 的 [!DNL People] 服務是 [!DNL Adobe Experience Cloud] 並為企業提供將客戶資料推送到 [!DNL Experience Cloud] 平台。

上架到 [!DNL Experience Cloud] 的資料可供所有 [!DNL Experience Cloud] 工作流程使用。[!DNL Target] 使用此資料根據屬性針對返回的客戶。 [!DNL Adobe Analytics] 會利用這些屬性，並可將這些屬性用於分析和劃分。

![crs示例](/help/main/c-target/c-visitor-profile/assets/crs.png)

考慮以下資訊作為您處理客戶屬性和 [!DNL Target]:

* 在使用 [!UICONTROL 客戶屬性] 的 [!DNL People] 服務。 有關詳細資訊，請參閱中的「上載客戶屬性的先決條件」 [客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) 的 *Experience Cloud服務和管理文檔*。
* 請注意檔案上載方面的限制，如中所述 [關於客戶屬性的資料檔案和資料源](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=zh-Hant) 的 *Experience Cloud中央介面元件指南*。 作為最佳做法：

   * 上載單個大型檔案(位於 [限制](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en))。 與多個較小的檔案相比，最好使用單個大檔案。
   * 如果必須將上載拆分為多個檔案，請確保在提交新檔案之前已完全處理檔案。 確保在提交批中的下一個檔案之前，已對批中的每個檔案進行完全處理。

* [!DNL Adobe] 不保證CRM資料庫中100%的客戶屬性（訪問者配置檔案）資料將連接到 [!DNL Experience Cloud] 因此，可用於 [!DNL Target]。 在當前設計中，有可能不裝載一小部分資料（大型生產批的0.1%）。
* 從導入的 [!DNL Experience Cloud] 至 [!DNL Target] 取決於訪問者配置檔案的使用期，預設為14天。 有關詳細資訊，請參見 [訪問者配置檔案生存期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)。
* 如果 `vst.*` 參數是唯一標識訪問者的東西，只要現有的「已驗證」配置檔案不會被提取 `authState` 為未驗證(0)。 只有在 `authState` 已更改為AUTHENTICATED(1)。

   例如，如果 `vst.myDataSource.id` 參數用於標識訪問者(其中 `myDataSource` 是資料源別名)，並且沒有MCID或第三方ID，使用參數 `vst.myDataSource.authState=0` 不提取可能通過客戶屬性導入建立的配置檔案。 如果所需的行為是讀取經過驗證的配置檔案， `vst.myDataSource.authState` 必須具有值1（已驗證）。

* 您無法在 `mbox3rdPartyID` 中傳送下列字元: 加號 (+) 和正斜線 (/)。

## 訪問People服務中的客戶屬性

1. 在 [!DNL Adobe Experience Cloud]，按一下菜單表徵圖( ![菜單表徵圖](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ，然後按一下 **[!UICONTROL 人物]**。

   ![People](/help/main/c-target/c-visitor-profile/assets/people.png)

1. 按一下 **[!UICONTROL 客戶屬性]** 頁籤。

   ![「客戶屬性」標籤](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## 客戶屬性工作流 [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

完成下列步驟在 [!DNL Target] 使用 CRM 資料，如下圖所示:

![crm工作流](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

有關完成以下任務的詳細說明，請參見 [建立客戶屬性源並上載資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) 的 *Experience Cloud服務和管理文檔*。

1. 建立資料檔案。

   從您的 CRM 將客戶資料匯出為 CSV 格式，以建立 .csv 檔案。此外，您也可以建立 zip 或 gzip 檔案進行上傳。確保CSV檔案的第一行是標題，並且所有行（客戶資料）的條目數相同。

   下圖顯示了企業客戶資料檔案示例：

   ![crs樣本](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   下圖顯示了企業客戶.csv檔案示例：

   ![csv示例](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 建立屬性來源及上傳資料檔案。

   指定資料來源的名稱和描述，以及別名 ID。別名ID是唯一ID，用於中的客戶屬性代碼 `VisitorAPI.js`。

   >[!IMPORTANT]
   >
   >資料來源名稱和屬性名稱不得有英文句點。

   您的資料檔案必須符合檔案上載要求，並且不能超過100 MB。 如果檔案太大，或者您有必須定期上載的資料，則可以改為FTP檔案。

   * **HTTPS:** 可以拖放.csv資料檔案，或按一下 **[!UICONTROL 瀏覽]** 從檔案系統上傳。
   * **FTP:** 按一下FTP連結以 [通過FTP上傳檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。 第一個步驟是提供 Adobe 所提供 FTP 伺服器的密碼。指定密碼，然後按一下 **[!UICONTROL 完成]**。

   現在將您的 CSV/ZIP/GZIP 檔案傳輸至 FTP 伺服器。此檔案傳輸成功後，建立具有相同名稱和 `.fin` 擴展。 將此空白檔案傳輸至伺服器。這表示傳輸的結束和 [!DNL Experience Cloud] 開始處理資料檔案。

1. 驗證結構。

   驗證程序可讓您將顯示名稱和說明對應至已上傳的屬性 (字串、整數、數字等)。將每個屬性與其正確的資料類型、顯示名稱和說明對應。

   按一下 **[!UICONTROL 保存]** 架構驗證完成後。 檔案上傳時間因大小而不同。

   ![驗證架構](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上載架構](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. 設定訂閱及啟動屬性來源。

   按一下&#x200B;**[!UICONTROL 「新增訂閱」]**，然後選取要訂閱這些屬性的解決方案。[配置訂閱](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) 設定資料流 [!DNL Experience Cloud] 和解決方案。 啟動屬性來源可讓資料流向訂閱的解決方案。您上傳的客戶記錄將與從您的網站或應用程式傳入的 ID 訊號比對。

   ![配置解決方案](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![啟動](/help/main/c-target/c-visitor-profile/assets/activate.png)

   執行此步驟時，請注意下列限制:

   * 使用 HTTP 方法的每個上傳的最大檔案大小為 100 MB。
   * 使用 FTP 方法的每個上傳的最大檔案大小為 4 GB。
   * 允許訂閱的屬性數量: [!DNL Target Standard] 為 5 個，而 [!DNL Target Premium] 為 200 個。

## 在中使用客戶屬性 [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

您可以在 [!DNL Target] 中以下列方式使用客戶屬性:

### 建立鎖定目標對象

在 [!DNL Target] 中，您可在建立對象時，從訪客資料區段選取客戶屬性。清單中的所有客戶屬性都會具備字首 &lt; data_source_name >。視需要將這些屬性與其他資料屬性結合，以建立對象。

![目標對象](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### 使用 Token 建立設定檔指令碼

可在描述檔指令碼中使用 `crs.get('<Datasource Name>.<Attribute name>')` 格式參考客戶屬性。

可以直接在選件中使用此設定檔指令碼，用於傳遞屬於目前訪客的屬性。

### 在您的網站使用 mbox3rdPartyID 以獲得成功的實作和使用狀況

通過 `mbox3rdPartyId` 作為全局框的參數 `targetPageParams()` 的雙曲餘切值。 值 `mbox3rdPartyId` 應設定為CSV資料檔案中存在的客戶ID。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服務

如果您使用Experience CloudID服務，則必須設定「客戶ID」和「驗證狀態」，以在目標中使用客戶屬性。 有關詳細資訊，請參見 [客戶ID和身份驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) 的 *Experience CloudID服務幫助*。

如需關於在 [!DNL Target] 中使用客戶屬性的詳細資訊，請參閱下列資源:

* [建立客戶屬性源並上載資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) 的 *Experience Cloud服務和管理文檔*

## 客戶經常遇到的問題 {#section_BE0F70E563F64294B17087DE2BC1E74C}

使用客戶屬性和 [!DNL Target]。

>[!NOTE]
>
>問題1和問題2導致該領域大約60%的問題。 問題3導致大約30%的問題。 問題4導致大約5%的問題。 其餘的 5% 則因為雜項問題。

### 問題一：由於配置檔案太大，客戶屬性被刪除

使用者設定檔中的特定欄位沒有字元限制，但如果設定檔變得大於 64K，則會透過移除最舊的屬性來將它截斷，直到設定檔再次低於 64K 為止。

### 問題二：未列在中的受眾庫中的屬性 [!DNL Target]即使在幾天後

這通常是管線連線問題。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題三：傳遞不基於屬性工作

Edge 上的設定檔尚未更新。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題四：實施問題

請注意下列實作問題:

* 訪客 ID 未正確傳遞。ID已傳入 `mboxMCGVID` 而不是 `setCustomerId`。
* 傳遞的訪客 ID 正確，但 AUTHENTICATION 狀態未設為 Authenticated。
* `mbox3rdPartyId` 未正確傳遞。

### 問題五： `mboxUpdate` 未正確執行

`mboxUpdate` 未正確搭配 `mbox3rdPartyId` 執行。

### 問題六：未將客戶屬性導入 [!DNL Target]

如果在「目標」中找不到「客戶屬性」資料，請確保在上次導入時 *x* 天數 *x* 是目標 [訪問者配置檔案生存期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) 值（預設為14天）。

## 培訓視頻：使用客戶屬性上載離線資料 ![教程徽章](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

此視頻向您演示如何將離線CRM、幫助台、銷售點和其他營銷資料導入到 [!DNL Experience Cloud People] 服務，並使用其已知ID將其與訪問者關聯。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
