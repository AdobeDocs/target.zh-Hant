---
keywords: 疑難排解;常見問答;FAQ;FAQs;推薦;特殊字元;屬性加權;內容相似度
description: 檢視有關 Adobe [!DNL Target] Recommendations 活動的常見問答清單。
title: 哪裡可以找到有關 [!DNL Target] Recommendations 的問答？
feature: Recommendations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '3153'
ht-degree: 98%

---

# ![PREMIUM](/help/main/assets/premium.png) Recommendations 常見問答

關於 [!DNL Adobe Target] [!DNL Recommendations] 活動的常見問答 (FAQ) 清單。

## 為什麼當我搜尋包含某數值的自訂屬性時，[!UICONTROL 目錄搜尋]未顯示正確的結果？

當您針對包含某數值的自訂屬性執行目錄搜尋時，結果會將自訂屬性視為字串類型，而非數值。

目前，沒有可讓客戶變更屬性類型的功能。若要變更，[開啟客戶問題](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，指出需要將類型從字串變更為數值的屬性。

## 我的目錄中的項目更新要多久的時間才會反映在我的網站上？

時間範圍和結果會因更新項目的方式而異。

| 來源 | 詳細資料 |
| --- | --- |
| 透過 mbox 或 API 更新項目屬性 | <ul><li>在 15 分鐘內更新建議。</li><li>在有更新可用之前會顯示現有的建議和項目屬性。</li><li>目錄搜尋會在目錄索引之後更新 (3-8 小時)。</li></ul> |
| 透過摘要更新項目屬性 | <ul><li>建議會在摘要擷取之後更新 (2-8 小時)。</li><li>在有更新可用之前會顯示現有的建議和項目屬性。</li><li>目錄搜尋會在摘要擷取之後更新 (2-8 小時) 並在後續的目錄索引之後更新 (3-8 小時)。 一共會在 5-16 小時內更新目錄搜尋。</li></ul> |
| 透過 [!DNL Target] UI 或 API 從目錄中刪除項目 | <ul><li>在 15 分鐘內更新建議。</li><li>在有更新可用之前會顯示現有的建議和項目屬性。</li><li>目錄搜尋會在目錄索引之後更新 (3-8 小時)。</li></ul> |
| 透過 mbox 或 API 在目錄中新增項目 | <ul><li>建議會在執行演算法之後更新。 對於 1-2 天的演算法，每 12 小時安排一次演算法執行，對於 7 天以上的演算法，每 24 小時安排一次演算法執行。</li><li>如果新增的項目不是要求的索引鍵，在有更新可用之前會顯示現有的建議。</li><li>如果新增的項目是要求的索引鍵，在有更新可用之前會顯示備用建議。</li><li>目錄搜尋會在目錄索引之後更新 (3-8 小時)。</li></ul> |
| 透過摘要在目錄中新增項目 | <ul><li>建議會在摘要擷取之後更新 (2-8 小時)。 對於 1-2 天的演算法，每 12 小時安排一次後續演算法執行，對於 7 天以上的演算法，每 24 小時安排一次演算法執行。 一共會在 2-32 小時內更新建議。</li><li>如果新增的項目不是要求的索引鍵，在有更新可用之前會顯示現有的建議。</li><li>如果新增的項目是要求的索引鍵，在有更新可用之前會顯示備用建議。</li><li>目錄搜尋會在摘要擷取之後更新 (2-8 小時) 並在目錄索引之後更新 (3-8 小時)。 一共會在 5-16 小時內更新目錄搜尋。</li></ul> |

匯入摘要檔案之後，或是透過 API 或 mbox 收到實體更新之後，將會在 60 分鐘以內反映下列變更：

* 如果某個項目之前已排除但現在應該納入，該項目將會納入下一次演算法執行 (12-24 小時)。

   發生此狀況是因為 [!DNL Target] 會在線上和離線兩個狀態下讓排除生效。 如果新排除某個項目，線上排除很快就會生效。 如果新納入某個項目，線上排除很快就會消失，但離線排除要等到下一次演算法執行後才會消失。

* 如果之前已納入某個項目，但現在應該將其排除，則會根據上面討論的「項目屬性更新...」時間行來排除該項目，這取決於摘要來源 (透過 mbox/API 為 15 分鐘或透過摘要為 12-24 小時)。

在下一個演算法執行作業發生之前 (在 12 至 24 小時內)，不會反映下列變更:

* 用於活動的收集規則中使用的項目屬性。
* 促銷活動中使用的項目屬性，根據與活動相關聯的屬性或集合。
* 項目類別，項目會出現在最暢銷商品或檢視次數最多演算法中的「目前類別」或「最喜愛類別」。
* 建議項目排名 (在已變更的屬性是用來作為演算法自訂金鑰的自訂屬性的情況下)。
* 根據已變更屬性的推薦項目排名 (在推薦邏輯為「具有類似屬性的項目」、已使用「內容相似度」加權因數，或是在已使用「屬性加權」因數的情況下)。

>[!NOTE]
>
>在摘要檔案的狀態從「匯入項目」變更為「準備搜尋索引更新」時，摘要檔案會視為已匯入。更新可能需要 60 分鐘以上的時間才會反映在目錄搜尋使用者介面中；在摘要狀態變更為「更新完成」時，目錄搜尋處於最新狀態。即使目錄搜尋尚未處於最新狀態，您的網站仍會在上方所列的時間範圍反映更新。 最新目錄搜尋索引更新時間會顯示在目錄搜尋頁面上。

## 變更我的 [!UICONTROL Recommendations] 活動、優惠、促銷活動或條件設定需要多久的時間才會反映在我的網站上？

* 促銷活動設定的變更最多可能需要五個小時的時間才會反映在網站上。
* 其他條件設定的變更可能要等到下一次演算法執行後才會反映在網站上。

   * 某些條件設定 (例如「新增動態包含規則」) 會即時反映。
   * 其他條件設定 (例如「移除動態包含規則」、變更回顧視窗等) 要等到下一次演算法執行後才能併入。
   * 這些變更會觸發演算法執行，但最多可能需要 24 小時的時間才能執行完成。 也會以每 12-24 小時的間隔安排執行演算法。

## 使用者的行為 (例如點擊產品 A 及購買產品 B) 需要多久的時間才會反映在&#x200B;*該*&#x200B;使用者收到的建議中？

* 目前已檢視/已購買的產品/內容會影響使用者在相同頁面檢視/[!DNL Target] 內容要求中所收到的建議。
* 過去的使用者行為 (例如「上一次檢視的產品」、「檢視次數最多的產品」及整體檢視/購買記錄) 會更新該要求，並影響使用者在下一個頁面檢視/[!DNL Target] 內容要求中收到的建議。 例如，「最近檢視的項目」和「為您推薦的項目」演算法會更新每個產品檢視/購買，並反映在後續的內容要求中。

## 使用者的行為 (例如點擊產品 A 及購買產品 B) 需要多久的時間才會反映在&#x200B;*其他*&#x200B;使用者收到的建議中？

隨著每 12-24 小時執行一次演算法，使用者的行為會以彙整方式併入離線演算法處理中。

## 如果特殊字元破壞陣列，怎麼辦？  {#section_D27214116EE443638A60887C7D1C534E}

在 JavaScript 中使用逸出值。引號 ( &quot; ) 會破壞陣列。下列程式碼片段是逸出值的範例:

```
#set($String='') 
#set($escaper=$String.class.forName('org.apache.commons.lang.StringEscapeUtils')) 
<script type="text/javascript"> 
console.log("$escaper.escapeJavaScript($entity1.name)") 
console.log("$escaper.escapeJavaScript($entity2.name)") 
console.log('$escaper.escapeJavaScript($entity3.name)') 
names.push("$escaper.escapeJavaScript($entity4.name)") 
</script>
```

## 建立 Recommendations 活動時，為何不是所有條件都可供選擇，包括自訂條件？ {#section_B2265AC8B8A94E0298D495A05C5D817F}

可用的條件取決於目前類別。建立推薦選件時，演算法選擇器會根據類別 ID 來顯示條件。

如果您套用此條件的位置不含類別 ID，則某些條件不會出現在演算法選擇器中。

如果您使用的位置有類別 ID 存在於 mbox 中，則條件選擇器會包含所有適用的條件。

[!DNL Target] 有 [篩選不相容的條件](https://developer.adobe.com/target/implement/recommendations/){target=_blank}設定，可控制演算法選擇器的智慧型篩選。

>[!NOTE]
>
>此設定僅適用於[!UICONTROL 可視化體驗撰寫器] (VEC) 中建立的活動。此設定不適用於表單式體驗撰寫器中建立的活動 ([!DNL Target] 沒有位置環境定義)。

若要存取「[!UICONTROL 篩選不相容的條件]」設定，請按一下「[!UICONTROL 建議] > [!UICONTROL 設定]」：

![recs_settings_filter影像](assets/recs_settings_filter.png)

如果「未」啟用「[!UICONTROL 篩選不相容的條件]」設定，[!DNL Target] 就不會篩選「演算法選擇器」中的演算法，且所有演算法都會顯示。

如果「[!UICONTROL 篩選不相容的條件]」設定已啟用，則在 VEC 活動中，[!DNL Target] 會從選取的位置讀取 entityId 和 categoryId，然後根據 `currentItem|currentCategory` 來顯示演算法 (如果該位置上有各自的值)。 因此，依預設，演算法選擇器中只會顯示所選位置的相容演算法。

如果[!UICONTROL 篩選不相容的條件]設定已啟用，您仍可在選取條件時取消選取[!UICONTROL 「相容」]核取方塊，以檢視不相容的演算法。

![compatible_checkbox映像](assets/compatible_checkbox.png)

下列清單包含 [!DNL Target] 未顯示「[!UICONTROL 相容]」核取方塊的特殊情況：

* 該位置上有 entityId 和 categoryId，所以完全不篩選。
* 您使用 [!DNL mbox.js] 55 版或更舊版本。
* 未從頁面上觸發任何 mbox 呼叫 (!config.isAutoCreateGlobalMbox &amp;&amp; !config.isRegionalMbox)
* [!DNL Target] 參數未定義。

## 如果 Recommendations 中的集合變成零 (0)，怎麼辦？ {#section_E2DB2FE67CF24EEC81412BFF3FA6385D}

如果您看到一個集合原先不是零而現在變成零，請考量下列資訊：

* 您可以重新儲存集合，檢查數字是否會更新。再次儲存，集合會重新執行所有使用該集合的演算法。
* 您所看的環境對嗎？ 請移至 [!DNL /target/products.html#recsSettings] 仔細檢查 (如下所示)。

   ![product_catalog影像](assets/product_catalog.png)

* 索引是最新的嗎？ 請移至[!DNL /target/products.html#productSearch]，檢查索引是幾小時以前編列的 (例如「3 小時前已編列索引」)。您可以視需要重新整理索引。
* 您是否更動過摘要或資料層，而導致實體不再符合收集規則？ 請確定「大小寫」相符 (區分大小寫)。
* 摘要執行成功嗎? 是否有人變更了 FTP 目錄、密碼等？
* [!DNL Target] 會盡全力讓傳送的更新 (在客戶的頁面/應用程式上) 盡快進行。 然而，[!DNL Target] 還是必須在 UI 上為行銷人員提供一些表示法。 [!DNL Target] 不會為了等待 UI 更新同步而延遲傳送更新。 您可以使用 [mboxTrace](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md) 查看當請求進來時系統中有什麼。

## 一般「屬性加權」和「內容相似度」特有的屬性加權之間有何差異？  {#section_FCD96598CBB44B16A4C6C084649928FF}

屬性加權有兩種形式：「標準屬性加權」和「內容相似度屬性加權」。

「標準屬性加權」適用於大部分 (但不是全部) 條件類型 (不只是「內容相似度」)。這種加權會給某些屬性值更多權重。在下列範例中，輸出推薦中會多一些 Nike 產品。

![attribute_weighting_example image](assets/attribute_weighting_example.png)

「內容相似度屬性加權」僅適用於內容相似度條件。

這種加權較動態，而且是根據目前的「建議金鑰」(目前檢視的項目)。在下列範例中 (品牌 x 16)，如果訪客在檢視 Nike 運動鞋，就很可能向該訪客建議其他 Nike 產品 (不一定是運動鞋)，而不是競爭者的運動鞋。如果訪客在檢視 Adidas 運動鞋，則很可能向該訪客建議 Adidas 產品。

![content_simility_example影像](assets/content_similarity_example.png)

## 為何 [!DNL Target] 有時無法顯示推薦？ {#section_DB3F40673AED42228E407C05437D99E9}

[!DNL Target] 有時會因為可用的建議數量不夠而無法顯示建議。

每個條件產生的值數量是設計中指定之實體數量的三倍。產生 3 倍的值之後會套用執行階段篩選 (例如、詳細目錄、mbox 屬性比對)，最後在傳送時可能會少於 3 倍的值。若要減少這種情況發生，請隱藏其他實體來增加設計中的實體數量。

可以在設計開始時使用以下 JavaScript 來增加請求實體的數量。在此範例中，請求的實體計數為 30 (3x10)。

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

## 插入/更新產品之 API 呼叫的大小限制是多少？ 我是否可以使用 API (而非動態消息) 更新某次呼叫中的 50,000 種產品？  {#section_434FE1F187B7436AA39B7C14C7895168}

[!DNL Target] 會在應用程式層級施加 50 MB 的限制；但只有在您傳遞 `application/x-www-form-urlencoded` 內容類型標頭時才會施加該限制。

您當然可以嘗試在單一呼叫中傳送 50,000 個產品。如果失敗，您應該將其分成幾個批次。Adobe 通常建議客戶將其呼叫分成 5,000 或 10,000 個產品批次，以降低系統負載造成逾時的可能性。

## 建立 Recommendations 條件、促銷活動或範本測試規則時，是否需要指定 mbox 名稱？  {#section_FFA42ABCC5954B48A46526E32A3A88A2}

根據 mbox 參數建立 Recommendations 條件、促銷活動或範本測試規則時，`mboxParameter` 不再提示您輸入 `mboxName`。mbox 名稱現在是可選項目。此變更可讓您使用多個 mbox 中的參數，或參考尚未記錄在 Edge 上的參數。

若要選取需要的參數:

* 建立條件、促銷活動或範本測試規則時，從清單中選擇一個參數名稱。開始輸想使用的參數名稱的第一個字元，或鍵入想使用的參數完整名稱。
* 如果您記得 mbox 名稱，但不記得參數名稱，請使用核取方塊來篩選會傳遞所需參數的確定 mbox。

不論使用哪一種方法，mbox 和參數之間並沒有任何連結。條件、促銷活動或範本測試規則將根據傳遞該參數之所有 mbox 的參數運作。

如果編輯現有條件、促銷活動或範本測試規則，則篩選條件將顯示建立期間提供的 mbox 名稱。

## 定義新對象後，為何無法儲存舊版 Recommendations 活動？ {#section_1E47C40B1FE7479BAC3EE0F50CE7C2C4}

請確定對象有唯一的名稱。若您為對象指定了與現有對象相同的名稱，則無法儲存舊版 Recommendations 活動 (2016 年 10 月以前建立的 Recommendations 活動)。

## 用於摘要上傳之 CSV 檔案的檔案大小上限是多少？ {#section_20F1AF4839A447B9889B246D6E873538}

摘要的 CSV 檔案上傳對於資料列數量或檔案大小並沒有嚴格限制。但是，作為最佳作法，Adobe 建議將 CSV 檔案大小限制為 1 GB，以避免檔案上傳處理期間失敗。若檔案大小超過 1 GB，最好將其分割成多個摘要檔案。自訂屬性欄數的上限為 100，而自訂屬性限制為 4096 個字元。在 [[!DNL Target] 限制頁面](/help/main/r-troubleshooting-target/target-limits.md#reference_BEFE60C3AAA442FF94D4EBFB9D3CC9B1)上有提供必要欄長度的其他限制。

## 是否可以動態地排除實體? {#exclude}

在查詢字串中，您可以傳遞要從推薦中排除之實體的實體 ID。例如，您可以排除已在購物車中的項目。

若要啟用排除功能，請使用 `excludedIds` mbox 參數。此參數指向逗號分隔的實體 ID 清單。例如, `mboxCreate(..., "excludedIds=1,2,3,4,5")`。要求建議時會傳送值。

只會針對目前的 [!DNL Target] 呼叫執行此排除；後續 [!DNL Target] 呼叫不會排除項目，除非再次傳遞 `excludedIds` 值。 若要在每個頁面將購物車中的項目自推薦中排除，繼續在每個頁面傳遞 `excludedIds` 值。

>[!NOTE]
>
>如果排除太多實體，則推薦會以沒有足夠實體可填入推薦範本的情況來處理。

若要排除 `entityIds`，請將 `&excludes=${mbox.excludedIds}` 權杖附加至選件內容 URL。擷取內容 URL 時，目前的 mbox 請求參數會替代必要參數。

依預設，新建立的建議會啟用此功能。必須儲存現有的建議來支援動態排除的實體。

## Recommendations 內容 trace 中有時會回傳 NO_CONTENT 回應是什麼意思？

若請求的演算法和重要組成沒有提供推薦，則會回傳 NO_CONTENT。一般而言，此情況會在備份於演算法中停用且下列一個或多個陳述為真時發生：

* 結果尚未準備好。

   此情況一般會在首次儲存一個新建立的活動之時、或在活動中使用的集合、條件或促銷活動的設定發生變更之後。

* 對於所請求的演算法／主要組合，結果已完成，但在最近的邊緣伺服器尚未被快取。

   此請求會起動快取作業，因而此問題應會在重新載入數個頁面和／或幾分鐘的時間內解決。

* 結果已完成，但不適用於所提供的索引鍵值。

   此情形一般發生是在請求某項目的推薦時發生，且該項目是在最近一次演算法執行後加入目錄並會在下一次演算法執行後解決。

* 部分範本顯示被停用，而且結果不足以將範本填滿。

   此情形一般在你有動態包含規則其該規則積極從可能的結果中篩選許多項目的時候發生。為避免此情況，請啟用備份，並且請勿將包含規則套用至備份，或在序列中使用較不積極的篩選條件。

## 根據最近檢視項目的建議會針對單一訪客保存在多個裝置上嗎？ {#persist-across-devices}

當訪客起始工作階段時，工作階段 ID 會繫結至單一邊緣機器，而暫時設定檔快取會儲存在這部邊緣機器中。 來自相同工作階段的後續要求會讀取此設定檔快取，包括最近檢視的項目。

當工作階段結束時 (通常會在 30 分鐘沒有活動後到期)，工作階段狀態 (包括最近檢視的項目) 會保存在相同地理邊緣中較永久的設定檔儲存空間。

之後來自不同裝置的後續工作階段就可以存取這些最近檢視的項目，前提為新的工作階段透過相同的 Marketing Cloud ID (MCID)、Experience Cloud ID (ECID) 或 CustomerID/mbox3rdPartyId 繫結至客戶設定檔。

如果訪客同時有兩個作用中工作階段，某台裝置上最近檢視的項目並不會更新另一台裝置上的最近檢視的項目，除非這些裝置被強制共用工作階段 ID。 此問題有可能的解決辦法，但 [!DNL Target] 無法直接支援跨多台裝置的工作階段 ID 共用。 客戶必須自行管理此 ID 共用。

如果訪客在某台裝置上很活躍，然後幾分鐘後於另一台裝置上很活躍，還是會發生此行為。 第一台裝置的工作階段不會在 30 分鐘後到期，而且在設定檔狀態寫入永久狀態並進行處理之前，最多可能會延遲五分鐘。 在測試此行為時，請等候 35 分鐘讓工作階段到期，並儲存設定檔。

如果訪客未同時擁有兩個作用中工作階段，只要工作階段已結束，某台裝置上最近檢視的項目就會更新另一台裝置上的最近檢視的項目。 在測試此行為時，請等候 35 分鐘讓工作階段到期。

## 我可以在 [!DNL Recommendations Premium] 中使用 [!DNL Adobe Recommendations Classic] 中建立的演算法嗎？

[!DNL Recommendations Premium] 不支援在 [!DNL Recommendations Classic] 中建立的演算法。您也許可以在 [!DNL Target Premium] 中使用舊版演算法；但是，當在 [!DNL Target Premium] UI 中停用或刪除活動時，演算法可能會產生同步問題。如需這兩個解決方案之間差異的詳細資訊，請參閱 [!DNL Target Premium]](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md)中的 [[!DNL Recommendations Classic] versus [!DNL Recommendations]  活動。

## 如何只推薦新文章或影片？ {#recommend-new-articles}

一些媒體和出版業客戶想確保推薦項目僅包含最新的文章或影片。例如，[!DNL Target] 客戶使用以下方法，推薦 60 天內的文章：

1. 以 YYMMDDD 格式傳遞文章發佈日期，作為自訂實體屬性。
1. 建立一個設定檔指令碼，將今天的日期減去 60 天，同樣是 YYYYMMDD 格式。
1. 在條件中使用動態包含篩選器，讓 `publish date > today’s date minus 60 days`。

### 傳遞文章發佈日期作為自訂實體屬性：

| 實體屬性 | 範例 |
| --- | --- |
| issueDate | 2021218 |
| lastViewDate | 2021701 |
| parentCategory | commentary |
| publishDate | 20210113 |
| publishDateDisplay | 2021 年 1 月 13 日 |

### 設定設定檔指令碼：

![範例設定檔指令碼](/help/main/c-recommendations/c-recommendations-faq/assets/sample-profile-script.png)

### 設定包含規則：

![範例包含規則](/help/main/c-recommendations/c-recommendations-faq/assets/sample-inclusion-rule.png)

>[!NOTE]
>
>此範例也可以使用參數比對並將 `priorDate60` 值作為 mbox 參數傳遞來完成。
