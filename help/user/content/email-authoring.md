---
title: 電子郵件製作
description: 瞭解如何建立用於帳戶歷程的個人化電子郵件內容。
feature: Email Authoring, Content
exl-id: 0f4ae644-ade7-49a0-935c-7f4779c25ffb
source-git-commit: 797d049cc5aefe710a39a980107f63e75cae12d2
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 11%

---

# 電子郵件編寫

使用Adobe Journey Optimizer B2B edition傳送電子郵件訊息給您的客戶。 您可以在視覺化設計工具中建立、個人化和預覽訊息。

## 在帳戶歷程中新增電子郵件動作

當您新增&#x200B;_[!UICONTROL 採取動作]_&#x200B;節點並執行下列動作時，可以在帳戶歷程中設定電子郵件傳遞：

1. 針對&#x200B;]_目標上的_[!UICONTROL &#x200B;動作，請選擇&#x200B;**[!UICONTROL 人員]**。
1. 針對人員&#x200B;]_的_[!UICONTROL &#x200B;動作，請選擇&#x200B;**[!UICONTROL 傳送電子郵件]**。
1. 針對&#x200B;_[!UICONTROL 電子郵件來源]_，請選擇&#x200B;**[!UICONTROL 建立新電子郵件]**。

   或者，您也可以選取「_[!UICONTROL 從Adobe Marketo Engage選取電子郵件]_」選項，以使用Marketo Engage中預先編寫的電子郵件之一，並將其作為帳戶歷程的一部分傳送。

   >[!NOTE]
   >
   >如果您是第一次建立電子郵件，請務必從Adobe Marketo Engage中設定電子郵件頻道。 若要深入瞭解，請參閱Marketo Engage檔案中的[確認電子郵件傳遞能力](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps#ensure-email-deliverability)。

   ![採取動作 — 傳送電子郵件](assets/journey-node-send-email.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 執行動作]_&#x200B;面板底部，按一下&#x200B;**[!UICONTROL 建立電子郵件]**。

1. 在對話方塊中，輸入電子郵件的唯一&#x200B;**[!UICONTROL 名稱]**，以及&#x200B;**[!UICONTROL 主旨列]**。

   ![建立新的電子郵件對話方塊](assets/create-new-email.png){width="400"}

1. 按一下&#x200B;**[!UICONTROL 建立]**。

   在電子郵件內容頁面的&#x200B;_[!UICONTROL 電子郵件屬性]_&#x200B;區段中，_[!UICONTROL 寄件者電子郵件]_&#x200B;與&#x200B;_[!UICONTROL 回覆地址]_&#x200B;欄位已設定。 您可以輸入&#x200B;_[!UICONTROL From name]_&#x200B;和&#x200B;_[!UICONTROL Description]_ （選擇性）欄位的值。

## 建立該電子郵件內容

按一下&#x200B;_[!UICONTROL 電子郵件]_&#x200B;預覽面板頂端的&#x200B;**[!UICONTROL 新增電子郵件內容]**。

![按一下[新增電子郵件內容] ](./assets/add-email-content.png){width="700" zoomable="yes"}

此動作會啟動電子郵件Designer，您可在其中從下列選項選擇設計電子郵件的方式：

* [使用電子郵件Designer介面，從草稿開始設計電子郵件](#design-your-email-from-scratch)。

* [從檔案或.zip資料夾匯入現有的HTML內容](#import-existing-html-content)。

* [從內建或自訂電子郵件範本清單中選取現有的範本](#select-a-template)。

若要使用運算式編輯器設定並個人化主旨列，請按一下&#x200B;_Personalization_&#x200B;圖示並新增任何Marketo Engage權杖。

建立並個人化電子郵件內容後，您可以匯出內容以供驗證或稍後使用。 按一下&#x200B;**[!UICONTROL 匯出HTML]**，將內容儲存為.zip檔案，其中包含您的HTML和資產。

>[!TIP]
>
>使用由generative AI支援的Adobe Journey Optimizer B2B edition中的AI助理，將您的內容提升到新的境界。 AI Assistant可以產生整封電子郵件、鎖定目標文字內容，並針對與對象產生迴響的影像取得AI Assistant建議，協助您最佳化傳送的影響。 [了解更多](./ai-assistant-emails.md)

### 從頭開始設計您的電子郵件 {#design-from-scratch}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_landing_page"
>title="新增結構元件"
>abstract="結構元件會定義登陸頁面的版面。將&#x200B;**結構**&#x200B;元件拖放到畫布中開始設計您的登入頁面內容。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_landing_page"
>title="關於內容元件"
>abstract="內容元件是可以用來建立登陸頁面版面的空白內容預留位置。"

使用視覺內容編輯器來定義電子郵件內容的結構。 透過使用簡單的拖放動作新增和移動結構元件，您可以在數秒內設計可重複使用電子郵件內容的形狀。

1. 從&#x200B;_[!UICONTROL 設計您的範本]_&#x200B;首頁，選取&#x200B;**[!UICONTROL 從頭開始設計]**&#x200B;選項。

1. [新增結構和內容](#add-structure-and-content)至電子郵件訊息。
1. [新增影像資產](#add-assets)至電子郵件訊息。
1. [個人化電子郵件內容](#personalize-content)。
1. [檢閱和更新連結](#preview-and-edit-linked-urls)。

<!-- If needed, you can further personalize your email by clicking **[!UICONTROL Switch to code editor]** from the advanced menu. The code editor allows you to edit the email source code, such as adding tracking or custom HTML tags.

>[!CAUTION]
>
>You cannot revert back to the visual designer for this email after switching to the code editor. -->

內容完成時，請按一下頂端的&#x200B;**[!UICONTROL 模擬內容]**&#x200B;以檢查轉譯。 您可以選擇案頭或行動檢視。

當您滿意內容時，請按一下[儲存]。****

### 匯入現有的HTML內容

{{$include /help/_includes/content-design-import.md}}

![將html內容匯入zip檔](./assets/email-import-zip-file.png){width="500"}

>[!NOTE]
>
>在HTML檔案中使用`<table>`標籤做為第一個圖層可能會造成樣式遺失，包括上層圖層標籤中的背景和寬度設定。

您可以視需要使用視覺化電子郵件編輯器工具個人化匯入的內容。

### 選取範本

{{$include /help/_includes/content-design-select-template.md}}

>[!NOTE]
>
> 儲存的範本可能會套用至一或多個元件的治理（內容鎖定）設定。 當您[從受控制的範本](./email-authoring-governance.md)撰寫電子郵件時，視覺化設計工具會提供鎖定元件的相關准則。

## 新增結構和內容 {#structure-content}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_email"
>title="新增結構元件"
>abstract="結構元件會定義電子郵件的版面。將&#x200B;**結構**&#x200B;元件拖放到畫布中開始設計您的電子郵件內容。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_email"
>title="關於內容元件"
>abstract="內容元件指可用於建立電子郵件版面的空白內容預留位置。"

{{$include /help/_includes/content-design-components.md}}

### 新增片段

{{$include /help/_includes/content-design-use-fragments.md}}

儲存電子郵件後，當您在摘要中選取&#x200B;_[!UICONTROL 使用者]_&#x200B;索引標籤時，它就會顯示在片段詳細資訊頁面中。

### 新增資產

{{$include /help/_includes/content-design-assets.md}}

### 導覽圖層、設定和樣式

{{$include /help/_includes/content-design-navigation.md}}

### 個人化內容

{{$include /help/_includes/content-design-personalization.md}}

>[!NOTE]
>
>如果針對帳戶歷程定義了&#x200B;_[!UICONTROL 我的Token]_，您也可以將這些歷程專屬的Token用於電子郵件內容。 如需詳細資訊，請參閱電子郵件個人化的[自訂權杖](./personalization-my-tokens.md)。

### 編輯連結的URL追蹤

{{$include /help/_includes/content-design-links.md}}

### 檢視選項

善用視覺化電子郵件編輯器中可用的檢視和內容驗證選項。

* 透過預設縮放選項放大/縮小內容。

* 切換在案頭、行動裝置或純文字/純文字間檢視內容。
   * 按一下&#x200B;_檢視_&#x200B;圖示，即可跨裝置預覽內容。
   * 選取其中一個現成可用的裝置，或輸入自訂維度以預覽內容。

### 更多選項

從電子郵件設計工具頂端的&#x200B;_[!UICONTROL 更多……]_&#x200B;功能表，您可以執行下列動作：

![按一下[更多]以存取範本動作](./assets/email-designer-more-menu.png){width="500"}

* **[!UICONTROL 重設電子郵件]** — 按一下此選項，將視覺化電子郵件設計工具畫布清除為空白並重新啟動內容建置。
* **[!UICONTROL 另存為片段]** — 將電子郵件的全部或部份另存為片段，以便在多個電子郵件或電子郵件範本中重複使用。 您提供片段的名稱和說明，並將其儲存到可用片段清單中。
* **[!UICONTROL 變更您的設計]** — 返回&#x200B;_設計您的電子郵件_&#x200B;頁面。 從那裡，您可以選擇另一個範本以重新啟動設計程式，或選擇在黑色畫布中從頭開始設計內容。\
* **[!UICONTROL 另存為內容範本]** — 將電子郵件內文另存為電子郵件範本，以便在多個電子郵件或電子郵件範本中重複使用。 您可以提供範本的名稱和說明，並將其儲存至已儲存電子郵件範本的清單。
* **[!UICONTROL 匯出HTML]** — 將視覺畫布中的內容以HTML格式下載到您的本機系統，並封裝成zip檔。

## 檢查警報

當您設計電子郵件訊息內容時，當關鍵設定遺失時，警示會顯示在介面（頁面右上方）中。

如果沒有看見此按鈕，表示沒有偵測到的問題。

可偵測到兩種型別的警報：

* **_警告_**&#x200B;參考建議與最佳實務的警告，例如：

   * `The opt-out link is not present in the email body`：將取消訂閱連結新增至您的電子郵件內文為最佳做法。

     >[!NOTE]
     >
     >行銷樣式的電子郵件訊息必須包含選擇退出連結，異動訊息不需要此連結。

   * `Text version of HTML is empty`：別忘了定義您的電子郵件內文的文字版本，此文字版本會在HTML內容無法顯示時使用。

   * `Empty link is present in email body`：檢查您電子郵件中的所有連結是否正確。

   * `Email size has exceeded the limit of 100KB`：若要取得最佳傳遞，請確定您的電子郵件大小不超過100KB。

* **_錯誤_**&#x200B;會阻止您測試或啟用歷程/行銷活動，只要這些錯誤尚未解決，例如：

   * `The subject line is missing`：電子郵件主旨列是必填欄位。

   * `The email version of the message is empty`：尚未設定電子郵件內容時，會顯示此錯誤。

## 檢查和測試電子郵件 {#preview-test}

>[!CONTEXTUALHELP]
>id="ajo-b2b_email_preview_simulate"
>title="檢查您內容的呈現方式"
>abstract="定義內容後，您可以進行預覽，並檢查所使用的頻道是否正確呈現。"

定義訊息內容後，您可以使用測試設定檔來預覽、傳送校樣，以及在熱門的案頭、行動及網頁型使用者端中控制其呈現。 如果您已插入個人化內容，您可以使用測試設定檔資料預覽此內容在訊息中的顯示方式。

若要預覽電子郵件內容，請按一下[模擬內容] ****，然後新增測試設定檔，以使用測試設定檔資料檢查您的訊息。

![類比電子郵件內容以檢查您的設計](./assets/email-designer-simulate-content.png){width="700" zoomable="yes"}
