---
title: 追蹤和電子郵件傳遞的通訊協定
description: 瞭解如何在Marketo Engage中設定通訊協定，以供Journey Optimizer B2B edition用於追蹤和電子郵件通道功能。
feature: Setup
role: Admin
source-git-commit: a8ca8b99ddf33b4a64b42b751f7be798274d0084
workflow-type: tm+mt
source-wordcount: '1798'
ht-degree: 0%

---

# 追蹤和電子郵件傳遞的通訊協定

Adobe Journey Optimizer B2B edition運用Marketo Engage中的電子郵件頻道功能和事件追蹤功能。 為確保電子郵件傳送如預期運作，適用於使用限制防火牆或Proxy伺服器設定的組織，系統管理員必須將特定網域和IP位址範圍新增至允許清單。

>[!NOTE]
>
>如果您的組織已使用連線的Marketo Engage例項來執行其行銷作業，這些通訊協定和設定應已就位。

請確定已將下列網域（包括星號）新增至允許清單，以啟用所有Marketo Engage資源和Web通訊端：

* `*.experience.adobe.com`
* `*.adobe.net`
* `*.marketo.com`
* `*.marketodesigner.com`
* `*.mktoweb.com`

請完成下列步驟，以確保追蹤及電子郵件傳送：

1. [建立DNS記錄 ](#create-dns-records-for-landing-pages-and-email)
1. [設定SPF和DKIM](#set-up-spf-and-dkim)
1. [設定DMARC](#set-up-dmarc)
1. [為您的網域設定MX記錄](#set-up-mx-records-for-your-domain)
1. [將輸出IP位址新增至允許清單](#outbound-ip-addresses)

## 建立<!-- landing pages and -->電子郵件的DNS記錄

連線CNAME記錄可讓行銷人員透過一致的品牌管理電子郵件、登陸頁面和部落格的網頁版本，以改善流量和轉換。 強烈建議您將CNAME新增至根網域主機，以便Marketo Engage託管以行銷為中心的網頁資產。 作為管理員，您應該與行銷團隊合作，針對透過Marketo Engage傳送的電子郵件中所包含的追蹤連結，規劃及實作CNAME記錄。
<!-- As an administrator, you should work with your Marketing team to plan and implement two CNAME records. The first one is for landing page URLs, so that the landing pages appear in URLs that reflect your domain and not Adobe Marketo Engage (the actual host). The second one is for the tracking links that are included in the emails sent through Marketo Engage.

### Add the CNAME for landing pages

Add the landing page CNAME to your DNS record, so that `[YourLandingPageCNAME]` points to the unique account string that is assigned to your landing pages. Log in to your domain registrar's site and enter the landing page CNAME and account string. This entry usually involves three fields:

* Alias: Enter `[YourLandingPageCNAME]`
* Type: CNAME
* Point to: Enter `[MunchkinID].mktoweb.com`
-->

### 新增電子郵件追蹤連結的CNAME

新增電子郵件CNAME，讓`[YourEmailCNAME]`指向`[MktoTrackingLink]` (Marketo Engage指派的預設追蹤連結)，格式為：

CNAME `[MktoTrackingLink]`中的`[YourEmailCNAME].[YourDomain].com`

例如：

`pages.abc.com IN CNAME mkto-a0244.com`

>[!NOTE]
>
>`[MktoTrackingLink]`值必須是預設品牌化網域。

### 布建SSL憑證

連絡[Adobe支援](https://experienceleague.adobe.com/home?lang=en&amp;support-tab=home#support){target="_blank"}以開始布建SSL憑證的程式。

此程式最多需要三個營業日才能完成。

## 設定SPF和DKIM

您的行銷團隊應提供要新增至DNS資源記錄的DKIM （網域金鑰識別郵件）資訊。 按照以下步驟設定DKIM和SPF (Sender Policy Framework)，然後在更新時通知您的行銷團隊。

1. 若要設定SPF，請在DNS專案中新增下列行：

   ```
   [CompanyDomain] IN TXT v=spf1 mx ip4:[CorpIP]  
   include: mktomail.com ~all
   ```

   如果您在DNS專案中已經有現有的SPF記錄，只需將以下內容新增到其中即可：

   ```
   include: mktomail.com
   ```

   將`CompanyDomain`取代為您網站的主要網域（例如`company.com/`），並將`CorpIP`取代為您公司電子郵件伺服器的IP位址（例如`255.255.255.255`）。 如果您打算透過Marketo Engage從多個網域傳送電子郵件，請為每個網域新增此行（一行）。

1. 對於DKIM，請為每個網域建立DNS資源記錄。

   新增每個網域的主機記錄和TXT值：

   `[DKIMDomain1]`：主機記錄為`[HostRecord1]`，且TXT值為`[TXTValue1]`。

   `[DKIMDomain2]`：主機記錄為`[HostRecord2]`，且TXT值為`[TXTValue2]`。

   遵循Marketo Engage檔案中的[指示](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"}後，複製每個DKIM網域的`HostRecord`和`TXTValue`。 您可以在Journey Optimizer B2B edition中驗證網域（請參閱[SPF/DKIM](../admin/configure-channels-emails.md#spfdkim)）。

## 設定DMARC

DMARC （網域型訊息驗證、報告和符合性）是一種驗證通訊協定，用於協助組織保護其網域免受未經授權的使用。 它會擴充現有的驗證通訊協定（例如SPF和DKIM），以通知收件者伺服器在其網域上發生驗證失敗時所採取的動作。 DMARC為選用，但強烈建議使用，以協助保護您的品牌和聲譽。 Google和Yahoo等主要提供者自2024年2月起開始要求大量傳送者使用DMARC。

若要讓DMARC正常運作，您必須至少擁有下列其中一個DNS TXT記錄：

* 有效的SPF
* 您的FROM：網域的有效DKIM記錄(建議用於Marketo Engage和Journey Optimizer B2B edition)

您也必須有`FROM:`網域的DMARC特定DNS TXT記錄。 或者，您可以定義電子郵件地址，指定DMARC報告在組織內用於報告監視的位置。

### DMARC工作流程範例

>[!TIP]
>
>最佳實務是以&#x200B;_緩慢轉出_&#x200B;的形式實作DMARC。 將您的DMARC原則從`p=none`提升為`p=quarantine`，然後再提升為`p=reject`，因為您可以瞭解潛在的影響，並將您的DMARC原則設定為放鬆對SPF和DKIM的一致性。

如果您收到DMARC報表，請務必採取下列步驟：

1. 使用`p=none`並分析您收到的意見與報告。 報告會告訴接收者，對於驗證失敗的訊息不執行任何動作，並向寄件者傳送電子郵件報告。

   * 如果合法訊息未通過驗證，請檢閱並修正SPF/DKIM的問題。

   * 判斷SPF或DKIM是否已對齊，並傳遞所有合法電子郵件的驗證。

   * 請檢閱報告，確保結果符合您的SPF/DKIM政策的預期結果。

1. 將原則調整為`p=quarantine`，這會通知接收電子郵件伺服器隔離驗證失敗的電子郵件（通常將這些郵件放在垃圾郵件資料夾中）。

   檢閱報告以確保結果如您所預期。

1. 如果您對`p=quarantine`層級的訊息行為感到滿意，您可以將原則調整為(`p=reject`)。

   拒絕原則會告訴接收者，拒絕驗證失敗之網域的任何電子郵件（退回）。 啟用此原則後，只有經過網域驗證為100%驗證的電子郵件才有機會放置收件匣。

   >[!CAUTION]
   >
   >請謹慎使用此原則，並判斷其是否適合您的組織。

### DMARC報告

DMARC提供接收有關SPF/DKIM失敗的電子郵件報表的功能。 在驗證過程中，ISP服務程式會產生兩種不同的報告。 寄件者可透過其DMARC原則中的RUA/RUF標籤接收這些報告。

* **彙總報表(RUA)**：未包含任何可能敏感GDPR （一般資料保護規範）的PII （個人識別資訊）。

* **鑑證報告(RUF)** — 包含對GDPR敏感的電子郵件地址。 實作此報表之前，請驗證您處理需要符合GDPR規範之資訊的組織原則。

這些報告的主要用途是接收企圖詐騙的電子郵件概觀。 它們是高度技術性的報告，最好透過協力廠商工具消化。

### DMARC記錄範例

* 最小裸記錄： `v=DMARC1; p=none`

* 導向至電子郵件地址以接收報告的記錄： `v=DMARC1; p=none;  rua=mailto:emaill@domain.com;  ruf=mailto:email@domain.com`

### DMARC標籤

DMARC記錄有多個名為&#x200B;_DMARC標籤_&#x200B;的元件。 每個標籤都有一個值，可指定DMARC的特定面向。

| 標記名稱 | 使用 | 函數 | 範例 | 預設值 |
|-----------|------------------------|-----------|----------|-----------------------------------|
| `v` | 必要 | 指定版本。 只有一個版本，因此其固定值為`v=DMARC1` | V=DMARC1 DMARC1 | DMARC1 |
| `p` | 必要 | 指定DMARC原則，該原則會指示接收者報告、隔離或拒絕驗證檢查失敗的電子郵件。 | `p=none`、`p=quarantine`或`p=reject` | - |
| `fo` | 選填 | 允許網域擁有者指定報告選項。 | `0`：如果SPF和DKIM都失敗，則產生報告<br> `1` — 如果SPF或DKIM失敗，則產生報告<br> `d` — 如果DKIM失敗，則產生報告<br> `s` — 如果SPF失敗，則產生報告 | `1` (建議用於DMARC報表) |
| `pct` | 選填 | 指定郵件須經過篩選的百分比。 | `pct=20` | `100` |
| `rua` | 選用（建議） | 指定彙總報表的傳送位置。 | `rua=mailto:aggrep@example.com` | - |
| `ruf` | 選用（建議） | 指定提供鑑證報告的位置。 | `ruf=mailto:authfail@example.com` | - |
| `sp` | 選填 | 指定上層網域之子網域的DMARC原則。 | `sp=reject` | - |
| `adkim` | 選填 | 指定嚴格(`s`)或寬鬆(`r`)對齊。 鬆弛對齊表示網域用於DKIM簽章中，可以是`From:`位址的子網域。 嚴格對齊表示網域用於DKIM簽章中，而且必須與`From:`位址中使用的網域完全相符。 | `adkim=r` | `r` |
| `aspf` | 選填 | 可以是嚴格(`s`)或寬鬆(`r`)。 寬鬆模式表示傳迴路徑網域可以是`From:`位址的子網域。 Strict模式表示Return-Path網域必須與`From:`位址完全相符。 | `aspf=r` | `r` |

如需DMARC及其所有選項的詳細資訊，請參閱[https://dmarc.org/](https://dmarc.org/){target="_blank"}。

### Marketo Engage的DMARC實作

DMARC有兩種型別的對齊：

* **DKIM** （網域金鑰識別郵件）對齊：電子郵件的`From:`標頭中指定的網域符合DKIM-Signature。 DKIM簽章包含`d=`值，其中指定網域與`From:`標頭網域相符。

  DKIM校準會驗證寄件者是否有權從網域傳送郵件，並驗證在電子郵件傳輸期間是否未變更任何內容。 若要實作DKIM校準的DMARC：

   * 為郵件的MAIL FROM網域設定DKIM。 在Marketo Engage檔案中使用[指示](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"}。

   * 為DKIM MAIL FROM網域設定DMARC。

  >[!NOTE]
  >
  >建議使用DKIM對齊進行Marketo Engage。

* **SPF** （寄件者原則架構）對齊： `From:`標頭中的網域必須符合Return-Path：標頭中的網域。 如果兩個DNS網域相同，則SPF會比對（對齊）並提供傳遞結果。 若要實作SPF校準的DMARC：

   * 設定品牌化的Return-Path網域。

      * 設定適當的SPF記錄。
      * 變更MX記錄，以指向郵件傳送來源資料中心的預設MX

   * 為品牌化傳迴路徑網域設定DMARC 。

  >[!NOTE]
  >
  >Marketo Engage不支援或建議使用嚴格的SPF對齊。

### 專用IP和共用集區

如果您透過專用IP的Marketo Engage傳送郵件，但尚未實作標籤傳迴路徑（或不確定您是否有），請開啟具有[Adobe支援](https://experienceleague.adobe.com/home?lang=en&amp;support-tab=home#support){target="_blank"}的票證。

信任的IP是共用IP集區，保留給每月傳送少於75,000的低容量使用者，且不符合專用IP的資格。 這些使用者也必須符合最佳實務需求。

* 如果您使用共用IP集區透過Marketo Engage傳送郵件，您可以透過[套用受信任的IP傳送範圍程式](https://na-sjg.marketo.com/lp/marketoprivacydemo/Trusted-IP-Sending-Range-Program.html){target="_blank"}來檢查您是否符合受信任的IP資格。 從Marketo Engage受信任的IP傳送時，會包含標籤傳迴路徑。 如果核准此方案，請聯絡Adobe支援以設定品牌傳迴路徑。

* 如果您每月傳送超過100,000則訊息，並想使用共用IP透過Marketo Engage傳送電子郵件，請聯絡Adobe客戶團隊（您的客戶經理）以購買專用IP。

## 為您的網域設定MX記錄

MX記錄可讓您接收寄送電子郵件至之網域的郵件，以處理回覆和自動回應者。 如果您要從公司網域傳送，則可能已設定該網域。 如果沒有，您通常可以將其設定為對應到您的公司網域MX記錄。

## 傳出IP位址

輸出連線是指Marketo Engage代表您連線至網際網路上的伺服器。 您的IT組織和某些合作夥伴/廠商可能會使用允許清單來限制對伺服器的存取。 若是如此，您必須提供Marketo Engage的輸出IP位址區塊，以新增至其允許清單。

<!-- ### Webhooks

Marketo Engage webhooks are an outbound integration mechanism. When a Smart Campaign executes a _Call Webhook_ flow action, it makes an HTTP request to an external web service. If the web service publisher uses an allowlist on the firewall of the network where the external web service is located, the publisher must add the IP address blocks listed below to their allowlist. For more information, see [Create a webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/additional-integrations/create-a-webhook){target="_blank"} and [Call Webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-campaigns/flow-actions/call-webhook){target="_blank"} in the Marketo Engage documentation.

### CRM sync

Marketo Engage Salesforce CRM Sync and Microsoft Dynamics Sync are integration mechanisms that make outbound HTTP requests to APIs published by your CRM vendor. Ensure that your IT organization does not block any of the IP address blocks below from accessing your CRM vendor APIs. For more information, see [Add an Existing Salesforce Field to the Marketo Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/salesforce-sync/sfdc-sync-details/add-an-existing-salesforce-field-to-the-marketo-sync){target="_blank"} and [Understanding the Microsoft Dynamics Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/microsoft-dynamics/understanding-the-microsoft-dynamics-sync){target="_blank"} in the Marketo Engage documentation. -->

## 輸出IP位址區塊

下列清單涵蓋進行傳出呼叫的所有Marketo Engage伺服器。 請參閱這些清單，以設定IP允許清單、伺服器、防火牆、存取控制清單、安全性群組或協力廠商服務，接收來自Marketo Engage的傳出連線。

| IP區塊（CIDR標籤法） | 個別IP位址 |
| ------------------------ | --------------------- |
| <ul><li>`94.236.119.0/26`</li><li>`103.237.104.0/22`</li><li>`130.248.172.0/24`</li><li>`130.248.173.0/24`</li><li>`130.248.244.88/29`</li><li>`185.28.196.0/22`</li><li>`192.28.144.0/20`</li><li>`192.28.160.0/19`</li><li>`199.15.212.0/22`</li></ul> | <ul><li>`13.237.155.207`</li><li>`13.55.192.247`</li><li>`18.200.201.81`</li><li>`34.247.24.245`</li><li>`35.165.244.220`</li><li>`44.235.171.179`</li><li>`52.20.211.99`</li><li>`52.64.109.86`</li><li>`54.160.246.246`</li><li>`54.212.167.17`</li><li>`54.220.138.65`</li><li>`54.237.141.197`</li><li>`130.248.168.16`</li><li>`130.248.168.17`</li></ul> |
