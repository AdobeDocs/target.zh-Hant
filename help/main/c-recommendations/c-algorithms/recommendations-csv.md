---
keywords: 建立自訂條件;演算法;條件;建議條件;csv;ftp;上傳 csv
description: 瞭解如何上傳CSV檔案，以自訂Adobe [!DNL Target] Recommendations中的建議。
title: 如何在 [!DNL Recommendations]中上傳自訂條件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 33%

---

# 上傳自訂條件

上傳CSV檔案以在[!DNL Adobe Target]中自訂您的建議。

有多種方式可以到達[!UICONTROL Create New Criteria]畫面。 根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;資料庫畫面上，按一下&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**。 您在這裡建立的條件會自動可供所有 [!DNL Recommendations] 活動使用。
* 當您使用[!UICONTROL Visual Experience Composer] (VEC)建立[!DNL Recommendations]活動時，在您選取頁面上的元素並按一下[!UICONTROL Replace w/ Recommendations]、[!UICONTROL Insert Recommendations Before]或[!UICONTROL Insert Recommendations After]後，就會立即進入[!UICONTROL Select Criteria]畫面。 然後，您可以選取可用的條件或按一下&#x200B;**[!UICONTROL Create Criteria]**。 如果您建立新條件，可以儲存條件以搭配其他[!DNL Recommendations]活動使用。 如需詳細資訊，請參閱[建立Recommendations活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。
* 編輯[!DNL Recommendations]活動時，請在頁面上的[!UICONTROL Recommendations Location]方塊中按一下，然後選取&#x200B;**[!UICONTROL Change Criteria]**。 在[!UICONTROL Select Criteria]畫面上，按一下&#x200B;**[!UICONTROL Create Criteria]**。 您可以儲存您的新條件以搭配其他[!DNL Recommendations]活動使用。

下列步驟假設您使用第一個方法存取[!UICONTROL Create New Criteria]畫面： **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;資料庫畫面。

1. 按一下&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**。

1. 按一下&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**。

1. 在[基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)區段中填入資訊。

1. 從&#x200B;**[!UICONTROL Select Algorithm Type]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Custom Criteria]**。

1. 從&#x200B;**[!UICONTROL Algorithm]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Custom Algorithm]**。

   >[!NOTE]
   >
   >上述步驟會使[!UICONTROL Upload CSV]區段顯示在[!UICONTROL Create Criteria]對話方塊的底部。

1. （視條件而定）在[備份內容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)區段中填入資訊。

1. （視條件而定）在[包含規則](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)區段中填入資訊。

1. 在&#x200B;**[!UICONTROL Upload CSV]**&#x200B;區段中，選取CSV檔案的&#x200B;**[!UICONTROL Location]**。

CSV 檔案的格式必須正確上傳才能成功。按一下&#x200B;**[!UICONTROL Download the CSV template]**&#x200B;以取得格式正確的CSV檔案。

您有兩個位置選項︰

    * **FTP：**若要從FTP伺服器上傳CSV檔案，請選取**[!UICONTROL FTP]**，然後輸入必要的資訊。 您可以使用SSL，其使用FTPS通訊協定來安全地傳輸您的CSV檔案。
    
    * **URL：**若要從URL上傳您的CSV檔案，請選取**[!UICONTROL URL]**，然後輸入摘要URL。

1. 按一下 **[!UICONTROL Create]**。

## 考量事項

* 自訂條件實體 (列) 現在可以包含最多 1,000 個建議的項目 (欄)。

* 自訂條件更新預設為「累積」。CSV 上傳檔案中指定的新機碼值組會覆寫現有的機碼值組。未在CSV上傳中指定索引鍵的現有索引鍵/值組仍可用於傳送，且會在最後一次做為CSV檔案一部分上傳的31天後過期。

  請聯絡客戶服務啟用這項設定，刪除下次 CSV 上傳中未涵蓋的現有結果。如果啟用此設定，則只有自訂CSV摘要檔案中存在的金鑰才可用於傳送。 這項設定會套用至所有自訂條件。

* 自訂條件摘要每 24 小時會更新一次。

  您可以在[!UICONTROL Recommendations] > [!UICONTROL Criteria]頁面上檢視每個條件之自訂條件上傳的上傳和同步狀態。 編輯自訂條件時，您也可以在[!UICONTROL Edit]對話方塊中看到狀態。

* 無錯誤上傳的流程應為[!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful]。

* 如果[!DNL Target]在上傳時遇到問題，您可能會收到下列錯誤訊息：

  | 錯誤訊息 | 詳細資料 |
  |--- |--- |
  | 未知錯誤 | 指出內部技術錯誤。 |
  | 剖析錯誤 | 摘要檔案格式可能有問題。修正檔案格式並重新儲存演演算法，這會重新啟動檔案下載程式。 |
  | 找不到伺服器 | 提供可在網際網路上顯示的 IP 或主機名稱。 |
  | 憑證錯誤 | 提供伺服器上使用中帳戶的有效的使用者和密碼。 |
  | 找不到目錄 | 提供伺服器上存在的目錄。 |
  | 找不到檔案 | 提供伺服器上存在於指出目錄中檔案的名稱。 |
