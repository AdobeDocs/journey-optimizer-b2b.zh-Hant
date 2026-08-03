---
title: Content Credentials
description: 瞭解Adobe Journey Optimizer B2B edition如何將Content Credentials自動套用至使用創作AI工具產生或編輯的影像，以及這對於您的內容有何意義。
feature: Assets, Content
role: User
autotag-review: '2026-07-31T22:15:54.535Z'
TQID: 'https://experienceleague.adobe.com/9XCqPWz62uDDLFAyxARfD2jErYx2aOiOB5fAOGLLTbo'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a65c8aea-b21a-41ce-9ed7-6b517a69fd0bid: bef5003b-cad2-4f40-bdb2-a80426d52ef5id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: c8402946-ff35-44c5-ab98-74c1bba0975f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ad794b50f6c6f3b59e853e99f7983136ee098e18
workflow-type: tm+mt
source-wordcount: 913
ht-degree: 0%

---

# Content Credentials

行銷組織更關注內容透明度、AI揭露和防止資產竄改。 Adobe的Content Authenticity Initiative (CAI)建立符合[內容來源與真偽聯盟](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA)技術標準的工具。 _Content Credentials_，加密且容易篡改的中繼資料，可協助檢視者瞭解內容歷程，並確保品牌資產的完整性。 此資訊包括：

* 簽發者或簽署者 — 關於簽發數位簽名以證明或簽署資產的實體或公司的資訊。
* 問題日期 — Content Credential套用至資產的日期。
* 評分和使用 — 有關資產製作者的資訊，包括名稱、社群媒體控制代碼或其他身分相關資訊。
* 程式 — 對資產進行任何編輯或修改的記錄。
* 裝置詳細資料 — 關於用來建立或編輯資產的應用程式或裝置的資訊。
* 使用的AI工具 — 如果使用generative AI編輯或建立資產，則可能包含使用的模型名稱。
* 其他相關資訊 — 可能還會包含其他資料，以協助提供有關資產歷史記錄的更多內容。

如需資產記錄的完整資訊，您可以使用Adobe Content Authenticity [檢查工具](https://contentauthenticity.adobe.com/inspect)。

Content Credentials會與影像檔案一起儲存。 使用產生AI產生或編輯的影像上傳至[!DNL Adobe Journey Optimizer B2B Edition]或從匯出時，會保留其Content Credentials。

>[!NOTE]
>
>有些將影像匯入內容的方法(例如從PDF或內嵌(base64)來源擷取影像)可能不會保留原始Content Credentials。 在這些情況下，無法從來源讀取Content Credentials，並且不會為結果建立任何專案。

>[!BEGINSHADEBOX]

## Content Credentials透過管道的持續性 {#channels}

當您將影像納入電子郵件或WhatsApp訊息中時，也會持續儲存傳送影像的Content Credentials：

* **電子郵件** — 當您使用&#x200B;_傳送電子郵件_&#x200B;歷程動作時，請將影像從&#x200B;_Assets_&#x200B;資料庫新增至您的電子郵件內容。 在傳送電子郵件時，收件者可以從訊息下載影像，且Content Credentials是完整的。
* **WhatsApp** — 將影像新增至Meta業務帳戶中的WhatsApp訊息範本。 您可以直接從自己的系統新增，或從&#x200B;_Assets_&#x200B;資料庫下載影像檔案。 使用範本進行&#x200B;_傳送WhatsApp_&#x200B;歷程動作。 傳送WhatsApp訊息時，收件者可以從訊息下載影像，且Content Credentials完好無損。

>[!ENDSHADEBOX]

## 影響Content Credentials的動作 {#cc-workflows}

>[!INFO]
>
>圍繞創作AI透明度的新法律不斷湧現，Adobe正在努力滿足各個司法轄區的適用要求。 Content Credentials是Adobe用來符合這些法律要求的來源工具。

當您在[!DNL Journey Optimizer B2B Edition]中使用產生式AI工具產生或編輯影像時，Content Credentials會自動附加至該影像，而您不需要採取任何動作。

### 產生影像 {#generate}

**_Example:_**&#x200B;從描述所需視覺效果的文字提示產生電子郵件的橫幅影像。 Content Credentials會附加至產生的影像。

當您從文字提示、參考影像或產生類似影像來建立新影像時，Content Credentials一律會附加。

### 裁切影像 {#crop}

**_範例:_**

* 裁切產生的橫幅影像以符合網頁。 Content Credentials會透過裁切保留。
* 使用上傳的庫存像片作為電子郵件背景，並裁切以符合熒幕。 如果庫存像片不含產生的AI資訊，則不會建立Content Credentials。

當您調整影像檔案時（例如將其裁切成要求的尺寸），只有在來源影像已有影像時，它才會保留Content Credentials。 裁切會重新建立影像的畫素，這通常會移除該Content Credential，因此AI助理會在裁切前從來源影像讀取該畫素，然後重新建立該畫素，並將其重新附加到裁切的結果。 裁切本身不會新增創作AI動作，而是保留現有動作。

### 新增文字覆蓋

**_Example:_**&#x200B;在登陸頁面產生的背景影像上，製作促銷標題作為文字覆蓋。 背景影像中的Content Credentials會保留。

當您在背景影像上方轉譯產生的文字時，只有在背景影像已具有Content Credentials的情況下，才會將Content Credentials附加至產生的影像。 彩現覆蓋會產生新影像，因此影像編輯工具會從背景讀取Content Credentials並重新附加至結果。 覆蓋步驟不會新增新產生的AI動作。

### 覆蓋影像

**_範例:_**

* 結合已產生的產品影像與已產生的背景，以建立電子郵件標題。 結果包含反映兩個產生AI來源的Content Credentials。
* 將兩張上載的品牌像片合併為一個拼貼影像。 由於兩個來源影像都不會執行產生式AI動作，因此不會建立Content Credentials。

當您將兩個或多個影像組合在一起，且任何來源影像具有Content Credentials時，組合影像會保留這些影像，並合併至單一Content Credentials中繼資料元素中。 合成作業會從來源產生新影像，這通常會移除那些Content Credentials。 但影像編輯工具在撰寫前會先讀取每個專案，然後建立單一合併Content Credentials元素，列出貢獻產生AI動作的每個來源。

<!--

In [!DNL Adobe Journey Optimizer B2B Edition], you can see Content Credentials directly within the _Assets_ library. When you open the asset details, any image with Content Credentials (such as those created with GenAI services) shows the manifest details in a dedicated panel. If the asset is downloaded, published, or shared, the Content Credentials remain intact with the asset.

_To access Content Credentials:_

1. In the left navigation, expand **[!UICONTROL Content Management]** and select **[!UICONTROL Assets]**.

   This action opens a listing page with all the assets listed.

1. Navigate to a folder, and select the desired asset.

1. In the right panel, ??? where is it.

-->