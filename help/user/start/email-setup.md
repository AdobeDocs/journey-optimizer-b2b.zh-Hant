---
title: 電子郵件設定
description: 預留位置
feature: Setup, Channels
role: Admin
source-git-commit: 55ffa7995a8d74d352a52f14bed5dd89d7d1c239
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 0%

---

# 電子郵件設定

若要支援附加的Marketo Egage例項所提供的電子郵件傳遞基礎結構，請設定下列電子郵件選項。 Marketo Engage產品管理員可以瀏覽至Marketo Engage執行個體中的&#x200B;**[!UICONTROL 管理員]**&#x200B;區域並選取&#x200B;**[!UICONTROL 電子郵件]**，以設定這些設定。

## 電子郵件設定

若要為附加的Marketo Engage執行個體設定電子郵件預設值，請變更設定值以反映行銷組織的使用情況。

### 從電子郵件和標籤

變更寄件者電子郵件和標籤的值，讓新電子郵件自動填入這些預設值。

>[!NOTE]
>
>這項變更僅適用於您建立的電子郵件，不適用於其他Marketo Engage或Journey Optimizer B2B edition使用者。

1. 移至附加的Marketo Engage執行個體中的&#x200B;**[!UICONTROL 管理員]**&#x200B;區域，並選取&#x200B;**[!UICONTROL 電子郵件]**。

1. 在「_[!UICONTROL 設定]_」面板中，輸入您想要的「**[!UICONTROL 來自電子郵件]**」和「**[!UICONTROL 來自標籤]**」預設值。

   ![電子郵件設定 — 寄件者電子郵件和寄件者標籤預設值](./assets/me-admin-email-settings-from.png){width="500"}

1. 按一下&#x200B;**[!UICONTROL 儲存變更]**。

### 取消訂閱訊息傳送

對於非營運行銷電子郵件，取消訂閱文字和連結會附加在底部。 作為產品管理員，您應該設定預設的HTML，以及當行銷人員未將電子郵件標籤為可操作時填入的文字。

1. 移至附加的Marketo Engage執行個體中的&#x200B;**[!UICONTROL 管理員]**&#x200B;區域，並選取&#x200B;**[!UICONTROL 電子郵件]**。

1. 在「_[!UICONTROL 設定]_」面板中，輸入您要用於&#x200B;**[!UICONTROL 取消訂閱HTML]**&#x200B;和&#x200B;**[!UICONTROL 取消訂閱文字]**&#x200B;的預設值。

   >[!TIP]
   >
   >行銷人員可以使用系統權杖，變更取消訂閱HTML在電子郵件中的位置。

   ![電子郵件設定 — 取消訂閱HTML和取消訂閱文字預設值](./assets/me-admin-email-settings-unsubscribe.png){width="500"}

   >[!CAUTION]
   >
   >下列變數至關重要。**請勿刪除**&#x200B;它們。
   >
   >* `%mkt_opt_out_prefix%`
   >* `mkt_unsubscribe=1&mkt_tok=##MKT_TOK##`

1. 按一下&#x200B;**[!UICONTROL 儲存變更]**。

如果您需要恢復為預設系統內容，請複製並貼上下列內容：

+++ 系統預設取消訂閱文字

```
<p><font face="Verdana" size="1">If you no longer wish to receive these emails, click on the following link: <a href="%mkt_opt_out_prefix%UnsubscribePage.html?mkt_unsubscribe=1&mkt_tok=##MKT_TOK##">Unsubscribe</a><br/></font></p>` [!UICONTROL Unsubscribe Text]:
%mkt_opt_out_prefix%UnsubscribePage.html?mkt_unsubscribe=1&mkt_tok=##MKT_TOK##
```

+++

### 以網頁檢視

電子郵件內容的顯示功能有限（CSS有限，無JavaScript或表單）。 行銷人員可使用&#x200B;_以網頁形式檢視_&#x200B;選項，透過Marketo Munchkin為電子郵件收件者套用Cookie。 作為產品管理員，您應該設定預設的HTML，以及行銷人員選擇此選項時填入的文字。

1. 移至附加的Marketo Engage執行個體中的&#x200B;**[!UICONTROL 管理員]**&#x200B;區域，並選取&#x200B;**[!UICONTROL 電子郵件]**。

1. 在&#x200B;_[!UICONTROL 設定]_&#x200B;面板中，變更&#x200B;**[!UICONTROL 以網頁HTML檢視]**&#x200B;和&#x200B;**[!UICONTROL 以網頁文字檢視]**&#x200B;欄位中的內容，以反映您的語調和訊息。

   ![電子郵件設定 — 以網頁檢視HTML和以網頁文字檢視預設值](./assets/me-admin-email-settings-view-as-web-page.png){width="500"}

   >[!CAUTION]
   >
   >下列變數至關重要。**請勿刪除**&#x200B;它們。
   >
   >`%mkt_webview_url%?mkt_tok=##MKT_TOK##`
   >
   >第二部分`##MKT_TOK##`是該人員的Munchkin Cookie。 這可確保在電子郵件收件者按一下連結時，正確套用Cookie。
   >
   >請務必避免：
   >
   >* 在任一HTML方塊中新增其他URL
   >* 將HTML放在文字版本中

1. 按一下&#x200B;**[!UICONTROL 儲存變更]**。

如果您需要恢復為預設系統內容，請複製並貼上下列內容：

+++ 系統預設網頁HTML

```
<div style="text-align: center"><font face="Verdana" size="1">To view this email as a web page, <a href="%mkt_webview_url%?mkt_tok=##MKT_TOK##">click here</a></font></div>
```

+++

+++ 系統預設網頁文字

```
To view this email as a web page, go to the following address:
`%mkt_webview_url%?mkt_tok=##MKT_TOK##`
```

+++

## 自訂物件擷取限制

如果您使用[!DNL Velocity Script]在電子郵件中顯示自訂物件資料，請調整父自訂物件擷取限制。 根據預設，此限制允許從Velocity指令碼存取10個父級自訂物件。 如有需要，您可以提高此限制。

[[!DNL Apache Velocity]](https://velocity.apache.org/)是建置在[!DNL Java]上的語言，專為範本化和指令碼HTML內容而設計。 Marketo Engage電子郵件基礎結構透過指令碼權杖支援其在電子郵件內容中的使用，該權杖可提供對儲存在自訂物件中之資料的存取權。

您可以參照直接連線到潛在客戶或連絡人的父項和子項自訂物件，但不能參照第三級自訂物件。 對於每個自訂物件，每個人員/連絡人的10個最近更新記錄可在執行階段使用，並依照最近更新（在`0`）到最舊更新（在`9`）的順序排列。

若要變更限制(_T):_

1. 移至附加的Marketo Engage執行個體中的&#x200B;**[!UICONTROL 管理員]**&#x200B;區域，並選取&#x200B;**[!UICONTROL 電子郵件]**。

1. 捲動至&#x200B;_[!UICONTROL 自訂物件擷取限制]_&#x200B;面板，並在&#x200B;**[!UICONTROL 父擷取限制]**中輸入新值
欄位。

   ![Marketo Engage電子郵件管理員 — 自訂物件擷取限制預設值](./assets/me-admin-email-custom-object-retrieval-limits.png){width="500"}

   支援介於10到100之間的值。 _[!UICONTROL 子擷取限制]_&#x200B;是以1000除以父限制來自動設定的。 例如，如果您將父限制設為50，子限制的計算方式為20 (1000 ÷ 50 = 20)。

1. 按一下&#x200B;**[!UICONTROL 儲存變更]**。

## 自訂標頭選項

變更電子郵件的&#x200B;_[!UICONTROL 自訂標題選項]_&#x200B;以設定電子郵件追蹤連結標題。 啟用這些選項，以使用使用嚴格傳輸的HTTPS實作安全追蹤連結。

1. 移至附加的Marketo Engage執行個體中的&#x200B;**[!UICONTROL 管理員]**&#x200B;區域，並選取&#x200B;**[!UICONTROL 電子郵件]**。

1. 捲動至&#x200B;_[!UICONTROL 自訂標題選項]_&#x200B;面板，並根據您的追蹤連結原則變更設定：

   ![Marketo Engage電子郵件管理員 — 自訂標頭選項預設設定](./assets/me-admin-email-custom-object-retrieval-limits.png){width="500"}

   * **[!UICONTROL 嚴格傳輸安全性]** — 將此選項設定為「已啟用」，可保證追蹤連結一律透過HTTPS提供（只應針對追蹤連結受SSL保護的訂閱設定）。
   * **[!UICONTROL Max-age]** — 此欄位支援必要指示詞，以秒為單位指定瀏覽器應記得僅透過HTTPS存取網域的時間。
   * **[!UICONTROL IncludeSubDomains]** — 使用此選項可包含將HSTS原則套用至主機所有子網域的指示詞。

   >[!IMPORTANT]
   >
   >請與您的IT團隊一起檢閱這些設定，以確保符合您組織的原則。 不正確的設定可能會讓某些訪客無法存取您的電子郵件連結。

1. 按一下&#x200B;**[!UICONTROL 儲存變更]**。

## 篩選電子郵件機器人活動 {#filter-email-bots}

電子郵件機器人活動(也稱為非人類互動(NHI))可能會誇大您的電子郵件&#x200B;_開啟_&#x200B;和&#x200B;_點按_&#x200B;資料，扭曲您的參與量度，並觸發事件型歷程進度。 使用電子郵件機器人篩選來維持點選參與量度和深入分析的完整性。 識別疑似機器人活動的方法有兩種：

* _**[!UICONTROL 與IAB機器人清單相符]**_ — 與[Interactive Advertising Bureau機器人清單](https://www.iab.com/guidelines/iab-abc-international-spiders-bots-list/){target="_blank"} （使用者代理程式/IP位址）上的任何專案相符的活動會標示為機器人。
* _**[!UICONTROL 符合近似程度模式]**_ — 將同時發生的兩個或多個活動（在一秒以內）識別為機器人。 比較期間考慮的屬性包括：
   * 銷售機會ID （應相同）
   * 電子郵件資產（應相同）
   * 連結點選或電子郵件開啟

對於電子郵件連結點選和電子郵件開啟活動，屬性會填入下列值：

* 識別為機器人的活動 — _機器人活動_ = `true`和&#x200B;_機器人活動模式_ =識別的模式/方法
* 識別為非機器人的活動 — _機器人活動_ = `false`和&#x200B;_機器人活動模式_ = `n/a`

### 設定篩選器

1. 移至附加的Marketo Engage執行個體中的&#x200B;**[!UICONTROL 管理員]**&#x200B;區域，並選取&#x200B;**[!UICONTROL 電子郵件]**。

1. 選取&#x200B;**[!UICONTROL 機器人活動]**&#x200B;標籤。

   ![Marketo Engage電子郵件管理員 — 機器人活動標籤](./assets/me-admin-email-bot-activity.png){width="700" zoomable="yes"}

   「機器人活動識別」面板會顯示兩個滑桿，可用來識別機器人活動。

1. 切換滑桿以啟用其中一項或兩項。

   針對您啟用的每個方法，選擇&#x200B;_[!UICONTROL 記錄機器人活動]_&#x200B;或&#x200B;_[!UICONTROL 篩選機器人活動]_。

   >[!IMPORTANT]
   >
   >如果選擇[!UICONTROL 篩選機器人活動]，您可能會看到電子郵件開啟次數和點按次數減少，因為會排除錯誤的活動。

   ![Marketo Engage電子郵件管理員 — 機器人活動識別選項](./assets/me-admin-email-bot-activity-set-filters.png){width="500"}

   針對&#x200B;_[!UICONTROL 與近似程度模式相符]_，您也可以設定活動之間&#x200B;**[!UICONTROL 持續時間]**&#x200B;的秒數（預設為`0`，最大為`3`）。

   >[!NOTE]
   >
   >當&#x200B;_活動_&#x200B;之間的持續時間`0`秒設定時，Marketo Engage會識別在同一秒發生的電子郵件活動。 如果在指定的秒數內發生多個電子郵件活動，則會將其識別為機器人活動。

   若要停用任一篩選方法，請將滑桿切換至左側。 如果您這麼做，資料不會重設。

### IP封鎖清單

Adobe已找出負責產生數百萬個假參與的IP位址清單，例如從下列任何IP收到的這類參與會自動篩選掉，而不會新增至您的Marketo Engage執行個體。 此篩選可能會導致電子郵件開啟、點按及其他相關活動的減少。 此清單可能會定期更新。

+++ 封鎖的IP位址

* 40.94.34.52
* 40.94.34.86
* 52.34.76.65
* 54.70.53.60
* 54.71.187.124
* 60.28.2.248
* 64.235.150.252
* 64.235.153.10
* 64.235.153.2
* 64.235.154.105
* 64.235.154.109
* 64.235.154.140
* 64.74.215.1
* 64.74.215.100
* 64.74.215.138
* 64.74.215.139
* 64.74.215.142
* 64.74.215.146
* 64.74.215.150
* 64.74.215.154
* 64.74.215.158
* 64.74.215.162
* 64.74.215.164
* 64.74.215.166
* 64.74.215.170
* 64.74.215.174
* 64.74.215.176
* 64.74.215.178
* 64.74.215.51
* 64.74.215.56
* 64.74.215.58
* 64.74.215.59
* 64.74.215.86
* 64.74.215.98
* 65.154.226.101
* 66.249.91.149
* 70.42.131.106
* 74.125.217.116
* 74.217.90.250
* 104.129.41.4
* 104.47.55.126
* 104.47.58.126
* 104.47.70.126
* 104.47.73.126
* 104.47.73.254
* 104.47.74.126
* 128.220.160.1
* 155.70.39.101
* 162.129.251.14
* 162.129.251.42
* 208.52.157.204

>[!NOTE]
>
>每個IP位址都經過仔細的分析和檢查，才會列入此清單，以確保只有最關鍵和最有害的IP會被封鎖。

+++

