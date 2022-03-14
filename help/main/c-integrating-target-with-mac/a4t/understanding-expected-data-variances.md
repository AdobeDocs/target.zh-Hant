---
keywords: 資料差異;analytics;差異;差別;a4t;analytics for target;analytics 作為報表來源
description: 瞭解Adobe之間的預期資料差異 [!DNL Target] 和Analytics（當未使用Analytics時） [!DNL Target] (A4T)，完全消除了資料差異。
title: 分析與A4T之間的預期資料差異是什麼？
feature: Analytics for Target (A4T)
exl-id: 9e63f309-8ec1-4ed5-a1f9-6c3098a7b8f6
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 48%

---

# 預期資料Adobe [!DNL Target] 和Adobe Analytics在使用和不使用A4T時

有關&#x200B;*使用*&#x200B;和&#x200B;*不使用* Analytics 做為報表來源 (A4T) 時，[!DNL Target] 和 Adobe [!DNL Analytics] 之間預期資料差異的資訊。A4T 可大幅減少資料差異.

## 使用 A4T 時的預期資料差異 {#expected-using-a4t}

若使用 A4T，活動的 Analytics 與 Target 報表皆僅使用 Analytics 資料，因此 Target 活動報表中的解決方案之間沒有差異。但是，在某些情況下，客戶將目標資料與A4T整合範圍之外的分析資料進行比較，因此，會遇到以下描述的差異問題。

以下是幾種情況，您可以在其中體驗預期的資料差異：

* A4T 允許 Target 點擊 (頁面頂端) 發生的可能性，但不允許 Analytics 點擊 (頁面底部) 發生。例如，假設訪問者載入了頁面，但在觸發分析調用之前關閉瀏覽器。 在這些情況下，A4T從資料中排除目標命中。 在沒有實際分析調用的情況下允許目標點擊量（再次，頁首）計數為分析點擊量，會與分析中的資料集（訪問者通脹等）產生不一致。

   如果在「目標」中設定了重定向test以分割流量50/50(或25/25/25/25等)，則用戶行為可能不會平均分割。 如果您看到不均勻的剝離，這僅僅意味著一組用戶在登錄頁上執行分析調用失敗的次數超過其他組。 這種某個群組無法執行 Analytics 呼叫的情況導致了該使用者的 Target 點擊遭到排除，產生不平均的問題。

   Adobe希望在Adobe團隊為Adobe Experience Platform的A4T而努力時，在未來解決這個問題。 Adobe團隊正在確定如何處理頁面上不同時間發生的這些不同事件。

   >[!NOTE]
   >
   >目前存在一個已知問題，該問題導致搭配 A4T 使用重新導向的部分客戶看見較高的散亂點擊率百分比。請參閱[已知問題和已解決的問題](/help/main/r-release-notes/known-issues-resolved-issues.md#redirect)。

## *不使用* A4T 時的預期資料差異 {#expected-not-using-a4t}

即使是使用相似的資料集，有 15-20% 的差異也是正常的。算法不同的系統可能會導致更高的資料差異，高達 35-50%。有時，差異可能更大。

雖然實際的資料可能會大幅不同，但趨勢通常會是一致的。只要差異與趨勢保持一致，這些資料還是十分重要而且非常有用。如果差異與趨勢不一致，可能表示某個設定不正確。此時請連絡您的帳戶代表以取得協助。

[!DNL Analytics] 使用的系統是根據瀏覽次數與交易，但是 使用的是以訪客為主的度量。[!DNL Target]每當訪問者開啟頁面時，它就算是訪問 [!DNL Analytics]但 [!DNL Target] 在滿足活動中設定的條件之前，不計算訪問。

報告 [!DNL Target] 根據定義活動時選定的轉換框顯示效能。 但是，此轉換框資料不會發送到 [!DNL Analytics]，它具有由 [!DNL Analytics] 標籤實現。 如果您期望得到相同的資料(例如，如果零售商的訂單確認該頁同時包含轉換框和轉換框 [!DNL Analytics] 購買事件)，由於這些標籤的放置，資料可能不同。 總體而言，兩種產品報告的趨勢是相似的。

預期的資料差異可能是因為技術與業務差異所致。

### 技術差異的範例 {#section_C3B50ED2E2F9416FAC91437CF1A87369}

下列的技術差異可能造成資料差異:

* [!DNL Target] 訪客必須同意允許 Cookie 與 JavaScript
* 第一方和第三方 Cookie 的處理方式不同；因此，這些 Cookie 類型的資料不相符
* 頁面上標記的相關位置，以及因訪客在頁面尚未完全載入前離開此頁面所造成的「資料流失」
* 時區考量
* 可計算的裝置差異

### 業務差異的範例 {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

下列的業務差異可能造成資料差異:

* 訪客與瀏覽度量之間的差異
* 鎖定目標的活動不包括某些訪客
* 多頁上的單個框，每頁的訪問者數
* 活動優先順序可以包括某些訪問者，並排除頁面上的其他訪問者
* 已轉換一次的訪問者在重新進入活動時可以再次計數
* [!DNL Analytics] 會計算所有瀏覽和訪客的所有轉換次數，但 [!DNL Target] 僅會計算活動中包含之瀏覽和訪客的轉換次數。
