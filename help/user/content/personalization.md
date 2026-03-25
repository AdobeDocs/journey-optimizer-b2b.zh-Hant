---
title: 內容個人化
description: 使用Journey OptimizerB2B版中的帳戶、人員和系統令牌對B2B電子郵件進行個性化。 瞭解如何使用個性化編輯器和語法。
feature: Personalization, Content Design Tools, Email Authoring
topic: Personalization
role: User, Developer
level: Intermediate
keywords: 表達式，編輯器，開始，個性化
exl-id: 60bf2e06-8d6e-4cc4-8aff-5c5ca11f05ab
source-git-commit: 10e02b821609c48b82ea0248501daa60de6daa12
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 6%

---

# 內容個人化 {#add-personalization}

>[!CONTEXTUALHELP]
>id="aj-b2b_personalization"
>title="個人化內容體驗"
>abstract="使用 **Adobe Journey Optimizer B2B Edition**，利用手邊關於各個特定接收者的資料與資訊，調整給其的訊息。 可以是使用者的名字、產業、職稱等。"

[!DNL Adobe Journey Optimizer B2B Edition]個性化功能允許您通過利用您擁有的有關電子郵件的資料和資訊，將電子郵件調整為每個特定收件人。 可以是使用者的名字、產業、職稱等。

使用&#x200B;_個性化編輯器_，您可以選擇、排列、自定義和驗證所有資料，以便為您的內容建立自定義個性化。 使用各種工具（如幫助程式功能）來定制消息。 編輯器使用基於&#x200B;_Handlebars_&#x200B;的內聯個性化語法，其中表達式由雙花括弧`{{}}`括起的內容構造。

處理消息時，Journey OptimizerB2B版用Adobe Experience Platform資料集和本地系統值中包含的資料替換表達式。 例如，`Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`動態變為`Hello John Doe`。

使用此語法，您可以在多個欄位中對郵件進行個性化設定，包括電子郵件主題行、郵件正文和發件人資訊。

## 個性化令牌

在[!DNL Journey Optimizer B2B Edition]中，您可以使用個性化令牌構建動態電子郵件內容：

* **帳戶令牌** — 這些令牌基於帳戶屬性，如&#x200B;_帳戶名_、_工業_&#x200B;和&#x200B;_員工數_。 使用這些令牌填充由&#x200B;**_XDM業務帳戶詳細資訊_**&#x200B;架構管理的屬性資料，該架構在Adobe Experience Platform定義。

* **人員令牌** — 這些令牌基於商業人員屬性，如&#x200B;_名字_、_職務_&#x200B;和&#x200B;_公司名稱_。 使用這些令牌填充由&#x200B;**_XDM Business Person Details_**&#x200B;架構管理的屬性資料，該架構在Adobe Experience Platform定義。

* **系統令牌** — 這些令牌基於系統欄位值，如&#x200B;_日期_、_時間_&#x200B;和&#x200B;_取消訂閱連結_。

* **我的令牌**（當為行程定義時） — 為電子郵件所在的行程定義的[自定義令牌](./personalization-my-tokens.md)。

>[!NOTE]
>
>瞭解有關[Adobe Experience Platform資料模型(XDM)文檔](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home){target="_blank"}中XDM架構的詳細資訊。

## 個性化編輯器

個性化編輯器在您需要在電子郵件內容中定義個性化的每個上下文中都可用。 在編輯器中，您可以選擇、排列、自定義和驗證所有資料，以便為您的內容建立自定義個性化。

按一下「_新增個人化_」（「![新增個人化圖示](../../assets/do-not-localize/icon-personalization-field.svg)」）圖示，在任何欄位或內容元件中新增個人化。

![Personalization編輯器](./assets/personalization-editor.png){width="800" zoomable="yes"}

>[!NOTE]
>
>下列有關個人化編輯器的資訊反映了[簡化架構](../simplified-architecture.md)上布建的[!DNL Journey Optimizer B2B Edition]環境可用的變更。

### Token和協助程式函式

若要使用個人化權杖或協助程式功能，請在左側導覽窗格中找出該權杖，然後按一下&#x200B;**+**&#x200B;將其新增至運算式。

按一下&#x200B;_更多功能表_ ( **...** )圖示(在&#x200B;_新增_ ( **+** )圖示旁)以檢視每個屬性的詳細資訊，並將您最常用的屬性新增至&#x200B;_我的最愛_。 新增至我的最愛屬性可從編輯器左側導覽的&#x200B;**[!UICONTROL 我的最愛]**&#x200B;功能表存取。

![Personalization編輯器 — Token更多功能表](./assets/personalization-editor-token-more-menu.png){width="800" zoomable="yes"}

<!-- >>[!NOTE]
>
>By default, the attributes list shows only populated attributes. To display all attributes, click the _Settings_ icon above the search field and toggle off the **[!UICONTROL Show only populated attributes]** option.
-->
您也可以定義預設後援文字字串，當字串型別的設定檔屬性為空白時就會顯示。 按一下屬性的&#x200B;_更多功能表_ ( **...** )圖示，然後選取&#x200B;**[!UICONTROL 插入後援文字]**。 輸入設定檔的屬性值為空時所應顯示的文字，然後按一下[新增]。**&#x200B;**

最佳實務是在將運算式插入內容之前先驗證該運算式。 按一下編輯器底部的&#x200B;**[!UICONTROL 驗證]**，檢查您的語法並確保沒有錯誤。

![Personalization編輯器驗證碼](./assets/personalization-editor-validated.png){width="500"}

當運算式完成且沒有錯誤時，請按一下[儲存]。**&#x200B;**

### 自訂資料集

[!BADGE Beta]{type=Informative tooltip="Beta功能"}

您可以使用關聯式結構描述進行電子郵件個人化。 自訂物件是在&#x200B;_關聯式結構描述_&#x200B;中定義，產品管理員可以在[!DNL Journey Optimizer B2B Edition]中[設定關聯式結構描述欄位](../admin/xdm-field-management.md#relational-schemas)。 可在個人化編輯器中存取這些欄位。 只有與「人員」或「帳戶」具有一對多(1:M)關係的自訂物件才可使用。

>[!IMPORTANT]
>
>在使用自訂物件進行指令碼式個人化之前，請確定您檢閱並瞭解[Handlebars範本化語言](https://handlebarsjs.com/guide/)、[個人化語法](./personalization-syntax.md)和內建[協助程式函式](./personalization-helper-functions.md)。

使用自訂物件定義個人化時，您可以透過&#x200B;**[!UICONTROL Personalization權杖]** （人員/銷售機會、帳戶、系統和My權杖）和&#x200B;**[!UICONTROL 自訂物件]** （關聯式結構描述），存取指令碼可存取物件中的所有變數。 選取自訂物件後，您可以按一下自訂物件資料夾來檢視欄位。 按一下每個要新增至運算式的欄位&#x200B;**+**。

![Personalization編輯器 — 模型型類別 — 新增自訂物件欄位](./assets/personalization-editor-custom-object-fields.png){width="700" zoomable="yes"}
