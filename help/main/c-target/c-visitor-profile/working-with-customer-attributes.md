---
keywords: 客戶關係管理；客戶記錄服務；crs；crm；mbox3rdpartyid；客戶屬性；鎖定目標；csv；crm；adobe experience cloud人員
description: 瞭解如何使用客戶關係管理(CRM)資料庫的企業客戶資料在 [!DNL Adobe Target]中鎖定內容。
title: 什麼是客戶屬性？如何使用客戶屬性？
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 31%

---

# 客戶屬性

關於使用Customer Relationship Management (CRM)資料庫的企業客戶資料，在[!DNL Adobe Target]中使用[!DNL Adobe Enterprise Cloud People]服務中的客戶屬性進行內容目標定位的資訊。

透過多個來源收集並儲存在CRM資料庫內的企業客戶資料，可用於[!DNL Target]來策略性地傳延最相關的內容給客戶，特別是著重在回頭的客戶上。 [!DNL People]服務（先前的「設定檔與對象」）中的對象和客戶屬性將資料收集與分析與測試及最佳化結合在一起，讓資料和分析可行。

## 客戶屬性總覽 {#section_B4099971FA4B48598294C56EAE86B45A}

[!DNL People]服務中的[客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html)是[!DNL Adobe Experience Cloud]的一部分，並提供工具讓企業將其客戶資料推送到[!DNL Experience Cloud]平台。

上架到 [!DNL Experience Cloud] 的資料可供所有 [!DNL Experience Cloud] 工作流程使用。[!DNL Target]使用此資料根據屬性來鎖定回頭的客戶。 [!DNL Adobe Analytics] 會利用這些屬性，並可將這些屬性用於分析和劃分。

![crs範例](/help/main/c-target/c-visitor-profile/assets/crs.png)

使用客戶屬性和[!DNL Target]時請考量下列資訊：

* 在[!DNL People]服務中使用[!UICONTROL Customer attributes]功能之前，您必須符合一些先決條件要求。 如需詳細資訊，請參閱&#x200B;*Experience Cloud服務與管理檔案*&#x200B;中[客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0)的「上傳客戶屬性的先決條件」。
* 請注意檔案上傳的限制，如&#x200B;*Experience Cloud中央介面元件指南*&#x200B;中的[關於客戶屬性的資料檔案和資料來源](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=zh-Hant)中所述。 最佳做法：

   * 上傳單一大型檔案（在指定的[限制內](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=zh-Hant)）。 單一大型檔案比多個較小檔案更適合。
   * 如果您必須將上傳分割成數個檔案，請在提交新檔案之前確保檔案已完全處理。 在提交批次中的下一個檔案之前，請確定批次中的每個檔案都已完全處理。

* [!DNL Adobe]不保證CRM資料庫中100%的客戶屬性（訪客設定檔）資料會上線至[!DNL Experience Cloud]，因此可在[!DNL Target]中用於鎖定目標。 在目前的設計中，小部分資料（最多佔大型生產批次的0.1%）有可能不會上線。
* 從[!DNL Experience Cloud]匯入至[!DNL Target]的客戶屬性資料存留期取決於訪客設定檔的存留期，預設為14天。 如需詳細資訊，請參閱[訪客設定檔存留期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)。
* 如果`vst.*`引數是識別訪客的唯一專案，只要`authState`是UNAUTHENTICATED (0)，將不會擷取現有的「已驗證」設定檔。 只有在`authState`變更為AUTHENTICATED (1)時，設定檔才會生效。

  例如，如果使用`vst.myDataSource.id`引數來識別訪客（其中`myDataSource`為資料來源別名），並且沒有MCID或第三方ID，則使用引數`vst.myDataSource.authState=0`不會擷取可能已透過「客戶屬性」匯入建立的設定檔。 如果需要的行為是擷取驗證的設定檔，`vst.myDataSource.authState`的值必須為1 (AUTHENTICATED)。

* 您無法在 `mbox3rdPartyID` 中傳送下列字元: 加號 (+) 和正斜線 (/)。

## 存取People服務中的客戶屬性

1. 在[!DNL Adobe Experience Cloud]中，按一下功能表圖示（ ![功能表圖示](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ），然後按一下&#x200B;**[!UICONTROL People]**。

   ![People](/help/main/c-target/c-visitor-profile/assets/people.png)

1. 按一下「**[!UICONTROL Customer Attributes]**」標籤。

   ![客戶屬性標籤](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## [!DNL Target]的客戶屬性工作流程 {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

完成下列步驟在 [!DNL Target] 使用 CRM 資料，如下圖所示:

![crm工作流程](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

您可以在[建立客戶屬性來源及上傳&#x200B;*Experience Cloud服務與管理檔案*&#x200B;中的資料檔](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html)中找到完成下列每項工作的詳細指示。

1. 建立資料檔案。

   將客戶資料從您的CRM匯出為CSV格式，以建立.csv檔案。 此外，您也可以建立 zip 或 gzip 檔案進行上傳。確保CSV檔案的第一列是標題且所有列（客戶資料）的專案數量相同。

   下圖顯示一個範例企業客戶資料檔案：

   ![crs範例](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   下圖顯示一個範例企業客戶.csv檔案：

   ![csv範例](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 建立屬性來源及上傳資料檔案。

   指定資料來源的名稱和描述，以及別名 ID。別名ID是用於您在`VisitorAPI.js`中的客戶屬性代碼的唯一識別碼。

   >[!IMPORTANT]
   >
   >資料來源名稱和屬性名稱不得有英文句點。

   您的資料檔案必須符合檔案上傳要求，且不得超過100 MB。 如果檔案太大，或您的資料必須定期上傳，您可以改用FTP傳送檔案。

   * **HTTPS：**&#x200B;您可以拖放.csv資料檔案，或按一下&#x200B;**[!UICONTROL Browse]**&#x200B;從您的檔案系統上傳。
   * **FTP：**&#x200B;按一下FTP連結以[透過FTP上傳檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。 第一個步驟是提供 Adobe 所提供 FTP 伺服器的密碼。指定密碼，然後按一下&#x200B;**[!UICONTROL Done]**。

   現在將您的 CSV/ZIP/GZIP 檔案傳輸至 FTP 伺服器。此檔案傳輸成功後，請建立具有相同名稱和`.fin`副檔名的檔案。 將此空白檔案傳輸至伺服器。這表示傳輸已結束，[!DNL Experience Cloud]開始處理資料檔案。

1. 驗證結構。

   驗證程序可讓您將顯示名稱和說明對應至已上傳的屬性 (字串、整數、數字等)。將每個屬性與其正確的資料類型、顯示名稱和說明對應。

   結構描述驗證完成後，請按一下&#x200B;**[!UICONTROL Save]**。 檔案上傳時間因大小而不同。

   ![驗證結構描述](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上傳結構描述](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. 設定訂閱及啟動屬性來源。

   按一下&#x200B;**[!UICONTROL Add Subscription]**，然後選取要訂閱這些屬性的解決方案。 [設定訂閱](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html)設定[!DNL Experience Cloud]和解決方案之間的資料流。 啟動屬性來源可讓資料流向訂閱的解決方案。您上傳的客戶記錄將與從您的網站或應用程式傳入的 ID 訊號比對。

   ![設定方案](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![啟動](/help/main/c-target/c-visitor-profile/assets/activate.png)

   執行此步驟時，請注意下列限制:

   * 使用 HTTP 方法的每個上傳的最大檔案大小為 100 MB。
   * 使用 FTP 方法的每個上傳的最大檔案大小為 4 GB。
   * 允許訂閱的屬性數量: [!DNL Target Standard] 為 5 個，而 [!DNL Target Premium] 為 200 個。

## 在[!DNL Target]中使用客戶屬性 {#section_107E3A0F0EC7478E82E6DBD17B30B756}

您可以在 [!DNL Target] 中以下列方式使用客戶屬性:

### 建立鎖定目標客群

在[!DNL Target]中，您可在建立對象時，從[!UICONTROL Visitor Profile]區段選取客戶屬性。 清單中的所有客戶屬性都會具備字首 &lt; data_source_name >。視需要將這些屬性與其他資料屬性結合，以建立客群。

![目標客群](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### 使用 Token 建立設定檔指令碼

可在描述檔指令碼中使用 `crs.get('<Datasource Name>.<Attribute name>')` 格式參考客戶屬性。

可以直接在選件中使用此設定檔指令碼，用於傳遞屬於目前訪客的屬性。

### 在您的網站使用 mbox3rdPartyID 以獲得成功的實作和使用狀況

將`mbox3rdPartyId`以引數的形式傳遞至`targetPageParams()`方法內的全域mbox。 `mbox3rdPartyId`的值應設為CSV資料檔案中顯示的客戶ID。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服務

如果您使用Experience CloudID服務，您必須設定客戶ID和驗證狀態，才能使用目標定位中的客戶屬性。 如需詳細資訊，請參閱&#x200B;*Experience CloudID服務說明*&#x200B;中的[客戶ID與驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。

如需關於在 [!DNL Target] 中使用客戶屬性的詳細資訊，請參閱下列資源:

* [在&#x200B;*Experience Cloud服務與管理檔案*&#x200B;中建立客戶屬性來源及上傳資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)

## 客戶經常遇到的問題 {#section_BE0F70E563F64294B17087DE2BC1E74C}

使用客戶屬性和[!DNL Target]時，您可能會遇到下列問題。

>[!NOTE]
>
>問題1和2造成此領域約60%的問題。 問題3造成約30%的問題。 問題4造成的問題約佔5%。 其餘的 5% 則因為雜項問題。

### 問題1：客戶屬性已移除，因為設定檔太大

使用者設定檔中的特定欄位沒有字元限制，但如果設定檔變得大於 64 K，則會透過移除最舊的屬性來將它截斷，直到設定檔再次低於 64 K 為止。

### 問題2：即使在數天後，屬性亦未列於[!DNL Target]的對象資料庫中

這通常是管線連線問題。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題3：傳遞無法根據屬性運作

Edge 上的設定檔尚未更新。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題4：實作問題

請注意下列實作問題:

* 訪客 ID 未正確傳遞。傳入的識別碼是`mboxMCGVID`，而非`setCustomerId`。
* 傳遞的訪客 ID 正確，但 AUTHENTICATION 狀態未設為 Authenticated。
* `mbox3rdPartyId` 未正確傳遞。

### 問題5：`mboxUpdate`未正確執行

`mboxUpdate`未透過`mbox3rdPartyId`正確執行。

### 問題6：未將客戶屬性匯入[!DNL Target]

如果您在Target中找不到客戶屬性資料，請確保在過去&#x200B;*x*&#x200B;天內發生匯入，其中&#x200B;*x*&#x200B;是Target [訪客設定檔存留期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md)值（預設為14天）。

## 訓練影片：使用客戶屬性上傳離線資料![教學課程徽章](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

此影片說明如何將離線CRM、服務檯、銷售點和其他行銷資料匯入[!DNL Experience Cloud People]服務，並使用訪客的已知ID將其與訪客建立關聯。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
