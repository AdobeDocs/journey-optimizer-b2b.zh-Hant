---
title: 片段製作
description: 瞭解如何編寫可重複用於您的電子郵件和範本設計的內容片段，以提高效率並維護設計和品牌標準。
feature: Fragments, Content Design Tools
role: User
exl-id: d29754cf-6721-489c-bff8-cde034456db2
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 19%

---

# 片段編寫

在您[建立片段](./fragments.md#create-fragments)之後，請使用視覺化編輯器來編寫片段中的結構和內容元件。

## 新增結構和內容 {#design-fragment}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_fragment"
>title="新增結構元件"
>abstract="結構元件會定義區段的版面。將&#x200B;**結構**&#x200B;元件拖放到畫布中開始設計您的片段內容。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_fragment"
>title="關於內容元件"
>abstract="內容元件指可用於建立片段版面的空白內容預留位置。"

{{$include /help/_includes/content-design-components.md}}

## 新增資產

{{$include /help/_includes/content-design-assets.md}}

## 導覽圖層、設定和樣式

{{$include /help/_includes/content-design-navigation.md}}

## 將內容個人化

{{$include /help/_includes/content-design-personalization.md}}

## 啟用片段自訂

當作者將片段新增至[電子郵件](./email-authoring.md#content-authoring---use-visual-fragments)或[電子郵件範本](./email-template-authoring.md#content-authoring---use-visual-fragments)時，依預設會鎖定片段內容。 對已發佈片段所做的任何變更都會自動傳播至使用該片段的所有內容資產。 當您將片段中元件的引數指定為可編輯時，電子郵件或範本作者可以指定特定於其需求的自訂欄位值。 此自訂標幟僅限影像、文字和按鈕視覺元件使用。

例如，如果您設計包含可點按按鈕的可重複使用橫幅，您可以將按鈕的URL引數指定為可編輯。 之後，電子郵件作者便可使用與其電子郵件促銷活動更為專屬的URL。 透過這些可自訂欄位，行銷人員可以管理和個人化可重複使用的內容，而無需建立全新的內容區塊或中斷來自原始片段的繼承更新。

1. 在視覺內容編輯器中，選取您要啟用自訂的影像、文字或按鈕元素。

1. 在右側的元件詳細資訊中，選取&#x200B;**[!UICONTROL 可編輯欄位]**&#x200B;索引標籤。

1. 按一下&#x200B;**[!UICONTROL 啟用版本]**&#x200B;選項切換並設定可編輯的欄位。

   ![啟用片段影像元件的可編輯欄位](./assets/fragment-editable-fields-image.png){width="700" zoomable="yes"}

   您可以根據元件型別和片段中定義的引數，啟用顯示欄位的自訂功能。

   針對您想要允許自訂的每個欄位，將切換變更為啟用狀態。

1. 按一下&#x200B;**[!UICONTROL 總覽]**&#x200B;以檢閱所有可編輯的欄位及其預設值。

   ![檢閱可編輯的欄位及其預設值](./assets/fragment-editable-fields-image-overview.png){width="700" zoomable="yes"}

1. 儲存您的變更。

## 編輯連結的URL追蹤

{{$include /help/_includes/content-design-links.md}}
