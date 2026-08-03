---
title: Content Credentials
description: 瞭解Adobe Journey Optimizer B2B Prime如何將Content Credentials自動套用至使用創作AI產生的影像，以及這對於您的內容有何意義。
feature: Assets, Content
role: User
badgeBeta: label="Beta" type="informative" tooltip="此功能屬於有限測試版的一部分。"
autotag-review: '2026-07-31T22:31:06.899Z'
TQID: 'https://experienceleague.adobe.com/fBPnAmupve3xMSw5fZPQBDTUfr-rwiH2-R3wbKvox-E'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a65c8aea-b21a-41ce-9ed7-6b517a69fd0b
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
  - id: c8402946-ff35-44c5-ab98-74c1bba0975f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ad794b50f6c6f3b59e853e99f7983136ee098e18
workflow-type: tm+mt
source-wordcount: 560
ht-degree: 0%

---

# Content Credentials

行銷組織更關注內容透明度、AI揭露和防止資產竄改。 Adobe的Content Authenticity Initiative (CAI)建立符合[內容來源與真偽聯盟](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA)技術標準的工具。 _Content Credentials_，加密且容易篡改的中繼資料，可協助檢視者瞭解內容歷程，並確保品牌資產的完整性。 此資訊包括：

* 發行者或簽署者 — 發行數位簽名以認證或簽署資產的實體或公司的相關資訊。
* 問題日期 — 將Content Credential套用至資產的日期。
* [Credit and Usage] — 有關資產製作者的資訊，包括名稱、社群媒體控制代碼或其他與身分相關的資訊。
* 程式 — 對資產所做的任何編輯或修改的記錄。
* 裝置詳細資訊 — 關於用來建立或編輯資產的應用程式或裝置的資訊。
* 使用的AI工具 — 如果使用產生AI來建立資產，則可能會包含使用的模型名稱。
* 其他相關資訊 — 可能也會包含其他資料，以協助提供有關資產歷史記錄的更多內容。

如需資產記錄的完整資訊，您可以使用Adobe Content Authenticity [檢查工具](https://contentauthenticity.adobe.com/inspect)。

Content Credentials會與影像檔案一起儲存。 使用產生AI產生或編輯的影像上傳至[!DNL Adobe Journey Optimizer B2B Prime]或從匯出時，會保留其Content Credentials。

>[!NOTE]
>
>有些將影像匯入內容的方法(例如從PDF或內嵌(base64)來源擷取影像)可能不會保留原始Content Credentials。 在這些情況下，無法從來源讀取Content Credentials，並且不會為結果建立任何專案。

>[!BEGINSHADEBOX]

## Content Credentials透過管道的持續性 {#channels}

當您將影像納入電子郵件或WhatsApp訊息中時，也會持續儲存傳送影像的Content Credentials：

* **電子郵件** — 當您使用&#x200B;_傳送電子郵件_&#x200B;歷程動作時，請將影像從&#x200B;_Assets_&#x200B;資料庫新增至您的電子郵件內容。 在傳送電子郵件時，收件者可以從訊息下載影像，且Content Credentials是完整的。
* **WhatsApp** — 將影像新增至Meta業務帳戶中的WhatsApp訊息範本。 您可以直接從自己的系統新增，或從&#x200B;_Assets_&#x200B;資料庫下載影像檔案。 使用範本進行&#x200B;_傳送WhatsApp_&#x200B;歷程動作。 傳送WhatsApp訊息時，收件者可以從訊息下載影像，且Content Credentials完好無損。

>[!ENDSHADEBOX]

## 影像產生 {#generate}

>[!INFO]
>
>圍繞創作AI透明度的新法律不斷湧現，Adobe正在努力滿足各個司法轄區的適用要求。 Content Credentials是Adobe用來符合這些法律要求的來源工具。

當您使用generative AI為[!DNL Journey Optimizer B2B Prime]中的電子郵件內容建立影像時，Content Credentials會自動附加至產生的影像，您不需要採取任何動作。 產生式AI工具會針對具有現有憑證（包括原始來源）的影像變體產生合併的Content Credentials元素。

>[!NOTE]
>
>[!DNL Journey Optimizer B2B Prime]目前不支援手動影像編輯動作。 這些動作的Content Credentials工作流程目前不適用。
