---
keywords: customer relationship management;customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm;adobe experience cloud people
description: 使用Adobe Experience Cloud People核心服務中的客戶屬性，從客戶關係管理(CRM)資料庫使用企業客戶資料以在Adobe Target中定位內容的相關資訊。
title: Adobe Target中的客戶屬性
feature: visitor profiles
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 37%

---


# 客戶屬性 {#customer-attributes}

Information about using enterprise customer data from Customer Relationship Management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud People] core service.

Enterprise customer data collected through multiple sources and stored inside CRM databases can be used in [!DNL Target] to strategically deliver the most relevant content to customers, specifically focusing on returning customers. Audiences and customer attributes in the [!DNL People] core service (formerly Profiles and Audiences) brings together data collection and analysis with testing and optimization, making data and insights actionable.

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

[核心服務中的客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) , [!DNL People] 是核心服務的一部分，為企業提供 [!DNL Adobe Experience Cloud] 了將客戶資料推送至平台的工具 [!DNL Experience Cloud] 。

上架到 [!DNL Experience Cloud] 的資料可供所有 [!DNL Experience Cloud] 工作流程使用。[!DNL Target] 使用此資料根據屬性定位舊客戶。 [!DNL Adobe Analytics] 會利用這些屬性，並可將這些屬性用於分析和劃分。

![crs示例](/help/c-target/c-visitor-profile/assets/crs.png)

Consider the following information as your work with customer attributes and [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL People] core service. For more information, see &quot;Prerequisites for uploading Customer Attributes&quot; in [Customer attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) in the *Experience Cloud and Core Services Product documentation*.

   >[!NOTE]
   >
   >[!DNL at.js] （任何版本）或 [!DNL mbox.js] 58版或更新版本為必要。

* [!DNL Adobe] 不保證來自CRM資料庫的100%客戶屬性（訪客資料）資料會載入 [!DNL Experience Cloud] ，因此可用於定位 [!DNL Target]。 在我們目前的設計中，有可能少量的資料（大量生產批次的0.1%）無法封存。
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. 如需詳細資訊，請參閱訪 [客資料存留期](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)。
* If the `vst.*` parameters are the only thing identifying the visitor, the existing &quot;authenticated&quot; profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile will come into play only if `authState` is changed to AUTHENTICATED (1).

   For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won&#39;t fetch the profile that might have been created through a Customer Attributes import. If the desired behavior is to fetch the authenticated profile, the `vst.myDataSource.authState` must have the value of 1 (AUTHENTICATED).

* 您無法在 `mbox3rdPartyID` 中傳送下列字元: 加號 (+) 和正斜線 (/)。

## 在人員核心服務中訪問客戶屬性

1. 在中，單 [!DNL Adobe Experience Cloud]擊菜單表徵圖(菜 ![單表徵圖](/help/c-target/c-visitor-profile/assets/menu-icon.png) )，然後按一下「 **[!UICONTROL People]**」。

   ![People](/help/c-target/c-visitor-profile/assets/people.png)

1. 按一下「 **[!UICONTROL 客戶屬性]** 」標籤。

   ![客戶屬性標籤](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Customer attribute workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

完成下列步驟在 [!DNL Target] 使用 CRM 資料，如下圖所示:

![crm工作流程](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud and Core Services Product Documentation*.

1. 建立資料檔案。

   從您的 CRM 將客戶資料匯出為 CSV 格式，以建立 .csv 檔案。此外，您也可以建立 zip 或 gzip 檔案進行上傳。請確定CSV檔案的第一列是標題，且所有列（客戶資料）的項目數都相同。

   下圖顯示企業客戶資料檔案範例：

   ![crs樣本](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   下圖顯示範例企業客戶。csv檔案：

   ![csv範例](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 建立屬性來源及上傳資料檔案。

   指定資料來源的名稱和描述，以及別名 ID。The alias Id is a unique ID to be used in your Customer Attribute code in `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >資料來源名稱和屬性名稱不得有英文句點。

   您的資料檔案必須符合檔案的上傳要求，且不得超過100MB。 如果您的檔案太大，或您有需要定期上傳的資料，您可以改用FTP來上傳檔案。

   * **HTTPS:** 您可以拖放。csv資料檔案，或按一下「瀏 **[!UICONTROL 覽]** 」從檔案系統上傳。
   * **FTP:** 按一下FTP連結， [透過FTP上傳檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。 第一個步驟是提供 Adobe 所提供 FTP 伺服器的密碼。Specify the password, then click **[!UICONTROL Done]**.

   現在將您的 CSV/ZIP/GZIP 檔案傳輸至 FTP 伺服器。此檔案傳輸成功後，請建立名稱相同且副檔名為。fin的新檔案。 將此空白檔案傳輸至伺服器。This indicates a End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. 驗證結構。

   驗證程序可讓您將顯示名稱和說明對應至已上傳的屬性 (字串、整數、數字等)。將每個屬性與其正確的資料類型、顯示名稱和說明對應。

   Click **[!UICONTROL Save]** after the schema validation is complete. 檔案上傳時間因大小而不同。

   ![驗證架構](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上傳結構](/help/c-target/c-visitor-profile/assets/upload1.png)

1. 設定訂閱及啟動屬性來源。

   按一下&#x200B;**[!UICONTROL 「新增訂閱」]**，然後選取要訂閱這些屬性的解決方案。[設定訂閱](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) ，設定和解決方案之間的資 [!DNL Experience Cloud] 料流。 啟動屬性來源可讓資料流向訂閱的解決方案。您上傳的客戶記錄將與從您的網站或應用程式傳入的 ID 訊號比對。

   ![配置解決方案](/help/c-target/c-visitor-profile/assets/solution.png)

   ![啟動](/help/c-target/c-visitor-profile/assets/activate.png)

   執行此步驟時，請注意下列限制:

   * 使用 HTTP 方法的每個上傳的最大檔案大小為 100 MB。
   * 使用 FTP 方法的每個上傳的最大檔案大小為 4 GB。
   * 允許訂閱的屬性數量: [!DNL Target Standard] 為 5 個，而 [!DNL Target Premium] 為 200 個。

## 在 Target 中使用客戶屬性 {#section_107E3A0F0EC7478E82E6DBD17B30B756}

您可以在 [!DNL Target] 中以下列方式使用客戶屬性:

### 建立鎖定目標對象

在 [!DNL Target] 中，您可在建立對象時，從訪客資料區段選取客戶屬性。清單中的所有客戶屬性都會具備字首 &lt; data_source_name >。視需要將這些屬性與其他資料屬性結合，以建立對象。

![目標對象](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### 使用 Token 建立設定檔指令碼

可在描述檔指令碼中使用 `crs.get('<Datasource Name>.<Attribute name>')` 格式參考客戶屬性。

可以直接在選件中使用此設定檔指令碼，用於傳遞屬於目前訪客的屬性。

### 在您的網站使用 mbox3rdPartyID 以獲得成功的實作和使用狀況

Pass `mbox3rdPartyId` as a parameter to the global mbox inside the `targetPageParams()` method. The value of `mbox3rdPartyId` should be set to the customer ID that was present in the CSV data file.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服務

如果您使用 Experience Cloud ID 服務，您需要設定客戶 ID 和驗證狀態，才能在鎖定目標中使用客戶屬性。For more information, see [Customer IDs and Authentication State](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) in the *Experience Cloud Identity Service Help*.

如需關於在 [!DNL Target] 中使用客戶屬性的詳細資訊，請參閱下列資源:

* [建立客戶屬性來源並上傳](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)*Experience Cloud產品檔案中的資料檔案*
* *數位行銷部落格*&#x200B;中的 [Customer Attributes: The More You Know, The Better You Connect](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/)

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

You might encounter the following issues when working with customer attributes and [!DNL Target].

>[!NOTE]
>
>問題1和問題2造成該領域大約60%的問題。 問題3導致大約30%的問題。 問題4導致大約5%的問題。 其餘的 5% 則因為雜項問題。

### 問題1:客戶屬性會移除，因為描述檔過大

使用者設定檔中的特定欄位沒有字元限制，但如果設定檔變得大於 64K，則會透過移除最舊的屬性來將它截斷，直到設定檔再次低於 64K 為止。

### Issue 2: Attributes not listing in the Audience Library in [!DNL Target], even after several days

這通常是管線連線問題。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題3:傳送無法根據屬性運作

Edge 上的設定檔尚未更新。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題四：實施問題

請注意下列實作問題:

* 訪客 ID 未正確傳遞。The ID was passed in `mboxMCGVID` instead of `setCustomerId`.
* 傳遞的訪客 ID 正確，但 AUTHENTICATION 狀態未設為 Authenticated。
* `mbox3rdPartyId` 未正確傳遞。

### 問題五： `mboxUpdate` 未正確執行

`mboxUpdate` 未正確搭配 `mbox3rdPartyId` 執行。

### Issue 6: Customer attributes are not being imported into [!DNL Target]

If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default).

## Training video: Upload Offline Data using Customer Attributes ![Tutorial badge](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

This video shows you how to import offline CRM, help desk, point-of-sale, and other marketing data into the [!DNL Experience Cloud People] service and associate it with visitors using their known IDs.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
