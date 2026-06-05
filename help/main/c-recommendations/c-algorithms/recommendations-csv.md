---
keywords: 建立自訂條件;演算法;條件;建議條件;csv;ftp;上傳 csv
description: 瞭解如何上傳CSV檔案，以自訂Adobe [!DNL Target] Recommendations中的建議。
title: 如何在 [!DNL Recommendations]中上傳自訂條件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
TQID: https://experienceleague.adobe.com/8gSKOQxHGB5TPe6vdhjgy5sAFxN8O7dodITo7wgrR50
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 32%

---

# 上傳自訂條件

上傳CSV檔案以在[!DNL Adobe Target]中自訂您的建議。

有多個方式可進入[!UICONTROL 「建立新條件」]畫面。 根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 條件]**&#x200B;資料庫畫面上，按一下&#x200B;**[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**。 您在這裡建立的條件會自動可供所有 [!DNL Recommendations] 活動使用。
* 當您使用[!UICONTROL 視覺化體驗撰寫器] (VEC)建立[!DNL Recommendations]活動時，在您選取頁面上的元素並按一下「[!UICONTROL 使用建議取代]」、「[!UICONTROL 插入建議在前]」或「[!UICONTROL 插入建議在後]」後，就會立即進入[!UICONTROL 選取條件]畫面。 然後，您可以選取可用的條件，或按一下&#x200B;**[!UICONTROL 建立條件]**。 如果您建立新條件，可以儲存條件以搭配其他[!DNL Recommendations]活動使用。 如需詳細資訊，請參閱[建立建議活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。
* 編輯[!DNL Recommendations]活動時，請在頁面上的[!UICONTROL Recommendations位置]方塊中按一下，然後選取&#x200B;**[!UICONTROL 變更條件]**。 在[!UICONTROL 選取條件]畫面上，按一下&#x200B;**[!UICONTROL 建立條件]**。 您可以儲存您的新條件以搭配其他[!DNL Recommendations]活動使用。

下列步驟假設您使用第一個方法存取[!UICONTROL 建立新條件]畫面： **[!UICONTROL Recommendations]** > **[!UICONTROL 條件]**&#x200B;資料庫畫面。

1. 按一下&#x200B;**[!UICONTROL 建議]** > **[!UICONTROL 條件]**。

1. 按一下&#x200B;**[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**。

1. 在[基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)區段中填入資訊。

1. 從&#x200B;**[!UICONTROL 選取演演算法型別]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 自訂條件]**。

1. 從&#x200B;**[!UICONTROL 演演算法]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 自訂演演算法]**。

   >[!NOTE]
   >
   >上述步驟會使[!UICONTROL 上傳CSV]區段顯示在[!UICONTROL 建立條件]對話方塊的底部。

1. （視條件而定）在[備份內容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)區段中填入資訊。

1. （視條件而定）在[包含規則](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)區段中填入資訊。

1. 在&#x200B;**[!UICONTROL 上傳CSV]**&#x200B;區段中，選取CSV檔案的&#x200B;**[!UICONTROL 位置]**。

   CSV 檔案的格式必須正確上傳才能成功。 按一下&#x200B;**[!UICONTROL 「下載 CSV 範本」]**&#x200B;來取得格式正確的 CSV 檔案。

   您有兩個位置選項︰

   * **FTP：**&#x200B;若要從FTP伺服器上傳CSV檔案，請選取&#x200B;**[!UICONTROL FTP]**，然後輸入必要的資訊。 您可以使用SSL，其使用FTPS通訊協定來安全地傳輸您的CSV檔案。

   * **URL：**&#x200B;若要從URL上傳您的CSV檔案，請選取&#x200B;**[!UICONTROL URL]**，然後輸入摘要URL。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

## 考量事項

* 自訂條件實體 (列) 現在可以包含最多 1,000 個建議的項目 (欄)。

* 自訂條件更新預設為「累積」。 CSV 上傳檔案中指定的新機碼值組會覆寫現有的機碼值組。 未在CSV上傳中指定索引鍵的現有索引鍵/值組仍可用於傳送，且會在最後一次做為CSV檔案一部分上傳的31天後過期。

  請聯絡客戶服務啟用這項設定，刪除下次 CSV 上傳中未涵蓋的現有結果。 如果啟用此設定，則只有自訂CSV摘要檔案中存在的金鑰才可用於傳送。 這項設定會套用至所有自訂條件。

* 自訂條件摘要每 24 小時會更新一次。

  您可以在[!UICONTROL Recommendations] > [!UICONTROL 條件]頁面上檢視每個條件之自訂條件上傳的上傳和同步狀態。 編輯自訂條件時，您也可以在[!UICONTROL 編輯]對話方塊中檢視狀態。

* 無錯誤上傳的流程應為[!UICONTROL 已排程] > [!UICONTROL 正在下載摘要檔案] > [!UICONTROL 正在匯入] > [!UICONTROL 成功]。

* 如果[!DNL Target]在上傳時遇到問題，您可能會收到下列錯誤訊息：

  | 錯誤訊息 | 詳細資料 |
  |--- |--- |
  | 未知錯誤 | 指出內部技術錯誤。 |
  | 剖析錯誤 | 摘要檔案格式可能有問題。 修正檔案格式並重新儲存演演算法，這會重新啟動檔案下載程式。 |
  | 找不到伺服器 | 提供可在網際網路上顯示的 IP 或主機名稱。 |
  | 憑證錯誤 | 提供伺服器上使用中帳戶的有效的使用者和密碼。 |
  | 找不到目錄 | 提供伺服器上存在的目錄。 |
  | 找不到檔案 | 提供伺服器上存在於指出目錄中檔案的名稱。 |
