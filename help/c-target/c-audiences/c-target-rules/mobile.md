---
keywords: 鎖定目標;行動裝置;目標行動裝置;deviceatlas;iphone;iphone 型號;device atlas;displaywidth;顯示寬度;裝置類型;displayheight;手機;平板電腦;裝置型號
description: 了解如何在 [!DNL Adobe Target] 中建立受眾，以根據行動裝置、裝置類型、裝置廠商、畫面維度（依像素）等參數來鎖定行動裝置。
title: 我可以根據行動選項定位訪客嗎？
feature: 對象
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 43%

---

# 行動

在[!DNL Adobe Target]中建立受眾，根據行動裝置、裝置類型、裝置廠商、畫面維度等參數來鎖定行動裝置。

例如，對於使用手機造訪您的頁面的使用者，您可能想要顯示與使用電腦造訪不同的內容。 在此情況下，您可以選取[!UICONTROL Mobile]對象，然後選取&#x200B;**[!UICONTROL Is Mobile Phone]**&#x200B;選項。 然後，您可以新增任何對您而言重要的特定詳細資料，例如電話類型、螢幕大小（以像素為單位）等。

行動定位是由 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 所提供，這是一項 DotMobi 服務。DeviceAtlas 是全面性的行動裝置資料庫，其中包含從眾多來源 (包括製造商及網路營運商) 彙整而成的資料。這些資料會經過確認、交叉參考及驗證，以建立準確的大型行動裝置資料庫。

裝置偵測是經由分析 User-Agent 字串來完成。某些裝置製造商 (例如 Apple) 在 UA 中不提供足夠資訊，所以會停用此功能。

例如，Apple 裝置不會在 UA 中透露裝置型號專屬 Token。結果是無法使用簡單的關鍵字方法偵測iPhone型號（例如iPhone 12 Pro、iPhone 12、iPhone 11 Pro Max等）。

為解決此問題，[!DNL Target]會使用下列參數收集其他資料，以精確偵測iPhone和其他Apple裝置：

| 參數 | 類型 | 說明 |
|--- |--- |--- |
| devicePixelRatio | 字串 | 瀏覽器上實體畫素和裝置獨立畫素 (DIP) 之間的比例。例如「1.5」或「2」 |
| screenOrientation | 字串 | 裝置和瀏覽器的 JavaScript 引擎支援裝置方向切換。可為橫向或縱向。 |
| webGLRenderer | 字串 | 顯示卡驅動程式的瀏覽器轉譯器。 |

>[!NOTE]
>
>使用Mobile SDK的客戶不需執行任何動作即可套用此功能。 使用 at.js 的客戶必須[升級至 at.js 版本 1.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) (或更新版本)。

您可以選擇多個行動裝置屬性。使用OR運算子聯結多個選取項目。

使用自訂整合 (不使用 at.js 或 Mobile SDK) 的客戶可自行收集這些參數，然後以 mbox 參數傳遞。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名並新增選用說明。
1. 將&#x200B;**[!UICONTROL Mobile]**&#x200B;拖放至對象產生器窗格。
1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

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
   >由於iOS 12.2中推出的新變更，使用由[!UICONTROL 裝置行銷名稱]和[!UICONTROL 裝置型號]定義的規則來建立對象時，會受到影響。 [!DNL Target] 無法再將目標定位為已安裝iOS 12.2（或更新版本）的iPhone使用者。不過，如果這些使用者沒有iOS 12.2（或更新版本）,iPhone型號鎖定目標功能將可繼續正常運作。
   >
   >iOS 12.2（或更新版本）更新不會影響下列機型的識別，因為這些機型不支援升級至iOS 12.2:iPhone、iPhone 3G、iPhone 3GS、iPhone 4、iPhone 4s、iPhone 5、iPhone 5c、iPad、iPad 2、iPad / Retina顯示器、iPad Retina（第4代）、iPod Touch 4和iPod Touch 5。

   >[!NOTE]
   >
   >您可以依行動裝置電信業者來鎖定目標，請使用[地理設定](/help/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)。

1. （選用）為對象設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

下圖顯示對象鎖定目標訪客使用由Google製造的行動裝置。

![Target 行動裝置](assets/target_mobile.png)

## 訓練影片: 建立對象

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
