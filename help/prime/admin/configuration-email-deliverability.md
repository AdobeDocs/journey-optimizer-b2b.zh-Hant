---
title: 電子郵件傳遞能力與通道設定
description: 為Journey Optimizer B2B Prime設定子網域委派、DMARC、SPF、DKIM、IP集區和電子郵件通道設定。
autotag-review: '2026-06-12T22:43:42.799Z'
TQID: 'https://experienceleague.adobe.com/RKZSQkjSRvHixOm2faRT5D-yB00IykXfPO06vvIUQ6k'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: d6e625c1-468f-4d73-9f32-fd1edb87f96bid: f01b5556-e951-40ba-8625-2e3001864f2bid: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1fid: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 63d3583081b6581af9475505174142b0bbde9d81
workflow-type: tm+mt
source-wordcount: 3095
ht-degree: 1%

---

# 電子郵件傳遞能力與通道設定

下列資訊適用於設定傳送基礎架構以支援行銷人員和電子郵件作者的管理員。 它說明了傳遞功能、角色和許可權，以及如何設定子網域、驗證、IP池和通道設定。

如需有關在電子郵件設計空間建立電子郵件和撰寫電子郵件內容的詳細資訊，請參閱[電子郵件撰寫](../content/email-authoring.md)。

## 重要概念 {#key-concepts}

在設定電子郵件之前，請檢閱這些適用於電子郵件通道傳遞能力的概念：

| 概念 | 在[!DNL Journey Optimizer B2B Edition] Prime中的意義 |
| ------- | ---------------------- |
| **_頻道設定_** | 可重複使用的一組電子郵件傳送設定 — 包括寄件者身分、回覆位址、子網域、IP集區、電子郵件型別（行銷或異動）及追蹤 — 可附加至歷程中的電子郵件動作。 您可以對不同品牌、業務單位或傳送型別擁有多個已命名管道設定。 |
| **_子網域_** | 您用來透過Prime傳送電子郵件的傳送網域委派部分（例如，`mail.contoso.com`）。 子網域會將您的B2B行銷信譽與公司或交易郵件隔離。 |
| **_IP集區_** | 與一或多個子網域相關聯的一組IP位址。 在此版本中，Prime支援由Adobe管理的共用IP集區；專用IP集區位於GA藍圖上。 |

## 角色和許可權 {#roles-permissions}

[!DNL Journey Optimizer B2B Edition] Prime對電子郵件功能使用角色型存取控制(RBAC)。 許可權是在Adobe Admin Console (IMS)中管理，並在登入時同步。 產品管理員會為產品設定檔指派精細的許可權，然後將這些產品設定檔附加至使用者。

在[!DNL Journey Optimizer B2B Edition] Prime中存取電子郵件功能是由兩個層級所控制：

1. **功能標幟(LD)。** LaunchDarkly標幟可控制是否針對您的組織開啟整個功能。 電子郵件製作與傳遞能力由`dx_ajo_btob_channel_foundation`控制。 若沒有此標幟，則無論許可權為何，都會隱藏功能。
2. **功能許可權。** 使用者層級的許可權，可控制特定使用者是否可以在功能內讀取或寫入。

大多數電子郵件功能都遵循`view-*` （讀取）和`manage-*` （寫入）模式。 使用者需要讀取許可權才能在導覽中檢視功能，需要寫入許可權才能在其中建立、編輯或刪除。

### 電子郵件編寫許可權 {#email-authoring-permissions}

| 功能 | 權限 | 它允許 |
| ---------- | ---------- | -------------- |
| **檢視電子郵件** | `view-b2b-emails` | 檢視電子郵件清單、開啟電子郵件、檢視內容（唯讀）。 |
| **建立/編輯/刪除電子郵件** | `manage-b2b-emails` | 所有讀取存取權以及建立、編輯、複製和刪除電子郵件。 在歷程中編寫電子郵件內容時需要。 |
| **檢視範本** | `view-b2b-templates` | 在範本庫中瀏覽和預覽範本（唯讀）。 |
| **建立/編輯/刪除範本** | `manage-b2b-templates` | 所有讀取存取權以及建立、編輯和刪除已儲存的範本。 |
| **檢視片段** | `view-b2b-fragments` | 瀏覽和預覽視覺片段（唯讀）。 |
| **建立/編輯片段** | `manage-b2b-fragments` | 所有讀取存取權以及建立和編輯視覺化片段。 |
| **發佈片段** | `publish-b2b-fragments` | 發佈片段，讓組織的電子郵件作者都能使用。 |
| **管理共用資產和程式庫專案** | `manage-b2b-library-items` | 管理範本、片段及電子郵件使用的基礎共用程式庫。 通常與範本/片段管理許可權一起授予。 |
| **管理使用標籤** | `manage-b2b-delete-usage-labels` | 管理附加到程式庫專案以供控管的資料使用標籤(DULE)。 |
| **管理封裝** | `manage-b2b-packages` | 在沙箱之間繫結和移動範本、片段和電子郵件。 |
| **檢視資產（Prime中的Marketo Design Studio資產）** | `view-b2b-assets` | 瀏覽資產選擇器並預覽影像。 唯讀。 |
| **管理資產** | `manage-b2b-assets` | 所有讀取存取權加上未來的資產管理動作（Beta範圍）。 |
| **匯出訊息資料** | `manage-b2b-message-export` | 匯出電子郵件層級的訊息資料和報表。 |

在人員歷程中，**傳送電子郵件**&#x200B;動作需要`manage-b2b-person-journeys` （以新增動作並啟用歷程）。 僅具有電子郵件許可權的使用者可以編寫內容，但無法將電子郵件新增到歷程中。

### 電子郵件傳遞能力許可權 {#email-deliverability-permissions}

傳遞功能（子網域、DMARC、IP集區、隱藏清單、允許清單、IP熱身計畫和種子清單）是管理員層級的設定。 它們受涵蓋整個&#x200B;**[!UICONTROL 管道]** > **[!UICONTROL 電子郵件設定]**&#x200B;區域的兩個許可權所控管：

| 功能 | 權限 | 它允許 |
| ---------- | ---------- | -------------- |
| **檢視電子郵件設定** | `view-b2b-email-settings` | 檢視子網域、PTR記錄、IP集區、隱藏清單、允許清單、IP熱身計畫和種子清單（唯讀）。 |
| **管理電子郵件設定** | `manage-b2b-email-settings` | 所有讀取存取權加上委派子網域、設定DMARC、管理隱藏和允許清單、管理IP熱身計畫和種子清單。 |

電子郵件設定中的部分子功能被其他LaunchDarkly旗標所限制 — 隱藏清單(`enable-suppression`)、允許清單(`enable-allow-list`)、種子清單(`enable-seedlist-ui`)。 如果您的組織中看不到子功能，請洽詢您的Adobe代表以啟用標幟。

### 頻道設定許可權 {#channel-configuration-permissions}

管道設定位於&#x200B;**[!UICONTROL 管道]** → **[!UICONTROL 一般設定]**&#x200B;下。 他們會將可傳遞性原件（子網域、IP集區、傳送者身分）繫結至歷程作者參考的可重複使用物件。 它們由單一許可權所控管：

| 功能 | 權限 | 它允許 |
| ---------- | ---------- | -------------- |
| **管理頻道設定** | `manage-b2b-channels-configurations` | 檢視、建立、編輯和刪除電子郵件通道設定。 |

## 電子郵件傳遞能力概觀 {#deliverability-overview}

[!DNL Journey Optimizer B2B Edition] Prime中的電子郵件傳遞能力是一組基礎架構和驗證設定，可協助電子郵件訊息到達收件者的收件匣，而非垃圾郵件資料夾，且不會被ISP （網際網路服務提供者）封鎖。

這會使用以下建置區塊，由管理員設定，通常依照以下順序：

1. 委派一或多個子網域至Adobe。
1. 在每個子網域上設定DMARC、SPF和DKIM記錄。
1. 確認將為您的子網域傳送電子郵件的IP集區。
1. 建立一個或多個電子郵件通道設定，以繫結子網域、IP集區和寄件者身分。
1. 在歷程電子郵件動作中使用這些管道設定。

>[!TIP]
>
>將傳遞能力設定視為每個業務單位或品牌的一次性管理員活動。 設定後，行銷人員和電子郵件作者就不需要重新造訪。

## 子網域委派 {#subdomain-delegation}

子網域委派會告訴網際網路，Adobe已獲得授權，可以代表您網域的特定子網域（例如，`mail.contoso.com`）傳送電子郵件。 委派專屬子網域（而非您的根網域）可保護您的公司郵件，並導致

* **信譽隔離。** 行銷傳送與公司郵件會分開。 如果行銷信譽下降，您的交易和公司郵件不受影響。
* **更快速的IP熱身。** 專用子網域可協助透過ISP更快建立正面的傳送者信譽。
* **新式驗證。** SPF、DKIM和DMARC可針對每個子網域進行徹底的設定，而不會影響其他郵件流程。
* **法規遵循。** 協助滿足Gmail、Yahoo和其他主要ISP的大量寄件者需求。

>[!NOTE]
>
>Prime中的每個子網域只能由一個Adobe產品使用。 您無法在Prime和其他產品（例如Adobe Marketo Engage或Adobe Campaign）之間共用相同的傳送子網域，您必須使用不同的子網域。

### 支援的方法

Prime支援Alpha的三種子網域委派方法中的兩種。 第三個方法（自訂委派）在藍圖上。

| 方法 | 使用時機 | 它包含的內容 |
| ------ | ----------- | ---------------- |
| **已完全委派** | 推薦 | 將子網域的完整DNS授權委派給Adobe。 Adobe會建立及維護MX、SPF、DKIM、DMARC、A和CNAME記錄。 最低的營運負荷。 Adobe會為您處理DNS變更。 |
| **CNAME** | 針對受限制的原則 | 將DNS授權保留在您的身邊，並建立指向Adobe管理記錄的CNAME記錄。 當貴組織的DNS原則不允許完全委派時，請使用此選項。 您有責任維護DNS記錄。 |
| **自訂委派** | 藍圖(GA) | 維護DNS和SSL憑證的完整所有權。 提供最大程度的控制，包括使用您自己的憑證的能力。 此目標為GA版本。 |

### 委派子網域（完全委派方法） {#delegate-fully-delegated}

>[!PREREQUISITES]
>
>* 決定子網域命名慣例（例如，`mail.contoso.com`代表行銷，`alerts.contoso.com`代表異動）。
>* 向您的IT/DNS團隊確認他們可以將子網域（NS記錄）委派給Adobe。
>* 在您的DNS提供者中建立新的子網域，然後等候24到48小時讓DNS傳播，再委派給Adobe。
>* 確認您擁有Prime中的管理員角色。

1. [!DNL Adobe Journey Optimizer B2B Edition] Prime，瀏覽至&#x200B;**[!UICONTROL 管理]** → **[!UICONTROL 管道]** → **[!UICONTROL 電子郵件設定]** → **[!UICONTROL 子網域]**。
1. 按一下&#x200B;**[!UICONTROL 設定子網域]**。
1. 輸入完整子網域名稱（例如，`mail.contoso.com`）。
1. 選擇&#x200B;**[!UICONTROL 完全委派]**&#x200B;作為委派方法。
1. 設定子網域的DMARC （請參閱[DMARC、SPF和DKIM](#dmarc-spf-dkim)）。

   至少需使用開始原則`none`來設定DMARC記錄，以便監視報告而不影響傳遞。

1. 檢視Adobe要管理的DNS記錄清單。

   這些通常包括MX、SPF、DKIM、DMARC、A和CNAME記錄（用於追蹤和映象頁面URL）。

1. 使用&#x200B;**[!UICONTROL 下載記錄]**&#x200B;按鈕將DNS記錄下載為CSV檔案。 與您的DNS團隊共用此檔案。

1. 您的DNS團隊會在您的網域託管解決方案中新增NS記錄，該解決方案會將子網域委派給Adobe。

1. 在您的DNS團隊確認記錄已就緒後，請返回[!DNL Journey Optimizer B2B Edition] Prime並核取方塊，確認您已在代管網站上建立所需記錄。

1. 按一下「**[!UICONTROL 提交]**」以啟動一系列驗證檢查（預先驗證、MX、SPF、DKIM、DMARC、FBL註冊）。

1. 等候子網域狀態變更為&#x200B;**[!UICONTROL 成功]**。

   DNS傳播完成後，這通常需要幾分鐘的時間。

>[!NOTE]
>
>如果驗證失敗，狀態會變更為&#x200B;**[!UICONTROL 失敗]**，[!DNL Journey Optimizer B2B Edition]Prime會顯示原因（例如，找不到NS記錄、遺失MX記錄或DMARC設定錯誤）。 請修正基礎DNS問題，然後重試提交。

### 委派子網域（CNAME方法） {#delegate-cname}

只有在貴組織的DNS原則禁止完全委派時，才使用此方法。 使用CNAME時，您可以自行維護DNS記錄。

1. 在[!DNL Adobe Journey Optimizer B2B Edition] Prime中，瀏覽至&#x200B;**[!UICONTROL 管理]** → **[!UICONTROL 管道]** → **[!UICONTROL 電子郵件設定]** → **[!UICONTROL 子網域]**。
1. 按一下&#x200B;**[!UICONTROL 設定子網域]**。
1. 輸入完整子網域名稱。
1. 選擇&#x200B;**[!UICONTROL CNAME]**&#x200B;做為委派方法。
1. 設定子網域的DMARC （[DMARC、SPF和DKIM](#dmarc-spf-dkim)）。
1. 檢閱Prime產生的CNAME記錄清單 — 這些會將您子網域的元件指向Adobe管理的記錄。
1. 將記錄下載為CSV檔並與您的DNS團隊共用。
1. 您的DNS團隊會將每個CNAME記錄新增到您的DNS託管解決方案。
1. 記錄就緒並傳播後，請返回Prime並確認。 按一下&#x200B;**[!UICONTROL 提交]**。
1. 等待狀態達到&#x200B;**[!UICONTROL 成功]**。

>[!IMPORTANT]
>
>使用CNAME時，Adobe無法協助您變更、維護子網域的DNS，或針對其進行疑難排解。 任何未來的變更（例如新增功能更新的CNAME）都必須由您的DNS團隊進行。

### 子網域護欄 {#subdomain-guardrails}

* **預設限制：**&#x200B;每個組織10個子網域。 如果您需要更多（根據合約，最多100個），請聯絡您的Adobe代表。
* **DNS傳輸：**&#x200B;允許24到48小時讓變更在全域傳播。 驗證可能會失敗，因為DNS尚未傳播。
* **子網域重複使用：**&#x200B;其他Adobe產品(Marketo Engage、Adobe Campaign)已使用的子網域無法在Prime中重複使用。

## DMARC、SPF和DKIM {#dmarc-spf-dkim}

DMARC、SPF和DKIM是電子郵件驗證標準。 一起向接收郵件伺服器證明您的郵件確實是以您網域的名義傳送，而且未受到欺騙。 現代ISP — Gmail、Yahoo、Microsoft — 需要這些標準才能大量傳送郵件。

| 記錄 | 表示 | 用途 |
| ------ | ---------- | ------- |
| **SPF** | 寄件者原則架構 | 列出允許從您的網域傳送郵件的郵件伺服器IP。 接收伺服器會拒絕來自不在此清單上IP的郵件。 當您委派子網域（已完全委派）時，Adobe會自動建立及維護SPF記錄。 |
| **DKIM** | DomainKeys識別的郵件 | 每個傳出電子郵件都新增了密碼編譯簽章。 接收伺服器會根據DNS中發佈的公開金鑰來驗證簽章。 在子網域委派期間，Adobe會自動產生DKIM金鑰和DNS記錄。 |
| **DMARC** | 網域型訊息驗證、報告和符合性 | 告訴接收伺服器如果SPF或DKIM失敗該怎麼做 — 並提供有關驗證結果的報告。 DMARC有三種原則模式：無、隔離和拒絕。 |

### DMARC原則模式

| 原則 | 動作 | 使用時機 |
| ------ | ------ | ----------- |
| `none` | 監視 | 如果DMARC失敗，接收伺服器不會執行任何動作，但仍會傳送報表。 首次委派子網域以確認驗證運作正常，且不會出現訊息遺失風險時，請使用此選項。 |
| `quarantine` | 隔離 | 接收伺服器會將失敗的郵件放入垃圾郵件/垃圾郵件資料夾。 |
| `reject` | 拒絕 | 接收伺服器會拒絕（退回）驗證失敗的訊息。 最嚴格的模式。 一旦您對驗證設定有信心，就建議使用。 |

### 設定DMARC {#configure-dmarc}

DMARC是在委派子網域時進行設定，但您也可以為已委派的子網域新增或更新DMARC 。

1. 瀏覽至&#x200B;**[!UICONTROL 管理]** → **[!UICONTROL 管道]** → **[!UICONTROL 電子郵件設定]** → **[!UICONTROL 子網域]**。

1. 在「子網域」清單中，找出您的子網域並勾選「DMARC記錄」欄。

   如果缺少記錄，則會顯示警報。

1. 開啟子網域並捲動至DMARC記錄區段。

   * 如果父網域上已存在DMARC記錄，[!DNL Journey Optimizer B2B Edition] Prime會自動擷取值。 您可以保留或覆寫。
   * 如果記錄不存在，請選擇&#x200B;**[!UICONTROL 使用Adobe管理]**，Adobe會建立並託管DMARC記錄。

1. 設定原則： `none`、`quarantine`或`reject`。 從`none`開始，除非您的上層網域已有成熟的DMARC狀態。

1. （選用）設定其他DMARC標籤（`sp`用於子網域原則，`pct`用於百分比，`rua`和`ruf`用於報表地址）。

1. 若使用已完全委派，請按一下&#x200B;**[!UICONTROL 儲存]**。

   Adobe會自動套用記錄。 如果使用CNAME，請複製DNS記錄並讓您的DNS團隊新增它，然後在[!DNL Journey Optimizer B2B Edition] Prime中確認。

1. 允許DNS傳播最多48小時，然後驗證子網域頁面上的DMARC狀態指標是綠色/狀況良好。

>[!TIP]
>
>從`policy=none`開始以監視驗證報告，然後進展到`quarantine`，最後在您的報告顯示健康的SPF和DKIM對齊時再進展到`reject`。 直接移至`reject`而不進行監視，可能會導致合法郵件遭到拒絕。

## IP集區 {#ip-pools}

IP集區是用來傳送電子郵件的已命名IP位址群組。 IP集區對傳送者信譽至關重要：每個集區在ISP中都有自己的信譽，因此一個集區的問題（例如觸發垃圾郵件投訴的行銷突發事件）不會汙染另一個集區（例如交易確認）。

### 集區型別

| 集區型別 | 可用性 | 說明 |
| --------- | ------------ | ----------- |
| **共用IP集區** | 可於Alpha取得 | 由Adobe管理並在許多客戶間共用的IP位址集區。 Adobe會在整個集區維護信譽。 最適合中低階電子郵件數量，以及不想管理IP熱身的客戶使用。 |
| **專用IP集區** | 藍圖(GA) | 一或多個IP位址僅分配給您的組織。 您擁有聲譽。 建議高容量寄件者使用。 包括IP熱身計畫和PTR記錄管理。 |

### 檢閱和指派IP集區 {#review-ip-pool}

在此版本中，會為您的組織預先布建IP集區。 您在建立電子郵件通道設定時指派IP集區。

1. 瀏覽至&#x200B;**[!UICONTROL 管理]** → **[!UICONTROL 管道]** → **[!UICONTROL 電子郵件設定]** → **[!UICONTROL IP集區]**。
1. 確認貴組織可以使用狀態為&#x200B;**[!UICONTROL 作用中]**&#x200B;的IP集區。
1. 將游標停留在集區上以檢視IP位址及其PTR記錄（反向DNS）。
1. 如果您的組織有多個業務單位或品牌，在建立管道設定之前，請先規劃如何使用IP集區（例如，行銷集區與網路研討會集區）。

>[!IMPORTANT]
>
>請勿在同一IP集區上混合行銷和異動流量，即使共用集區可供使用亦然。 管道設定上的電子郵件型別設定（行銷與交易）會控制隱藏行為，但您的管道設定仍應儘可能使用不同的集區。

## 電子郵件通道設定 {#email-channel-configurations}

管道設定是將您的傳送者身分識別、子網域、IP集區和追蹤設定繫結在一起的中央物件。 歷程中的電子郵件動作會參考頻道設定，以瞭解如何傳送訊息：

* **頻道：**&#x200B;電子郵件。
* **電子郵件型別：**&#x200B;行銷或異動。 此設定會決定是否套用隱藏規則（行銷會套用這些規則；交易會略過合法交易訊息的預設垃圾郵件投訴隱藏）。
* **標頭引數：**&#x200B;來自名稱、來自電子郵件、回覆名稱、回覆電子郵件、錯誤電子郵件。
* **子網域：**&#x200B;用於傳送的委派子網域。 寄件者電子郵件必須使用此子網域。
* **IP集區：**&#x200B;用來傳遞訊息的IP集區。
* **URL追蹤：**&#x200B;啟用或停用點選並開啟追蹤；設定追蹤網域。
* **標籤：**&#x200B;組織和搜尋的標籤。

### 建立電子郵件通道設定 {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* 至少必須委派一個子網域且處於作用中。
>* 至少必須指派一個IP集區給您的組織。
>* 您需要管理員角色。

1. 瀏覽至&#x200B;**[!UICONTROL 頻道]** → **[!UICONTROL 一般設定]** → **[!UICONTROL 頻道設定]**。
1. 按一下&#x200B;**[!UICONTROL 建立通道組態]**。
1. 輸入名稱（例如「Contoso B2B行銷 — 北美」）和選用的說明。
1. 選取&#x200B;**[!UICONTROL 電子郵件]**&#x200B;頻道。
1. 選擇性地選取標籤以將設定分類。
1. 在&#x200B;**[!UICONTROL 電子郵件型別]**&#x200B;區段中，選擇「行銷」或「異動」。
1. 在&#x200B;**[!UICONTROL 子網域]**&#x200B;區段中，選取先前委派的子網域。
1. 在&#x200B;**[!UICONTROL IP集區]**&#x200B;區段中，選取作用中IP集區。 您可以將游標停留在IP上以檢視PTR記錄。
1. 設定&#x200B;**[!UICONTROL 標頭引數]**：
   * 來源名稱（例如「Contoso行銷」）。
   * 來自電子郵件 — 必須使用選取的子網域（例如，`marketing@mail.contoso.com`）。
   * 回覆名稱與回覆電子郵件 — 若為空白，則預設為「從」。
   * 錯誤電子郵件 — 接收未傳遞通知的地址。
1. 啟用&#x200B;**[!UICONTROL URL追蹤]**&#x200B;並選取追蹤網域。
1. 按一下&#x200B;**[!UICONTROL 提交]**。
1. Prime執行驗證：子網域狀態、MX記錄、SPF/DKIM/DMARC校準、IP集區整備、FBL註冊。 組態會透過「草稿→處理」→「作用中」移動。

>[!NOTE]
>
>如果驗證失敗，組態會移至&#x200B;**[!UICONTROL 失敗]**&#x200B;狀態。 開啟設定以檢視失敗原因 — 常見的原因是MX記錄驗證失敗、集區中的IP不符合設定，或DMARC未對齊。 解決並重新提交。

### 編輯或刪除頻道設定 {#edit-channel-configuration}

您可以在建立後編輯管道設定，但有一個重要限制：

* 無法變更&#x200B;**頻道。** 設定已繫結至其通道。

編輯使用中的設定時：

* **對於已發佈的歷程：**&#x200B;此變更會在下次週期或下次執行時套用。 在執行中執行會繼續沿用先前的設定。
* **對於異動或即時訊息：**&#x200B;變更會在約五分鐘內傳播。

若要刪除設定，請先移除或更新參照它的每個電子郵件動作。[!DNL Journey Optimizer B2B Edition] Prime不會刪除作用中歷程目前使用的設定。

### 多頻道設定 {#multiple-channel-configurations}

大部分的B2B組織會使用多個管道設定來分隔品牌、區域或傳送型別。 常見模式：

* 每個業務單位的個別行銷組態（例如，*BU-A行銷*、*BU-B行銷*）。
* 產品或合約通知的專用交易式設定，其電子郵件型別=交易式。
* 使用區域特定子網域的區域特定設定（例如，`mail.eu.contoso.com`、`mail.us.contoso.com`）以符合區域ISP和法規遵循。

>[!TIP]
>
>以清楚、結構化的慣例命名您的組態 — 例如： *[品牌] - [地區] - [型別]*。 一旦您擁有十數個或更多組態，這一點就變得至關重要。

### 已知限制 {#known-limitations}

* 子網域委派的&#x200B;**自訂委派方法**&#x200B;尚無法使用 — 請使用「完全委派」或CNAME。 GA的目標為自訂委派。
* 在Alpha中無法使用&#x200B;**專用IP集區**。 共用IP集區是唯一的選項。 GA提供專屬的IP，包括IP熱身計畫和PTR記錄管理。
* 透過.html或.zip上傳的&#x200B;**HTML匯入**&#x200B;在Alpha受到限制。 完整的HTML匯入（包括程式碼編輯器+視覺畫布雙重檢視、驗證和內嵌CSS自動轉換）出貨於Beta。
* **Prime中的原生影像上傳和DAM** （上傳、組織、編輯）位於Beta藍圖上。 在此版本中使用Marketo Design Studio資產。 Marketo中的重新上傳不會反映在Prime中。
* **測試設定檔、模擬內容和傳送校樣**&#x200B;在此版本中無法使用。 Litmus呈現和以SpamAssassin為基礎的垃圾郵件報告都在Beta藍圖上。
* **此版本中無法使用帳戶層級的個人化和自訂物件資料**。 使用設定檔屬性。
* 正式發行時，現有Marketo範本的&#x200B;**Velocity-to-Handlebars自動移轉**。
* 在「快速後續追蹤」發行版本中，寄出&#x200B;**電子郵件**&#x200B;上的註解與共同作業（內嵌註解、@mentions、要求檢閱工作流程）。
* **AEM Assets、AEM內容片段和Adobe Express**&#x200B;整合在「快速後續追蹤」藍圖上。

<!--

### Frequently asked questions {#faq}

| Question | Answer |
| -------- | ------ |
| **Can I reuse the subdomain I already use in Marketo Engage?** | No. A subdomain can only be associated with one Adobe product at a time. Create a new subdomain (for example, mail2.contoso.com) for Prime. |
| **Why does my channel configuration show Failed?** | The most common reasons are: MX record validation failed (your subdomain DNS isn't fully configured); DMARC misalignment; or an IP pool that is in Processing and has never been associated with the selected subdomain. Open the configuration to see the specific reason. |
| **What happens if a personalization token has no value at send time?** | If you defined a fallback with the Handlebars `default` helper, the fallback is used. If not, the token resolves to an empty string. Prime warns you when a token has no fallback and the underlying attribute is not guaranteed by the audience definition. |
| **Can I personalize using account-level attributes?** | Not in this release. Personalization in Prime today supports profile attributes only. |
| **What's the maximum email size?** | 100 KB is the recommended best-practice cap for inbox rendering. Prime warns you in the editor if you exceed it. |
| **Can I migrate existing Marketo email templates into Prime?** | A guided self-serve migration tool — including Velocity-to-Handlebars conversion — is delivered at GA. In this release, you can manually rebuild templates or paste raw HTML. |
| **Will my updates to Marketo assets show up in Prime?** | No. Asset availability in Prime is based on a one-time copy from Marketo Design Studio. Re-uploaded or modified Marketo assets are not reflected in Prime today. Native asset upload and management within Prime is on the Beta roadmap. |

## Glossary {#glossary}

| Term | Definition |
| ---- | ---------- |
| **DKIM** | DomainKeys Identified Mail — cryptographic email signature. |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance. |
| **FBL** | Feedback Loop — a service ISPs offer to receive spam-complaint reports back to senders. |
| **Handlebars** | JavaScript templating language used in Prime for personalization expressions. |
| **IP pool** | Group of IP addresses used to send email. |
| **MX record** | Mail Exchange DNS record — directs incoming mail to the correct mail servers. |
| **NS record** | Name Server DNS record — used to delegate a subdomain. |
| **PTR record** | Pointer record — reverse DNS that maps an IP address back to a hostname. |
| **RBAC** | Role-Based Access Control. |
| **SPF** | Sender Policy Framework — DNS record listing authorized sending IPs. |
| **Subdomain delegation** | Granting Adobe authority over a portion of your domain (a subdomain) for sending email. |

-->
