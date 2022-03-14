---
keywords: 對象;對象規則;建立對象;建立對象
description: 瞭解如何建立自定義的受眾並將其保存到 [!DNL Adobe Target] [!UICONTROL 觀眾] 用於活動的庫。
title: 如何構建受眾？
feature: Audiences
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 61%

---

# 在 [!DNL Target] 中建立對象 

您可以建立自定義的受眾並將其保存到 [!DNL Adobe Target] [!UICONTROL 觀眾] 用於活動的庫。 您還可以複製現有受眾，然後可以編輯這些受眾以建立類似的受眾並合併多個受眾。

## 對象概覽

對象是由可決定要從 [!DNL Target] 活動中包括或排除的規則定義。對象定義可以包括多個規則，並且每個規則可以包括多個參數。複雜的對象定義會使用布林值運算子 AND 和 OR 結合規則和參數，以讓您對哪些網站訪客會計入活動加入者能進行詳細控制。

將規則或參數與AND組合時，任何潛在受眾成員必須滿足 *全部* 定義的要作為參與者包括的條件。 例如，如果您定義作業系統規則 AND 瀏覽器規則，則只會在活動中包括同時使用已定義作業系統&#x200B;*與*&#x200B;已定義瀏覽器的訪客。

使用 OR 結合規則或參數時，任何潛在的對象成員只需符合任何單一定義的條件，即可包括為加入者。例如，如果您定義使用 OR 連接的多個行動規則，則將在活動中包括符合&#x200B;*任何*&#x200B;所定義條件的訪客。

您可以將這兩個布林運算子混合來建立複雜的規則; 不過，相同規則層級的運算子必須相符。使用者介面會自動套用至正確的運算子。

例如，下列規則會鎖定在 Windows 電腦上使用 Chrome *或* Firefox 的訪客:

![建立受眾](assets/audience_create.png)

>[!NOTE]
>
>請小心，避免建立規則來排除所有可能的對象成員。例如，某人無法同時使用 Chrome *與* Firefox 來造訪頁面。

## 建立對象

1. 按一下上方功能表列中的&#x200B;**[!UICONTROL 「對象」]**。

   ![](assets/audiences_list.png)

1. 從 [!UICONTROL 觀眾] 清單，按一下 **[!UICONTROL 建立受眾]**。

   或

   複製現有受眾，從 [!UICONTROL 觀眾] 清單，按一下 **[!UICONTROL 更多操作]** 表徵圖（省略號表徵圖），然後按一下 **[!UICONTROL 重複]**。 然後您可以編輯對象以建立類似的對象。

1. 鍵入唯一、描述性的受眾名稱和可選說明。
1. 從 **[!UICONTROL 屬性]** 對話框。

   ![拖放屬性](assets/drag-attribute.png)

   每個規則類型都有其專屬的參數。請參閱[對象的類別](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D)，以取得關於設定每個類型的對象規則的詳細資訊。

1. 定義規則參數。

   例如，以下受眾使用Macintosh作業系統針對來自猶他州的訪問者。

   ![猶他州/Macintosh受眾](assets/adience-builder.png)

1. （條件）繼續添加和定義所需屬性。

   要建立另一個容器，請按一下 **[!UICONTROL 添加容器]** 或只是將另一個屬性拖到「受眾生成器」窗格中。 然後，可使用下拉清單調整運算子（AND或OR）。

1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

   新建立的對象會在處理延遲幾秒之後出現在清單中。如果對象未立即在清單中顯示，請嘗試搜尋對象或重新整理清單。

## 訓練影片: 建立對象 ![概述徽章](/help/main/assets/overview.png)

此影片包括關於建立對象的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
