---
keywords: 客戶關係管理；客戶記錄服務；crs;crs;crm;mbox3rdpartyid；客戶屬性；定位；csv;crm;adobe experience Cloud人員
description: 瞭解如何從Adobe Target的客戶關係管理(CRM)資料庫使用企業客戶資料，以鎖定內容。
title: 什麼是客戶屬性，我要如何使用這些屬性？
feature: 對象
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1501'
ht-degree: 37%

---

# 客戶屬性

有關使用[!DNL Adobe Enterprise Cloud People]服務中的客戶屬性，從客戶關係管理(CRM)資料庫使用企業客戶資料，以在[!DNL Adobe Target]中定位內容的資訊。

透過多個來源收集並儲存在CRM資料庫中的企業客戶資料，可用於[!DNL Target]，以策略性方式向客戶傳遞最相關的內容，尤其是針對舊客戶。 [!DNL People]服務（先前稱為「設定檔與對象」）中的受眾和客戶屬性將資料收集與分析與測試與最佳化結合在一起，讓資料與見解可行。

## 客戶屬性概觀{#section_B4099971FA4B48598294C56EAE86B45A}

[服務](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) 中的客 [!DNL People] 戶屬性是服務的一部 [!DNL Adobe Experience Cloud] 分，為企業提供將客戶資料推送至平台的 [!DNL Experience Cloud] 工具。

上架到 [!DNL Experience Cloud] 的資料可供所有 [!DNL Experience Cloud] 工作流程使用。[!DNL Target] 使用此資料根據屬性定位舊客戶。[!DNL Adobe Analytics] 會利用這些屬性，並可將這些屬性用於分析和劃分。

![crs示例](/help/c-target/c-visitor-profile/assets/crs.png)

請考慮以下資訊作為您使用客戶屬性和[!DNL Target]的工作：

* 您必須符合一些先決條件要求，才能使用[!DNL People]服務中的[!UICONTROL 客戶屬性]功能。 如需詳細資訊，請參閱&#x200B;*Experience Cloud服務與管理檔案*&#x200B;中[客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0)中的「上傳客戶屬性的必要條件」。

   >[!NOTE]
   >
   >[!DNL at.js] （任何版本）或 [!DNL mbox.js] 58版或更新版本為必要。

* [!DNL Adobe] 不保證來自CRM資料庫的100%客戶屬性（訪客資料）資料將會登入 [!DNL Experience Cloud] ，因此可用於定位 [!DNL Target]。在我們目前的設計中，有可能少量的資料（大量生產批次的0.1%）無法封存。
* 從[!DNL Experience Cloud]匯入至[!DNL Target]的客戶屬性資料的期限取決於訪客描述檔的期限，預設為14天。 如需詳細資訊，請參閱[訪客資料存留期](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)。
* 如果`vst.*`參數是唯一識別訪客的項目，則只要`authState`為UNAUTHENTICATED(0)，就不會擷取現有的「已驗證」描述檔。 只有`authState`變更為「已驗證」(1)時，描述檔才會生效。

   例如，如果`vst.myDataSource.id`參數用於識別訪客（其中`myDataSource`是資料來源別名）且沒有MCID或第三方ID，則使用參數`vst.myDataSource.authState=0`將不會擷取可能透過「客戶屬性」匯入建立的描述檔。 如果想要的行為是擷取已驗證的描述檔，`vst.myDataSource.authState`的值必須為1（已驗證）。

* 您無法在 `mbox3rdPartyID` 中傳送下列字元: 加號 (+) 和正斜線 (/)。

## 在人員服務中訪問客戶屬性

1. 在[!DNL Adobe Experience Cloud]中，按一下菜單表徵圖（![菜單表徵圖](/help/c-target/c-visitor-profile/assets/menu-icon.png)），然後按一下&#x200B;**[!UICONTROL People]**。

   ![People](/help/c-target/c-visitor-profile/assets/people.png)

1. 按一下&#x200B;**[!UICONTROL 客戶屬性]**&#x200B;頁籤。

   ![客戶屬性標籤](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}的客戶屬性工作流程

完成下列步驟在 [!DNL Target] 使用 CRM 資料，如下圖所示:

![crm工作流程](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

有關完成以下每項任務的詳細說明，請參閱[「建立客戶屬性源」和&#x200B;*「Experience Cloud服務和管理文檔」中的*&#x200B;上載資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)。

1. 建立資料檔案。

   從您的 CRM 將客戶資料匯出為 CSV 格式，以建立 .csv 檔案。此外，您也可以建立 zip 或 gzip 檔案進行上傳。請確定CSV檔案的第一列是標題，且所有列（客戶資料）的項目數都相同。

   下圖顯示企業客戶資料檔案範例：

   ![crs樣本](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   下圖顯示範例企業客戶。csv檔案：

   ![csv範例](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 建立屬性來源及上傳資料檔案。

   指定資料來源的名稱和描述，以及別名 ID。別名ID是用於`VisitorAPI.js`中客戶屬性代碼的唯一ID。

   >[!IMPORTANT]
   >
   >資料來源名稱和屬性名稱不得有英文句點。

   您的資料檔案必須符合檔案的上傳要求，且不得超過100MB。 如果您的檔案太大，或您有需要定期上傳的資料，您可以改用FTP來上傳檔案。

   * **HTTPS：您** 可以拖放。csv資料檔案，或按一下「瀏覽」 **** 從檔案系統上傳。
   * **FTP：按** 一下FTP連結， [透過FTP上傳檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。第一個步驟是提供 Adobe 所提供 FTP 伺服器的密碼。指定密碼，然後按一下&#x200B;**[!UICONTROL Done]**。

   現在將您的 CSV/ZIP/GZIP 檔案傳輸至 FTP 伺服器。此檔案傳輸成功後，請建立名稱相同且副檔名為。fin的新檔案。 將此空白檔案傳輸至伺服器。這表示傳輸結束，[!DNL Experience Cloud]開始處理資料檔案。

1. 驗證結構。

   驗證程序可讓您將顯示名稱和說明對應至已上傳的屬性 (字串、整數、數字等)。將每個屬性與其正確的資料類型、顯示名稱和說明對應。

   模式驗證完成後，按一下&#x200B;**[!UICONTROL 保存]**。 檔案上傳時間因大小而不同。

   ![驗證架構](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上傳結構](/help/c-target/c-visitor-profile/assets/upload1.png)

1. 設定訂閱及啟動屬性來源。

   按一下&#x200B;**[!UICONTROL 「新增訂閱」]**，然後選取要訂閱這些屬性的解決方案。[設定](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) 訂閱會設定與解決方案之間的資 [!DNL Experience Cloud] 料流程。啟動屬性來源可讓資料流向訂閱的解決方案。您上傳的客戶記錄將與從您的網站或應用程式傳入的 ID 訊號比對。

   ![配置解決方案](/help/c-target/c-visitor-profile/assets/solution.png)

   ![啟動](/help/c-target/c-visitor-profile/assets/activate.png)

   執行此步驟時，請注意下列限制:

   * 使用 HTTP 方法的每個上傳的最大檔案大小為 100 MB。
   * 使用 FTP 方法的每個上傳的最大檔案大小為 4 GB。
   * 允許訂閱的屬性數量: [!DNL Target Standard] 為 5 個，而 [!DNL Target Premium] 為 200 個。

## 在[!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}中使用客戶屬性

您可以在 [!DNL Target] 中以下列方式使用客戶屬性:

### 建立鎖定目標對象

在 [!DNL Target] 中，您可在建立對象時，從訪客資料區段選取客戶屬性。清單中的所有客戶屬性都會具備字首 &lt; data_source_name >。視需要將這些屬性與其他資料屬性結合，以建立對象。

![目標對象](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### 使用 Token 建立設定檔指令碼

可在描述檔指令碼中使用 `crs.get('<Datasource Name>.<Attribute name>')` 格式參考客戶屬性。

可以直接在選件中使用此設定檔指令碼，用於傳遞屬於目前訪客的屬性。

### 在您的網站使用 mbox3rdPartyID 以獲得成功的實作和使用狀況

將`mbox3rdPartyId`作為參數傳遞至`targetPageParams()`方法內的全域mbox。 `mbox3rdPartyId`的值應設為CSV資料檔案中的客戶ID。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服務

如果您使用 Experience Cloud ID 服務，您需要設定客戶 ID 和驗證狀態，才能在鎖定目標中使用客戶屬性。如需詳細資訊，請參閱&#x200B;*Experience CloudID服務說明*&#x200B;中的[客戶ID和驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。

如需關於在 [!DNL Target] 中使用客戶屬性的詳細資訊，請參閱下列資源:

* [建立客戶屬性來源並上傳「Experience Cloud服](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) 務與管理」 *檔案中的資料檔案*
* *數位行銷部落格*&#x200B;中的 [Customer Attributes: The More You Know, The Better You Connect](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/)

## 客戶常遇到的問題{#section_BE0F70E563F64294B17087DE2BC1E74C}

使用客戶屬性和[!DNL Target]時，可能會遇到以下問題。

>[!NOTE]
>
>問題1和問題2造成該領域大約60%的問題。 問題3導致大約30%的問題。 問題4導致大約5%的問題。 其餘的 5% 則因為雜項問題。

### 問題1:客戶屬性會移除，因為描述檔過大

使用者設定檔中的特定欄位沒有字元限制，但如果設定檔變得大於 64K，則會透過移除最舊的屬性來將它截斷，直到設定檔再次低於 64K 為止。

### 問題2:在[!DNL Target]的「對象庫」中未列出屬性，即使在數天後亦然

這通常是管線連線問題。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題3:傳送無法根據屬性運作

Edge 上的設定檔尚未更新。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題四：實施問題

請注意下列實作問題:

* 訪客 ID 未正確傳遞。ID已傳入`mboxMCGVID`，而非`setCustomerId`。
* 傳遞的訪客 ID 正確，但 AUTHENTICATION 狀態未設為 Authenticated。
* `mbox3rdPartyId` 未正確傳遞。

### 問題五：`mboxUpdate`未正確執行

`mboxUpdate` 未正確搭配 `mbox3rdPartyId` 執行。

### 問題六：客戶屬性未匯入至[!DNL Target]

如果您在Target中找不到「客戶屬性」資料，請確定匯入發生在最近&#x200B;*x*&#x200B;天內，其中&#x200B;*x*&#x200B;是「Target [訪客資料存留期](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md)」值（預設為14天）。

## 訓練影片：使用客戶屬性![教學課程標章](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}上傳離線資料

此影片示範如何將離線CRM、服務台、銷售點和其他行銷資料匯入[!DNL Experience Cloud People]服務，並使用其已知ID將其與訪客建立關聯。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
