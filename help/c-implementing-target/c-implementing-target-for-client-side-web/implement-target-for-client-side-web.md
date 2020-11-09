---
description: 有關為用戶端 Web 實作 Adobe Target 的資訊。
title: 為用戶端 Web 實作 Adobe Target
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 100%

---


# 概覽: 為用戶端 Web 實作 Target

在 [!DNL Adobe Target] 的用戶端實作中，[!DNL Target] 會將與活動相關聯的體驗直接提供給用戶端瀏覽器。瀏覽器會決定要顯示哪個體驗，然後顯示其內容。在用戶端實作中，您可以使用 WYSIWYG 編輯器、[可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 或非視覺化介面 ([表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md))，建立您的活動和個人化體驗。

若要實作 [!DNL Adobe Target] 用戶端，您必須使用 [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) 或 mbox.js 資料庫。

>[!NOTE]
>
>將不再開發 mbox.js 資料庫。所有客戶皆應[部署 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) 或[從 mbox.js 移轉至 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)。
