---
title: 簡訊製作
description: 瞭解如何在其行動裝置上傳送簡訊(SMS)給您的客戶，以及從SMS編輯器使用文字格式個人化和預覽訊息。
feature: SMS Authoring, Content, Channels
role: User
exl-id: bd648253-74de-4083-a37a-ab7ceaea2746
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 3%

---

# 簡訊編寫

使用Adobe Journey Optimizer B2B edition傳送簡訊(SMS)給行動裝置上的客戶。 您可以從簡訊編輯器建立、個人化及預覽文字格式的訊息。

在建立帳戶歷程的SMS訊息之前，請確定[SMS服務提供者已由&#x200B;_[!UICONTROL 系統管理員]_&#x200B;設定設定](../admin/configure-channels-sms.md)。

## 在帳戶歷程中新增簡訊動作

當您新增&#x200B;_[!UICONTROL 採取動作]_&#x200B;節點並執行下列動作時，可以在帳戶歷程中設定文字訊息傳遞：

1. 針對&#x200B;_目標上的_&#x200B;動作，請選擇&#x200B;**[!UICONTROL 人員]**。

1. 針對人員&#x200B;_上的_&#x200B;動作，請選擇&#x200B;**[!UICONTROL 傳送簡訊]**。

   ![採取動作 — 傳送簡訊](assets/journey-node-send-sms.png){width="800" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 執行動作]_&#x200B;面板底部，按一下&#x200B;**[!UICONTROL 建立簡訊]**。

1. 在對話方塊中，輸入簡訊的唯一名稱&#x200B;**[!UICONTROL 名稱]**。

   ![建立新的簡訊對話方塊](assets/create-new-sms.png){width="400"}

1. 按一下&#x200B;**[!UICONTROL 建立]**。

   _歷程圖_&#x200B;開啟，您可以建立訊息並設定用於傳送訊息的SMS屬性。

### 建立簡訊訊息

>[!IMPORTANT]
>
>**簡訊同意管理**<br/>
>
>根據業界標準及法規，所有簡訊行銷訊息都必須包含讓收件者輕鬆取消訂閱的方式。 要執行此操作，簡訊收件者可以使用選擇加入和選擇退出關鍵字進行回覆。 支援並遵循所有標準的選擇加入和選擇退出關鍵字。 此外，也會支援並接受為您的SMS服務提供者帳戶設定的任何自訂關鍵字。

在&#x200B;**[!UICONTROL 訊息]**&#x200B;欄位中輸入您要傳送的文字。

您可以建立最多1600個字元的訊息，將每160個字元視為單一SMS訊息。

![按一下[個人化]圖示以新增代號至郵件](./assets/sms-message-compose.png){width="800" zoomable="yes"}

#### 個人化簡訊

1. 編寫文字訊息時，隨時按一下文字訊息方塊右側的&#x200B;_個人化_&#x200B;圖示（ ![個人化圖示](../assets/do-not-localize/icon-personalize.svg)）。

   顯示的頁面可讓您存取Adobe Marketo Engage銷售機會和系統Token。 包含標準和自訂Token。 您可以使用&#x200B;_搜尋_&#x200B;列來尋找您需要的權杖，或瀏覽資料夾樹狀結構來尋找及選取任何銷售機會/系統權杖。

1. 將游標放在訊息中要新增權杖的位置。

1. 按一下標籤旁的加號( **+** )以新增標籤。

   如果您想要新增具有遞補字元的權杖（預設會顯示在該欄位不適用於潛在客戶的情況下出現），請按一下&#x200B;_更多_&#x200B;圖示( **...** )，然後選擇&#x200B;**[!UICONTROL 插入具有遞補文字]**。

   ![按一下省略符號即可使用權杖的遞補](./assets/sms-message-personalize-ellipsis-fallback.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 輸入遞補值]_&#x200B;對話方塊中，輸入顯示為遞補的文字，然後按一下&#x200B;**[!UICONTROL 新增]**。

   ![輸入權杖的遞補文字](./assets/sms-message-personalize-fallback-text.png){width="400"}

1. 置入個人化權杖後，按一下&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存變更並返回主要SMS編寫工作區。

   您可以視需要繼續編輯含有代號的訊息。

#### 新增連結(URL)至文字訊息

1. 輸入訊息文字後，請按一下文字訊息方塊右側的&#x200B;_連結_&#x200B;圖示（ ![連結圖示](../assets/do-not-localize/icon-link.svg)）。

1. 在對話方塊中，選擇要連結的URL型別：

   * **[!UICONTROL 登陸頁面]** — 選擇此選項可從Marketo Engage執行個體中選取任何已核准的Adobe Marketo Engage登陸頁面。 選取工作區，然後選取登入頁面。

   * **[!UICONTROL 外部URL]** — 此型別是您在文字方塊中輸入的任何外部URL。

1. 如果您選擇使用登入頁面，請設定追蹤選項。

   * **[!UICONTROL 啟用追蹤]** — 選取此核取方塊以啟用追蹤，這需要&#x200B;_縮短_ URL。 對於登入頁面，此維度會使用Marketo Engage子網域作為縮短的URL。 畫面會顯示縮短的URL格式範例。 實際URL會在SMS傳送給收件者時建立。

   * **[!UICONTROL 包含mkt_tok]** — 選取此核取方塊可追蹤使用者的活動。

     >[!NOTE]
     >
     >當您允許追蹤但停用&#x200B;_[!UICONTROL 包含mkt_tok]_&#x200B;時，目的地URL在重新導向後不會包含`mkt_tok`查詢字串引數。 Marketo Engage登陸頁面和Munchkin會使用此引數，以確保追蹤人員活動（例如當人員取消訂閱電子郵件時）。 除非引數造成您網站上的問題，否則請勿停用此選項。<br/>
     >如需有關在網站上使用Munchkin追蹤代碼的詳細資訊，請參閱[Marketo Engage檔案](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/additional-integrations/add-munchkin-tracking-code-to-your-website){target="_blank"}。

   ![新增SMS訊息的連結對話方塊](./assets/sms-add-link-dialog.png){width="470"}

1. 連結選項完成時，按一下&#x200B;**[!UICONTROL 新增]**&#x200B;以儲存變更，並將URL連結新增至SMS訊息。

### 設定簡訊屬性

1. 在&#x200B;_[!UICONTROL SMS屬性]_&#x200B;區段中，為您的訊息輸入&#x200B;**[!UICONTROL 名稱]** （必要，最多100個字元）和&#x200B;**[!UICONTROL 描述]** （選用，最多300個字元）。

   這些欄位允許Alpha、數值、特殊字元。 下列保留的字元是&#x200B;**不允許**： `\`、`/`、`:`、`*`、`?`、`"`、`<`、`>`和`|`。

1. 選擇&#x200B;**[!UICONTROL 簡訊型別]**：

   * 針對需要使用者同意的促銷文字訊息，請使用`Marketing`。
   * 將`Transactional`用於非商業訊息，例如訂單確認、密碼重設通知或傳遞資訊。

1. 針對&#x200B;**[!UICONTROL SMS設定]**，請選擇其中一個預先定義的API設定。

   此設定會決定使用哪個SMS閘道服務提供者和帳戶來傳遞訊息。

1. 輸入您要&#x200B;用於通訊的&#x200B;**[!UICONTROL 寄件者號碼]**。

   ![採取動作 — 傳送簡訊](./assets/sms-properties.png){width="700" zoomable="yes"}

   收件者號碼一律對應至Marketo Engage中的`Lead.mobilePhone`欄位。

### 模擬文字訊息內容 {#preview-test}

>[!CONTEXTUALHELP]
>id="ajo-b2b_sms_preview_simulate"
>title="檢查您內容的呈現方式"
>abstract="定義內容後，您可以進行預覽，並檢查所使用的頻道轉譯狀況。"

定義訊息內容時，您可以使用測試設定檔來模擬（預覽）其內容。 如果您已插入個人化內容，您可以使用測試設定檔資料檢查此內容在訊息中的顯示方式。

>[!IMPORTANT]
>
>繼續模擬文字訊息之前，請務必儲存您的SMS訊息。

1. 按一下SMS編寫工作區頂端的&#x200B;**[!UICONTROL 模擬內容]**。

1. 從&#x200B;_[!UICONTROL 模擬內容]_&#x200B;頁面，按一下&#x200B;**[!UICONTROL 新增人員]**。

1. 使用&#x200B;_模擬內容_&#x200B;頁面來管理測試設定檔所使用的銷售機會。

   在顯示的清單中，您可以從Marketo Engage銷售機會資料庫搜尋並新增任何銷售機會（一次最多10個銷售機會）。

   若要搜尋，請輸入整個電子郵件地址，然後按&#x200B;_Enter_。 隨即顯示對應的潛在客戶設定檔以供選取。

   預覽會更新所選設定檔的個人化欄位。

   所有新增的潛在客戶都會顯示在左側。

   您可以新增更多人員並從設定檔清單中刪除個別銷售機會，以管理此清單（但不會從資料庫中將其移除）。

1. 模擬所選潛在客戶的內容。

   選取左側列出的任何銷售機會。 頁面上的SMS預覽會更新所選銷售機會。

   您也可以從預覽空間上方的選取器中選取銷售機會，以更新相應銷售機會在頁面上的SMS預覽。

1. 若要結束&#x200B;_[!UICONTROL 模擬內容]_&#x200B;頁面並返回SMS編寫工作區，請按一下右上方的&#x200B;**[!UICONTROL 關閉]**。

## 簡訊同意管理

讓收件者能夠取消訂閱來自品牌的通訊，並遵守此選擇為法律要求。 若未遵守這些法規，您的品牌將面臨法律風險。 此功能也可協助您避免傳送未經請求的通訊給您的收件者，這可能會將您的訊息標示為垃圾訊息，並損害您的聲譽。

提供此選項時，簡訊收件者可使用選擇加入和選擇退出關鍵字進行回覆。 支援並接受所有標準的選擇加入和選擇退出關鍵字，以及在SMS服務提供者設定的任何自訂關鍵字。 取消訂閱後，設定檔會自動從未來行銷訊息的對象中移除。

Journey Optimizer B2B edition可讓您使用下列邏輯，管理簡訊訊息中的選擇退出：

* 根據預設，如果潛在客戶選擇不接收來自您的通訊，則對應的設定檔會從後續SMS傳送中排除

* 來自不同來源(例如AEP或SMS服務提供者)的潛在客戶同意會同步至Journey Optimizer B2B edition。 目前，其在執行個體層級僅支援每個潛在客戶的單一同意狀態（潛在客戶「John Doe」已訂閱或取消訂閱執行個體中的所有促銷SMS）。 目前不支援品牌層級/個別訂閱清單層級同意的雙重選擇加入。
