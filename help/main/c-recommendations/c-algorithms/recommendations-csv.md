---
keywords: 建立自訂條件；演演算法；條件；建議條件；csv；ftp；sftp；上傳csv
description: 瞭解如何上傳CSV檔案以自訂Adobe [!DNL Target] Recommendations中的建議。
title: 上傳自訂條件
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
TQID: 'https://experienceleague.adobe.com/8gSKOQxHGB5TPe6vdhjgy5sAFxN8O7dodITo7wgrR50'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 14%
---
# 上傳自訂條件 {#upload-custom-criteria}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何上傳CSV檔案的建議以在[!DNL Adobe Target Recommendations]中建立自訂條件。

>[!ENDSHADEBOX]

自訂條件使用已上傳至[!DNL Target]的建議的CSV檔案。 這允許在[!DNL Target]以外計算的建議在[!DNL Recommendations]活動中傳遞。 如需自訂條件如何運作的詳細資訊，請參閱[ Target的建議演演算法背後的科學](/help/main/c-recommendations/c-algorithms/recommendations-algorithms.md)。

自訂條件是從&#x200B;**[!UICONTROL 建立新條件]**&#x200B;畫面建立的。 如需進入此畫面的方法，請參閱[存取「建立新條件」畫面](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#access-create-criteria)。 下列步驟從&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 條件]**&#x200B;資料庫畫面開始。

1. 按一下&#x200B;**[!UICONTROL 建議]** > **[!UICONTROL 條件]**。

1. 按一下&#x200B;**[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**。

   ![已開啟[建立條件]功能表的[條件]頁面，顯示[建立條件]和[建立條件順序]](../assets/criteria_create_1.png)

1. 在[基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)區段中填入資訊。

1. 從&#x200B;**[!UICONTROL 選取演演算法型別]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 自訂條件]**。 從&#x200B;**[!UICONTROL 演演算法]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 自訂演演算法]**。

   以自訂條件作為演演算法型別，以自訂演演算法作為演演算法![建議演演算法區段](../assets/criteria_create_9.png)

1. （視條件而定）在[備份內容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)和[包含規則](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)區段中填入資訊。

1. 在&#x200B;**[!UICONTROL 上傳CSV]**&#x200B;區段中，選取CSV檔案的&#x200B;**[!UICONTROL 位置]**。

   CSV 檔案的格式必須正確上傳才能成功。 若要取得格式正確的CSV檔案，請按一下&#x200B;**[!UICONTROL 下載CSV範本]**。

   下列位置選項可供使用：

   * **FTP**：若要從FTP伺服器上傳CSV檔案，請選取&#x200B;**[!UICONTROL FTP]**，然後輸入必要的資訊。 可使用SSL，其使用FTPS通訊協定來安全地傳輸CSV檔案。

   * **SFTP**：若要從SFTP伺服器上傳CSV檔案，請選取&#x200B;**[!UICONTROL SFTP]**，然後輸入主機名稱或IP位址、連線埠（預設為22）、使用者名稱、密碼和/或SSH私密金鑰、目錄和檔案名稱。 如需詳細資訊，請參閱[支援的SFTP伺服器設定](/help/main/c-recommendations/c-products/feeds.md#steps)。

     SFTP不會變更自訂條件CSV格式。 使用`# Key,Recommendation_1,...`格式。 格式為不同摘要型別的CSV檔案會導致匯入失敗。

   * **URL**：若要從URL上傳CSV檔案，請選取&#x200B;**[!UICONTROL URL]**，然後輸入摘要URL。

     ![使用反白顯示的位置選項FTP、SFTP和URL以及選取的SFTP上傳CSV區段](../assets/criteria_create_10.png)

1. 按一下&#x200B;**[!UICONTROL 建立]**。

## 考量事項

* 自訂條件實體 (列) 現在可以包含最多 1,000 個建議的項目 (欄)。

* 自訂條件更新預設為「累積」。 CSV上傳檔案中的新機碼值組會覆寫現有的機碼值組。 其金鑰不在CSV上傳中的現有金鑰值組仍可用於傳送，並於上次作為CSV檔案的一部分上傳後31天到期。

  若要捨棄未包含在下一個CSV上傳中的現有結果，請聯絡客戶服務以啟用對應的設定。 啟用此設定時，只有自訂CSV摘要檔案中存在的金鑰才可用於傳送。 這項設定會套用至所有自訂條件。

* 自訂條件摘要每 24 小時會更新一次。

  每個自訂條件上傳的上傳和同步狀態會顯示在&#x200B;**[!UICONTROL 建議]** > **[!UICONTROL 條件]**&#x200B;頁面上。 編輯自訂條件時，**[!UICONTROL 編輯]**&#x200B;對話方塊中也會顯示狀態。

* 無錯誤上傳的流程為&#x200B;**[!UICONTROL 已排程]** > **[!UICONTROL 正在下載摘要檔案]** > **[!UICONTROL 正在匯入]** > **[!UICONTROL 成功]**。

* 如果[!DNL Target]在上傳時遇到問題，可能會出現下列錯誤訊息：

  | 錯誤訊息 | 詳細資料 |
  |--- |--- |
  | 未知錯誤 | 指出內部技術錯誤。 |
  | 剖析錯誤 | 摘要檔案格式可能有問題。 修正檔案格式並重新儲存演演算法，這會重新啟動檔案下載程式。 |
  | 找不到伺服器 | 提供網際網路上可見的IP或主機名稱。 |
  | 憑證錯誤 | 提供伺服器上使用中帳戶的有效的使用者和密碼。 |
  | 找不到目錄 | 提供伺服器上存在的目錄。 |
  | 找不到檔案 | 提供伺服器上指定目錄中的檔案名稱。 |
