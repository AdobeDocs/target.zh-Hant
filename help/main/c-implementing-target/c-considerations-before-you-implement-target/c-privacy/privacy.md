---
keywords: 隱私；ip地址；地域分割；選擇退出；optout;optout;data privacy；政府規章；規章；gdpr;ccpa
description: 瞭解如何Adobe [!DNL Target] 遵守適用的資料隱私法，包括IP地址的收集和處理以及選擇退出說明。
title: 如何 [!DNL Target] 處理隱私問題？
feature: Privacy & Security
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 59%

---

# 隱私權

[!DNL Adobe Target] 已啟用程序和設定，允許您使用 遵守適用的資料隱私權法律。[!DNL Target]

## 功能使用資料的集合

為內部收集單個特徵使用資料 [!DNL Adobe] 以確定 [!DNL Target] 功能正按照預期執行，或標識正被未充分利用的功能。 收集各種延遲測量以幫助解決效能問題。 不會收集個人資料。

您可以通過設定 `telemetryEnabled` 到false。 如需詳細資訊，請參閱 [targetGlobalSettings 中的 telemetryEnabled](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry)。

## IP地址的集合 {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

您網站訪客的 IP 位址將傳輸到 Adobe 資料處理中心 (DPC)。視訪客的網路設定而定，此 IP 位址不一定代表訪客電腦的 IP 位址。例如，該 IP 位址可能是網路位址轉譯 (NAT) 防火牆、HTTP Proxy 或內部閘道的外部 IP 位址。Target 不會儲存使用者的任何 IP 位址或任何個人身分識別資訊 (PII)。IP地址僅由目標在會話期間使用（記憶體中，從不保留）。

## 替換IP地址的最後八位數 {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe 已開發新的「設計隱私權」設定，可由 Adobe 客戶服務為 Adobe Target 啟用。啟用此設定時，當 Adobe 收集到 IP 位址時，就會立即隱藏 IP 位址的最後八位元 (最後一部分)。該匿名化在IP地址的任何處理之前執行，包括在IP地址的可選地理查找之前執行。

啟用此功能時，IP 位址的匿名性已足夠，不再能識別為個人資訊。因此，Adobe Target 的使用便能遵守不允許收集個人資訊之國家/地區的資料隱私權法律。IP 位址模糊化可能會顯著影響城市層級資訊的取得。地區和國家層級資訊則只會受到輕微影響。

可使用下列設定:

* 無混淆：目標不隱藏IP地址的任何部分。
* 最後一個二進位八位數：Target隱藏IP地址的最後八位數。
* 完整IP:目標隱藏整個IP地址。

目標接收完整的IP地址，並按指定的方式將其模糊化（如果設定為「Last octet」或「Full IP」）。 然後，目標在會話期間將模糊化的IP地址保存在記憶體中。

>[!NOTE]
>
>[聯繫Adobe客戶保護](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 確定當前使用的設定或啟用IP混淆功能。

## 地域劃分 {#section_BB69F96559BD44BDA4177537C4A5345A}

如果您啟用取代 IP 位址的最後八位元，可使用 Adobe Target 中的報表來分析 IP 位址的其餘值。如果 IP 位址的最後八位元未被模糊化，則可在 Adobe Target 中分析完整 IP 位址。您可以使用 GeoSegmentation 功能，依地理區域來安排訪客位置。地域劃分資料的詳細程度只到城市層級或郵遞區號層級，不到個人層級。

如果 IP 位址完全模糊，則無法使用 GeoSegmentation 和地理位置定位。

## 選擇退出連結 {#section_E7A62B7B99C94B3A806CB262D16E27FC}

您可以在您的網站中新增選擇退出連結，讓訪客能夠選擇退出所有 計數及內容傳遞。

1. 將下列連結新增至您的網站:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. （條件）如果您使用CNAME，則連結應包含&quot;client=`clientcode` 參數，例如：https://my.cname.domain/optout?client=clientcode。

1. 替換 `clientcode` 將文本或影像連結到選擇退出URL。

訪客只要按一下此連結，就不會包含在任何從該訪客的瀏覽作業呼叫的 mbox 中，直到訪客刪除本身的 Cookie 或事隔滿兩年 (以先發生者為準) 為止。其原理是在 `disableClient` 中為訪客設定一個名稱為 `clientcode.tt.omtrdc.net` 的 Cookie。

即使您使用第一方 Cookie 實作，所提供的選擇退出還是透過第三方 Cookie 來設定。若客戶僅使用第一方 Cookie，Target 會檢查是否有設定選擇退出 Cookie。

## 隱私權與資料保護規範

請參閱 [隱私和資料保護法規](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) 有關歐盟的一般資料保護條例(GDPR)、加利福尼亞消費者隱私法(CCPA)和其他國際隱私要求的資訊，以及這些條例如何影響您的組織和Adobe Target。
