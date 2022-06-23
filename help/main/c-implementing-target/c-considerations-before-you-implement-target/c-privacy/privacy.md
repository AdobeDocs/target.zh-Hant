---
keywords: 隱私權;ip 位址;地域劃分;選擇退出;資料隱私;政府法規;法規;gdpr;ccpa
description: 了解 Adobe [!DNL Target] 如何遵守適用的資料隱私法，包括收集和處理 IP 位址及選擇退出的說明。
title: ' [!DNL Target] 如何處理隱私問題？'
feature: Privacy & Security
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 98%

---

# 隱私權

[!DNL Adobe Target] 已啟用程序和設定，好讓您在遵守適用的資料隱私法的情況下使用 [!DNL Target]。

## 功能使用情況資料的收集

收集個別功能使用情況資料以供內部 [!DNL Adobe] 用來識別 [!DNL Target] 功能的執行是否如預期或是識別未被充分利用的功能。 收集各種延遲測量結果來協助解決效能問題。 不會收集個人資料。

您可以在用戶端初始化選項中將 `telemetryEnabled` 設定為 false 來選擇退出我們 SDK 中的使用資料報告。 如需詳細資訊，請參閱 [targetGlobalSettings 中的 telemetryEnabled](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。

## 收集 IP 位址 {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

您網站訪客的 IP 位址將傳輸到 Adobe 資料處理中心 (DPC)。視訪客的網路設定而定，此 IP 位址不一定代表訪客電腦的 IP 位址。例如，該 IP 位址可能是網路位址轉譯 (NAT) 防火牆、HTTP Proxy 或內部閘道的外部 IP 位址。Target 不會儲存使用者的任何 IP 位址或任何個人身分識別資訊 (PII)。Target 只會在工作階段期間使用 IP 位址 (只放在記憶體內，絕對不會保存)。

## 取代 IP 位址的最後一個八位元 {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe 已開發新的「設計隱私權」設定，可由 Adobe 客戶服務為 Adobe Target 啟用。啟用此設定時，當 Adobe 收集到 IP 位址時，就會立即隱藏 IP 位址的最後一個八位元 (最後的部分)。 在對 IP 位址進行任何處理前 (包括選用的 IP 位址地理查閱)，就會執行這種匿名化作業。

啟用此功能時，IP 位址的匿名性已足夠，不再能識別為個人資訊。因此，Adobe Target 的使用便能遵守不允許收集個人資訊之國家/地區的資料隱私權法律。IP 位址模糊化可能會顯著影響城市層級資訊的取得。地區和國家層級資訊則只會受到輕微影響。

有以下設定可使用：

* 無模糊化：Target 不會隱藏 IP 位址的任何部分。
* 最後一個八位元：Target 會隱藏 IP 位址的最後一個八位元。
* 完整 IP：Target 會隱藏整個 IP 位址。

Target 會收到完整 IP 位址並根據指定加以模糊化 (如果設定為最後一個八位元或完整 IP)。 然後 Target 會在工作階段期間將模糊化的 IP 位址存在記憶體內。

>[!NOTE]
>
>[聯絡 Adobe 客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以確定您目前正在使用哪一項設定或是啟用 IP 模糊化功能。

## 地域劃分 {#section_BB69F96559BD44BDA4177537C4A5345A}

如果您啟用取代 IP 位址的最後八位元，可使用 Adobe Target 中的報表來分析 IP 位址的其餘值。如果 IP 位址的最後八位元未被模糊化，則可在 Adobe Target 中分析完整 IP 位址。您可以使用 GeoSegmentation 功能，依地理區域來安排訪客位置。地域劃分資料的詳細程度只到城市層級或郵遞區號層級，不到個人層級。

如果 IP 位址完全模糊，則無法使用 GeoSegmentation 和地理位置定位。

## 選擇退出連結 {#section_E7A62B7B99C94B3A806CB262D16E27FC}

您可以在您的網站中新增選擇退出連結，讓訪客能夠選擇退出所有 計數及內容傳遞。

1. 將下列連結新增至您的網站:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. (有條件性) 如果您正在使用 CNAME，連結應該包含「client=`clientcode`」參數，例如：
https://my.cname.domain/optout?client=clientcode.

1. 將 `clientcode` 替換為您的用戶端代碼，然後新增要連結至選擇退出 URL 的文字或影像。

訪客只要按一下此連結，就不會包含在任何從該訪客的瀏覽作業呼叫的 mbox 中，直到訪客刪除本身的 Cookie 或事隔滿兩年 (以先發生者為準) 為止。其原理是在 `disableClient` 中為訪客設定一個名稱為 `clientcode.tt.omtrdc.net` 的 Cookie。

即使您使用第一方 Cookie 實作，所提供的選擇退出還是透過第三方 Cookie 來設定。若客戶僅使用第一方 Cookie，Target 會檢查是否有設定選擇退出 Cookie。

## 隱私權與資料保護規範

請參閱[隱私權與資料保護規範](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/)，以取得有關歐盟一般資料保護規範 (GDPR)、加州消費者隱私保護法 (CCPA) 及其他國際隱私規定的資訊，並了解這些規定對貴組織和 Adobe Target 有何影響。
