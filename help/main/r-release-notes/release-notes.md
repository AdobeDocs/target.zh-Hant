---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 550fa1e8d4127babe02403708b73862505bf8c99
workflow-type: tm+mt
source-wordcount: '1772'
ht-degree: 15%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

如需詳細資訊，請參閱[[!DNL Target] UI更新常見問題](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 26.1.1 （2026年1月18日）

**活動**

+++檢視詳細資料

* **無法複製活動 — 無效的使用者輸入。**&#x200B;已修正複製活動時，造成使用者看到無用的「無效使用者輸入」錯誤的問題。 先前，複製活動時，不會保留其工作區特有的屬性指派，導致後端拒絕儲存請求，因為ABActivity至少需要一個屬於非預設工作區的屬性。 這種不匹配在UI中觸發了一般錯誤，導致使用者沒有指引。 此修正可確保工作區指派在復製作業期間正確保留，讓使用者可儲存複製的活動而不需修改，並防止誤導性的驗證錯誤。 (TGT-54282)
* **啟用Web編輯器選件的Workspace欄。**&#x200B;此更新解決來自[!UICONTROL Default Workspace]的優惠方案出現在網頁編輯器中的其他工作區所造成的客戶混淆。 雖然此行為如預期般運作，但所有工作區中都會刻意顯示[!UICONTROL Default Workspace]選件，客戶回報UI未明確工作區來源，尤其是在非預設工作區（例如「核准者」）中建立活動時更是如此。 為了提高清晰度，[!UICONTROL Workspace]欄現在已在網頁編輯器的選件清單中啟用，可讓使用者輕鬆區分每個選件屬於哪個工作區，並防止誤解顯示的其他選件。 (TGT-54138)
* 在新標籤中開啟具有target=&quot;_blank&quot;的&#x200B;**連結。**&#x200B;此修正解決含有具有~target=&quot;_blank&quot;~之連結的已撰寫網站在[!UICONTROL Browse]模式中按一下時，會在新的瀏覽器標籤中開啟，中斷編輯器內預覽體驗的問題。 發生此行為是因為編寫頁面的原生連結屬性沒有受到擴充功能插入的JavaScript攔截，不像在舊版UI中，錨點元素會進行轉換，且其目標會覆寫，以保留在編輯器內的導覽。 更新可確保使用~target=&quot;_blank&quot;~的連結現在可在網頁編輯器中正確處理，因此在編寫期間不再開啟外部索引標籤。 (TGT-54134)
* **取消選取屬性警告。**&#x200B;此更新會引入視覺化警告，當使用者在活動編輯器中取消選取自動偵測的屬性時，會明確通知使用者。 以前，移除自動偵測的屬性時，並不會指出該屬性會被永久刪除，而這會造成目標設定意外遺失。 此修正會新增警告圖示，與舊版UI中的行為一致，以通知使用者取消選取屬性會將其從活動中移除。 (TGT-54121)
* **[!UICONTROL Workspaces]區段中的[!UICONTROL Users]下拉式清單限製為20個。**&#x200B;此修正解決以下問題： [!UICONTROL Workspaces] > [!UICONTROL Administration]區段中的[!UICONTROL Users]下拉式清單僅顯示20個工作區，即使使用者擁有存取更多工作區亦然。 `licenseGroups`的基礎GraphQL呼叫也限製為20個結果，導致使用者擁有組織中更多工作區的存取權，UI仍會顯示不完整的清單。 更新會移除此硬性限制，因此現在會傳回完整的可用工作區集，並正確顯示。 (TGT-53820)
* **修正優惠模式未顯示Workspace欄的問題。**&#x200B;修正優惠模式在更新的UI中未顯示Workspace欄的問題。 這會導致客戶感到困惑，因為來自[!UICONTROL Default Workspace]的優惠方案會與來自所選工作區的優惠方案一起出現，而不會指出其來源。 工作區欄現已啟用，客戶可清楚識別每個選件所屬的工作區。 (TGT-52320)

+++

**屬性**

+++檢視詳細資料
* **活動編輯不應新增自動偵測的屬性（如果已移除）。**&#x200B;此修正解決編輯活動會自動重新引入使用者先前已移除的自動偵測屬性的問題。 重新開啟活動以進行編輯時，系統錯誤地還原了移除的屬性，導致[!UICONTROL Properties List]中的行為不一致並產生混淆。 此更新可確保在移除自動偵測到的屬性後，該屬性會在所有後續編輯期間保持被移除狀態，且除非使用者明確將其新增回，否則其不會重新出現。 (TGT-54182)
* **如果已經移除，請勿新增自動偵測的內容。**&#x200B;此修正可確保一旦使用者手動從活動中移除自動偵測到的屬性，系統就不會在活動編輯器中的後續導覽期間重新引入該屬性。 先前，如果使用者取消選取自動偵測的屬性，移至[!UICONTROL Targeting]步驟，然後返回[!UICONTROL Experiences]，則編輯器會根據活動編輯器狀態片段中儲存的自動偵測清單重新填入移除的屬性。 更新後的邏輯現在會將自動偵測到的屬性與~ActivityState~磁碟片段中的目前屬性進行比較，並防止重新加入使用者已移除的任何自動偵測到的屬性。 這會產生跨步驟的一致行為並尊重使用者意圖。 (TGT-54181)
* **將自動偵測的文字新增至屬性清單。**&#x200B;此增強功能會更新[!UICONTROL Properties List]，以清楚標示系統自動偵測到的任何屬性。 當使用者可見的[!UICONTROL Properties List]中也存在自動偵測的屬性時，它現在會使用儲存在~ActivityEditorSlice~狀態的值，在其名稱旁邊顯示「（自動偵測）」文字。 這反映了舊版UI的行為，並幫助使用者輕鬆區分手動選取的屬性和自動識別的屬性。 (TGT-54120)
* **將自動偵測到的[!UICONTROL Properties]加入狀態。**&#x200B;此更新可確保~ActivityEditorSlice.ExperienceEditor~狀態一致地維護所有自動偵測屬性ID的最新清單，這些屬性ID是從Web編輯器傳入Activity [!UICONTROL Experiences]索引標籤的。 每次使用者導覽至[!UICONTROL Experiences]索引標籤時，都會使用任何新偵測到的屬性重新整理狀態，同時避免重複專案，確保準確追蹤且可靠的下遊行為。 (TGT-54119)

+++

**推薦**

+++檢視詳細資料
* **[!UICONTROL Environment]下拉式清單僅顯示100個結果。**&#x200B;此修正解決具有超過100個環境的客戶在[!UICONTROL Environment]內的[!UICONTROL Recommendations]下拉式清單中只能看到前100個專案的限制。 基礎GraphQL查詢(~getEnvironmentsV2~)已使用100的硬式編碼頁面大小進行分頁，導致UI即使有其他頁面可用，也只顯示部分清單。 對於擁有超過100個環境的客戶，此問題會導致缺少選項和不完整的選擇體驗。 更新會增加上限，因此所有環境都會傳回和顯示，確保完整可見性（無論環境計數為何）。 (TGT-53903)

+++

**報表**

+++檢視詳細資料

* **修正[!UICONTROL Reports]箭頭未明確表示可展開欄的問題。**&#x200B;修正報表表格未清楚顯示其他欄可以在更新的UI中展開的問題。 在欄標題附近的[!UICONTROL Reports]箭頭新增了消失的工具提示，以幫助客戶瞭解有更多欄可用。

+++

**檢視**

+++檢視詳細資料

* **無法刪除套用至檢視表的修改。**&#x200B;此修正解決使用者無法刪除活動內的修改問題，除非修改已首次重新套用至其他檢視。 編輯活動時(例如活動ID 302467)，嘗試刪除任何修改都沒有效果，導致使用者無法移除不需要的變更。 不過，使用「套用至更多檢視」重新套用修改並指派給`Page Load`事件後，刪除突然如預期般運作。 (TGT-54088)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++檢視詳細資料
* 在新的VEC UI **[!UICONTROL Experience Fragment]中，**&#x200B;名稱被截斷(TGT-54312)
* **無法將[!UICONTROL Advanced Settings]用於[!UICONTROL Revenue]量度。**&#x200B;此修正解決使用者在[!UICONTROL Advanced Settings]中為[!UICONTROL Revenue]量度設定[!UICONTROL Goals & Settings]時遇到403「存取遭拒」錯誤的問題。 新增與主要目標繫結的相依性條件時發生問題；後端不正確地要求編輯者許可權，即使使用者已經有足夠的許可權可建立和編輯活動。 因此，儘管設定有效，儲存活動仍會失敗。 更新會更正許可權檢查，使具有適當存取許可權的使用者可以成功新增收入量度相依性，而不會觸發禁止的資源錯誤。 (TGT-54092)
* **修正「新增」按鈕未套用至所選取影像的問題。**&#x200B;修正客戶在活動建立程式中選取或更新影像時，無法新增特定影像的問題。 例如，當客戶搜尋特定資產時，搜尋「ipp」時傳回的影像，按一下[!UICONTROL Add]按鈕未套用選取的影像，且未建立任何修改。 選取其他影像（例如`Homepage-banner-1-moz.jpg`）可繼續如預期運作。 此更新可確保所有有效影像都能在更新後的UI中一致地套用。 (TGT-53610)
* **修正刪除URL條件會重設目標量度組態的問題。**&#x200B;修正[!UICONTROL Goal]量度中移除單一URL條件導致整個設定在更新的UI中重設的問題。 當客戶嘗試刪除[!UICONTROL Conversion] > [!UICONTROL Viewed a Page]下儲存的URL條件時，目標型別意外地切換為[!UICONTROL Viewed an Mbox]，且先前設定的所有設定均已移除。 此更新可確保只刪除選取的URL條件，而其餘的所有目標設定都會保持不變。 (TGT-53271)
* **修正搜尋未檢視子資料夾的問題。**&#x200B;修正搜尋優惠未在更新的UI中傳回子資料夾結果的問題。 客戶只有在手動導覽至儲存選件的資料夾時，才能找到選件，導致搜尋行為與API功能不一致。 搜尋現在支援遞回檢視資料夾，因此客戶可以找到選件，而無需個別開啟每個資料夾。 (TGT-51954)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
