---
description: 根據參數例如行動裝置、裝置類型、裝置廠商、畫面維度 (依像素) 及其他來鎖定行動裝置。
keywords: 鎖定目標;行動裝置;目標行動裝置;deviceatlas;iphone;iphone 型號;device atlas;displaywidth;顯示寬度;裝置類型;displayheight;手機;平板電腦;裝置型號
seo-description: 根據參數例如行動裝置、裝置類型、裝置廠商、畫面維度 (依像素) 及其他來鎖定行動裝置。
seo-title: 行動
solution: Target
title: 行動
topic: Standard
uuid: a731e8c0-e9c1-4971-95b7-882cefcabfc7
translation-type: tm+mt
source-git-commit: f59e96cd5afcae9d27d730aecead9eb360f04026

---


# 行動{#mobile}

根據參數例如行動裝置、裝置類型、裝置廠商、畫面維度 (依像素) 及其他來鎖定行動裝置。

例如，對於從手機進入您頁面的使用者和從電腦造訪的使用者，您想要分別顯示不同內容。在此情況下，您可以選取「行動裝置對象」，再選取**[!UICONTROL 「是手機」]選項，然後新增您認為重要的任何特定詳細資料，例如手機類型、螢幕大小 (畫素）等。**

行動定位是由 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 所提供，這是一項 DotMobi 服務。DeviceAtlas 是全面性的行動裝置資料庫，其中包含從眾多來源 (包括製造商及網路營運商) 彙整而成的資料。這些資料會經過確認、交叉參考及驗證，以建立準確的大型行動裝置資料庫。

裝置偵測是經由分析 User-Agent 字串來完成。某些裝置製造商 (例如 Apple) 在 UA 中不提供足夠資訊，所以會停用此功能。

例如，Apple 裝置不會在 UA 中透露裝置型號專屬 Token。結果就是不可能以簡單的關鍵字方法來偵測 iPhone 型號 (例如 iPhone 5S、iPhone SE、iPhone 6 等等)。

為解決此問題，Target 會使用下列參數來收集額外資訊，以精確偵測 iPhone 和其他 Apple 裝置:

| 參數 | 類型 | 說明 |
|--- |--- |--- |
| devicePixelRatio | 字串 | 瀏覽器上實體畫素和裝置獨立畫素 (DIP) 之間的比例。例如:「1.5」或「2」 |
| screenOrientation | 字串 | 裝置和瀏覽器的 JavaScript 引擎支援裝置方向切換。可為橫向或縱向。 |
| webGLRenderer | 字串 | 顯示卡驅動程式的瀏覽器轉譯器。 |

>[!NOTE]
>
>使用 Mobile SDK 的客戶不須採取任何動作，即可使用這項功能。使用 at.js 的客戶必須[升級至 at.js 版本 1.5.0](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) (或更新版本)。

您可以選擇多個行動裝置屬性。多個選擇是利用 OR 來結合。

使用自訂整合 (不使用 at.js 或 Mobile SDK) 的客戶可自行收集這些參數，然後以 mbox 參數傳遞。

1. 在 [!DNL Target] 介面中，按一下**[!UICONTROL 「對象]** &gt; **[!UICONTROL 建立對象」]**。
1. 為對象命名。
1. 按一下**[!UICONTROL 「新增規則]** &gt; **[!UICONTROL 行動裝置」]**。

   ![](assets/target_mobile.png)

1. 按一下**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

   * 裝置行銷名稱
   * 裝置型號
   * 裝置供應商
   * 是行動裝置
   * 是行動電話
   * 是平板電腦
   * 作業系統
   * 螢幕高度 (px)
   * 螢幕寬度 (px)
   >[!NOTE]
   >
   >您可以依行動裝置電信業者來鎖定目標，請使用[地理設定](../../../c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)。

1. (可選) 按一下**[!UICONTROL 「新增規則」]並設定對象的其他規則。**
1. 按一下**[!UICONTROL 「儲存」]**。

## 訓練影片: 建立對象

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
