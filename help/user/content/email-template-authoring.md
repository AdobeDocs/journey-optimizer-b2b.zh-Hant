---
title: 電子郵件範本製作
description: 瞭解如何撰寫可用於帳戶歷程電子郵件的內容電子郵件範本，以輕鬆且有效率地重複使用您的設計。
feature: Email Authoring, Content
source-git-commit: 8315c760e573aa36819652798a400206e6268ccc
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 10%

---

# 電子郵件範本製作

在您[建立電子郵件範本](./email-templates.md#create-an-email-template)之後，請使用視覺化設計工具來編寫電子郵件範本中的結構和內容元件。

## 新增結構和內容 {#structure-content}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_template"
>title="新增結構元件"
>abstract="結構元件會定義範本的版面。將&#x200B;**結構**&#x200B;元件拖放到畫布中，開始設計您的範本內容。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_template"
>title="關於內容元件"
>abstract="內容元件指可用於建立範本版面的空白內容預留位置。"

{{$include /help/_includes/content-design-components.md}}

### 新增片段

在視覺內容編輯器中，_片段_&#x200B;圖示會顯示在左側。 以下範例概述將片段新增至範本內容的步驟。

1. 若要開啟片段清單，請選取&#x200B;_片段_&#x200B;圖示（ ![片段圖示](../assets/do-not-localize/icon-fragments.svg) ）。

   您可以：

   * 排序清單。
   * 瀏覽、搜尋或篩選清單。
   * 在縮圖和清單檢視之間切換。
   * 重新整理清單以反映任何最近建立的片段。

   ![從清單中選取片段](./assets/visual-designer-fragments.png){width="700" zoomable="yes"}

1. 將任何片段拖放至結構元件的預留位置。

   編輯器會在電子郵件結構的區段/元素中轉譯片段。

片段的內容會在結構內動態更新，以顯示內容在電子郵件中的顯示方式。

>[!TIP]
>
>如果您希望片段佔據電子郵件內的整個水準版面，請新增1:1欄結構，然後將片段拖放至其中。

儲存電子郵件後，當您在摘要中選取&#x200B;_[!UICONTROL 使用者]_&#x200B;索引標籤時，它就會顯示在片段詳細資訊頁面中。 新增到電子郵件範本的片段在範本中無法編輯 — 來源片段會定義內容。

### 新增資產

{{$include /help/_includes/content-design-assets.md}}

### 導覽圖層、設定和樣式

{{$include /help/_includes/content-design-navigation.md}}

### 個人化內容

{{$include /help/_includes/content-design-personalization.md}}

### 編輯連結的URL追蹤

{{$include /help/_includes/content-design-links.md}}

## 檢視選項

運用視覺化設計工具中可用的檢視和內容驗證選項。

* 透過預設縮放選項放大/縮小內容。

* 切換在案頭、行動裝置或純文字/純文字間檢視內容。
   * 按一下&#x200B;_眼睛_&#x200B;圖示，即可跨裝置預覽內容。
   * 選取其中一個現成可用的裝置，或輸入自訂維度以預覽內容。

### 更多選項

從電子郵件設計工具頂端的&#x200B;_[!UICONTROL 更多……]_&#x200B;功能表，您可以執行下列動作：

![按一下[更多]以存取範本動作](./assets/visual-designer-more-menu.png){width="500"}

* **[!UICONTROL 重設範本]** — 按一下此選項，將視覺化設計工具畫布清除為空白並重新啟動建立內容。
* **[!UICONTROL 另存為片段]** — 將範本的所有或部份另存為片段，以便在多個電子郵件或電子郵件範本中重複使用。 您提供片段的名稱和說明，並將其儲存到可用片段清單中。
* **[!UICONTROL 變更您的設計]** — 返回&#x200B;_設計您的範本_&#x200B;頁面。 從那裡，您可以選擇從頭開始設計範本，或使用現有的範本來重新啟動設計流程。
* **[!UICONTROL 匯出HTML]** — 將視覺畫布中的內容以HTML格式下載到您的本機系統，並封裝成zip檔。
