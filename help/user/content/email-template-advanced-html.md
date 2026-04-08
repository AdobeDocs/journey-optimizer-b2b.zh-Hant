---
title: 電子郵件範本設計的進階HTML模式
description: 使用進階HTML模式，直接在Journey Optimizer B2B edition的電子郵件設計空間中檢視及編輯電子郵件範本內容的原始HTML來源。
feature: Email Authoring, Templates, Content Design Tools
level: Experienced
role: User
source-git-commit: 95dba963e08125370f998cf3960d51ede94c2fb9
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---

# 適用於電子郵件範本設計的進階HTML模式

_進階HTML模式_&#x200B;提供檢視，讓經驗豐富的使用者直接檢視及編輯電子郵件範本內容的原始原始程式碼。 如果您想要將複雜的運算式（例如條件式邏輯）直接插入來源中，這個模式是理想的選擇。 在超越視覺設計工具所公開範圍的結構調整上，它也很有用。

<!-- We don't have the code editor at this point 
>[!NOTE]
>
>_Advanced HTML mode_ is different from the code editor option that is available when you start a new design. The code editor does not allow you to change to the visual design space. With _advanced HTML mode_, you can toggle back and forth between the HTML source view and the visual design view at any time. -->

>[!AVAILABILITY]
>
>此功能目前處於&#x200B;_有限可用性_&#x200B;中，並非所有使用者都可使用。

## 重要限制

在您使用進階HTML模式進行[電子郵件範本編寫](./email-template-authoring.md)之前，請確定您瞭解下列限制：

* **沒有驗證** — HTML編輯器不會執行語法檢查或配置驗證。 儲存前，請仔細檢閱您的程式碼。

* **內容更新** — 未來的系統變更可能會影響或覆寫在進階HTML模式下對預設標籤所做的修改。 在產品更新後檢查您的內容，確保內容如預期般呈現。

* **有限支援** — Adobe無法疑難排解在進階HTML模式中修改自訂程式碼所造成的轉譯問題或內容錯誤。

* **預覽限制** — 內容模擬（使用設定檔預覽）僅適用於案頭檢視，而非直接從HTML來源檢視。

### 存取進階HTML模式

當在畫布中載入電子郵件範本時，可從視覺設計空間頂端的工具列存取進階HTML模式。

1. 開啟或[建立電子郵件範本](./email-templates.md#create-an-email-template)並開啟設計空間以編輯內容。

1. 在設計空間中，按一下工具列中的&#x200B;_[!UICONTROL HTML]_ （ ![HTML圖示](../assets/do-not-localize/icon-code.svg) ）圖示。

   ![按一下電子郵件範本設計空間工具列中的HTML圖示](./assets/email-template-advanced-html-mode-toolbar.png){width="750" zoomable="yes"}

   如果您是第一次開啟進階HTML模式（或經過一個月以上），系統會顯示警告訊息。 檢閱資訊，然後按一下[確定] **&#x200B;**&#x200B;以繼續。

   ![檢閱進階HTML模式警告，然後按一下[確定]繼續](./assets/email-template-html-mode-warning.png){width="500"}

   設計畫布會切換為原始HTML來源檢視。

1. 檢閱程式碼，並將所需的變更新增至電子郵件內容。

   在&#x200B;_進階HTML模式_&#x200B;中，您可以直接存取電子郵件範本內容的完整HTML來源：

   * 檢視和修改原始HTML標籤的任何部分。
   * 將進階[個人化運算式](./personalization.md)直接插入來源。
   * 使用運算式語法新增[條件式內容](./conditional-content.md)邏輯。
   * 新增自訂HTML屬性、追蹤標籤，或其他無法透過視覺化編輯器控制項使用的標籤。

   ![進階HTML模式搭配電子郵件內容的原始HTML來源](./assets/email-template-advanced-html-mode.png){width="800" zoomable="yes"}

   >[!IMPORTANT]
   >
   >請務必輸入正確的HTML和CSS程式碼；Adobe不提供語法驗證或自訂程式碼支援。

   基於相容性原因，內容模擬和儲存不適用於進階HTML模式。 您可以切換回案頭檢視，以預覽您的內容並儲存範本。 當您在HTML來源檢視和視覺化設計檢視之間切換時，您所做的任何編輯都會保留。

   如果您在進階HTML模式中按一下右上方的&#x200B;**[!UICONTROL 儲存]**&#x200B;或&#x200B;**[!UICONTROL 儲存並關閉]**，會出現警示對話方塊，通知您必須在儲存範本並退出設計空間之前切換出進階HTML模式。

   ![在進階HTML模式下已停用儲存的警示對話方塊](./assets/email-template-advanced-html-save-disabled-alert.png){width="500"}

1. 按一下工具列中的&#x200B;_[!UICONTROL 案頭]_ （ ![案頭圖示](../assets/do-not-localize/icon-desktop-spectrum-1.svg) ）圖示，從進階HTML模式（HTML來源檢視）切換為視覺化設計畫布。

   當您切換檢視時，您的編輯會保留。
