---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: 上傳 CSV 檔案來自訂您的建議。
title: 上傳自訂條件
feature: criteria
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 63%

---


# ![PREMIUM](/help/assets/premium.png) 上傳自訂條件{#upload-custom-criteria}

上傳 CSV 檔案來自訂您的建議。

有多個方式可進入[!UICONTROL 「建立新條件」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. 您在這裡建立的條件會自動可供所有 [!DNL Recommendations] 活動使用。
* 當您使用 [!DNL Recommendations][!UICONTROL Visual Experience Composer] (VEC)進行活動時，在頁面上的元素和 [!UICONTROL Click Web後，您會立即被帶到] Select Select Reperience Composer(Visual Experience Composer (VEC)螢幕)的Recommendations。 然後，您可以選取可用的標準，或按一下「建 **[!UICONTROL 立標準」]**。 如果您建立新標準，您可以選擇儲存標準以用於其他活 [!DNL Recommendations] 動。 For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* 編輯 [!DNL Recommendations] 活動時，請在頁面上的[!UICONTROL 「Recommendations 位置」]方塊中按一下，然後選取&#x200B;**[!UICONTROL 「變更條件」]**。On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. 您將可以選擇儲存您的新條件以搭配其他 [!DNL Recommendations] 活動使用。

以下步驟假定您使用第一 [!UICONTROL 種方法訪問「建立新標準] 」螢幕：「建 **[!UICONTROL 議]** > **[!UICONTROL 准則]** 」程式庫畫面。

1. 按一 **[!UICONTROL 下「建議]** > **[!UICONTROL 准則]**」。

1. 按一 **[!UICONTROL 下「建立條件]** >上 **[!UICONTROL 傳自訂條件」]**。

1. Fill in the information in the [Basic Information](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info) section.

1. 填寫「資料來源」區 [段中的資訊](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) 。

1. Fill in the information in the [Content](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content) section.

1. （條件性）填寫「內容相似性」區 [段中的資](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity) 訊。

1. （條件性）填入「包含規則」區 [段中的資](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) 訊。

1. （條件性）填入「屬性加權」區 [段中的資訊](/help/c-recommendations/c-algorithms/create-new-algorithm.md#weighting) 。

1. 在「上 **[!UICONTROL 傳CSV]** 」區段中，選 **[!UICONTROL 取CSV檔案的位置]** 。

   ![上傳CSV區段](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   CSV 檔案的格式必須正確上傳才能成功。按一下&#x200B;**[!UICONTROL 「下載 CSV 範本」]**&#x200B;來取得格式正確的 CSV 檔案。

   您有兩個位置選項︰

   * **FTP:** 若要從 FTP 伺服器上傳 CSV 檔案，請選取 **[!UICONTROL FTP]**，然後輸入必要的資訊。您有選項可使用 SSL，其使用 FTPS 通訊協定來安全地傳輸您的 CSV 檔案。
   * **URL:** 若要從URL上傳CSV檔案，請選取 **[!UICONTROL URL]**，然後輸入動態消息URL。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   >[!NOTE]
   >
   >自訂條件實體 (列) 現在可以包含最多 1,000 個建議的項目 (欄)。

自訂條件更新預設為「累積」。CSV 上傳檔案中指定的新機碼值組會覆寫現有的機碼值組。未在 CSV 上傳中指定索引鍵的現有索引鍵/值組將仍可用於傳送，且將在最後一次做為 CSV 檔案一部分上傳的 31 天後過期。

請聯絡客戶服務啟用這項設定，刪除下次 CSV 上傳中未涵蓋的現有結果。如果已啟用這項設定，則只有自訂 CSV 摘要檔案的機碼可供傳送。這項設定會套用至所有自訂條件。

自訂條件摘要每 24 小時會更新一次。

您可以在「Recommendations > 條件」頁面上每個條件卡片的底端查看您的自訂條件上傳的上傳和同步狀態。編輯自訂條件時，您也可以在「編輯」對話方塊中看見狀態。

沒有錯誤的上傳流程應該是「已排程」>「下載摘要檔案」>「正在匯入」>成功。

The following are possible error messages you might receive if [!DNL Target] encounters a problem with the upload:

| 錯誤訊息 | 詳細資料 |
|--- |--- |
| 未知錯誤 | 指出內部技術錯誤。 |
| 剖析錯誤 | 摘要檔案格式可能有問題。更正檔案格式並重新儲存演算法，如此將重新開始檔案下載程序。 |
| 找不到伺服器 | 提供可在網際網路上顯示的 IP 或主機名稱。 |
| 憑證錯誤 | 提供伺服器上使用中帳戶的有效的使用者和密碼。 |
| 找不到目錄 | 提供伺服器上存在的目錄。 |
| 找不到檔案 | 提供伺服器上存在於指出目錄中檔案的名稱。 |

## 訓練影片: 在 Recommendations 中建立條件 (12:33) ![教學課程徽章](/help/assets/tutorial.png)

此影片包含下列資訊（有關上傳自訂准則的詳細資訊，從11:43開始）:

* 建立條件
* 建立條件序列
* 上傳自訂條件

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)