---
description: 關於建議活動常見問題集 (FAQ) 的清單。
keywords: 疑難排解;常見問題集;FAQ;建議;特殊字元;屬性加權;內容相似度
seo-description: 關於建議活動常見問題集 (FAQ) 的清單。
seo-title: Recommendations 常見問題集
solution: Target
title: Recommendations 常見問題集
title-outputclass: premium
topic: Premium
uuid: 27752811-0ffe-4d60-83d1-39e18b1953d5
badge: premium
translation-type: tm+mt
source-git-commit: 9fbcbdff934b0c372e4de94f846f01953f7bc77f

---


# ![PREMIUM](/help/assets/premium.png) Recommendations 常見問題集{#recommendations-faq}

關於建議活動常見問題集 (FAQ) 的清單。

## 目錄中的項目更新要多久時間才會反映在網站上?

匯入摘要檔案之後，或是透過 API 或 mbox 收到實體更新之後，將會在 60 分鐘以內反映下列變更:

* 設計範本中傳回的項目屬性。
* 全域排除規則中使用的項目屬性，可防止傳回的建議中包含該項目。
* 條件的包含規則中使用的項目屬性，這會影響是否要再傳回的建議中包含或排除項目。

在下一個演算法執行作業發生之前 (在 12 至 24 小時內)，不會反映下列變更:

* 用於活動的收集規則中使用的項目屬性。
* 促銷活動中使用的項目屬性，根據與活動相關聯的屬性或集合。
* 項目類別，項目會出現在最暢銷商品或檢視次數最多演算法中的「目前類別」或「最喜愛類別」。
* 建議項目排名 (在已變更的屬性是用來作為演算法自訂金鑰的自訂屬性的情況下)。
* 根據已變更屬性的建議項目排名 (在建議邏輯為「具有類似屬性的項目」、已使用「內容相似度」加權因數，或是在已使用「屬性加權」因數的情況下)。

>[!NOTE]
>
>在摘要檔案的狀態從「匯入項目」變更為「準備搜尋索引更新」時，摘要檔案會視為已匯入。更新可能需要 60 分鐘以上的時間才會反映在目錄搜尋使用者介面中；在摘要狀態變更為「更新完成」時，目錄搜尋處於最新狀態。即使目錄搜尋尚未處於最新狀態，網站仍會在上方所列的時間範圍反映更新。最新目錄搜尋索引更新時間會顯示在目錄搜尋頁面上。

## 如果特殊字元破壞陣列，怎麼辦? {#section_D27214116EE443638A60887C7D1C534E}

在 JavaScript 中使用逸出值。引號 ( " ) 會破壞陣列。下列程式碼片段是逸出值的範例:

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

## 建立「建議」活動時，為何不是所有條件都可供選擇，包括自訂條件?    {#section_B2265AC8B8A94E0298D495A05C5D817F}

可用的條件取決於目前類別。建立建議選件時，演算法選擇器會根據類別 ID 來顯示條件。

如果您套用此條件的位置不含類別 ID，則某些條件不會出現在演算法選擇器中。

如果您使用的位置有類別 ID 存在於 mbox 中，則條件選擇器會包含所有適用的條件。

Target 具有[篩選不相容的條件](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)設定，可控制演算法選擇器的智慧型篩選。

>[!NOTE]
>
>此設定僅適用於可視化體驗撰寫器 (VEC) 中建立的活動。此設定不適用於表單式體驗撰寫器中建立的活動 (Target 沒有位置環境定義)。

若要存取[!UICONTROL 篩選不相容的條件]設定，請按一下「[!UICONTROL 建議] &gt; [!UICONTROL 設定]」:

![](assets/recs_settings_filter.png)

如果「未」啟用[!UICONTROL 篩選不相容的條件]設定，Target 就不會篩選「演算法選擇器」中的篩選演算法，所有演算法都會出現。

如果[!UICONTROL 篩選不相容的條件]設定已啟用，則在 VEC 活動中，Target 會從選取的位置讀取 entityId 和 categoryId，然後根據 `currentItem|currentCategory` 來顯示演算法 (如果各自的值存在該位置上)。因此，依預設，演算法選擇器中只會顯示所選位置的相容演算法。

如果[!UICONTROL 篩選不相容的條件]設定已啟用，您仍可在選取條件時取消選取[!UICONTROL 「相容」]核取方塊，以檢視不相容的演算法。

![](assets/compatible_checkbox.png)

下列清單包含 Target 未顯示[!UICONTROL 「相容」]核取方塊的特殊情況:

* entityId 和 categoryId 都存在位置上，所以完全不篩選。
* 您使用 [!DNL mbox.js] 55 版或更舊版本。
* 未從頁面上觸發任何 mbox (!config.isAutoCreateGlobalMbox &amp;&amp; !config.isRegionalMbox)
* Target 參數未定義。

## 如果「建議」中的集合變成零 (0)，怎麼辦?    {#section_E2DB2FE67CF24EEC81412BFF3FA6385D}

如果您看到一個集合原先不是零而現在變成零，請考量下列資訊:

* 您可以重新儲存集合，檢查數字是否會更新。請注意，重新儲存會讓集合重新執行所有用到該集合的演算法。
* 您所看的環境對嗎? 請移至 [!DNL /target/products.html#recsSettings] 仔細檢查 (如下所示)。

   ![](assets/product_catalog.png)

* 索引是最新的嗎? 請移至 [!DNL /target/products.html#productSearch]，檢查索引是幾小時以前編列的 (例如「3 小時前已編列索引」)。您可以視需要重新整理索引。
* 您是否更動過摘要或資料層，而導致實體不再符合收集規則? 請確定「大小寫」相符 (區分大小寫)。
* 摘要執行成功嗎? 有人變更過 FTP 目錄、密碼...等等嗎?
* Target 會儘力讓傳送儘快更新 (在客戶的頁面/應用程式上)。然而，我們還是必須在 UI 上為市場行銷人員提供一些表示法。我們不一定會為了等待 UI 更新同步而延遲傳送更新。您可以使用 [mboxTrace](https://marketing.adobe.com/resources/help/en_US/target/target/c_content_trouble.html#) 查看當請求進來時系統中有什麼。

## 一般「屬性加權」和「內容相似度」特有的屬性加權之間有何差異? {#section_FCD96598CBB44B16A4C6C084649928FF}

屬性加權有兩種形式:「標準屬性加權」和「內容相似度屬性加權」。

「標準屬性加權」適用於大部分 (但不是全部) 條件類型 (不只是「內容相似度」)。這種加權會給某些屬性值更多權重。在下列範例中，輸出建議中會多一些 Nike 產品。

![](assets/attribute_weighting_example.png)

「內容相似度屬性加權」僅適用於內容相似度條件。

這種加權較動態，而且是根據目前的「建議金鑰」(目前檢視的項目)。在下列範例中 (品牌 x 16)，如果訪客在檢視 Nike 運動鞋，就很可能向該訪客建議其他 Nike 產品 (不一定是運動鞋)，而不是競爭者的運動鞋。如果訪客在檢視 Adidas 運動鞋，則很可能向該訪客建議 Adidas 產品。

![](assets/content_similarity_example.png)

## 為何 Target 有時無法顯示建議?    {#section_DB3F40673AED42228E407C05437D99E9}

Target 有時會因為可用的建議數量不夠而無法顯示建議。

每個條件產生的值數量是設計中指定之實體數量的 5 倍。產生 5 倍的值之後會套用執行階段篩選 (例如、詳細目錄、mbox 屬性比對)，最後在傳送時可能會少於 5 倍的值。若要減少這種情況發生，請隱藏其他實體來增加設計中的實體數量。

可以在設計開始時使用以下 JavaScript 來增加請求實體的數量。在此範例中，請求的實體計數為 50 (5x10)。

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

## 插入/更新產品之 API 呼叫的大小限制是多少? 我是否可以使用 API (而非動態消息) 更新某次呼叫中的 50,000 種產品? {#section_434FE1F187B7436AA39B7C14C7895168}

Target 在應用程式層級實施 50 MB 的限制；但是，只有當您傳遞 `application/x-www-form-urlencoded` 內容類型標頭時才會實施該限制。

您當然可以嘗試在單一呼叫中傳送 50,000 個產品。如果失敗，您應該將其分成幾個批次。我們通常建議客戶將其呼叫分成 5,000 或 10,000 個產品批次，以降低系統負載造成逾時的可能性。

## 建立建議條件、促銷活動或範本測試規則時，是否需要指定 mbox 名稱?    {#section_FFA42ABCC5954B48A46526E32A3A88A2}

根據 mbox 參數建立建議條件、促銷活動或範本測試規則時，`mboxParameter` 不再提示您輸入 `mboxName`。mbox 名稱現在是可選項目。此變更可讓您使用多個 mbox 中的參數，或參考尚未記錄在 Edge 上的參數。

若要選取需要的參數:

* 建立新條件、促銷活動或範本測試規則時，請從清單中選取參數名稱，開始輸入所需參數名稱的第一個字元，或輸入所需參數名稱的完整名稱。
* 如果您記得 mbox 名稱，但不記得參數名稱，請使用核取方塊來篩選會傳遞所需參數的確定 mbox。

不論使用哪一種方法，mbox 和參數之間並沒有任何連結。條件、促銷活動或範本測試規則將根據傳遞該參數之所有 mbox 的參數運作。

如果編輯現有條件、促銷活動或範本測試規則，則篩選條件將顯示建立期間提供的 mbox 名稱。

## 定義新對象後，為何無法儲存舊版 Recommendations 活動?    {#section_1E47C40B1FE7479BAC3EE0F50CE7C2C4}

請確定對象有唯一的名稱。若您為對象指定了與現有對象相同的名稱，則無法儲存舊版 Recommendations 活動 (2016 年 10 月以前建立的 Recommendations 活動)。

## 用於摘要上傳之 CSV 檔案的檔案大小上限是多少?    {#section_20F1AF4839A447B9889B246D6E873538}

摘要的 CSV 檔案上傳對於資料列數量或檔案大小並沒有嚴格限制。但是，作為最佳作法，我們建議將 CSV 檔案大小限制為 1 GB，以避免檔案上傳處理期間失敗。若檔案大小超過 1 GB，最好將其分割成多個摘要檔案。自訂屬性欄數的上限為 100，而自訂屬性限制為 4096 個字元。「Target 限制」頁面上提供了對於所需欄長度的[其他限制](../../r-troubleshooting-target/target-limits.md#reference_BEFE60C3AAA442FF94D4EBFB9D3CC9B1)。

## 是否可以動態地排除實體?

在查詢字串中，您可以傳遞要從建議中排除之實體的實體 ID。例如，您可以排除已在購物車中的項目。

若要啟用排除功能，請使用 `excludedIds` mbox 參數。此參數指向逗號分隔的實體 ID 清單。例如, `mboxCreate(..., "excludedIds=1,2,3,4,5")`。要求建議時會傳送值。

排除僅針對目前的Target呼叫執行；後續Target呼叫中不會排除項目，除非 `excludedIds` 再次傳遞值。 若要從每個頁面上的建議中排除購物車中的項目，請繼續在每個頁 `excludedIds` 面上傳遞值。

>[!NOTE]
>
>如果排除太多實體，則建議會以沒有足夠實體可填入建議範本的情況來處理。

To exclude `entityIds`, append the `&excludes=${mbox.excludedIds}` token to the offer content url. 擷取內容 URL 時，目前的 mbox 請求參數會替代必要參數。

依預設，新建立的建議會啟用此功能。必須儲存現有的建議來支援動態排除的實體。
