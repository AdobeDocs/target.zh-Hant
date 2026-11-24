---
keywords: 建議;常見問題;faq
description: 常見問題集(FAQ)及其關於[!DNL Target Recommendations]設計的回答。
title: 設計常見問題集
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
TQID: 'https://experienceleague.adobe.com/xRu0XEnc8wX8PZngba7CO67mFdja7HALL-1OSnhAmuY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 10%
---
# 設計常見問題集 {#design-faq}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;尋找有關[!DNL Adobe Target]常見問題的解答[!DNL Recommendations]設計。

>[!ENDSHADEBOX]

+++ 建議專案的價格如何在小數點的右邊同時顯示兩位數？

根據預設，設計中所傳回的數值（例如`entity.value`）不會在小數點後顯示任何尾隨零。 例如，如果專案成本為$35.00，`entity.value`等於35且只會在頁面上顯示35，而不是$35.00。

有兩個選項可解決此問題：

* Velocity指令碼或JavaScript可套用格式至傳回的值。

* 專案的價格可以傳遞至兩個個別的實體屬性。 第一個 (`entity.value`) 可用於數值比較 (例如價格比較規則)。 第二個應該是自訂屬性（例如`entity.displayValue`），可將實體的值儲存為字串，以正確地顯示。

  例如，

  `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

+++

+++ 使用$entity1.categoryId時，為何設計中未顯示類別？

類別ID無法在設計中顯示。 可以儲存多個類別，因此系統不知道要顯示哪個類別。

+++

+++ 如何變更設計以立即更新？

更改目前使用中的設計需要一段時間才會更新。 若要立即變更設計，請建立新設計、在活動中選取該設計，然後儲存建議。

+++

+++ 如何在設計中顯示關鍵資訊，例如關鍵產品的類別？

`$key`引數會擷取重要產品的大部分資訊，以顯示在設計內。 例如，若要顯示重要產品的縮圖，請使用`$key.thumbnailURL`。

+++

+++ 使用什麼 Velocity 版本?

1.7版，不需新增其他工具或程式庫。 提供基本 Velocity 功能。

+++

+++ 如何以空白取代現有的實體值，例如當必須在促銷活動結束時清除專案的entity.message時？

傳送JavaScript不斷行空格似乎有助於執行此操作。 開發人員傳送`\u00A0`作為值，例如`entity.message=\u00A0`。 如果沒有值，也可以考慮使用該值作為預設值，而不是null。

+++

+++ 設定檔指令碼是否可用於[!DNL Recommendations]設計？

是. 若要在[!DNL Recommendations]設計中使用設定檔指令碼，請將名稱包裝在`\${...}`中。 例如，如果設定檔指令碼名為`user.basket`，請在設計中將其參照為`\${user.basket}`。 反斜線表示Velocity不會轉譯設定檔指令碼，因此在Velocity範本中無法對設定檔指令碼執行任何作業。 值會直接列印在頁面上。

+++
