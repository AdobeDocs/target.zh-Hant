---
keywords: 建立自訂條件;演算法;條件;建議條件;csv;ftp;上傳 csv
description: 了解如何上傳CSV檔案以自訂Adobe中的建議 [!DNL Target] Recommendations。
title: 如何在Recommendations中上傳自訂條件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 39%

---

# 上傳自訂條件

上傳CSV檔案以在 [!DNL Adobe Target].

有多個方式可進入[!UICONTROL 「建立新條件」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在 **[!UICONTROL Recommendations]** > **[!UICONTROL 條件]** 程式庫畫面，按一下 **[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**. 您在這裡建立的條件會自動可供所有 [!DNL Recommendations] 活動使用。
* 建立 [!DNL Recommendations] 使用的活動 [!UICONTROL 可視化體驗撰寫器] (VEC)，系統會立即將您帶至 [!UICONTROL 選取條件] 畫面 [!UICONTROL 使用Recommendations取代], [!UICONTROL 插入Recommendations在前]，或 [!UICONTROL 插入Recommendations在後]. 然後，您可以選取可用條件，或按一下 **[!UICONTROL 建立條件]**. 如果您建立新條件，您可以儲存條件以搭配其他條件使用 [!DNL Recommendations] 活動。 如需詳細資訊，請參閱 [建立Recommendations活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* 編輯 [!DNL Recommendations] 活動時，請在頁面上的[!UICONTROL 「Recommendations 位置」]方塊中按一下，然後選取&#x200B;**[!UICONTROL 「變更條件」]**。在 [!UICONTROL 選取條件] 按一下 **[!UICONTROL 建立條件]**. 您可以儲存新條件以搭配其他 [!DNL Recommendations] 活動。

下列步驟假設您存取 [!UICONTROL 建立新條件] 使用第一個方法進行篩選：the **[!UICONTROL Recommendations]** > **[!UICONTROL 條件]** 程式庫畫面。

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 條件]**.

1. 按一下&#x200B;**[!UICONTROL 「建立條件」]**。

1. 填寫 [基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) 區段。

   1. 從 **[!UICONTROL 選擇算法]** 類型下拉式清單，選取 **[!UICONTROL 自訂條件]**.

   1. 從 **[!UICONTROL 演算法]** 下拉清單，選擇 **[!UICONTROL 自訂演算法]**.

      >[!NOTE]
      >
      >前述步驟會導致 [!UICONTROL 上傳CSV] 區段來顯示 [!UICONTROL 建立新條件] 對話框。

1. （條件性）填入 [備份內容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) 區段。

1. （條件性）填入 [包含規則](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) 區段。

1. 在 **[!UICONTROL 上傳CSV]** 區段，選取 **[!UICONTROL 位置]** 的CSV檔案。

   ![上傳CSV區段](assets/upload-csv.png)

   CSV 檔案的格式必須正確上傳才能成功。按一下&#x200B;**[!UICONTROL 「下載 CSV 範本」]**&#x200B;來取得格式正確的 CSV 檔案。

   您有兩個位置選項︰

   * **FTP:** 若要從 FTP 伺服器上傳 CSV 檔案，請選取 **[!UICONTROL FTP]**，然後輸入必要的資訊。您可以使用SSL，此SSL使用FTPS通訊協定來安全地傳輸您的CSV檔案。
   * **URL:** 若要從URL上傳CSV檔案，請選取 **[!UICONTROL URL]**，然後輸入摘要URL。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 考量事項

* 自訂條件實體 (列) 現在可以包含最多 1,000 個建議的項目 (欄)。

* 自訂條件更新預設為「累積」。CSV 上傳檔案中指定的新機碼值組會覆寫現有的機碼值組。未在CSV上傳中指定索引鍵的現有索引鍵/值組仍可供傳送，並會在上次作為CSV檔案一部分上傳的31天後過期。

   請聯絡客戶服務啟用這項設定，刪除下次 CSV 上傳中未涵蓋的現有結果。如果已啟用此設定，則只有自訂CSV摘要檔案中顯示的索引鍵可供傳送。 這項設定會套用至所有自訂條件。

* 自訂條件摘要每 24 小時會更新一次。

   您可以在 [!UICONTROL Recommendations] > [!UICONTROL 條件] 頁面。 您也可以在 [!UICONTROL 編輯] 對話框。

* 無錯誤上傳的流程應為 [!UICONTROL 已排程] > [!UICONTROL 下載摘要檔案] > [!UICONTROL 匯入] > [!UICONTROL 成功].

* 如果 [!DNL Target] 上傳遇到問題：

   | 錯誤訊息 | 詳細資料 |
   |--- |--- |
   | 未知錯誤 | 指出內部技術錯誤。 |
   | 剖析錯誤 | 摘要檔案格式可能有問題。修正檔案格式並重新儲存演算法，這會重新啟動檔案下載程式。 |
   | 找不到伺服器 | 提供可在網際網路上顯示的 IP 或主機名稱。 |
   | 憑證錯誤 | 提供伺服器上使用中帳戶的有效的使用者和密碼。 |
   | 找不到目錄 | 提供伺服器上存在的目錄。 |
   | 找不到檔案 | 提供伺服器上存在於指出目錄中檔案的名稱。 |

## 訓練影片: 在 Recommendations 中建立條件 (12:33) ![Tutorial badge](/help/main/assets/tutorial.png)

此影片包含下列資訊（上傳自訂條件的詳細資訊於11:43開始）:

* 建立條件
* 建立條件序列
* 上傳自訂條件

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
