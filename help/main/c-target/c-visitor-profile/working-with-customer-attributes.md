---
keywords: 客戶關係管理；客戶記錄服務；crs；crm；mbox3rdpartyid；客戶屬性；鎖定目標；csv；crm；adobe experience cloud人員
description: 瞭解如何使用客戶關係管理(CRM)資料庫的企業客戶資料在中進行內容目標定位 [!DNL Adobe Target].
title: 什麼是客戶屬性？如何使用客戶屬性？
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 34%

---

# 客戶屬性

使用客戶關係管理(CRM)資料庫的企業客戶資料在中進行內容目標定位的相關資訊 [!DNL Adobe Target] 使用中的客戶屬性 [!DNL Adobe Enterprise Cloud People] 服務。

透過多個來源收集並儲存在CRM資料庫內的企業客戶資料可用於 [!DNL Target] 策略性地將最相關的內容提供給客戶，尤其著重於回頭的客戶。 中的對象和客戶屬性 [!DNL People] 服務（先前稱為Profiles and Audiences）將資料收集和分析與測試和最佳化結合在一起，讓資料和深入分析可行。

## 客戶屬性總覽 {#section_B4099971FA4B48598294C56EAE86B45A}

[客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) 在 [!DNL People] 服務屬於 [!DNL Adobe Experience Cloud] 並提供企業工具來將其客戶資料推送至 [!DNL Experience Cloud] 平台。

上架到 [!DNL Experience Cloud] 的資料可供所有 [!DNL Experience Cloud] 工作流程使用。[!DNL Target] 使用此資料根據屬性來鎖定回頭的客戶。 [!DNL Adobe Analytics] 會利用這些屬性，並可將這些屬性用於分析和劃分。

![crs範例](/help/main/c-target/c-visitor-profile/assets/crs.png)

當您使用客戶屬性時，請考慮下列資訊 [!DNL Target]：

* 使用「 」之前，您必須符合一些先決條件要求 [!UICONTROL 客戶屬性] 中的功能 [!DNL People] 服務。 如需詳細資訊，請參閱以下的「上傳客戶屬性的先決條件」： [客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) 在 *Experience Cloud服務與管理檔案*.
* 請注意檔案上傳的限制，如中所述 [關於客戶屬性的資料檔案和資料來源](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=zh-Hant) 在 *Experience Cloud中央介面元件指南*. 最佳做法：

   * 上傳單一大型檔案(在 [指定的限制](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=zh-Hant))。 單一大型檔案比多個較小檔案更適合。
   * 如果您必須將上傳分割成數個檔案，請先確定檔案已完全處理完畢，然後再提交新檔案。 在提交批次中的下一個檔案之前，請確定批次中的每個檔案都已完全處理。

* [!DNL Adobe] 並不保證會將來自CRM資料庫的全部客戶屬性（訪客設定檔）資料上架到 [!DNL Experience Cloud] 因此，也可用於在中鎖定目標 [!DNL Target]. 在目前的設計中，一小部分資料（最多佔大型生產批次的0.1%）可能無法上線。
* 從匯入的客戶屬性資料的生命週期 [!DNL Experience Cloud] 至 [!DNL Target] 取決於訪客設定檔的存留期，預設為14天。 如需詳細資訊，請參閱 [訪客設定檔存留期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* 如果 `vst.*` 引數為可識別訪客的唯一專案，只要條件具備，即不會擷取現有的「已驗證」設定檔 `authState` 為UNAUTHENTICATED (0)。 設定檔只有在以下情況下才會發揮作用 `authState` 已變更為AUTHENTICATED (1)。

   例如，如果 `vst.myDataSource.id` 引數用於識別訪客(其中 `myDataSource` 是資料來源別名)，且沒有使用引數的MCID或第三方ID `vst.myDataSource.authState=0` 不會擷取可能透過匯入客戶屬性而建立的設定檔。 如果需要的行為是擷取已驗證的設定檔，則 `vst.myDataSource.authState` 值必須為1 (AUTHENTICATED)。

* 您無法在 `mbox3rdPartyID` 中傳送下列字元: 加號 (+) 和正斜線 (/)。

## 存取People服務中的客戶屬性

1. 在 [!DNL Adobe Experience Cloud]，按一下功能表圖示( ![功能表圖示](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) )然後按一下 **[!UICONTROL 人員]**.

   ![People](/help/main/c-target/c-visitor-profile/assets/people.png)

1. 按一下 **[!UICONTROL 客戶屬性]** 標籤。

   ![客戶屬性頁標](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## 的客戶屬性工作流程 [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

完成下列步驟在 [!DNL Target] 使用 CRM 資料，如下圖所示:

![crm工作流程](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

完成下列各項工作的詳細指示請參閱 [建立客戶屬性來源及上傳資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) 在 *Experience Cloud服務與管理檔案*.

1. 建立資料檔案。

   從您的 CRM 將客戶資料匯出為 CSV 格式，以建立 .csv 檔案。此外，您也可以建立 zip 或 gzip 檔案進行上傳。請確定CSV檔案的第一列是標題，且所有列（客戶資料）的專案數量相同。

   下圖顯示一個範例企業客戶資料檔案：

   ![crs範例](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   下圖顯示一個範例企業客戶.csv檔案：

   ![csv範例](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 建立屬性來源及上傳資料檔案。

   指定資料來源的名稱和描述，以及別名 ID。別名ID為唯一ID，用於客戶屬性程式碼中： `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >資料來源名稱和屬性名稱不得有英文句點。

   您的資料檔案必須符合檔案上傳要求，且不得超過100 MB。 如果您的檔案太大，或您的資料必須定期上傳，您可以改用FTP傳送檔案。

   * **HTTPS：** 您可以拖放.csv資料檔案或按一下 **[!UICONTROL 瀏覽]** 以從您的檔案系統上傳。
   * **FTP：** 按一下FTP連結，前往 [透過FTP上傳檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). 第一個步驟是提供 Adobe 所提供 FTP 伺服器的密碼。指定密碼，然後按一下 **[!UICONTROL 完成]**.

   現在將您的 CSV/ZIP/GZIP 檔案傳輸至 FTP 伺服器。此檔案傳輸成功後，請建立具有相同名稱和 `.fin` 副檔名。 將此空白檔案傳輸至伺服器。這表示傳輸結束，而且 [!DNL Experience Cloud] 開始處理資料檔案。

1. 驗證結構。

   驗證程序可讓您將顯示名稱和說明對應至已上傳的屬性 (字串、整數、數字等)。將每個屬性與其正確的資料類型、顯示名稱和說明對應。

   按一下 **[!UICONTROL 儲存]** 結構描述驗證完成後。 檔案上傳時間因大小而不同。

   ![驗證結構](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上傳結構描述](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. 設定訂閱及啟動屬性來源。

   按一下&#x200B;**[!UICONTROL 「新增訂閱」]**，然後選取要訂閱這些屬性的解決方案。[設定訂閱](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) 設定資料流在 [!DNL Experience Cloud] 和解決方案。 啟動屬性來源可讓資料流向訂閱的解決方案。您上傳的客戶記錄將與從您的網站或應用程式傳入的 ID 訊號比對。

   ![設定解決方案](/help/main/c-target/c-visitor-profile/assets/solution.png)

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

通過 `mbox3rdPartyId` 做為內的全域mbox的引數 `targetPageParams()` 方法。 的值 `mbox3rdPartyId` 應設為CSV資料檔案中顯示的客戶ID。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服務

如果您使用Experience CloudID服務，您必須設定客戶ID和驗證狀態，才能在目標定位中使用客戶屬性。 如需詳細資訊，請參閱 [客戶ID和驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) 在 *Experience CloudID服務說明*.

如需關於在 [!DNL Target] 中使用客戶屬性的詳細資訊，請參閱下列資源:

* [建立客戶屬性來源及上傳資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) 在 *Experience Cloud服務與管理檔案*

## 客戶經常遇到的問題 {#section_BE0F70E563F64294B17087DE2BC1E74C}

使用客戶屬性時，您可能會遇到下列問題 [!DNL Target].

>[!NOTE]
>
>問題1和2造成此領域約60%的問題。 問題3造成約30%的問題。 問題4造成的問題約佔5%。 其餘的 5% 則因為雜項問題。

### 問題1：客戶屬性已移除，因為設定檔太大

使用者設定檔中的特定欄位沒有字元限制，但如果設定檔變得大於 64K，則會透過移除最舊的屬性來將它截斷，直到設定檔再次低於 64K 為止。

### 問題2：屬性未列在的對象庫中 [!DNL Target]，即使在幾天之後

這通常是管線連線問題。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題3：傳遞無法根據屬性運作

Edge 上的設定檔尚未更新。作為解決方案，請要求您的客戶屬性團隊重新發佈摘要。

### 問題4：實作問題

請注意下列實作問題:

* 訪客 ID 未正確傳遞。傳入的ID `mboxMCGVID` 而非 `setCustomerId`.
* 傳遞的訪客 ID 正確，但 AUTHENTICATION 狀態未設為 Authenticated。
* `mbox3rdPartyId` 未正確傳遞。

### 第5期： `mboxUpdate` 未正確執行

`mboxUpdate` 未正確搭配 `mbox3rdPartyId` 執行。

### 問題6：客戶屬性未匯入 [!DNL Target]

如果您在Target中找不到客戶屬性資料，請確保匯入發生在上一個 *x* 天數，其中 *x* 是目標 [訪客設定檔存留期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) 值（預設為14天）。

## 訓練影片：使用客戶屬性上傳離線資料 ![教學課程徽章](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

本影片說明如何將離線CRM、服務檯、銷售點和其他行銷資料匯入 [!DNL Experience Cloud People] 服務，並使用訪客已知的ID將其與訪客建立關聯。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
