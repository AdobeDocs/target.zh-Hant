---
keywords: 建議;常見問題;faq
description: 查看常見問題(FAQ)清單及其有關Adobe的回答 [!DNL Target] Recommendations設計。
title: 在何處可以回答設計問題 [!DNL Target] Recommendations?
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 70%

---

# ![PREMIUM](/help/main/assets/premium.png) 設計常見問題集

常見問題清單，關於 [!DNL Adobe Target] [!DNL Recommendations] 設計。

## 我的建議項目價格未在小數點右方顯示兩個值。我該如何顯示這些值?

根據預設，設計範本中所傳回的數值 (例如 `entity.value`) 不會在小數點後顯示任何尾隨零。例如，如果項目為 $35.00 美元，`entity.value` 等於 35 且只會在頁面上顯示 35，而不是 $35.00。

有兩個選項可解決此問題：

* 您可以使用 Velocity 指令碼或 JavaScript，將格式設定套用到傳回的值。

* 您可以將項目價格傳送到兩個個別的實體屬性。第一個 (`entity.value`) 可用於數值比較 (例如價格比較規則)。第二個應為自訂屬性 (例如 `entity.displayValue`)，可將實體的值儲存為字串，以正確地顯示。

   例如，

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## 設計中為何沒有顯示類別? 我在用 `$entity1.categoryId`。 {#section_073309B8051049C7953D396A93EA0713}

設計中無法顯示類別 ID。因為可能會儲存多個類別，系統無法決定要顯示的類別。

## 如何變更設計才能立即更新?    {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

更改目前使用中的設計需要一段時間才會更新。要立即更改設計，請建立新設計，在活動中選擇它，然後保存建議。

## 如何擷取重要資訊以顯示在設計中? 範例: 如果想要顯示重要產品的類別，如何在 Velocity 設計中編寫該值? {#section_F08043B14BA24BC8815FEF25F4F84C39}

`$key. *`value`*` 參數會擷取重要產品的大部分資訊以顯示在設計內。範例: 如果要顯示重要產品的縮圖，請使用 `$key.thumbnailURL`。

## 使用什麼 Velocity 版本? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

1.7 版，不含其他工具或程式庫。提供基本 Velocity 功能。

## 如何將現存的實體值改為空白? 例如，促銷活動結束時需要清空項目的 entity.message。 {#section_B88F2C2925DC4508974B2F8B13F961CB}

在JavaScript中發送不中斷的空間似乎可以做到這一點。 由開發人員傳入 `\u00A0` 當作值。範例: `entity.message=\u00A0`。您可以考慮沒有值時以此為預設值，而非使用 null。

## 我可以在 [!DNL Recommendations] 設計中使用設定檔指令碼嗎？ {#section_6BD55203984A4D80A0C6F241AD7806DF}

是.在 [!DNL Recommendations] 設計，將名稱包裝在 `\${...}`。 例如，如果您的配置檔案指令碼被命名 `user.basket`，請參閱 `\${user.basket}` 在設計中。 請注意，反斜線表示輪廓指令碼不由Velocity呈現。 因此，您不能對Velocity模板中的配置檔案指令碼執行任何操作。 值將直接打印在頁面上。
