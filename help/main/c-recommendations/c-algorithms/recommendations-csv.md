---
keywords: 建立自訂條件;演算法;條件;建議條件;csv;ftp;上傳 csv
description: 瞭解如何上載CSV檔案以在Adobe中自定義建議 [!DNL Target] Recommendations。
title: 如何在Recommendations上傳自定義條件？
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 39%

---

# ![PREMIUM](/help/main/assets/premium.png) 上傳自訂條件

上載CSV檔案以在 [!DNL Adobe Target]。

有多個方式可進入[!UICONTROL 「建立新條件」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* 在 **[!UICONTROL Recommendations]** > **[!UICONTROL 標準]** 庫螢幕，按一下 **[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**。 您在這裡建立的條件會自動可供所有 [!DNL Recommendations] 活動使用。
* 建立 [!DNL Recommendations] 活動 [!UICONTROL 視覺體驗作曲家] (VEC)，您將立即轉到 [!UICONTROL 選擇條件] 在頁面上選擇元素並按一下 [!UICONTROL 更換為Recommendations]。 [!UICONTROL 在前面插入Recommendations]或 [!UICONTROL 在後面插入Recommendations]。 然後可以選擇可用標準，或按一下 **[!UICONTROL 建立條件]**。 如果建立新標準，則可以保存標準以便與其他標準一起使用 [!DNL Recommendations] 活動。 有關詳細資訊，請參見 [建立Recommendations活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。
* 編輯 [!DNL Recommendations] 活動時，請在頁面上的[!UICONTROL 「Recommendations 位置」]方塊中按一下，然後選取&#x200B;**[!UICONTROL 「變更條件」]**。在 [!UICONTROL 選擇條件] 螢幕，按一下 **[!UICONTROL 建立條件]**。 您可以保存新條件以便與其他 [!DNL Recommendations] 活動。

以下步驟假定您訪問 [!UICONTROL 建立新條件] 使用第一種方法進行螢幕顯示：這樣 **[!UICONTROL Recommendations]** > **[!UICONTROL 標準]** 庫螢幕。

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 標準]**。

1. 按一下&#x200B;**[!UICONTROL 「建立條件」]**。

1. 填寫 [基本資訊](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) 的子菜單。

   1. 從 **[!UICONTROL 選擇算法]** 鍵入下拉清單，選擇 **[!UICONTROL 自定義條件]**。

   1. 從 **[!UICONTROL 算法]** 下拉清單，選擇 **[!UICONTROL 自定義算法]**。

      >[!NOTE]
      >
      >前面的步驟導致 [!UICONTROL 上載CSV] 顯示 [!UICONTROL 建立新條件] 對話框。

1. （條件）填寫 [備份內容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) 的子菜單。

1. （條件）填寫 [包含規則](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) 的子菜單。

1. 在 **[!UICONTROL 上載CSV]** 的 **[!UICONTROL 位置]** 的子菜單。

   ![上載CSV部分](assets/upload-csv.png)

   CSV 檔案的格式必須正確上傳才能成功。按一下&#x200B;**[!UICONTROL 「下載 CSV 範本」]**&#x200B;來取得格式正確的 CSV 檔案。

   您有兩個位置選項︰

   * **FTP:** 若要從 FTP 伺服器上傳 CSV 檔案，請選取 **[!UICONTROL FTP]**，然後輸入必要的資訊。您可以使用SSL，該SSL使用FTPS協定安全地傳輸CSV檔案。
   * **URL:** 要從URL上載CSV檔案，請選擇 **[!UICONTROL URL]**，然後輸入源URL。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 考量事項

* 自訂條件實體 (列) 現在可以包含最多 1,000 個建議的項目 (欄)。

* 自訂條件更新預設為「累積」。CSV 上傳檔案中指定的新機碼值組會覆寫現有的機碼值組。沒有在CSV上載中指定鍵的現有鍵值對仍可用於交付，並在上次作為CSV檔案的一部分上載時起31天內過期。

   請聯絡客戶服務啟用這項設定，刪除下次 CSV 上傳中未涵蓋的現有結果。如果啟用此設定，則只有自定義CSV源檔案中存在的鍵可供傳遞。 這項設定會套用至所有自訂條件。

* 自訂條件摘要每 24 小時會更新一次。

   您可以在上載的每個條件卡的底部查看自定義條件上載的上載和同步狀態 [!UICONTROL Recommendations] > [!UICONTROL 標準] 的子菜單。 您還可以在 [!UICONTROL 編輯] 對話框。

* 無錯誤上載的流應為 [!UICONTROL 計畫] > [!UICONTROL 下載源檔案] > [!UICONTROL 導入] > [!UICONTROL 成功]。

* 以下是可能的錯誤消息： [!DNL Target] 上載遇到問題：

   | 錯誤訊息 | 詳細資料 |
   |--- |--- |
   | 未知錯誤 | 指出內部技術錯誤。 |
   | 剖析錯誤 | 摘要檔案格式可能有問題。更正檔案格式並重新保存算法，這將重新啟動檔案下載過程。 |
   | 找不到伺服器 | 提供可在網際網路上顯示的 IP 或主機名稱。 |
   | 憑證錯誤 | 提供伺服器上使用中帳戶的有效的使用者和密碼。 |
   | 找不到目錄 | 提供伺服器上存在的目錄。 |
   | 找不到檔案 | 提供伺服器上存在於指出目錄中檔案的名稱。 |

## 訓練影片: 在 Recommendations 中建立條件 (12:33) ![Tutorial badge](/help/main/assets/tutorial.png)

此視頻包含以下資訊（有關上載自定義條件的詳細資訊，從11:43開始）:

* 建立條件
* 建立條件序列
* 上傳自訂條件

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
