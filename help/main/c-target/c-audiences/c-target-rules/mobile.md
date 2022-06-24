---
keywords: 鎖定目標;行動裝置;目標行動裝置;deviceatlas;iphone;iphone 型號;device atlas;displaywidth;顯示寬度;裝置類型;displayheight;手機;平板電腦;裝置型號
description: 瞭解如何在 [!DNL Adobe Target] 目標移動設備。
title: 我是否可以基於移動選項來瞄準訪問者？
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 38%

---

# 行動

在 [!DNL Adobe Target] 根據諸如移動設備、設備類型、設備供應商、螢幕尺寸等參數來目標移動設備。

例如，您可能希望向使用電話訪問您頁面的用戶顯示的內容，而不是向他們使用電腦訪問時顯示的內容。 在這種情況下，您可以 [!UICONTROL 移動] 觀眾，然後選擇 **[!UICONTROL 是手機]** 的雙曲餘切值。 然後，您可以添加對您來說重要的任何特定詳細資訊，如電話類型、螢幕大小（以像素為單位）等。

行動定位是由 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 所提供，這是一項 DotMobi 服務。DeviceAtlas 是全面性的行動裝置資料庫，其中包含從眾多來源 (包括製造商及網路營運商) 彙整而成的資料。這些資料會經過確認、交叉參考及驗證，以建立準確的大型行動裝置資料庫。

裝置偵測是經由分析 User-Agent 字串來完成。某些裝置製造商 (例如 Apple) 在 UA 中不提供足夠資訊，所以會停用此功能。

例如，Apple 裝置不會在 UA 中透露裝置型號專屬 Token。結果是，不可能使用簡單的基於關鍵字的方法來檢測iPhone模型(如iPhone12 Pro、iPhone12、iPhone11 Pro Max等)。

為瞭解決這個問題， [!DNL Target] 收集其他資料，以便使用以下參數準確檢測iPhone和Apple的其他設備：

| 參數 | 類型 | 說明 |
|--- |--- |--- |
| devicePixelRatio | 字串 | 瀏覽器上實體畫素和裝置獨立畫素 (DIP) 之間的比例。例如，&quot;1.5&quot;或&quot;2&quot; |
| screenOrientation | 字串 | 裝置和瀏覽器的 JavaScript 引擎支援裝置方向切換。可為橫向或縱向。 |
| webGLRenderer | 字串 | 顯示卡驅動程式的瀏覽器轉譯器。 |

>[!NOTE]
>
>使用移動SDK的客戶無需執行任何操作即可應用此功能。 使用at.js的客戶必須 [升級到at.js 1.5.0版](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}（或更高版本）{target=_blank}。

您可以選擇多個行動裝置屬性。多個選擇與OR運算子聯接。

使用自訂整合 (不使用 at.js 或 Mobile SDK) 的客戶可自行收集這些參數，然後以 mbox 參數傳遞。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 命名訪問群體並添加可選說明。
1. 拖放 **[!UICONTROL 移動]** 對話框。
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

1. （可選）為受眾設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

下圖顯示的受眾是使用Google製造的移動設備的訪問者。

![Target 行動裝置](assets/target_mobile.png)

## 考量事項

當瞄準移動設備時，請考慮以下資訊：

### 瞄準運行iOS12.2或更高版本的設備

由於iOS12.2中引入的新更改，建立了具有以下定義的規則的受眾 [!UICONTROL 設備營銷名稱] 和 [!UICONTROL 設備型號] 指定iPhone模型受影響。 [!DNL Target] 不能再瞄準安裝了iOS12.2（或更高版本）的iPhone的用戶。 但是，如果這些用戶沒有iOS12.2（或更高版本），則iPhone模式的目標仍然正確。

iOS12.2（或更高版本）更新不影響以下型號的標識，因為這些型號不支援升級到iOS12.2:iPhone、iPhone3G、iPhone3GS、iPhone4、iPhone4s、iPhone5、iPhone5c、iPad、iPad2、iPad/Retina顯示屏、iPadRetina（第4代）、iPod Touch 4和iPod Touch 5。

### 針對運行Safari 14.0.2（或更高版本）的設備

當將移動規則用於在macOS運行Safari 14.0.2版（或更高版本）的目標設備時，由於涉及Apple用戶代理和DeviceAtlas的已知問題， [!DNL Target] 在Mac和iPad設備上錯誤地標識了Safari。 這個問題將在今後解決。

## 訓練影片: 建立對象

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
