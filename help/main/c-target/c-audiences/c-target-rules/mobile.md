---
keywords: 鎖定目標;行動裝置;目標行動裝置;deviceatlas;iphone;iphone 型號;device atlas;displaywidth;顯示寬度;裝置類型;displayheight;手機;平板電腦;裝置型號
description: 了解如何在 [!DNL Adobe Target] 定位行動裝置。
title: 我可以根據行動選項定位訪客嗎？
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: 1383088bb2f6be0432e6f140400d8723048c8530
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 38%

---

# 行動

在中建立對象 [!DNL Adobe Target] 依據行動裝置、裝置類型、裝置廠商、畫面維度等參數來鎖定行動裝置。

例如，對於使用手機造訪您的頁面的使用者，您可能想要顯示與使用電腦造訪不同的內容。 在此情況下，您可以選取 [!UICONTROL 行動] 對象，然後選取 **[!UICONTROL 是行動電話]** 選項。 然後，您可以新增任何對您而言重要的特定詳細資料，例如電話類型、螢幕大小（以像素為單位）等。

行動定位是由 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 所提供，這是一項 DotMobi 服務。DeviceAtlas 是全面性的行動裝置資料庫，其中包含從眾多來源 (包括製造商及網路營運商) 彙整而成的資料。這些資料會經過確認、交叉參考及驗證，以建立準確的大型行動裝置資料庫。

裝置偵測是經由分析 User-Agent 字串來完成。某些裝置製造商 (例如 Apple) 在 UA 中不提供足夠資訊，所以會停用此功能。

例如，Apple 裝置不會在 UA 中透露裝置型號專屬 Token。結果是無法使用簡單的關鍵字方法偵測iPhone模型(例如iPhone 12 Pro、iPhone 12、iPhone 11 Pro Max等)。

為了解決這個問題， [!DNL Target] 收集其他資料，以使用下列參數精確偵測iPhone和其他Apple裝置：

| 參數 | 類型 | 說明 |
|--- |--- |--- |
| devicePixelRatio | 字串 | 瀏覽器上實體畫素和裝置獨立畫素 (DIP) 之間的比例。例如「1.5」或「2」 |
| screenOrientation | 字串 | 裝置和瀏覽器的 JavaScript 引擎支援裝置方向切換。可為橫向或縱向。 |
| webGLRenderer | 字串 | 顯示卡驅動程式的瀏覽器轉譯器。 |

>[!NOTE]
>
>使用Mobile SDK的客戶不需執行任何動作即可套用此功能。 使用at.js的客戶必須 [升級至at.js 1.5.0版](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} (or later){target=_blank}.

您可以選擇多個行動裝置屬性。使用OR運算子聯結多個選取項目。

使用自訂整合 (不使用 at.js 或 Mobile SDK) 的客戶可自行收集這些參數，然後以 mbox 參數傳遞。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名並新增選用說明。
1. 拖放 **[!UICONTROL 行動]** 進入audience builder窗格。
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
   >您可以依行動裝置電信業者來鎖定目標，請使用[地理設定](/help/main/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)。

1. （選用）為對象設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

下圖顯示對象鎖定目標訪客使用Google所製造的行動裝置。

![Target 行動裝置](assets/target_mobile.png)

## 考量事項

定位行動裝置時，請考量下列資訊：

### 執行iOS 12.2或更新版本的鎖定目標裝置

由於iOS 12.2中推出的新變更，請使用定義的規則建立對象 [!UICONTROL 裝置行銷名稱] 和 [!UICONTROL 裝置型號] 指定iPhone模型時，會受到影響。 [!DNL Target] 無法再將目標鎖定在安裝了iOS 12.2（或更新版本）的iPhone使用者。 不過，如果這些使用者沒有iOS 12.2（或更新版本），則iPhone模型鎖定目標會繼續正常運作。

iOS 12.2（或更新版本）更新不會影響下列機型的識別，因為這些機型不支援升級至iOS 12.2:iPhone、iPhone 3G、iPhone 3GS、iPhone 4、iPhone 4s、iPhone 5、iPhone 5c、iPad、iPad 2、iPad/ Retina顯示器、iPad Retina（第4代）、iPod Touch 4和iPod Touch 5。

### 執行Safari 14.0.2（或更新版本）的鎖定裝置

使用行動規則來鎖定在macOS上執行Safari 14.0.2版（或更新版本）的裝置時，由於Apple的使用者代理和DeviceAtlas的已知問題， [!DNL Target] 在Mac和iPad裝置上不正確識別Safari。 這個問題將在今後解決。

## 訓練影片: 建立對象

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
