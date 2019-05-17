---
description: 關於 Recommendations 設計常見問題集 (FAQ) 的清單。
keywords: 建議;常見問題;faq
seo-description: 關於 Recommendations 設計常見問題集 (FAQ) 的清單。
seo-title: 設計常見問題集
solution: Target
title: 設計常見問題集
title-outputclass: premium
topic: Premium
uuid: ac222ade-ddd9-4b32-a16f-4d83b8766384
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) 設計常見問題集{#design-faq}

關於 Recommendations 設計常見問題集 (FAQ) 的清單。

## 設計中為何沒有顯示類別? 我使用 $entity1.categoryId。{#section_073309B8051049C7953D396A93EA0713}

設計中無法顯示類別 ID。因為可能會儲存多個類別，系統無法決定要顯示的類別。

## 如何變更設計才能立即更新?  {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

更改目前使用中的設計需要一段時間才會更新。若要立即變更設計，請建立新設計，在行銷活動中加以選取，再儲存建議。

## 如何擷取重要資訊以顯示在設計中? 範例: 如果想要顯示重要產品的類別，如何在 Velocity 設計中編寫該值? {#section_F08043B14BA24BC8815FEF25F4F84C39}

`$key. *`value`*` 參數會擷取重要產品的大部分資訊以顯示在設計內。範例: 如果要顯示重要產品的縮圖，請使用 `$key.thumbnailURL`。

## 使用什麼 Velocity 版本? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

1.7 版，不含其他工具或程式庫。提供基本 Velocity 功能。

## 如何將現存的實體值改為空白? 例如，促銷活動結束時需要清空項目的 entity.message。{#section_B88F2C2925DC4508974B2F8B13F961CB}

傳送 JavaScript 不斷行空格似乎有助於執行此操作。由開發人員傳入 `\u00A0` 當作值。範例: `entity.message=\u00A0`。您可以考慮沒有值時以此為預設值，而非使用 null。

## 我可以在「建議」設計中使用設定檔指令碼嗎? {#section_6BD55203984A4D80A0C6F241AD7806DF}

是. 不過，在設定檔指令碼名稱中，您必須在 $ 前面加上反斜線 (\)。
