---
keywords: 目標定位
description: 了解Adobe [!DNL Target] 顯示並計算每個體驗的轉換率、提升度、信賴度和信賴區間。
title: 如何檢視轉換率、提升度和信賴等級？
feature: Reports
exl-id: b4cfe926-eb36-4ce1-b56c-7378150b0b09
source-git-commit: 493ecd762b5228d33377ac8263b90a0f9c73127e
workflow-type: tm+mt
source-wordcount: '2150'
ht-degree: 53%

---

# 轉換率

每次體驗皆會回報轉換率、提升度、信賴度和信賴區間。

下圖顯示活動範例的圖表標題，並醒目提示[!UICONTROL 轉換率]、[!UICONTROL 提升度]和[!UICONTROL 信賴度]。

![](assets/conversion-rate.jpg)

>[!NOTE]
>
>在所有資料中，若傳遞 `orderID`，則會忽略重複訂單。稽核報表會列出忽略的重複訂單。

## 轉換率 {#section_07A36846C4E84D0881906809B9CE5A74}

顯示中位數轉換率、信賴度、區間和轉換次數。

例如，檢查下列轉換率報表欄:

![](assets/conversion-rate-detail.jpg)

第一行是控制體驗。其中顯示 15% 的轉換率，轉換三次。第二行 (體驗 B) 顯示 15% 轉換率，信賴區間加或減 15.65%，轉換三次。

>[!NOTE]
>
>目前，信賴區間僅針對二進位量度計算。

## 提升度 {#section_0F409572C720433D9378092ABC999982}

對照控制體驗來比較每一個體驗的轉換率。

提升度 = (體驗 CR - 控制 CR) / 控制 CR

若控制值為 0，則無百分比提升度。


## 零售資料 {#section_30A674731BA6440E9BB93C421BE990EE}

如果您插入下訂單(`orderConfirmPage`)mbox，並選取它作為轉換mbox。

## 信賴等級與信賴區間 {#concept_0D0002A1EBDF420E9C50E2A46F36629B}

對於每個體驗，會顯示信賴和信賴區間。

您可以對 for Target (A4T) 執行離線計算，但在 [!DNL Analytics]Analytics 中需要執行資料匯出的步驟。如需詳細資訊，請參閱以下的「對 Target (A4T) 執行離線計算」。

### 可信度 {#section_26FE5E44BDD5478792A65FCFD83DCCDC}

顯示的體驗或選件的信賴度，是獲得結果低於實際觀察到的結果的機率（以百分比表示），如果null假設為真，（實質上，如果該體驗或選件與控制體驗/選件之間的轉換率沒有差異）。 就p值而言，顯示的信賴度為1 - p值。 更簡單地說，信賴度較高表示資料與控制項和非控制項選件/體驗具有相同轉換率的假設不一致。

可信度大於或等於 99.995% 時會四捨五入為 100.00%。

![](assets/conf_report.png)  ![](assets/conf_report_detail.png)

下定任何商業決策之前，請試著靜待出現足夠大小的樣本，且有一或多個體驗的四條信賴度在一段持續的時間內保持一致，以確保獲得穩定的結果。


### 信賴區間 {#section_F582738DFE1648C78B93D81EBC6CACF7}

>[!NOTE]
>
>目前，信賴區間僅針對二進位量度計算。

此 *信賴區間* 是一個估計範圍，可在指定的信賴等級中找到量度的真值。 Target一律會顯示95%信賴區間。 信賴區間在「轉換率」欄中以淺灰色 +/- 百分比出現。在下列範例中，體驗 B 提升度的信賴區間會加或減 15.65%。

![](assets/conversion_rate.png)

**範例：** 體驗觀察到的RPV為$10，而其為95% **信賴區間** 是$5到$15。 我們不知道，其真實RPV為$12。 然後，如果我們執行此測試多次，我們計算的信賴區間95%的時間會包含 _true_ RPV的值$12。

**影響信賴區間的因素為何？**&#x200B;公式會遵循標準統計方法來計算信賴區間。

* **樣本尺寸:** 樣本增大，區間就縮小或變窄。這代表您的報表越來越接近成功度量的真值，因此為有利狀況。
* **標準偏差較小:** 結果越近似 (例如相似的 AOV、數字或每日轉換訪客)，便越會縮小標準偏差。

## 可信度計算以及如何離線執行計算 {#section_86F7C231943043A5B8B6BFE67B706E3B}

[下載的 CSV 報表](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)只包含原始資料，不含計算度量，例如每次造訪帶來的收入、提升度或用於 A/B 測試的信賴度。

若要計算這些計算量度，請下載Target的 [完整可信度電腦](/help/main/assets/complete_confidence_calculator.xlsx) 輸入活動值或檢閱的Excel檔案 [A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

>[!NOTE]
>
>此計算機適用於鎖定目標型報表，而非 A4T 報表。

## 執行Adobe Target(A4T)的Analytics離線計算 {#section_B34BD016C8274C97AC9564F426B9607E}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。

若為A4T，我們會使用 [韋爾奇的T型](https://en.wikipedia.org/wiki/Welch%27s_t-test)連續變數（而非二進位量度）的{target=_blank}計算。 在 Analytics 中，一律會追蹤訪客，並統計每一個採取的動作。因此，如果訪客多次購物或多次造訪成功量度，這些額外的點閱會納入計算。這會使量度變成連續變數。為了進行Welch的t檢定計算，需要「平方和」來計算方差，用於t統計量的分母。 [A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) 說明所用數學公式的詳細資訊。 平方和可從 [!DNL Analytics]. 若要取得平方和資料，您需要針對想要最佳化的量度，在樣本期間內執行訪客等級的匯出。

例如，如果您最佳化為每位訪客的頁面檢視，您會在指定的時間範圍內，依每位訪客匯出頁面檢視總數的範例，可能需要幾天（您只需要幾千個資料點）。 接著，您會求每一個值的平方，並算出總和 (此處的運算順序很重要)。然後，在「完整信賴度計算機」中會使用此「平方和」值。針對這些值，使用該試算表的「收入」區段。

**使用 [!DNL Analytics] 資料匯出功能來這樣做:**

1. 登入 [!DNL Adobe Analytics]。
1. 按一下「**[!UICONTROL 工具]** > **[!UICONTROL 資料倉儲]**」。
1. 在&#x200B;**[!UICONTROL 「資料倉儲要求」]**&#x200B;標籤上，填寫欄位。

   如需每一個欄位的相關資訊，請參閱[資料倉儲](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html)中的「資料倉儲說明」。

   | 欄位 | 說明 |
   |--- |--- |
   | 請求名稱 | 指定要求的名稱。 |
   | 報告日期 | 指定時段和精度。<br>最佳做法是不要為第一個要求選擇超過一小時或一天的資料。所要求的時段越長，資料倉儲檔案處理的時間就越長，最好一律先要求較短時段的資料，以確保檔案傳回預期的結果。接著，前往「要求管理程式」，複製要求，再第二次要求更多資料。此外，如果您將粒度切換為「無」以外的任何值，則檔案大小會大幅增加。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 可用區段 | 視需要套用區段。 |
   | 劃分 | 選取所需的維度:標準是內建 (OOTB)，而「自訂」包含 eVars 與屬性。如果需要訪客ID層級資訊，建議您使用「訪客ID」，而非「Experience Cloud訪客ID」。<ul><li>訪客 ID 是 Analytics 使用的最終 ID。這會是 AID (如果客戶是舊的) 或 MID (如果客戶是新的，或已清除從 MC 訪客 ID 服務啟動以來的 Cookie)。</li><li>僅針對新的客戶，或客戶已清除從 MC 訪客服務啟動以來的 Cookie，才會設定 Experience Cloud 訪客 ID。</li></ul> |
   | 量度 | 選取所需的量度。標準是 OOTB，而「自訂」包含自訂事件。 |
   | 報表預覽 | 在排定報表之前檢閱設定。<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 計劃傳送 | 輸入要將檔案傳送到哪個電子郵件地址、命名檔案，然後選取[!UICONTROL 「立即傳送」]。<br>注意: 在[!UICONTROL 「進階傳送選項」]<br>![下，您可以透過 FTP 傳送檔案排程傳送](/help/main/c-reports/assets/datawarehouse3.png)。 |

1. 按一下&#x200B;**[!UICONTROL 「請求此報表」]**。

   檔案傳送最多可能需要 72 小時，視所要求的資料量而定。您隨時可以按一下「[!UICONTROL 工具] > [!UICONTROL 資料倉儲] > [!UICONTROL 要求管理程式]」，以檢查要求的進度。

   如果您想要重新請求過去請求的資料，可以從 [!UICONTROL 請求管理員] 視需要。

如需 [!DNL Data Warehouse] 的相關資訊，請參閱 [!DNL Analytics] 說明文件中的下列連結:

* [建立 Data Warehouse 請求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Data Warehouse最佳實務](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)

## 計算方法 {#concept_EC19BC897D66411BABAF2FA27BCE89AA}

您可以選擇依不同的計算方法來檢視報表，以瞭解活動在其存留期或單一作業階段期間影響使用者的方式。

下列活動類型支援計數方法:

* A/B 測試

   例外的是 A/B 活動僅支援預設「造訪」計數方法。

* 體驗鎖定目標 (XT)
* 多變數測試 (MVT)

   對於 MVT 元素貢獻報表，Target 不支援「收入量度」類型的「活動曝光次數」。

* Recommendations

對於自動個人化 (AP) 活動，目前僅支援預設計數方法 (造訪)。

您可以遵循下列計數方法來檢視報表:

* **訪客:** 活動期間的唯一參與者。

   如果某人從新電腦或新瀏覽器造訪網站、刪除 Cookie，或以相同 Cookie 轉換和回到活動，則會將此人視為新的加入者。系統會使用訪客 mbox Cookie 中的 PCID 來識別加入者。若 PCID 變更，則會將使用者視為新訪客。

* **造訪:** 在單一 30 分鐘的瀏覽器工作階段期間，體驗中的唯一參與者。

   若達成轉換或訪客在離開至少 30 分鐘後返回網站，則會將再度訪問的訪客視為新的造訪。系統會使用訪客 mbox Cookie 中的 `sessionID` 來識別瀏覽。當 `sessionID` 變更，則會視為新瀏覽。

* **曝光/頁面檢視:** 每次使用者載入任何活動的頁面時，就計算一次。

   單次造訪可能包含多次曝光，例如首頁。

>[!NOTE]
>
>計數通常是由 Cookie 和作業活動所決定。不過，若您達到活動的最終轉換點，然後重新進入活動，則會將您視為該活動的新加入者和新的造訪。即使您的 PCID 和 `sessionID` 值未變更，亦會採取此處理方式。

## 為什麼 [!DNL Target] 推薦使用韋爾奇的t檢定？ {#t-test}

A/B測試是實驗，用來比較控制變體中某些業務量度（也稱為體驗）的平均值與一或多個替代體驗中相同量度的平均值。

[!DNL Target] 建議使用 [韋爾奇的T型](https://en.wikipedia.org/wiki/Welch%27s_t-test)，因為這些假設需要的假設比z檢定之類的替代項目少，而且是在控制體驗和替代體驗之間進行成對（定量）業務量度比較的適當統計測試。

### 更詳細

執行線上A/B測試時，每個使用者/訪客會隨機指派給單一變體。 隨後，我們會測量興趣的業務量度（例如轉換、訂購、收入等） 適用於每個變體中的訪客。 我們使用的統計測試接著會測試平均業務量度（例如轉換率、每位使用者訂單、每位使用者收入等）的假設 等於控制項和給定的替代變體。

雖然業務量度本身可能會根據某些任意分佈而分佈，但此量度（在每個變體內）的平均分佈應會透過 [中心極限定理](https://en.wikipedia.org/wiki/Central_limit_theorem). 請注意，雖然無法保證此取樣分佈的平均值會以多快的速度收斂至正常，但一般會根據線上測試中的訪客規模來達成此條件。

根據平均值的這種正常性，可以顯示要使用的測試統計值以遵循t分佈，因為它是常態分佈值（業務量度的手段的差）與基於資料的估計的縮放項的比率（裝置差的標準誤差）。 此 **t檢定** 則是適當的假設測試，假設測試統計值遵循t分佈。

### 未使用其他測試的原因

A **z檢定** 技術上不適當，因為在一般A/B測試情境中，測試統計資料的分母並非衍生自已知的變數，而是必須從資料中估計。 然而，對於足夠大的樣本尺寸，z檢定和t檢定是相同的。

**卡方檢驗** 不會使用，因為這些變數適合用於判斷兩種變體之間是否存在定性關係（亦即在變體之間沒有差異的null假設）。 T測試更適合 _定量_ 比較量度。

此 **Mann-Whitney U測試** 是非參數測試，當平均業務量度（對於每個變數）的取樣分佈不正常時，此測試即適用。 但是，如前所述，考慮到線上測試所涉及的流量大小，中心極限定理通常適用，因此t檢測可以安全地應用。

更複雜的方法，例如 **ANOVA** 當測試有超過兩個體驗時（「A/Bn測試」），可套用（這會將t測試歸納為兩個以上的變體）。 然而，ANOVA回答了「所有變體是否都有相同的意義」的問題，而在典型的A/Bn測試中，我們更感興趣的是 _特定變體_ 最好。 在 [!DNL Target]因此，我們會套用一般t檢定來比較每個變體與控制，並使用Bonferroni校正來計算多個比較。