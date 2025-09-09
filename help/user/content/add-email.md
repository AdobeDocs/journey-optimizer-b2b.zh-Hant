---
title: 新增電子郵件至您的歷程
description: 新增電子郵件動作節點至帳戶歷程 — 建立新電子郵件或使用現有Marketo Engage電子郵件在Journey Optimizer B2B edition中進行目標通訊。
feature: Email Authoring, Account Journeys
role: User
exl-id: 21a6ce0f-b59d-4be2-abc3-fda5c6a6334f
source-git-commit: 79012352c3ae4e2f3d38b632b1f523d262f74f96
workflow-type: tm+mt
source-wordcount: '1348'
ht-degree: 0%

---

# 新增電子郵件至您的歷程

使用Adobe Journey Optimizer B2B edition透過帳戶歷程傳送電子郵件訊息給您的客戶。 您可以選擇在電子郵件設計空間建立、個人化和預覽訊息。 或者，您也可以選擇傳送已在連線的Marketo Engage執行個體中定義的電子郵件。

>[!NOTE]
>
>如果您是第一次傳送電子郵件，請務必從Adobe Marketo Engage中設定電子郵件頻道。 若要深入瞭解，請參閱[追蹤和電子郵件傳遞的通訊協定](../start/email-protocols.md)。

## 在歷程中新增電子郵件動作節點

當您[新增&#x200B;_[!UICONTROL 採取動作]_&#x200B;節點](../journeys/action-nodes.md)並執行下列動作時，您可以在歷程中設定電子郵件傳遞：

1. 針對&#x200B;_[!UICONTROL 目標上的]_&#x200B;動作，請選擇&#x200B;**[!UICONTROL 人員]**。

1. 針對人員&#x200B;_[!UICONTROL 的]_&#x200B;動作，請選擇&#x200B;**[!UICONTROL 傳送電子郵件]**。

1. 針對&#x200B;_[!UICONTROL 電子郵件來源]_，選擇您要如何取得要傳送的電子郵件。

   ![採取動作 — 傳送電子郵件](assets/journey-node-send-email.png){width="700" zoomable="yes"}

   * 選擇&#x200B;**[!UICONTROL 建立新電子郵件]**，在Journey Optimizer B2B edition中以原生方式編寫電子郵件。

     此選項可讓您在Journey Optimizer B2B edition中以原生方式管理電子郵件內容。 按一下[建立電子郵件]&#x200B;**[!UICONTROL 以開啟[建立新電子郵件]]**&#x200B;對話方塊&#x200B;_。_&#x200B;您可以建立新的電子郵件內容資產或複製現有的電子郵件內容資產。

     +++新電子郵件

     若要使用空白畫布或電子郵件範本建立電子郵件，請使用&#x200B;_[!UICONTROL 新增電子郵件]_&#x200B;選項。

      1. 在對話方塊中，選擇&#x200B;**[!UICONTROL 新增電子郵件]**。

      1. 輸入電子郵件唯一&#x200B;**[!UICONTROL 名稱]**&#x200B;和&#x200B;**[!UICONTROL 主旨列]**。

         ![建立新電子郵件對話方塊 — 新電子郵件](assets/create-new-email.png){width="400"}

      1. 按一下&#x200B;**[!UICONTROL 建立]**。

         在電子郵件內容頁面的&#x200B;_[!UICONTROL 電子郵件屬性]_&#x200B;區段中，_[!UICONTROL 寄件者電子郵件]_&#x200B;與&#x200B;_[!UICONTROL 回覆地址]_&#x200B;欄位已設定。 您可以輸入&#x200B;_[!UICONTROL From name]_&#x200B;和&#x200B;_[!UICONTROL Description]_ （選擇性）欄位的值。

      1. 按一下&#x200B;**[!UICONTROL 編輯電子郵件]**&#x200B;以定義電子郵件[設定](#define-the-email-settings)並設計[內容](./email-authoring.md)。

     +++

     +++複製現有的電子郵件

     當您想要使用目前歷程或其他歷程中的現有電子郵件建立電子郵件時，請使用&#x200B;_[!UICONTROL 複製現有電子郵件]_&#x200B;選項。 您可以根據歷程節點的目標來變更重複的電子郵件。

      1. 在&#x200B;_[!UICONTROL 建立新電子郵件]_&#x200B;對話方塊中，選擇&#x200B;**[!UICONTROL 複製現有電子郵件]**。

      1. 若要複製&#x200B;**[!UICONTROL 現有電子郵件]**，請按一下&#x200B;_選取範圍_&#x200B;圖示（![選取範圍圖示](../assets/do-not-localize/icon-email-select.svg)）並選取您要複製並用於歷程節點的電子郵件。

         您可以在搜尋欄位中輸入文字字串以符合電子郵件名稱，藉此篩選電子郵件清單。

         ![選取電子郵件](assets/create-new-email-duplicate-select-email.png){width="600" zoomable="yes"}

         選取您要複製之電子郵件的核取方塊，然後按一下&#x200B;**[!UICONTROL 選取]**。

      1. 輸入電子郵件唯一&#x200B;**[!UICONTROL 名稱]**&#x200B;和&#x200B;**[!UICONTROL 主旨列]**。

         ![建立新電子郵件對話方塊 — 複製現有電子郵件](assets/create-new-email-duplicate.png){width="400"}

      1. 按一下&#x200B;**[!UICONTROL 建立]**。

         在電子郵件內容頁面的&#x200B;_[!UICONTROL 電子郵件屬性]_&#x200B;區段中，_[!UICONTROL 寄件者電子郵件]_&#x200B;與&#x200B;_[!UICONTROL 回覆地址]_&#x200B;欄位已設定。 您可以輸入&#x200B;_[!UICONTROL From name]_&#x200B;和&#x200B;_[!UICONTROL Description]_ （選擇性）欄位的值。

      1. 如有需要，請按一下[編輯電子郵件] **&#x200B;**&#x200B;來修改電子郵件[設定](#define-the-email-settings)和[內容](./email-authoring.md)。

     +++

   * 選擇&#x200B;**[!UICONTROL 從Adobe Marketo Engage選取電子郵件]**&#x200B;以使用Marketo Engage中預先編寫的電子郵件之一，並將其作為歷程的一部分傳送。

     如果您在連線的Market Engage執行個體中有多個工作區可用，請選取工作區。 然後，選取您要為歷程節點傳送的已核准電子郵件。

     ![選取Marketo Engage電子郵件](./assets/email-select-marketo.png){width="500" zoomable="yes"}

     使用此選項，節點已設定，且電子郵件內容不需要在歷程中進一步定義。

## 定義電子郵件設定

在右側的&#x200B;**[!UICONTROL 摘要]**&#x200B;面板中選取&#x200B;_詳細資料_&#x200B;索引標籤後，捲動至底部以檢視並定義電子郵件設定。

![電子郵件設定](./assets/email-summary-details-settings.png){width="700" zoomable="yes"}

| 選項 | 說明 |
| ------ | ----------- |
| [!UICONTROL 來自名稱] | 電子郵件標頭中使用的寄件者名稱。 輸入您希望向收件者顯示的寄件者名稱。 按一下「_個人化_」圖示（「![個人化圖示](../assets/do-not-localize/icon-personalize.svg)」）以在欄位中使用個人化權杖。 |
| [!UICONTROL 來自電子郵件] | 電子郵件標頭中使用的寄件者地址。 預設值是從[電子郵件通道傳遞設定](../admin/configure-channels-emails.md#delivery-settings)填入。 按一下「_個人化_」圖示（「![個人化圖示](../assets/do-not-localize/icon-personalize.svg)」）以在欄位中使用個人化權杖。 |
| [!UICONTROL 回覆地址] | 電子郵件標頭中使用的寄件者地址。 預設值是從[電子郵件通道傳遞設定](../admin/configure-channels-emails.md#delivery-settings) （[!UICONTROL 來自標籤]）填入。 輸入當收件者使用回覆功能時，您想要填入的電子郵件地址（可能與寄件者地址不同或相同）。 按一下「_個人化_」圖示（「![個人化圖示](../assets/do-not-localize/icon-personalize.svg)」）以在欄位中使用個人化權杖。 |
| [!UICONTROL 主旨列] | 顯示在電子郵件主旨欄位中的文字。 預設值是從您在&#x200B;_[!UICONTROL 建立新電子郵件]_&#x200B;對話方塊中輸入的文字填入。 您可以視需要變更文字。 按一下&#x200B;_個人化_&#x200B;圖示（![個人化圖示](../assets/do-not-localize/icon-personalize.svg)）以在欄位中使用個人化權杖。<!-- Click the AI Assistant button ( ![AI Assistant icon](../../assets/do-not-localize/icon-gen-ai.svg){width="30" zoomable="no"} ) to generate the subject line based on the current email content.--> |
| [!UICONTROL 品牌化網域] | 如果您在系統中定義了多個[品牌化網域](../admin/configure-channels-emails.md#branding-domains)，請選取要用來傳送電子郵件的品牌化網域。 使用特定品牌網域來傳送看似來自您的品牌而非整個公司的電子郵件。 它可建立與品牌的信任、個人化電子郵件體驗，並提高開啟率和回應率。 |
| [!UICONTROL 專用IP] | 如果您定義了多個專用IP位址，請選取用於傳送電子郵件的專用IP位址。 當您為方案使用特定的專用IP時，可以更密切地追蹤和監視傳遞能力，並快速回應傳遞量度的任何變更。 如需為連線的Marketo Engage執行個體新增專用IP的詳細資訊，請參閱[Marketo Engage檔案](https://experienceleague.adobe.com/zh-hant/docs/marketo/using/product-docs/email-marketing/deliverability/use-your-dedicated-ip-addresses-to-send-emails){target="_blank"}。 |
| [!UICONTROL 操作電子郵件] | 如果要將電子郵件指定為可操作，請選取核取方塊。 營運電子郵件會從選擇退出/取消訂閱清單及通訊限制中排除。 只有當收件者無法將電子郵件視為未經請求的商業郵件(SPAM)時，才選取此選項。 |
| [!UICONTROL 包含網頁檢視] | 選取核取方塊以包含從電子郵件內容產生的網頁連結。 電子郵件訊息的功能比網頁更為有限，因此對JavaScript、擴充式CSS和表單相當實用。 用來產生連結的文字已在[電子郵件通道傳遞設定](../admin/configure-channels-emails.md#delivery-settings)中設定([!UICONTROL 以網頁檢視HTML]和[!UICONTROL 以網頁文字檢視])。 |
| [!UICONTROL 停用開啟追蹤] | 選取當您不想追蹤電子郵件開啟活動時的核取方塊。 停用此功能後，只有在不重複人員開啟電子郵件時，電子郵件開啟活動計數才會增加。 當您設計電子郵件內文內容時，可以[管理電子郵件內容連結追蹤](./email-authoring.md#content-authoring---link-tracking)。 |
| [!UICONTROL Preheader] | 選取核取方塊以包含預覽文字。 預覽文字是簡短摘要文字，顯示在部分電子郵件使用者端的主旨行後面。 它通常提供電子郵件的簡短摘要，通常是單句話。 在欄位<!-- , or click the AI Assistant button ( ![AI Assistant icon](../../assets/do-not-localize/icon-gen-ai.svg){width="30" zoomable="no"} ) to generate summary text based on the current email content -->中輸入摘要文字。 |
| [!UICONTROL 用作CC位址的欄位] | 如果可用，請選取最多25個在Marketo Engage中使用`Email`型別設定的潛在客戶或公司欄位。 |

## 檢查警報

當您設計電子郵件訊息內容時，當關鍵設定遺失時，警示會顯示在介面（頁面右上方）中。 如果沒有看見此按鈕，表示沒有偵測到的問題。

![電子郵件警示](./assets/email-alerts.png){width="600" zoomable="yes"}

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

   * `From name is empty`：未定義電子郵件&#x200B;_來自_&#x200B;欄位（必要）。

   * `The subject line is missing`：未定義電子郵件主旨列（必要）。

   * `The email version of the message is empty`：未定義電子郵件內容。
