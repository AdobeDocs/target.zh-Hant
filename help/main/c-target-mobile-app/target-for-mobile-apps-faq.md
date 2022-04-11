---
keywords: 移動應用；常見問題；常見問題；常見問題；目標移動應用
description: 查看有關Adobe的常見問題及其答案 [!DNL Target] 移動應用。
title: 關於哪些常見問題 [!DNL Target] 移動應用？
feature: Implement Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 3%

---

# 適用於行動應用程式的 Target 常見問答

常見問題清單 [!DNL Target] 移動應用。

## 是否應在中使用標籤 [!DNL Adobe Experience Platform] 部署SDK，或者我可以不使用 [!DNL Launch]?

SDK在 [Adobe Marketing Cloud吉特](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。 如果你不用 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)，您必須管理自己的設定檔案並在應用中管理它。

## 目前有哪些SDK可用？

Adobe Experience Platform移動軟體開發工具包目前支援iOS、Android和React。 有關詳細資訊，請參見 [Adobe Experience Cloud平台移動SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 從經緯度的驗證來看，基於位置的特徵的頻率是多少？

查看 [Adobe位置服務文檔](https://experienceleague.adobe.com/docs/places/using/home.html) 的子菜單。

## 我是否需要at.js才能使Adobe Experience Platform移動軟體開發工具包工作？

不，您不需要at.js來使用移動SDK。 at.js是 [!DNL Target] 網站的JavaScript庫。 Adobe Experience Platform移動軟體開發工具包適用於移動應用。

## 是 [!DNL Target] 移動Adobe [!DNL Target] 僅限高級產品SKU?

無.對於 [!DNL Adobe Target Standard] 客戶，您只能將我們的移動SDK用於A/BTest和體驗目標(XT)活動 [!DNL Target Standard] 移動應用載入項。 如果想在移動應用中使用Recommendations或人工智慧支援的功能，您需要 [Adobe Target高級](/help/main/c-intro/intro.md#premium) 許可證。

## Adobe Experience Manager()和 [!DNL Target] 移動活動？

它已列在我們的路線圖上，但還沒有時間表。 當前，您可以共用JSON [體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) 從AEM到Target，然後可能會在移動應用活動中使用它們。
