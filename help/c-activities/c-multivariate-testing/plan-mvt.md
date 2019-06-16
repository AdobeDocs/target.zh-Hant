---
description: Adobe Target中的多變數測試需要一些規劃，才能建立成功的測試。
keywords: 多變數測試;mvt;mvt 計劃;多變數測試計劃
seo-description: Adobe Target中的多變數測試需要一些規劃，才能建立成功的測試。
seo-title: 在Adobe Target中規劃多變數測試
solution: Target
title: 計劃多變數測試
uuid: f286d08a-e11d-4a39-8c62-3eba99885299
translation-type: tm+mt
source-git-commit: c6085fae6428cb837eed6eadd778140687348817

---


# 計劃多變數測試{#plan-a-multivariate-test}

[!UICONTROL 多變數測試] (MVT)需要 [!DNL Adobe Target] 一些規劃，才能建立成功測試。

MVT需要足夠的流量來產生有用的結果。設定測試之前，請注意您平常取得的流量，包括曝光次數和轉換次數。參考此資訊可儘量避免所設計的測試超過網站流量的需求。

建議您將元素與元素之間分開測試。(例如，請勿在相同測試中測試版面與內容。)

檢查您要測試的頁面的 HTML 程式碼。確定網站上的 HTML 元素沒有重複的 DOM ID。重復ID可能會導致同一部分內容傳送至多個位置。

規劃測試網頁上很可能產生重大結果的元素。例如，橫幅或英雄影像可能會導致轉換多於頁尾的變更。將較無影響力的元素納入測試中，只會造成測試頁面上更重要的元素需要更多流量和時間。

最後，在建立測試之前，請建立您想測試的內容。瞭解每一個選件的內容差異，並建立您打算用在測試中的任何影像、文字和 HTML 選件。

## 訓練影片: 建立多變數測試 (9:25)

此影片示範如何使用 Target 三步驟引導式工作流程來規劃和建立多變數測試。

* 定義和設計多變數測試
* 建立多變數測試

>[!VIDEO](https://video.tv.adobe.com/v/17395?captions=chi_hant)