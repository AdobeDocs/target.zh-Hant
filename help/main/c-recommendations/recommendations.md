---
keywords: 推薦;推薦條件;推薦演算法;推薦活動;條件;推薦鎖定目標;recs
description: 了解 Adobe [!DNL Target] 中的推薦活動，這些活動會根據先前的使用者活動或其他演算法，自動顯示可能吸引客戶的內容。
title: 什麼是  [!DNL Target] 推薦？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 97%

---

# 推薦

[!DNL Adobe Target Recommendations] 活動可依據先前的使用者活動、偏好設定或其他條件，自動顯示可能使訪客感興趣的產品、服務或內容。[!DNL Target Recommendations] 可協助引導訪客至他們可能不知道的相關項目。[!DNL Recommendations] 讓您在適當的時間地點提供訪客相關內容。

>[!NOTE]
>
>[!DNL Recommendations] 活動是 [Target Premium 解決方案](/help/main/c-intro/intro.md#premium)內建的功能。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。
>
>若您目前採用 [!DNL Recommendations Classic]，請參閱 [Target Premium 中的推薦經典版與推薦活動的比較](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5)，以瞭解這兩個解決方案的相關資訊。

[!DNL Recommendations] 可協助您在通路、應用程式、頁面、電子郵件訊息和其他傳送選項上，最佳化和自訂即時建議，以促進參與和轉換，同時降低管理工作量。

[!DNL Recommendations] 可助您:

* 建立更準確的條件 (規則) 將建議自動化
* 使用少許 JavaScript 程式片段以自動顯示建議
* 測試和最佳化建議條件及用於顯示建議的設計
* 報告建議活動的結果

下圖顯示網頁上的建議:

![velocity_example image](assets/velocity_example.png)

推薦會根據訪客在網站上的活動，決定對訪客建議產品的方式。例如:

| 所需的動作 | 建議 |
|--- |--- |
| 鼓勵購買背包的使用者考慮購買登山鞋和登山杖。 | 使用「購買了此項目、也購買了其他項目的使用者」條件，建立顯示經常一起購買項目的建議。 |
| 根據訪客觀賞的影片來建議類似的媒體內容，以吸引訪客在您的媒體網站上停留更久。 | 使用「瀏覽過此項目、也瀏覽了其他項目的使用者」條件，建立建議其他影片的建議。 |
| 建議檢視了關於在您的銀行存款計劃的客戶也閱讀關於 IRA 帳戶的資訊。 | 使用「瀏覽過此項目、但購買了其他項目的使用者」條件，顯示人員在檢視一個產品而沒有顯示建議中第一個產品之後購買的其他產品。 |

如需這些事項和其他 [!DNL Recommendations] 條件的相關資訊，請參閱[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)。

## 詞彙

開始使用 [!DNL Recommendations] 之前，請務必熟悉本節中使用的部分詞語。如果您尚未完全瞭解這些詞語，請放心，當您設定 [!DNL Recommendations] 活動時，您會更熟悉這些詞語。

| 術語 | 定義 |
| --- | --- |
| 活動 | [!DNL Target] 中的活動可讓您將內容個人化給特定客群，並測試頁面設計。[!DNL Recommendations] 只是 [!DNL Target] 中的眾多活動類型之一。如需詳細資訊，請參閱「[目標活動類型](/help/main/c-activities/target-activities-guide.md)」。 |
| 實體 | 實體會參考您要建議的項目。實體可以是產品、內容 (文章、幻燈片、影像、電影和電視節目)、工作清單、餐廳等。如需詳細資訊，請參閱「[實體](/help/main/c-recommendations/c-products/products.md)」。 |
| 摘要 | 動態消息用於將實體導入到 [!DNL Recommendations]。實體可以使用 CSV 檔案、Google Product Search 摘要格式和 Adobe Analytics 產品分類來進行傳送。如需詳細資訊，請參閱[摘要](/help/main/c-recommendations/c-products/feeds.md)。 |
| 目錄 | 目錄是指您的整個產品集 (實體)。您的型錄可包含許多系列——以邏輯區間組織產品的方式。 |
| 集合 | 系列是指一組類似或相關的項目，例如單一產品類別。不過，只要符合業務的需要，您可以將任何項目分組到類別中，例如特定價格範圍或顏色的產品，或可能在特定地理區受到歡迎的項目。如需詳細資訊，請參閱「[集合](/help/main/c-recommendations/c-products/collections.md)」。 |
| 條件 | 條件即為一種規則，用來根據預先決定的一組訪客行為決定要建議的產品。<br>條件範例包括： <ul><li>購買了此項目、也購買了其他項目的使用者</li><li>檢視過此項目、也檢視了其他項目的使用者</li><li>具有類似屬性的項目</li><li>上次購買的項目</li><li>最喜愛的類別</li></ul>  如需詳細資訊，請參閱[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)。 |
| 設計 | 設計會定義 [!DNL Recommendations] 活動中推薦的外觀，例如列、欄、表格或格線。本文最上方的插圖顯 示4 x 1設計。如需詳細資訊，請參閱[建立設計](/help/main/c-recommendations/c-design-overview/create-design.md)。 |
| 位置 | 位置是指您執行活動以進行個人化和最佳化目的之網頁、行動應用程式或電子郵件上的特定內容區域。 |
| 客群 | 客群是類似活動進入者的群組，他們會看到目標活動。客群是具有相同特性的一組人員，例如新訪客、回頭客或來自中西部的回頭客。客群功能可讓您將不同的內容和體驗鎖定在特定客群，利用在正確時間向正確的人員顯示正確的訊息來最佳化您的數位行銷。如需詳細資訊，請參閱[客群](/help/main/c-target/target.md)。 |
| 推薦作為產品建議 | 可讓您在 A/B 測試 (包括自動分配和自動定位) 和體驗定位 (XT) 活動中加入推薦的功能。如需詳細資訊，請參閱 [推薦作為產品建議](/help/main/c-recommendations/recommendations-as-an-offer.md)。 |

## 培訓影片：活動類型![Overview badge](/help/main/assets/overview.png)

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。從7[!DNL Recommendations]開始討論:20。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Adobe Target基礎網路研討會： Recommendations簡介![教學課程徽章](/help/main/assets/tutorial.png) {#intro-to-recs}

*推薦簡介*&#x200B;網路研討會包含有關如何運用 [!DNL Adobe Target Recommendations] 的值的深入探討。瞭解此 [!DNL Target] 活動如何根據先前的造訪最佳化即時建議，藉此自動顯示可能使您的客戶感興趣的產品或內容。此外，深入探討 [!DNL Target] UI，瞭解如何建置 [!DNL Recommendations] 活動的逐步概觀。

[推薦簡介](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
