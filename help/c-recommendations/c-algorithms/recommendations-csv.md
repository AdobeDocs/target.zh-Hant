---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: 上傳 CSV 檔案來自訂您的建議。
title: 上傳自訂條件
feature: criteria
uuid: e0b4d320-db00-43ad-b49e-ce36c8532320
translation-type: tm+mt
source-git-commit: 66b3c42181daf582c9b3bee1f83a2229b823c5c3
workflow-type: tm+mt
source-wordcount: '1873'
ht-degree: 66%

---


# ![PREMIUM](/help/assets/premium.png) 上傳自訂條件{#upload-custom-criteria}

上傳 CSV 檔案來自訂您的建議。

## 存取「建立新准則」畫面

有多個方式可進入[!UICONTROL 「建立新條件」]畫面。根據您達到畫面的方式，部分畫面選項可能有所不同。

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. 您在這裡建立的條件會自動可供所有 [!DNL Recommendations] 活動使用。
* 當您使用 [!DNL Recommendations][!UICONTROL Visual Experience Composer] (VEC)進行活動時，在頁面上的元素和 [!UICONTROL Click Web後，您會立即被帶到] Select Select Reperience Composer(Visual Experience Composer (VEC)螢幕)的Recommendations。 然後，您可以選取可用的標準，或按一下「建 **[!UICONTROL 立標準」]**。 如果您建立新標準，您可以選擇儲存標準以用於其他活 [!DNL Recommendations] 動。 For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* 編輯 [!DNL Recommendations] 活動時，請在頁面上的[!UICONTROL 「Recommendations 位置」]方塊中按一下，然後選取&#x200B;**[!UICONTROL 「變更條件」]**。On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. 您將可以選擇儲存您的新條件以搭配其他 [!DNL Recommendations] 活動使用。

以下步驟假定您使用第一 [!UICONTROL 種方法訪問「建立新標準] 」螢幕：「建 **[!UICONTROL 議]** > **[!UICONTROL 准則]** 」程式庫畫面。

1. 按一 **[!UICONTROL 下「建議]** > **[!UICONTROL 准則]**」。

1. 按一 **[!UICONTROL 下「建立條件]** >上 **[!UICONTROL 傳自訂條件」]**。

1. 在下列章節中設定資訊。

## 基本資訊 {#info}

1. 輸入&#x200B;**[!UICONTROL 條件名稱]**。

   這是用來說明該條件的「內部」名稱。例如，您可能想要將您的條件稱為「利潤最高的產品」，但您不想要將該標題公開顯示。請參閱下一個步驟來設定公開顯示的標題。

   ![「基本資訊」部分](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. 輸入公開顯示的&#x200B;**[!UICONTROL 顯示標題]**，以在使用此條件的任何 Recommendations 頁面上顯示。

   例如，使用此條件來顯示建議時，您可能想要顯示「瀏覽過此項目、也瀏覽了其他項目的使用者」或「類似產品」。

1. 輸入條件的簡短&#x200B;**[!UICONTROL 說明]**。

   說明應協助您識別標準，並可能包含標準用途的相關資訊。

1. 選取&#x200B;**[!UICONTROL 垂直產業]**:

   * [!UICONTROL 零售/電子商務]
   * [!UICONTROL 潛在客戶開發/B2B/金融服務]
   * [!UICONTROL 媒體/出版]

   其他條件選項將根據您選取的垂直產業而變更。

1. 選取一個&#x200B;**[!UICONTROL 頁面類型]**。

   您可以選取多個頁面類型。

   產業垂直和頁面類型可共同用來分類您儲存的條件，讓您可輕鬆對其他 [!DNL Recommendations] 活動重複使用條件。

1. 選取一個&#x200B;**[!UICONTROL 建議索引鍵]**。

   如需依據索引鍵的條件之相關詳細資訊，請參閱[讓建議以建議索引鍵為依據](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

1. 選取&#x200B;**[!UICONTROL 「建議邏輯」]**。

   如需關於建議邏輯選項的詳細資訊，請參閱[條件](../../c-recommendations/c-algorithms/algorithms.md)。

   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](#similarity).

## 內容 {#content}

Content rules determine what happens if the number of recommended items does not fill your [recommendations design](/help/c-recommendations/c-design-overview/design-overview.md). [!DNL Recommendations] 條件可能傳回較您的設計所需更少的建議。例如，如果您的設計有四個項目的插槽，但您的條件只會建議兩個項目，您可以將其餘的插槽留空，或者您可以使用備份建議來填滿額外的插槽。

![內容區段](/help/c-recommendations/c-algorithms/assets/content.png)

1. （可選）將「部 **[!UICONTROL 分設計演算]** 」切換至「開啟」位置。

   將會填入盡可能多的槽，但設計範本可能包含剩餘槽的空白空間。 如果此選項已停用，而且沒有足夠的內容來填滿所有可用的位置，則不會提供建議，而會改為顯示預設內容。

   如果您想要將建議與空白位置搭配使用，請啟用此選項。 如果您希望根據您的准則以內容填入建議槽，並填入空白槽，而且網站上已填入類似或熱門內容，請使用備份建議，如下一步所述。

1. （可選）將「顯 **[!UICONTROL 示備份建議]** 」切換至「開啟」位置。

   從您的網站上隨機選擇檢視次數最多的產品，以填入設計中剩餘的空白位置。

   使用備份建議可確保建議設計填滿所有可用的位置。 假設您有4 x 1設計，如下圖所示：

   ![4 x 1設計](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   假設您的准則只會建議兩個項目。 如果啟用「部 [!UICONTROL 分設計渲染] 」(Partial Design Rendering)選項，前兩個插槽將被填充，但其餘兩個插槽仍為空。 不過，如果您啟用「顯 [!UICONTROL 示備份建議」選項] ，則前兩個插槽會根據您的指定條件填入，其餘兩個插槽則會根據您的備份建議填入。

   下列矩陣顯示使用「部分設計演算」和「備 [!UICONTROL 份建議」選項時][!UICONTROL 將觀察的結果] :

   | 部分設計呈現 | 備份 Recommendations | 結果 |
   |--- |--- |--- |
   | 已停用 | 已停用 | 如果傳回的建議少於設計呼叫的數目，則會以預設內容取代建議設計，並且不顯示建議。 |
   | 已啟用 | 已停用 | 系統會轉譯設計，但如果傳回的建議少於設計呼叫的數目，則可能包含空格。 |
   | 已啟用 | 已啟用 | 備用建議會填滿可用的設計「槽」，以完整呈現設計。<br>如果因套用包含規則至備用建議而限制了合格備用建議的數量，以致設計無法填滿，則會轉譯部分設計。<br>如果條件未傳回任何建議，並且包含規則將備用建議限制為零，則會以預設內容來取代設計。 |
   | 已停用 | 已啟用 | 備用建議會填滿可用的設計「槽」，以完整呈現設計。<br>如果因套用包含規則至備用建議而限制了合格備用建議的數量，以致設計無法填滿，則會以預設內容取代設計，並且不顯示建議。 |

   如需詳細資訊，請參 [閱使用備份建議](/help/c-recommendations/c-algorithms/backup-recs.md)。

1. （條件性）如果您在上 **[!UICONTROL 一步驟中選取「顯示備份建議]** 」，則可以啟用「套 **[!UICONTROL 用包含規則至備份建議」]**。

   包含規則會決定哪些項目包含在建議中。 可用的選項取決於您的垂直產業。

   如需更多詳細資料，請參閱 [請在下方指定包含規則](#inclusion) 。

1. （可選）投影片「 **[!UICONTROL 建議先前購買的項目]** 」會切換至「開啟」位置。

   此設定是根據 `productPurchasedId`。預設行為是不推薦先前購買的項目。大多數情況下，您不會想推銷客戶最近已購買的項目。如果您銷售的是客戶一般只會購買一次的項目，例如獨木舟，則此相當實用。如果您銷售的是人們反複回來購買的物品，例如洗髮水或其他個人物品，您應啟用此選項。

## 包含規則 {#inclusion}

有數個選項可以協助您縮減在建議中顯示的項目。您可以在建立條件或促銷活動時使用包含規則。

![包含規則](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

包含規則屬於可選; 不過，設定這些詳細資料可讓您對於建議中出現的項目擁有更多控制。您設定的每個詳細資訊都會進一步縮小顯示條件。

例如，您可以選擇只顯示存貨超過 50 雙且價格介於 $25 和 $45 之間的女鞋。您也可以加權每個屬性，讓對於您業務更為重要的項目可以更常顯示。

另一個範例是，您可以選擇對造訪您的網站、僅來自特定城市且擁有所需大學學位的訪客顯示職缺。

包含規則選項可能因垂直產業而不同。依預設，包含規則會套用至備用建議。

>[!IMPORTANT]
>
>您應該謹慎使用包含規則。例如，如果您的組織具有規則，要求在顯示某個品牌時不建議其他品牌，則這些選項很有用。不過，此功能有機會成本。將活動條件通常會顯示的某些項目限制為不要顯示時，您可能會遺失提升度百分比。

利用 AND 聯合包含規則。必須符合所有規則，才能在建議中納入某個項目。

如先前所提及，若要建立簡單的包含規則，僅顯示存貨大於 50 且價格介於 $25 與 $45 之間的女鞋，請執行下列步驟:

1. 設定您要建議之產品的價格範圍。
1. 設定您要建議之產品的存貨量下限。
1. 設定建議只在項目符合您的特定條件時才顯示。

   ![](assets/Recs_InclusionRules.png)

   您可以指定僅在符合清單中的其中一項屬性，或不符合一項或多項指定的條件時，才包括項目。

   可用的評估工具取決於您在第一個下拉式清單中選擇的值。您可以列出多個項目。這些項目會使用 OR 來評估。

   多個規則會使用 AND 來結合。

   >[!NOTE]
   >
   >此選項會限制建議中所顯示的項目。不會限制在哪些頁面中顯示建議。若要限制建議顯示的位置，請在體驗撰寫器中選取頁面。

For more information, see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## 上傳CSV

1. 選取您的 CSV 檔案的&#x200B;**[!UICONTROL 位置]**。

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