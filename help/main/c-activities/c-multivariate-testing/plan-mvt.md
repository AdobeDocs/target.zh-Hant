---
keywords: 多變數測試;mvt;mvt 計劃;多變數測試計劃
description: 瞭解如何在[!UICONTROL Multivariate Test]中規劃 [!DNL Adobe Target] ，以便建立成功的測試。
title: 如何計畫[!UICONTROL Multivariate Test]？
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 64%

---

# 計畫[!UICONTROL Multivariate Test]

[!UICONTROL Multivariate Tests]中的[!DNL Adobe Target] (MVT)活動需要一些規劃，才能建立成功的測試。

MVT需要足夠的流量，才能產生有用的結果。 設定測試之前，請注意您平常取得的流量，包括曝光次數和轉換次數。擁有此資訊有助於降低設計需求超過網站流量的測試的可能性。

元素彼此獨立。 例如，請勿在相同測試中測試版面配置與內容。

檢查您要測試之頁面的HTML程式碼。 確定網站上的 HTML 元素沒有重複的 DOM ID。重複 ID 會導致同一份內容傳遞至多個位置。

規劃測試網頁上很可能產生重大結果的元素。例如，相較頁尾中的變更，橫幅或主圖影像可能會導致更多轉換。將較無影響力的元素納入測試中，只會造成測試頁面上更重要的元素需要更多流量和時間。

最後，在建立測試之前，請建立您想測試的內容。瞭解每一個產品建議的內容差異，並建立您打算用在測試中的任何影像、文字和 HTML 產品建議。

## 訓練影片：建立多變數測試(9:25) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片示範如何使用[!DNL Target]三步驟引導式工作流程來規劃和建立多變數測試。

* 定義和設計多變數測試
* 建立多變數測試

>[!VIDEO](https://video.tv.adobe.com/v/17395)
