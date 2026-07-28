---
title: 指令碼產生器
description: 使用Script Builder （電子郵件設計空間中的AI支援助理）來產生Handlebars個人化指令碼，並在Journey Optimizer B2B edition中轉換Marketo Engage Velocity指令碼。
feature: AI Assistant, Generative AI, Personalization, Email Authoring
role: User, Developer
badgeBeta: label="Beta" type="informative" tooltip="此功能目前在有限測試版中提供"
autotag-review: '2026-07-27T16:18:02.498Z'
TQID: 'https://experienceleague.adobe.com/JWnXAAbCuZVLv4ZhWubpNsZ61xbYU7xtdOXkG9uoWis'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: bd3c685c-6c92-4a4a-becb-535cc25215de
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 0004f8fba0c3d4ae89063418e4d3ef8fea22b0c3
workflow-type: tm+mt
source-wordcount: 1074
ht-degree: 2%

---

# 指令碼產生器

_指令碼產生器_&#x200B;是AI支援的助理，可在[!DNL Adobe Journey Optimizer B2B Edition]電子郵件設計空間中使用。 它可協助行銷人員和電子郵件開發人員更快建立個人化指令碼，並透過將現有的個人化邏輯轉換為[!DNL Journey Optimizer B2B Edition]以協助從[!DNL Marketo Engage]移轉，而不需手動重寫程式碼。

>[!AVAILABILITY]
>
>指令碼產生器目前僅適用於&#x200B;**_帳戶歷程_**&#x200B;中的電子郵件，可作為有限測試版提供給選取的客戶。 計畫在未來版本支援個人歷程。 若要取得存取權，請聯絡您的Adobe代表。

建立條件式電子郵件個人化（例如依地區設定切換語言區塊、依地區或角色交換內容，或插入動態設定檔或自訂物件值）需要編寫&#x200B;_Handlebars_&#x200B;運算式。 如果您從[!DNL Marketo Engage]移轉，您會面臨另一個挑戰，需要逐行重寫&#x200B;_Velocity_&#x200B;指令碼。 指令碼產生器可透過單一對話介面解決這兩個障礙：

* 從純語言說明產生新的Handlebars個人化指令碼。
* 貼上[!DNL Marketo Engage] Velocity指令碼並將其轉換為具有自動權杖對應的對等Handlebars指令碼。
* 直接預覽、編輯、驗證和儲存輸出至電子郵件，無需在工具之間複製和貼上。

## 指引和限制

>[!IMPORTANT]
>
>使用者對Script Builder的存取權是透過[!DNL Journey Optimizer B2B Edition]中其他產生AI功能所使用的相同許可權所控制。 如需授與功能許可權的資訊，請參閱[啟用AI助理存取權](../ai-assistant/enable-ai-assistant-access.md)。

使用指令碼產生器之前，請先檢閱[!DNL Journey Optimizer B2B Edition]中適用於產生AI功能的[指引和限制](../ai-assistant/generative-ai-content.md#general-guidelines-and-limitations)。 [在使用AI功能之前，還需要使用者同意](https://www.adobe.com/tw/legal/licenses-terms/adobe-gen-ai-user-guidelines.html){target="_blank"}。

熟悉[Handlebars範本化語言](https://handlebarsjs.com/guide/){target="_blank"}、[個人化語法](./personalization-syntax.md)，以及[!DNL Journey Optimizer B2B Edition]支援的[協助程式功能](./personalization-helper-functions.md)。 指令碼產生器會產生有效的Handlebars，但瞭解語法有助於您放心地檢閱和編輯輸出。

## 開啟指令碼產生器 {#open-script-builder}

指令碼產生器可從[個人化編輯器](./personalization.md)使用，而您[為帳戶歷程編寫電子郵件內容](./email-authoring.md)。

1. 在電子郵件設計空間中，選取您要新增或取代個人化指令碼的元件。

1. 若要開啟個人化編輯器，請按一下&#x200B;_新增個人化_ （ ![新增個人化圖示](../../assets/do-not-localize/icon-personalization-field.svg) ）圖示。

1. 在編輯器中，選取&#x200B;**[!UICONTROL 指令碼產生器]**。

   ![Personalization編輯器 — 選取指令碼產生器](./assets/personalization-script-builder-select.png){width="700" zoomable="yes"}

   >[!BEGINSHADEBOX]

   第一次存取指令碼產生器時，請檢閱[_[!UICONTROL 產生式AI使用條款&#x200B;]_](https://www.adobe.com/tw/legal/licenses-terms/adobe-gen-ai-user-guidelines.html){target="_blank"}，並確認您的合約。

   ![指令碼產生器中的Generative AI使用條款合約對話方塊](./assets/personalization-script-builder-gen-ai-terms.png){width="400"}

   >[!ENDSHADEBOX]

   Script Builder面板隨即開啟，其中包含對話式聊天介面。

   ![Personalization編輯器 — Script Builder面板](./assets/personalization-script-builder-welcome.png){width="700" zoomable="yes"}

1. 根據您想要做的事情開始聊天：

   * [產生新指令碼](#generate-personalization-script)
   * [轉換現有的Velocity指令碼](#convert-marketo-velocity-script)

## 產生個人化指令碼 {#generate-personalization-script}

使用Script Builder從純語言說明建立新的Handlebars個人化指令碼，而不需自行撰寫運算式。

指令碼產生器包含對應程式庫，會根據針對貴組織定義的[XDM欄位對應](../admin/xdm-field-management.md)，將[!DNL Marketo Engage]銷售機會和帳戶欄位解析為與其對等的[!DNL Journey Optimizer B2B Edition]個XDM設定檔屬性。

1. 在Script Builder聊天介面中，說明您想要的個人化邏輯。

   例如，說明決定要顯示哪個內容變體的屬性、自訂物件或條件。

1. 在預覽窗格中檢閱產生的Handlebars指令碼。

1. 如果您要調整邏輯或措辭，請直接在預覽窗格中編輯指令碼。

1. 按一下&#x200B;**[!UICONTROL 驗證]**&#x200B;以根據[!DNL Journey Optimizer B2B Edition]結構描述檢查指令碼。

   驗證會在您儲存指令碼之前擷取語法錯誤和未解析的Token參考，因此中斷的個人化不會發佈至即時電子郵件。

1. 按一下&#x200B;**[!UICONTROL 儲存]**，將指令碼直接插入電子郵件中選取的位置。

## 轉換Marketo Engage Velocity指令碼 {#convert-marketo-velocity-script}

使用Script Builder將現有的[!DNL Marketo Engage] Velocity指令碼移轉至[!DNL Journey Optimizer B2B Edition]的對等Handlebars指令碼。

1. 在Script Builder聊天中，輸入`Convert this`並貼上您要轉換的Velocity指令碼。

   指令碼產生器會剖析Velocity建構、比對代號參考至XDM設定檔屬性，並產生對等的Handlebars指令碼。

1. 檢閱[轉換報告](#review-conversion-report)和[解析任何需要手動對應](#resolve-tokens-without-mapping)的權杖。

1. [預覽及驗證](#preview-validate-script)產生的指令碼，然後直接儲存至電子郵件中。

### 支援的Velocity建構 {#supported-velocity-constructs}

指令碼產生器將下列[!DNL Marketo Engage]個Velocity控制流程建構轉換成其對應的Handlebars或條件式內容運算式：

| Velocity結構 | Handlebars或條件式內容等同專案 |
| ------------------- | --------------------------------------------- |
| `#if` / `#elseif` / `#else` | Handlebars `{{#if}}`、`{{else if}}`和`{{else}}`區塊協助程式，或[!DNL Journey Optimizer B2B Edition] [條件式內容](./conditional-content.md)規則 |
| `#set` | 所產生指令碼中的Handlebars變數指派 |

它將以區段為基礎的條件式邏輯轉譯為[條件式內容](./conditional-content.md)規則，以複製分支行為，包括含有許多語言變體區塊的電子郵件。

如果Velocity建構沒有直接的Handlebars或條件式內容等同專案，Script Builder會在[轉換報表](#review-conversion-report)中標示它，而非產生不完整或不正確的運算式。

### 檢閱轉換報告 {#review-conversion-report}

每次轉換後，Script Builder會顯示一個結構化報表，其中列出：

* 已成功對應的權杖。
* 需要手動解析的權杖。
* Velocity建構沒有等同於直接Handlebars。

在您解析任何剩餘的Token並儲存指令碼之前，請使用報表來確認轉換已完成。

### 解析沒有對應的權杖 {#resolve-tokens-without-mapping}

對於不在對應程式庫中的權杖（例如自訂銷售機會屬性或自訂[!DNL Marketo Engage]物件），指令碼產生器會嘗試以下列順序解析對應：

1. 它會根據可用的XDM欄位建議可能的對應，如果是自訂物件，則為貴組織設定的[模型型類別](./personalization.md#custom-datasets) （當有信賴的相符專案存在時）。

1. 如果它無法建議可信的配對，它會要求您在聊天中輸入正確的對應。

當您確認不在程式庫中的Token對應時，指令碼產生器會詢問您是否要記住此決定。 如果您同意，系統會記住來源[!DNL Marketo Engage]執行個體的對應，並以其Munchkin ID識別，這樣當您下次轉換該執行個體的指令碼時，相同的權杖會自動解析。

### 預覽及驗證指令碼 {#preview-validate-script}

在您認可轉換之前，Script Builder會並排預覽原始Velocity指令碼和產生的Handlebars輸出，並排支援內嵌編輯。 使用預覽來比較兩個版本，並直接在產生的指令碼中進行任何調整。

按一下&#x200B;**[!UICONTROL 驗證]**&#x200B;以根據[!DNL Journey Optimizer B2B Edition]結構描述檢查產生的Handlebars。 儲存時驗證會再次執行，這樣損壞的個人化就不會發佈到即時電子郵件。

當您滿意結果時，請按一下[儲存]，將指令碼直接插入電子郵件中所選的位置。****

<!--
### Save reusable conversion profiles {#save-reusable-conversion-profiles}

Save your field mappings and segment mappings as a reusable conversion profile so that your token schema does not need to be re-entered for each script or migration batch. Select a saved profile at the start of a conversion to apply its mappings automatically.

### Audit logs {#conversion-audit-logs}

Script Builder records an audit log for every conversion event, including which scripts were processed, which tokens were remapped, which tokens required manual intervention, and who approved the final output. Use the audit log to review migration activity across your organization.

-->
