---
title: 表單設計
description: 瞭解如何設計用於收集商業潛在客戶資訊的可重複使用表單。
feature: Forms, Content Design Tools
role: User
badgeBeta: label="Beta" type="informative" tooltip="此功能目前在有限測試版中提供"
exl-id: 1e19e8a7-8d4f-442f-a2e6-aba52e5a356c
source-git-commit: fd26ecdb0457141f7beb7fd46d01e609da011a38
workflow-type: tm+mt
source-wordcount: '2054'
ht-degree: 1%

---

# 表單設計

在您[建立表單](./forms.md#create-forms)之後，視覺化設計空間會開啟具有預設基本表單定義的草稿。 在右側的&#x200B;_[!UICONTROL 摘要]_&#x200B;面板中，按一下&#x200B;**[!UICONTROL 編輯表單]**，並使用視覺化設計空間來定義表單樣式和欄位元件。

![存取表單庫](./assets/form-new-design-space.png){width="700" zoomable="yes"}

## 欄位

表單欄位用於擷取人員設定檔資料，這些資料可用於鎖定人員並將他們與帳戶和購買群組建立關聯。 所有新表單在單一欄版面配置中都以下列欄位開頭：

* 名字
* 姓氏
* 電子郵件地址

使用欄位設計工具來建構一組欄位和版面配置，以收集以帳戶為基礎行銷活動所需的資料。

### 新增欄位 {#add-field}

1. 在左側的&#x200B;_[!UICONTROL 元件]_&#x200B;面板中，將&#x200B;**[!UICONTROL 欄位]**&#x200B;內容元件拖放到畫布上。

   ![新增欄位元件至表單](./assets/form-content-add-field.png){width="700" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 選取欄位屬性]**。

1. 在&#x200B;_[!UICONTROL 選取欄位屬性]_&#x200B;對話方塊中，選取您要用於欄位之人員設定檔屬性的核取方塊，然後按一下&#x200B;**[!UICONTROL 選取]**。

   [XDM商業結構描述](../data/field-mapping.md#xdm-business-person-attributes)決定可用的屬性。  您也可以使用為您的Journey Optimizer B2B edition執行個體定義的任何自訂欄位。 使用「搜尋」文字方塊可依名稱篩選清單，或按一下「篩選」圖示可依結構/資料型別篩選清單。

   ![新增欄位元件至表單](./assets/form-field-select-attribute-filtered.png){width="700" zoomable="yes"}

   在畫布上，所選屬性的預設欄位標籤會填入畫布上。 **[!UICONTROL 欄位詳細資料]**&#x200B;會顯示在右側的面板中。

1. 如有需要，請變更&#x200B;**[!UICONTROL 標籤]**&#x200B;文字。

   此文字會顯示在表單中的欄位旁。 預設文字會從欄位屬性填入。

1. 根據欄位的資料型別設定&#x200B;**[!UICONTROL 欄位型別]**：

   | 欄位型別 | 使用情況 | 範例 |
   | ---------- | ----- | ------- |
   | **[!UICONTROL 核取方塊]** | 使用此型別，讓訪客可以選取&#x200B;_true_ （已核取）或&#x200B;_false_ （未核取）值。 | |
   | **[!UICONTROL 核取方塊群組]** | 使用此型別，讓訪客可以為多個專案選取&#x200B;_true_ （已核取）或&#x200B;_false_ （未核取）值。 | |
   | **[!UICONTROL 貨幣]** | 使用此型別可允許代表為Journey Optimizer B2B edition執行個體選取的預設貨幣型別的浮點數欄位。 | |
   | **[!UICONTROL 日期]** | 使用此型別將輸入限製為日期格式，並在欄位中提供行事曆選擇器。 | |
   | **[!UICONTROL 雙倍]** |  | |
   | **[!UICONTROL 電子郵件]** | 使用此型別將輸入限製為電子郵件地址格式。 | |
   | **[!UICONTROL 數字]** | 使用此型別將欄位限製為數值。 | |
   | **[!UICONTROL 無線電群組]** | 使用此型別可允許訪客選取一組選項之一。 | |
   | **[!UICONTROL 選取]** | 使用此型別，可讓訪客使用下拉式清單選取一組選項之一。 | |
   | **[!UICONTROL 滑桿]** | 使用此型別，可讓訪客使用滑桿設定數值。 | |
   | **[!UICONTROL 電話]** | 將此型別用於電話號碼輸入欄位。 | |
   | **[!UICONTROL 文字]** | 將此型別用於標準文字（字串）輸入欄位。 | |
   | **[!UICONTROL 文字區域]** | 使用此型別支援較長的文字輸入。 | |
   | **[!UICONTROL URL]** | 使用此型別將文字輸入限製為URL，包括標準URL通訊協定。 | |

1. 視選取的欄位型別而定，設定欄位輸入與驗證的其他選項：

   ![根據選取的欄位型別設定欄位選項](./assets//form-field-details-text-type.png){width="400" zoomable="yes"}

   * **[!UICONTROL 預留位置]** — 欄位的預留位置值，提供訪客該欄位應有的範例。

   * **[!UICONTROL 指示]** — 可協助訪客完成欄位的指示文字。 輸入您要顯示為&#x200B;_暫留文字_&#x200B;的欄位文字。

     >[!TIP]
     >
     >_指示與預留位置文字_<br/>
     >
     >使用這兩個屬性來引導訪客填寫欄位。 將指標暫留在欄位上時，指示文字會顯示為工具提示/快顯文字。 預留位置文字在欄位內顯示&#x200B;_變暗_，當訪客將其文字加入欄位時便會消失。 您可以使用這兩種方法，或只使用其中一種。

   * **[!UICONTROL 預設值]** — 使用此選項來指定欄位的預設值。

   * **[!UICONTROL 驗證訊息]** — 使用此選項來指定欄位的驗證訊息。 如果訪客為欄位輸入無效值，則會顯示此訊息。 _[!UICONTROL Standard]_&#x200B;訊息已預設設定。 選擇&#x200B;**[!UICONTROL 自訂]**&#x200B;並輸入您自己的訊息。

   * **最大長度** — 輸入欄位可輸入的最大字元數。

1. 視需要設定&#x200B;**[!UICONTROL 欄位行為]**：

   * **必要** — 選取核取方塊，讓欄位輸入成為提交表單的必要欄位。

   * **啟用輸入遮罩** — 選取核取方塊，以使用輸入遮罩限制訪客的輸入。 例如，您可能希望訪客以特定格式輸入電話號碼。 在對話方塊中，使用`9`輸入任何數字的遮罩，`a`輸入任何字母，`*`輸入任一數字。 按一下「儲存」以啟用指定的輸入遮罩。

     ![定義欄位](./assets/form-field-mask-input-dialog.png){width="500" zoomable="yes"}的輸入遮罩

### 變更欄位樣式 {#field-styling}

選取右側面板中的&#x200B;**[!UICONTROL 樣式]**&#x200B;索引標籤，以變更所選欄位的樣式。

* **[!UICONTROL 背景]** — 選取核取方塊以套用欄位的背景顏色。 預設顏色為白色。 按一下&#x200B;**[!UICONTROL 背景顏色]**&#x200B;方塊以開啟彈出式檢色器，並選擇欄位背景的顏色。

  ![設定表單欄位的背景樣式](./assets/form-field-styles-background-color.png){width="600" zoomable="yes"}

* **[!UICONTROL 標籤]** — 標籤樣式會控制欄位旁邊所顯示文字的視覺特性。 選擇相對於欄位的頂端或側邊標籤顯示。 您可以設定字型大小、行高、文字樣式及文字對齊方式。 按一下&#x200B;**[!UICONTROL 字型顏色]**&#x200B;方塊以開啟彈出式檢色器，並選擇標籤文字的顏色。

  ![設定表單欄位的標籤樣式](./assets/form-field-styles-label.png){width="600" zoomable="yes"}

* **[!UICONTROL 邊框]** — 按一下&#x200B;**[!UICONTROL 邊框顏色]**&#x200B;方塊以開啟彈出式檢色器，並選擇邊框顏色。 您可以定義欄位的邊框，包括顏色和線條寬度。 清除核取方塊可移除顯示的欄位邊框。 您也可以變更邊角的邊框大小（畫素寬度）、樣式和半徑設定。

  ![設定表單欄位的框線樣式](./assets/form-field-styles-border.png){width="600" zoomable="yes"}

* **[!UICONTROL 大小]** — 選取大小設定以決定欄位的顯示寬度。 選擇&#x200B;_[!UICONTROL 全寬]_、_[!UICONTROL 半寬]_&#x200B;或&#x200B;_[!UICONTROL 自動]_。

* **[!UICONTROL 邊界]** — 設定欄位周圍的邊界（畫素）。 您可以在所有四個邊上設定相同的邊界，或選取&#x200B;**[!UICONTROL 每個邊不同的邊界]**&#x200B;核取方塊，分別設定水準邊界和垂直邊界。

* **[!UICONTROL 內距]** — 設定欄位周圍的內距（畫素）。 您可以在所有四個邊上設定相同的邊界，或選取&#x200B;**[!UICONTROL 每個邊不同的邊距]**&#x200B;核取方塊，分別設定水準邊界和垂直邊界。

  ![設定表單欄位的大小、邊界和填補樣式](./assets/form-field-styles-size-margin-padding.png){width="600" zoomable="yes"}

### 重新排序欄位 {#field-reorder}

您可以在視覺工作區中直接移動表單欄位。 按一下所選欄位右邊緣的&#x200B;_移動_&#x200B;工具，並將其拖曳到新位置。

將結構元件新增至表單，並將欄位移動至欄，以分組它們並變更版面。 按一下所選欄元件左邊緣的&#x200B;_移動_&#x200B;工具，並將其拖曳至表單中的新位置。

![移動表單中的欄位並使用結構元件進行分組和佈局](./assets/form-field-move-tool.png){width="500"}

### 刪除或複製欄位 {#field-delete-duplicate}

按一下工具列或右側面板中的&#x200B;_刪除_&#x200B;圖示（![刪除圖示](../assets/do-not-localize/icon-delete.svg)）以刪除選取的欄位。 在確認對話框中，按一下「**[!UICONTROL 刪除]**」。

按一下工具列或右側面板中的&#x200B;_複製_&#x200B;圖示（![復製圖示](../assets/do-not-localize/icon-duplicate.svg)）以複製選取的欄位。 新欄位會顯示在原始欄位的正下方。 按一下&#x200B;**[!UICONTROL 選取欄位屬性]**&#x200B;以設定欄位屬性。 視需要設定欄位型別、詳細資訊和樣式。

![刪除和複製表單欄位的圖示](./assets/form-field-delete-duplicate.png){width="600" zoomable="yes"}

## 提交按鈕

依預設，提交按鈕（頁尾欄位）是表單的一部分，無法移除。 在表單中選取按鈕/頁尾元件，以變更按鈕的文字和樣式。

### 編輯按鈕內容 {#button-content}

使用右側面板中顯示的&#x200B;_[!UICONTROL Content]_&#x200B;索引標籤，變更&#x200B;**[!UICONTROL 按鈕文字]**&#x200B;欄位中的文字。 按鈕大小會調整以符合文字的長度。

![變更表單中的按鈕文字](./assets//form-field-button-text.png){width="600" zoomable="yes"}

### 設定提交按鈕的樣式 {#button-styles}

選取右側面板中的&#x200B;**[!UICONTROL 樣式]**&#x200B;索引標籤，以變更所選按鈕/頁尾元件的樣式。

* **[!UICONTROL 背景]** — 選取核取方塊以套用按鈕的背景顏色。 藍色是預設顏色。 按一下&#x200B;**[!UICONTROL 背景顏色]**&#x200B;方塊以開啟彈出式檢色器，並選擇按鈕背景的顏色。

  ![設定表單按鈕的背景樣式](./assets/form-button-styles-background-color.png){width="600" zoomable="yes"}

* **[!UICONTROL 標籤]** — 標籤樣式控制按鈕內文字的視覺特性。 您可以設定字型大小、行高、文字樣式及文字對齊方式。 按一下&#x200B;**[!UICONTROL 字型顏色]**&#x200B;方塊以開啟彈出式檢色器，並選擇標籤文字的顏色。

* **[!UICONTROL 邊框]** — 按一下&#x200B;**[!UICONTROL 邊框顏色]**&#x200B;方塊以開啟彈出式檢色器，並選擇邊框顏色。 您可以定義按鈕的框線，包括顏色和線條寬度。 清除核取方塊可移除顯示的按鈕邊框。 您也可以變更圓角邊框大小（畫素寬度）、樣式和半徑設定。

* **[!UICONTROL 大小]** — 選取大小設定以決定按鈕的顯示寬度。 選擇&#x200B;_[!UICONTROL 全寬]_、_[!UICONTROL 半寬]_&#x200B;或&#x200B;_[!UICONTROL 自動]_。 內距會根據大小和對齊設定進行調整。

  ![設定表單按鈕的標籤、邊框和大小樣式](./assets/form-button-styles-label-border-size.png){width="600" zoomable="yes"}

* **[!UICONTROL 按鈕對齊方式]** — 當您選擇按鈕的&#x200B;_半寬_&#x200B;或&#x200B;_自動_&#x200B;大小時，請將對齊方式設定在左、右或中央。 內距會根據大小和對齊設定進行調整。

* **[!UICONTROL 邊界]** — 設定欄位周圍的邊界（畫素）。 您可以在所有四個邊上設定相同的邊界，或選取&#x200B;**[!UICONTROL 每個邊不同的邊界]**&#x200B;核取方塊，分別設定水準邊界和垂直邊界。

* **[!UICONTROL 內距]** — 設定欄位周圍的內距（畫素）。 您可以在所有四個邊上設定相同的邊界，或選取&#x200B;**[!UICONTROL 每個邊不同的邊距]**&#x200B;核取方塊，分別設定水準邊界和垂直邊界。 如果您變更大小和對齊設定，邊框間距會隨之調整。

  ![設定表單按鈕的對齊方式、邊界和邊框間距樣式](./assets/form-button-styles-alignment-margin-padding.png){width="600" zoomable="yes"}

## 表單樣式 {#form-styling}

當您在結構或表單元件外部按一下時，可以變更表單元區的樣式。 表單元件（欄位和按鈕）會繼承定義最上層樣式的&#x200B;_內文_&#x200B;樣式，除非已在欄位或按鈕/頁尾層級定義其他樣式。

![設定表單主體的最上層樣式](./assets/form-body-styles.png){width="600" zoomable="yes"}

### CSS樣式

新表單使用預設的CSS來設定樣式。 如果您想要透過修改CSS來變更樣式，可以複製樣式，然後使用樣式來定義表單的自訂CSS。

定義表單&#x200B;:_的自訂CSS(_T)

1. 按一下右側面板中的&#x200B;**[!UICONTROL 檢視CSS]**&#x200B;以檢視CSS程式碼。

   ![設定表單的背景顏色](./assets/form-body-styles-view-css.png){width="450" zoomable="yes"}

1. 在捲動視窗中選取CSS程式碼，並將其複製到剪貼簿。

1. 按一下 **[!UICONTROL 關閉]**。

1. （選用）將複製的程式碼貼到您最愛的CSS工具中，並編輯CSS以反映您想要的樣式。

1. 按一下右側面板中的「**[!UICONTROL 新增自訂CSS]**」。

1. 將CSS程式碼貼到視窗中。

   ![設定表單的背景顏色](./assets/form-body-styles-custom-css.png){width="450" zoomable="yes"}

   您可以在此視窗中編輯貼上的文字。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

### 手動樣式設定

變更右側面板中的設定，以定義整個表單的顯示。

* **[!UICONTROL 背景顏色]** — 選取核取方塊以在表單區域周圍套用背景顏色。 預設顏色為白色。 按一下顏色方塊以開啟彈出式檢色器，並選擇表單背景的顏色。

* **[!UICONTROL 檢視區背景]** — 選取核取方塊以將背景顏色套用至所有表單元件。 預設為無顏色（繼承自外部背景）。 按一下顏色方塊以開啟彈出式檢色器，並選取表單結構元件的顏色。

  ![設定表單的背景顏色](./assets/form-body-styles-background-colors.png){width="600" zoomable="yes"}

* **[!UICONTROL 文字]** — 選擇表單的&#x200B;**[!UICONTROL 字型系列]**，這會影響表單欄位的標籤、提示及預留位置文字。 它也會影響預設的提交按鈕文字。

* **[!UICONTROL 大小]** — 變更表單的大小（寬度） （以畫素為單位）。

* **[!UICONTROL 邊界]** — 設定表單元件周圍的邊界（畫素）。 您可以在所有四個邊上設定相同的邊界，或選取&#x200B;**[!UICONTROL 每個邊不同的邊界]**&#x200B;核取方塊，分別設定水準邊界和垂直邊界。

  ![設定表單的文字、大小和邊界](./assets/form-body-styles-text-size-margin.png){width="600" zoomable="yes"}
