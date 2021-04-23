---
keywords: recommendations;recommendations活動；准則；算法；建議鍵；自訂鍵；行業垂直；零售；eccommerce;lead generation;b2b；金融服務；媒體；發佈
description: 瞭解如何在Adobe [!DNL Target] Recommendations中使用標準。 准則是根據一組預先確定的訪客行為來決定要推薦哪些內容的規則。
title: 如何在 [!DNL Target] Recommendations中使用標準？
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 52%

---

# ![PREMIUM](/help/assets/premium.png) 條件

[!DNL Adobe Target]中的准則是規則，可根據一組預先確定的訪客行為來決定要推薦哪些產品或內容。 條件可以基於人氣趨勢、訪客的目前和過去行為，或類似的產品和內容。您可以新增多個條件，將多個建議類型彼此測試。

以下各節將進一步說明准則索引鍵和可用於每個索引鍵的建議邏輯。 按一下連結，以取得詳細資訊。

## 垂直產業 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

建立准則時，您會根據建議活動的目標選取垂直的產業。

| 垂直產業 | 目標 |
|--- |--- |
| 零售/電子商務 | 轉換帶動購買 |
| 潛在客戶開發/B2B/金融服務 | 轉換但未購買 |
| 媒體/出版 | 參與 |

其他條件選項會根據您選取的產業垂直而變更。 您可以在&#x200B;**[!UICONTROL Recommendations>設定]**&#x200B;頁面上設定預設產業垂直，或為每個准則指定產業垂直。

## 建議索引鍵{#section_885B3BB1B43048A88A8926F6B76FC482}

您選取的建議金鑰決定條件類型。提供幾個條件類型，當您設定 [!DNL Recommendations] 活動時會以條件卡呈現。

![「標準」頁](/help/c-recommendations/c-algorithms/assets/criteria-page.png)

下表說明各種准則類型及其隨附的鍵。 按一下連結，以取得每個索引鍵的詳細資訊。

| 條件類型 | 密鑰 |
|--- |--- |
| 目前頁面活動 | 根據使用者在目前頁面上的行為來建議項目。例如，訪客在檢視特定文章時，可能想看同類型的其他文章。<ul><li>[目前項目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[目前類別](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| 自訂 | 根據自訂屬性來建議項目。<ul><li>[自訂屬性](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>根據自訂屬性來建議時，您必須選取自訂屬性，然後選取建議類型。 |
| 過去行為 | 根據訪客以往如何回應項目來建議項目。例如，購買特定牌品的人很可能購買相同牌品的其他項目。<ul><li>[上次購買的項目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[上次檢視的項目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[檢視次數最多的項目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[最喜愛的類別](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| 人氣 | 建議最熱門項目，例如相關類別中最熱門的影片，或您網站上最常被看到的產品。<ul><li>[人氣](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| [最近查看的項目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed) | 建議訪客最近檢視的項目，例如訪客上次瀏覽您網站時所檢視的項目，或目前趨勢最高的文章。 |

## 使用自訂建議金鑰{#custom-key}

您也可以根據自訂描述檔屬性的值來建議。

>[!NOTE]
>
>自訂描述檔參數可透過JavaScript、API或整合傳遞至Target。 如需自訂描述檔屬性的詳細資訊，請參閱[訪客描述檔](/help/c-target/c-visitor-profile/visitor-profile.md)。

例如，假設您想根據使用者最近新增至佇列的影片來顯示建議的影片。

1. 從[!UICONTROL 建議金鑰]下拉式清單中選取您的自訂描述檔屬性（例如[!UICONTROL 上次新增至Watchlist]）。

1. 選擇您的[!UICONTROL 建議邏輯]（例如，[!UICONTROL 檢視此項、檢視該]的人員）。

   ![「建立新標準」對話框](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

如果您的自訂描述檔屬性不直接符合單一實體ID，則必須向[!DNL Recommendations]說明您要如何符合實體。

例如，假設您想要顯示來自使用者最愛品牌的暢銷商品。

1. 從[!UICONTROL 建議金鑰]下拉式清單中選取您的自訂描述檔屬性（例如[!UICONTROL 最愛品牌]）。

1. 選擇您要使用此索引鍵的[!UICONTROL 建議邏輯]（例如[!UICONTROL 最暢銷商品]）。

   [!UICONTROL 依下列唯一值分組]選項隨即顯示。

1. 選取比對至您已選擇之索引鍵的實體屬性。在此例中，[!UICONTROL 最愛品牌]與`entity.brand`相符。

   [!DNL Recommendations] 現在會針對每個品牌產生「最暢銷商品」清單，並根據「我的最愛品牌設定檔」屬性中儲存的值，向使用者顯示適當的「最暢銷商品」  清單。

   ![「最暢銷商品」屬性](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## 准則／演算法{#criteria-algorithms}

[!DNL Target Recommendations] 採用複雜的演算法，用於判斷訪客的動作何時符合活動中設定的條件。建議金鑰決定可用的建議邏輯選項。

| 標準 | 說明 |
|--- |--- |
| [具有類似屬性的項目/媒體](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#similar-attributes) | 根據目前頁面活動或訪客的過去行為，建議相似的項目或媒體。 |
| [瀏覽過此項目、也瀏覽了其他項目的使用者](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-viewed) | 建議在檢視所指定項目的相同工作階段中，最常檢視的項目。 |
| [瀏覽過此項目、但購買了其他項目的使用者](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-bought) | 建議在檢視所指定項目的相同工作階段中，最常購買的項目。 |
| [購買了此項目、也購買了其他項目的使用者](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#bought-bought) | 建議當客戶購買所指定項目的同時，最常購買的項目。 |
| [網站相關性](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#site-affinity) | 根據項目之間關係的必然性來建議項目。 |
| [最暢銷商品](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#top-sellers) | 多數完成的訂單中包含的項目。單一訂單中相同項目的多個單位視為一份訂單。 |
| [檢視次數最多](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed) | 最常檢視的項目或媒體。 |
| [以使用者為基礎的Recommendations](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | 根據每位訪客的瀏覽、檢視和購買記錄來建議項目。 這些項目通常稱為「為您推薦」。 |

>[!NOTE]
>
>如果執行建議時變更其條件，將會失去報表資料。

您也可以使用訪客的其他已知資訊來增強建議。

所有一天條件每日執行兩次。所有一週及更久條件每日執行一次。網站相關性條件每日執行一次。備用條件每日執行兩次。

## 查看標準資訊{#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以將游標移至卡片上並按一下卡片上的「資訊」圖示，這樣無需開啟條件，即可在快顯卡上查看條件詳情。

![條件卡暫留](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

按一下&#x200B;**[!UICONTROL 「演算法資訊」]**&#x200B;索引標籤，即可查看選取條件的一般資訊，包括名稱、說明、垂直產業、頁面類型、建議金鑰、建議邏輯和演算法 ID。

![演算法資訊索引標籤](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

按一下&#x200B;**[!UICONTROL 「演算法使用情形」]**&#x200B;索引標籤，即可查看參照選取條件的活動清單。卡片會列出活動中、非活動中和草稿活動。 按一下「即時活動／非活動／草稿活動」下拉式清單，以檢視參照該准則之活動的完整清單。 您可以按一下活動連結以開啟活動並編輯。

![演算法使用標籤](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>[!UICONTROL 演算法使用]功能目前僅支援Recommendations活動。 A/B測試、自動分配、自動定位和體驗定位(XT)活動目前不支援此功能，這些活動包含[建議作為選件](/help/c-recommendations/recommendations-as-an-offer.md)。
