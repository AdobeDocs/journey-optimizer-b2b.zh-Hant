---
title: 建立和發佈登陸頁面
description: 建立、設計和發佈歷程的登入頁面 — 從頭開始建立、匯入HTML、新增表單、個人化內容，以及從Journey Optimizer B2B edition中的電子郵件連結。
feature: Landing Pages, Content
role: User
autotag-review: '2026-05-27T16:10:09.537Z'
TQID: 'https://experienceleague.adobe.com/e-tguY-9v6CPOehYL7vI22fzQBk3L0h1EOpa-e54q7A'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: a96755d6-1f54-4f3f-a971-d31f83705ab7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e4bd5f48-22a4-465d-a046-5ffb52e27856
source-git-commit: 144848cff6a37691ccbe7a83b78f9db33d8a2b3d
workflow-type: tm+mt
source-wordcount: 1719
ht-degree: 5%

---

# 建立和發佈登陸頁面

行銷人員可以定義並發佈您要併入帳戶和個人歷程的頁面。 新增登陸頁面時，您可以設定主要頁面及任何子頁面、設計內容、測試頁面及發佈頁面。

![登陸頁面工作流程圖表](./assets/landing-page-work-flow-diagram-no-subpages.svg)

>[!BEGINSHADEBOX]

## 登陸頁面的先決條件 {#landing-page-prerequisites}

行銷人員必須具備下列設定和資產，才能建立登入頁面以支援其歷程和行銷活動：

* [登陸頁面子網域](../admin/configure-channels-landing-pages.md#lp-subdomains) — 設定專用於託管登陸頁面的子網域。
* [登陸頁面預設集](../admin/configure-channels-landing-pages.md#lp-presets) — 預設集會定義套用至登陸頁面的子網域和其他設定。
* [表單](./forms.md) （用於資料擷取使用案例） — 當您想要將表單內嵌在登陸頁面上並將資料提交到Experience Platform時，此為必要專案。
  <!-- * Subscription list (for subscription use cases) - Required if you want customers to subscribe to or unsubscribe from a specific service. This is in AJO B2C-->

>[!ENDSHADEBOX]

## 建立登陸頁面 {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b_lp_create"
>title="定義和設定您的登陸頁面"
>abstract="若要建立登陸頁面，您需要選取一個預設集，然後設定主要頁面和子頁面，最後在發佈頁面之前進行測試。"

1. 前往左側導覽並選取&#x200B;**[!UICONTROL 內容管理]** > **[!UICONTROL 登入頁面]**。

1. 按一下右上方的&#x200B;**[!UICONTROL 建立登陸頁面]**。

1. 在頁面上，輸入有用的&#x200B;**[!UICONTROL Title]** （必要）和&#x200B;**[!UICONTROL Description]** （選用）。

   標題和說明條件：

   * 標題 — 最多100個字元，必須是唯一的，不區分大小寫

   * 說明 — 最多300個字元

   * 允許使用Alpha、數值和特殊字元

   * 保留的字元是&#x200B;**_不允許_**： `\ / : * ? " < > |`

   ![建立登陸頁面](./assets/landing-page-create.png){width="600"}

1. 選取&#x200B;**[!UICONTROL 預設集]**。

   產品管理員[設定預設集](../admin/configure-channels-landing-pages.md#lp-presets)，以定義用於登入頁面的子網域和其他設定。 您可以選取預設集，然後按一下「**[!UICONTROL 檢視預設集]**」以開啟預設集詳細資料，並檢查設定以確定其符合您的登陸頁面需求。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

   主要頁面及其屬性隨即顯示。

   ![新登陸頁面 — 主要頁面屬性](./assets/landing-page-primary-new-properties.png){width="700" zoomable="yes"}

## 設定主要頁面 {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b_lp_primary_page"
>title="定義您的主要頁面設定"
>abstract="定義主要頁面，當收件者按一下登入頁面連結（例如從電子郵件或網站）時，就會立即顯示。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_lp_access_settings"
>title="定義您的登陸頁面 URL"
>abstract="在本區段中，定義一個唯一的登陸頁面 URL。 URL的第一個部分會要求您先前將登陸頁面子網域設定為您所選預設集的一部分。"

1. 根據您的需求變更&#x200B;**[!UICONTROL 頁面名稱]**，預設為&#x200B;_主要頁面_。

1. 定義頁面URL的結束部分。

   您選取的預設集決定了URL的第一個部分。

   >[!CAUTION]
   >
   >登陸頁面URL必須是唯一的。
   >
   >您無法將此URL複製貼入網頁瀏覽器，即使已發佈，仍可存取您的登入頁面。 使用預覽功能加以測試。

1. 如果您想要匿名登陸頁面，請停用&#x200B;**[!UICONTROL 需要已識別的使用者]**&#x200B;選項。

   <!-- The option 'Require identified users' would be visible in both AJO & AJOB2B when the Landing page is of type 'Data capture' -->

1. 按一下&#x200B;_行事曆_ （ ![行事曆圖示](../assets/do-not-localize/icon-calendar.svg) ）圖示以設定&#x200B;**[!UICONTROL 頁面到期]**。

   選取到期日後，請選擇頁面到期時的動作：

   * **[!UICONTROL 重新導向URL]** — 輸入要做為重新導向之頁面的URL。

     ![登陸頁面到期 — 重新導向URL](./assets/landing-page-expiry-redirect-url.png){width="400"}

     <!-- * **[!UICONTROL Custom page]** - Configure a subpage and select it from the list. -->
   * **[!UICONTROL 瀏覽器錯誤]** — 輸入要取代頁面的錯誤文字。

     ![登入頁面到期 — 瀏覽器錯誤](./assets/landing-page-expiry-browser-error.png){width="400"}

## 選擇內容設計型別 {#choose-design-type}

若要新增頁面的&#x200B;_[!UICONTROL 內容]_，請按一下&#x200B;**[!UICONTROL 開啟Designer]**。 _[!UICONTROL 建立您的主要登陸頁面]_&#x200B;首頁會載入，而設計程式會從選擇您要如何開始設計開始：

* [[!UICONTROL 從頭開始設計]](#design-from-scratch)
* [[!UICONTROL 為您自己的程式碼]](#code-your-own)
* [[!UICONTROL 匯入HTML]](#import-html)
* [使用登入頁面範本](#select-template)

![選擇您要如何開始您的登入頁面設計](./assets/landing-page-create-design.png){width="800" zoomable="yes"}

在您選取您偏好的方法來開始登入頁面設計後，請使用視覺化設計工具來[完成頁面內容](./landing-page-design.md)。

### 從頭開始設計 {#design-from-scratch}

使用視覺內容編輯器來定義登入頁面內容的結構。 透過使用簡單的拖放動作新增和移動結構元件，您可以在數秒內設計頁面內容的形狀。

1. 從&#x200B;_[!UICONTROL 建立您的主要登陸頁面]_&#x200B;首頁，選取&#x200B;**[!UICONTROL 從頭開始設計]**&#x200B;選項。

1. 選擇您要如何管理頁面內容的樣式：

   * **[!UICONTROL 使用佈景主題]** — 選擇此選項可在&#x200B;_佈景主題模式_&#x200B;中建立頁面內容。 在此模式中，您可以使用已定義的[品牌主題](./brand-themes.md)來簡化內容製作程式，並確保設計符合已定義的標準。

   * **[!UICONTROL 手動樣式]** — 選擇此選項可在&#x200B;_手動模式_&#x200B;中建立頁面內容。 在此模式中，您可以手動設定新增至空白畫布的所有結構和內容元件的樣式。

1. 按一下「**[!UICONTROL 確認]**」。

1. [新增結構和內容](./landing-page-design.md#structure-content-landing-page)至頁面。

### 自行撰寫程式碼 {#code-your-own}

_自行編碼_&#x200B;可讓您撰寫或貼上原始HTML，以直接在設計空間建立頁面內容。 當您需要完全控制標籤時，請使用此模式。 使用此模式需要您具備HTML技能。

選擇此模式後，您將停留在程式碼編輯器中；您無法切換到視覺化編輯器。

1. 從&#x200B;_[!UICONTROL 建立您的主要登陸頁面]_&#x200B;首頁，選取&#x200B;**[!UICONTROL 自行編碼]**&#x200B;選項。

1. 輸入或貼上原始 HTML 程式碼。

如果您想要清除頁面內容並從新設計開始，請從[選項]功能表選取[變更設計]。****

### 匯入HTML {#import-html}

Adobe Journey Optimizer B2B edition可讓您匯入現有的HTML內容，以設計您的登入頁面。

{{$include /help/_includes/content-design-import.md}}

![將HTML內容匯入ZIP檔](./assets/templates-import-zip-file.png){width="500"}

>[!NOTE]
>
>在HTML檔案中使用`<table>`標籤做為第一個圖層可能會造成樣式遺失，包括上層圖層標籤中的背景和寬度設定。

您可以視需要利用視覺化設計空間個人化匯入的內容。

### 選取範本 {#select-template}

[!BADGE Beta]{type=Informative tooltip="Beta功能"}

如果您想要使用登入頁面範本，可以選擇：

* **範例範本**。 Journey Optimizer B2B edition介面提供一系列現成的登陸頁面範本，您可以將這些範本作為登陸頁面設計的起點。

* **儲存的範本**。 使用貴組織成員使用&#x200B;_[!UICONTROL 範本]_&#x200B;功能表<!-- or the _[!UICONTROL Save as content template]_ option when designing a landing page. -->建立的已儲存自訂範本

使用&#x200B;_[!UICONTROL 選取設計範本]_&#x200B;區段來開始從範本建立您的內容。 您可以使用範例範本或儲存的Journey Optimizer B2B edition例項自訂登陸頁面範本。

>[!BEGINTABS]

>[!TAB 儲存的範本]

_建立您的主要登陸頁面_&#x200B;首頁預設會顯示&#x200B;_範例範本_&#x200B;索引標籤。 若要使用自訂範本，請選取&#x200B;**[!UICONTROL 儲存的範本]**&#x200B;索引標籤。

所有已儲存的登入頁面範本清單隨即顯示。 您可以依&#x200B;_[!UICONTROL 名稱]_、_[!UICONTROL 上次修改時間]_&#x200B;和&#x200B;_[!UICONTROL 上次建立時間]_&#x200B;來排序它們。

![選擇儲存的範本](./assets/landing-page-design-saved-templates-sort-by.png){width="700" zoomable="yes"}

選取範本縮圖以顯示預覽。 在預覽模式中，您可以使用向右和向左箭頭，在單一類別的所有範本（範例或已儲存，視您的選擇而定）之間導覽。

![預覽儲存的範本](./assets/landing-page-design-saved-template-preview.png){width="800" zoomable="yes"}

當顯示符合您要使用的內容時，請按一下預覽視窗右上角的&#x200B;**[!UICONTROL 使用此範本]**。

此動作會將內容複製到視覺化設計空間，以便您視需要編輯內容。

<!-- 
>[!NOTE]
>
>Saved templates may have governance (content locking) settings applied to one or more components. The design tools provide guidelines about locked components when you [author content from a governed template](./email-authoring-governance.md). 
-->

>[!TAB 範例範本]

Adobe Journey Optimizer B2B edition提供一系列&#x200B;_立即可用的_&#x200B;登入頁面範本，可讓您建立自己的登入頁面和登入頁面範本。

<!-- ![Choose a sample template provided by Adobe](../assets/content-design-shared/templates-design-samples.png){width="800" zoomable="yes"} -->

>[!ENDTABS]

## 檢查警報 {#check-alerts}

當您設計登入頁面內容時，如果關鍵設定遺失，警示會出現在右上方。

![頁面內容問題的警示](./assets/alerts-button.png){width="250"}

如果沒有看見此按鈕，表示沒有偵測到的問題。

警報有兩種型別：

* **_警告_**&#x200B;參考建議與最佳實務的警告，例如：

   * `Placeholder links are present in the landing page body`：別忘了以有效連結取代預留位置。

   * `Text version of HTML is empty`：別忘了定義頁面內文的文字版本，當HTML內容無法顯示時會使用此版本。

   * `Empty link is present in page body`：檢查頁面中的所有連結是否正確。

* **_錯誤_**&#x200B;會阻止您測試或啟用歷程/行銷活動，只要這些錯誤尚未解決，例如：

   * `The landing page content is empty`：頁面內容是必要的。

## 測試登陸頁面 {#test-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b_preview_lp_profiles"
>title="預覽和測試您的登陸頁面"
>abstract="定義登入頁面設定和內容後，請使用測試設定檔來預覽頁面。"

定義登入頁面設定和內容時，您可以使用測試設定檔來預覽頁面。 如果您已插入[個人化內容](./personalization.md)，您可以使用測試設定檔資料檢查此內容在登入頁面中的顯示方式。

>[!PREREQUISITES]
>
>若要預覽和測試登入頁面，您必須擁有&#x200B;**[!UICONTROL 發佈訊息]**&#x200B;許可權，以及包含[測試設定檔](../audiences/test-profiles.md)的已定義資料集。

1. 按一下&#x200B;**[!UICONTROL 預覽和測試]**&#x200B;以開啟測試設定檔選取專案。

   >[!NOTE]
   >
   >當您在視覺化設計空間時，也可以使用&#x200B;**[!UICONTROL 模擬內容]**。

1. 從&#x200B;_[!UICONTROL 模擬]_&#x200B;畫面選取測試設定檔。

   ![針對選取的設定檔模擬登陸頁面內容](./assets/landing-page-simulate.png){width="700" zoomable="yes"}

   如果未列出您需要的設定檔，請按一下[管理測試設定檔] ]**，使用已知的[測試設定檔](../audiences/test-profiles.md)電子郵件地址，並將其新增至清單。**[!UICONTROL 

   +++新增測試設定檔

   針對&#x200B;**[!UICONTROL 身分識別名稱空間]**，按一下&#x200B;_選取_ （![選取圖示](../assets/do-not-localize/icon-select-data.svg) ）圖示，然後選擇用於測試設定檔的`Email`名稱空間。

   ![管理測試設定檔集電子郵件身分名稱空間](./assets/manage-test-profiles.png){width="700" zoomable="yes"}

   在&#x200B;**[!UICONTROL 識別值]**&#x200B;欄位中，輸入識別測試設定檔的電子郵件地址，然後按一下&#x200B;**[!UICONTROL 新增設定檔]**。 您可以重複此步驟以新增多個設定檔。

   ![管理測試設定檔新增設定檔](./assets/manage-test-profiles-add.png){width="700" zoomable="yes"}

   按一下左上方的向後箭頭，返回&#x200B;_[!UICONTROL 模擬]_&#x200B;頁面。

   +++

1. 選取&#x200B;**[!UICONTROL 開啟預覽]**&#x200B;以測試您的登陸頁面。

   登入頁面預覽會在新標籤中開啟。 選取的測試設定檔資料會取代個人化元素。

   ![含有設定檔資料的登陸頁面預覽](assets/landing-page-preview.png){width="600"}

1. 選取其他測試設定檔以預覽登陸頁面每個變體的呈現。

## 發佈頁面 {#publish-landing-page}

>[!PREREQUISITES]
>
>若要發佈登入頁面，您必須擁有&#x200B;**[!UICONTROL 發佈訊息]**&#x200B;許可權。  發佈之前，[檢查並解決所有警示](#check-alerts)。

當草稿頁面符合您的條件且您想要讓頁面可從歷程訊息連結時，請按一下右上方的&#x200B;**[!UICONTROL 發佈]**。 在確認對話中，按一下&#x200B;**[!UICONTROL 發佈]**。

![用於發佈的確認對話方塊](./assets/landing-page-publish-confirm.png){width="250"}

發佈登入頁面時，其會顯示在具有&#x200B;**_[!UICONTROL 已發佈]_**&#x200B;狀態的登入頁面清單中。 這表示其為即時狀態，並準備好用於透過歷程傳送的電子郵件、簡訊或WhatsApp訊息。

您無法將URL複製貼至網頁瀏覽器，以存取已發佈的登陸頁面。 您可以隨時使用[預覽函式](#test-landing-page)來測試它。

您可以透過特定報告監控您的登入頁面影響。
