---
title: 追蹤和電子郵件傳送的協定
description: 了解如何在 Marketo Engage 中設定協定，以供 Journey Optimizer B2B Edition 追蹤和電子郵件頻道功能使用。
feature: Setup
role: Admin
exl-id: 3d56f147-ad0a-4686-b14e-375c2eca8806
source-git-commit: 4ba1beb7f252c94379f984b32d8f581ee57038e3
workflow-type: ht
source-wordcount: '1798'
ht-degree: 100%

---

# 追蹤和電子郵件傳送的協定

Adobe Journey Optimizer B2B Edition 利用 Marketo Engage 中的電子郵件頻道功能和事件追蹤。為了確保使用限制性防火牆或代理伺服器設定的組織之電子郵件能夠按預期傳送，系統管理員必須將某些網域和 IP 位址範圍新增至允許清單。

>[!NOTE]
>
>如果您的組織已經在使用連線的 Marketo Engage 執行個體來執行其行銷作業，這些協定和設定應該已經設定完成。

務必將下列網域 (包括星號) 新增至允許清單中，以啟用所有 Marketo Engage 資源和 Web 通訊端：

* `*.experience.adobe.com`
* `*.adobe.net`
* `*.marketo.com`
* `*.marketodesigner.com`
* `*.mktoweb.com`

遵照以下步驟來確保追蹤與電子郵件傳送的運作：

1. [建立 DNS 記錄 ](#create-dns-records-for-landing-pages-and-email)
1. [設定 SPF 和 DKIM](#set-up-spf-and-dkim)
1. [設定 DMARC](#set-up-dmarc)
1. [設定您的網域的 MX 記錄](#set-up-mx-records-for-your-domain)
1. [將對外連線 IP 位址新增至允許清單](#outbound-ip-addresses)

## 建立<!-- landing pages and -->電子郵件的 DNS 記錄

透過連接 CNAME 記錄，行銷人員可以託管擁有一致品牌形象的電子郵件、登陸頁面和部落格的網頁版，從而提高流量和轉換率。強烈建議您將 CNAME 新增至根網域主機，以便 Marketo Engage 託管以行銷為主的 Web 資產。身為管理員，您應該與行銷團隊合作計畫及實施 CNAME 記錄，並適用於透過 Marketo Engage 傳送的電子郵件中所包含的追蹤連結。
<!-- As an administrator, you should work with your Marketing team to plan and implement two CNAME records. The first one is for landing page URLs, so that the landing pages appear in URLs that reflect your domain and not Adobe Marketo Engage (the actual host). The second one is for the tracking links that are included in the emails sent through Marketo Engage.

### Add the CNAME for landing pages

Add the landing page CNAME to your DNS record, so that `[YourLandingPageCNAME]` points to the unique account string that is assigned to your landing pages. Log in to your domain registrar's site and enter the landing page CNAME and account string. This entry usually involves three fields:

* Alias: Enter `[YourLandingPageCNAME]`
* Type: CNAME
* Point to: Enter `[MunchkinID].mktoweb.com`
-->

### 新增電子郵件追蹤連結的 CNAME

新增電子郵件 CNAME，使`[YourEmailCNAME]`指向`[MktoTrackingLink]`，這是 Marketo Engage 指派的預設追蹤連結，格式如下：

`[YourEmailCNAME].[YourDomain].com` IN CNAME `[MktoTrackingLink]`

例如：

`pages.abc.com IN CNAME mkto-a0244.com`

>[!NOTE]
>
>`[MktoTrackingLink]` 值必須是預設品牌網域。

### 佈建 SSL 憑證

聯絡 [Adobe 支援](https://experienceleague.adobe.com/home?lang=en&amp;support-tab=home#support){target="_blank"}以開始 SSL 憑證的佈建流程。

此流程可能需要最多三個工作天才能完成。

## 設定 SPF 和 DKIM

您的行銷團隊應提供 DKIM (Domain Keys Identified Mail) 資訊以新增至您的 DNS 資源記錄。請依照下列步驟設定 DKIM 和 SPF (寄件者原則框架)，然後在更新時通知您的行銷團隊。

1. 若要設定 SPF，請將下面一行新增至 DNS 項目：

   ```
   [CompanyDomain] IN TXT v=spf1 mx ip4:[CorpIP]  
   include: mktomail.com ~all
   ```

   如果您的 DNS 項目中已經有 SPF 記錄，只需在其中新增以下內容：

   ```
   include: mktomail.com
   ```

   將 `CompanyDomain` 換成您的網站主網域 (例如 `company.com/`)，並將 `CorpIP` 換成您公司電子郵件伺服器的 IP 位址 (例如 `255.255.255.255`)。如果您打算透過 Marketo Engage 從多個網域傳送電子郵件，請在每個網域新增這一行 (限一行)。

1. 針對 DKIM，建立每個網域的 DNS 資源記錄。

   新增每個網域的主機記錄和 TXT 值：

   `[DKIMDomain1]`：主機記錄為 `[HostRecord1]`，TXT 值為 `[TXTValue1]`。

   `[DKIMDomain2]`：主機記錄為 `[HostRecord2]`，TXT 值為 `[TXTValue2]`。

   依照 Marketo Engage 文件中的[說明](https://experienceleague.adobe.com/zh-hant/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"}操作後，複製每個 DKIM 網域的 `HostRecord` 和 `TXTValue`。您可以在 Journey Optimizer B2B Edition 中驗證網域 (請參閱 [SPF/DKIM](../admin/configure-channels-emails.md#spfdkim))。

## 設定 DMARC

DMARC (網域型訊息驗證、報告和合規) 是一種驗證通訊協定，可以協助組織保護其網域，避免未經授權者存取。此通訊協定擴展現有的驗證通訊協定 (例如 SPF 和 DKIM)，當收件者的網域驗證失敗時，通知收件者伺服器應採取什麼行動。DMARC 是選用功能，但我們強烈建議使用，有助於保護您的品牌和聲譽。Google 和 Yahoo 等主要供應商從 2024 年 2 月開始要求大量郵件的寄件者使用 DMARC。

要讓 DMARC 正常運作，您必須至少擁有以下其中一項 DNS TXT 記錄：

* 有效的 SPF
* 寄件者網域的有效 DKIM 記錄 (Marketo Engage 和 Journey Optimizer B2B Edition 建議使用)

您的 `FROM:` 網域也必須具備 DMARC 特定的 DNS TXT 記錄。或者，您可以定義電子郵件，指定 DMARC 報告應該發送到組織的哪個單位進行報告監控。

### DMARC 工作流程範例

>[!TIP]
>
>最佳實務是以&#x200B;_緩慢推動_&#x200B;的方式實施 DMARC。當您了解潛在影響後，請將您的 DMARC 原則從 `p=none` 升級到 `p=quarantine`，然後再升級到 `p=reject`，並將您的 DMARC 原則設定為對 SPF 和 DKIM 採寬鬆比對。

如果您收到 DMARC 報告，您應該執行以下動作：

1. 使用 `p=none` 並分析您收到的回饋意見和報告。報告告知接收者不要對未通過驗證的郵件採取任何動作，並把電子郵件報告傳送給寄件者。

   * 如果合法郵件驗證失敗，請檢查並修復 SPF/DKIM 的問題。

   * 確定 SPF 或 DKIM 是否一致，且是否通過所有合法電子郵件的驗證。

   * 查看報告以確保結果符合您的 SPF/DKIM 原則所預期的結果。

1. 將政策調整為 `p=quarantine`，要求接收電子郵件的伺服器將未通過驗證的電子郵件隔離 (通常會將這些郵件放入垃圾郵件資料夾中)。

   查看報告以確保結果符合您的預期。

1. 如果您對 `p=quarantine` 等級的郵件行為感到滿意，則可以將原則調整為 (`p=reject`)。

   拒絕原則會要求接收者拒絕 (退回) 來自未通過驗證的網域之任何電子郵件。啟用此原則後，只有百分百通過您的網域驗證的電子郵件才有機會進入收件匣。

   >[!CAUTION]
   >
   >謹慎使用此原則並確認其是否適合您的組織。

### DMARC 報告

DMARC 可以接收未通過 SPF/DKIM 驗證的電子郵件之報告。在驗證過程中，ISP 服務商會產生兩份不同的報告。寄件者可以透過其 DMARC 原則中的 RUA/RUF 標記接收這些報告。

* **彙總報告 (RUA)**：不包含任何可能屬於 GDPR (一般資料保護規範) 敏感資訊的個人識別資訊 (PII)。

* **鑑識報告 (RUF)**  - 包含屬於 GDPR 敏感資訊的電子郵件。在實施此報告之前，請先確認您的組織處理必須符合 GDPR 規範的資訊時採取什麼原則。

這些報告的主要用途是讓您大致了解有哪些偽冒的電子郵件。這些報告含有大量技術知識，最好透過第三方工具來消化。

### DMARC 記錄範例

* 最低限度記錄：`v=DMARC1; p=none`

* 導向到電子郵件以便接收報告的記錄：`v=DMARC1; p=none;  rua=mailto:emaill@domain.com;  ruf=mailto:email@domain.com`

### DMARC 標記

DMARC 記錄有多個組成部分，稱為 _DMARC 標記_。每個標記都有一個值，可用來指定 DMARC 的某個部分。

| 標記名稱 | 使用 | 功能 | 範例 | 預設值 |
|-----------|------------------------|-----------|----------|-----------------------------------|
| `v` | 必要 | 指定版本。因為只有一個版本，所以是固定的值 `v=DMARC1` | V=DMARC1 DMARC1 | DMARC1 |
| `p` | 必要 | 指定 DMARC 原則，其中指示接收者報告、隔離或拒絕未通過驗證檢查的電子郵件。 | `p=none`、`p=quarantine` 或 `p=reject` | - |
| `fo` | 選用 | 允許網域擁有者指定報告選項。 | `0`：如果 SPF 和 DKIM 都失敗，則產生報告<br> `1` - 如果 SPF 或 DKIM 失敗，則產生報告<br> `d` - 如果 DKIM 失敗，則產生報告<br> `s` - 如果 SPF 失敗，則產生報告 | `1` (DMARC 報告建議使用) |
| `pct` | 選用 | 指定需要篩選的訊息之百分比。 | `pct=20` | `100` |
| `rua` | 選用 (建議) | 指定彙總報告要傳送到哪裡。 | `rua=mailto:aggrep@example.com` | - |
| `ruf` | 選用 (建議) | 指定鑑識報告要傳送到哪裡。 | `ruf=mailto:authfail@example.com` | - |
| `sp` | 選用 | 指定父網域的子網域 DMARC 原則。 | `sp=reject` | - |
| `adkim` | 選用 | 指定嚴格 (`s`) 或寬鬆的 (`r`) 比對。寬鬆比對代表該網域用於 DKIM 簽章，並且可以是 `From:` 位址的子網域。嚴格比對代表 DKIM 簽章中使用的網域必須與 `From:` 位址使用的位址完全相符。 | `adkim=r` | `r` |
| `aspf` | 選用 | 可以是嚴格 (`s`) 或寬鬆 (`r`)。寬鬆模式表示 Return-Path 網域可以是 `From:` 位址的子網域。嚴格模式表示 Return-Path 網域必須與 `From:` 位址完全相符。 | `aspf=r` | `r` |

有關 DMARC 及其所有選項的詳細資訊，請參閱 [https://dmarc.org/](https://dmarc.org/){target="_blank"}。

### Marketo Engage 的 DMARC 實作

DMARC 有兩種比對類型：

* **DKIM** (Domain Keys Identified Mail) 比對：電子郵件 `From:` 標頭中指定的網域與 DKIM 簽章相符。DKIM 簽章包含 `d=` 值，其中指定的網域與 `From:` 標頭網域相符。

  DKIM 比對驗證寄件者是否獲得授權從該網域發送郵件，並確認電子郵件傳輸過程中內容沒有發生變更。實施與 DKIM 比對的 DMARC：

   * 為您的郵件的 MAIL FROM 網域設定 DKIM。使用在 Marketo Engage 文件中的[說明](https://experienceleague.adobe.com/zh-hant/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"}。

   * 為 DKIM MAIL FROM 網域設定 DMARC。

  >[!NOTE]
  >
  >建議 Marketo Engage 使用 DKIM 比對。

* **SPF** (寄件者原則框架) 比對：`From:` 標頭中的網域必須與 Return-Path: 標頭中的網域相符。如果兩個 DNS 網域相同，則 SPF 匹配正確 (比對符合) 並給予通過。實施與 SPF 比對的 DMARC：

   * 設定具品牌識別的 Return-Path 網域。

      * 設定適當的 SPF 記錄。
      * 將 MX 記錄變更為指向傳送郵件之資料中心的預設 MX

   * 設定具品牌識別的 Return-Path 網域之 DMARC。

  >[!NOTE]
  >
  >Marketo Engage 不支援也不建議使用嚴格的 SPF 比對。

### 專用 IP 和共用集區

如果您使用專用 IP 透過 Marketo Engage 傳送郵件，但尚未實施具品牌識別的 return-path (或不確定是否已實施)，請透過 [Adobe 支援](https://experienceleague.adobe.com/home?lang=en&amp;support-tab=home#support){target="_blank"}開啟服務單。

受信任的 IP 是指一個共用 IP 集區，其中 IP 保留給每月發送量少於 75k 而且不符合條件使用專用 IP 的低流量使用者使用。這些使用者亦必須滿足最佳實務要求。

* 如果您使用共用的 IP 集區透過 Marketo Engage 發送郵件，只要[申請受信任的 IP 發送範圍方額](https://na-sjg.marketo.com/lp/marketoprivacydemo/Trusted-IP-Sending-Range-Program.html){target="_blank"}，即可確認自己是否有資格使用受信任的 IP。從 Marketo Engage 受信任 IP 發送時包含具品牌識別的 return-path。如果此方案獲得批准，請聯絡 Adobe 支援部門來設定具品牌識別的 return-path。

* 如果您每月發送超過 100,000 則訊息，並希望使用共用 IP 透過 Marketo Engage 發送電子郵件，請聯絡 Adobe 帳戶團隊 (您的帳戶經理) 購買專用 IP。

## 設定您的網域的 MX 記錄

您可以利用 MX 記錄來接收要傳送至您發送電子郵件的網域的郵件，以處理回覆和自動回覆。如果您從公司網域發送，則可能已經設定完成。如果沒有，您通常可以將其設定為對應到您的公司網域 MX 記錄。

## 對外連線 IP 地址

對外連線是 Marketo Engage 代表您與網際網路上的伺服器建立的連線。您的 IT 組織和一些合作夥伴/供應商可能會使用允許清單來限制伺服器的存取權。如果是這樣，您必須把 Marketo Engage 的對外連線 IP 位址區塊提供給他們，以便新增至允許清單中。

<!-- ### Webhooks

Marketo Engage webhooks are an outbound integration mechanism. When a Smart Campaign executes a _Call Webhook_ flow action, it makes an HTTP request to an external web service. If the web service publisher uses an allowlist on the firewall of the network where the external web service is located, the publisher must add the IP address blocks listed below to their allowlist. For more information, see [Create a webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/additional-integrations/create-a-webhook){target="_blank"} and [Call Webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-campaigns/flow-actions/call-webhook){target="_blank"} in the Marketo Engage documentation.

### CRM sync

Marketo Engage Salesforce CRM Sync and Microsoft Dynamics Sync are integration mechanisms that make outbound HTTP requests to APIs published by your CRM vendor. Ensure that your IT organization does not block any of the IP address blocks below from accessing your CRM vendor APIs. For more information, see [Add an Existing Salesforce Field to the Marketo Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/salesforce-sync/sfdc-sync-details/add-an-existing-salesforce-field-to-the-marketo-sync){target="_blank"} and [Understanding the Microsoft Dynamics Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/microsoft-dynamics/understanding-the-microsoft-dynamics-sync){target="_blank"} in the Marketo Engage documentation. -->

## 對外連線 IP 地址區塊

以下清單涵蓋所有發出對外連線的 Marketo Engage 伺服器。請參閱這些清單來設定 IP 允許清單、伺服器、防火牆、存取控制清單、安全性群組或第三方服務，以接收來自 Marketo Engage 的對外連線。

| IP 區塊 (CIDR 標記法) | 個人 IP 地址 |
| ------------------------ | --------------------- |
| <ul><li>`94.236.119.0/26`</li><li>`103.237.104.0/22`</li><li>`130.248.172.0/24`</li><li>`130.248.173.0/24`</li><li>`130.248.244.88/29`</li><li>`185.28.196.0/22`</li><li>`192.28.144.0/20`</li><li>`192.28.160.0/19`</li><li>`199.15.212.0/22`</li></ul> | <ul><li>`13.237.155.207`</li><li>`13.55.192.247`</li><li>`18.200.201.81`</li><li>`34.247.24.245`</li><li>`35.165.244.220`</li><li>`44.235.171.179`</li><li>`52.20.211.99`</li><li>`52.64.109.86`</li><li>`54.160.246.246`</li><li>`54.212.167.17`</li><li>`54.220.138.65`</li><li>`54.237.141.197`</li><li>`130.248.168.16`</li><li>`130.248.168.17`</li></ul> |
