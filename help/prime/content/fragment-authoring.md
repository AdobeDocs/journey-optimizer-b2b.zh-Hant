---
title: 片段製作
description: 使用視覺化設計工具製作可重複使用的內容片段 — 為Journey Optimizer B2B Prime中的電子郵件和範本新增結構、資產、個人化、條件式內容和連結URL追蹤。
badgeBeta: label="Beta" type="informative" tooltip="此功能屬於有限測試版的一部分。"
autotag-review: '2026-07-13T16:38:09.506Z'
TQID: 'https://experienceleague.adobe.com/Zn5L6Bc3x8SuGyjOPDdTWI-oxrrhk06a2f8ZvX2SN4s'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2:
  - id: e1663313-7961-4100-bea9-fa9f4edf8493
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 5206ed7bc0ce24e65700da28b023d76c68cb6419
workflow-type: tm+mt
source-wordcount: 215
ht-degree: 4%

---

# 片段編寫

在您[建立片段](./fragments.md#create-fragments)後，請使用視覺設計空間來編寫片段中的結構和內容元件。

## 新增結構和內容 {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## 新增資產 {#add-assets}

在視覺化設計空間中，選取左側導覽列中的&#x200B;_Assets_ （![Assets圖示](../../assets/do-not-localize/icon-assets-me.svg) ）圖示，以瀏覽並選取[!DNL Journey Optimizer B2B Prime]資產庫中的影像資產。

如需選取、取代或上傳影像資產的步驟，請參閱[使用資產進行內容製作](./digital-asset-management.md#assets-authoring)。

## 導覽圖層、設定和樣式 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## 將內容個人化 {#personalize-content}

[!DNL Journey Optimizer B2B Prime]使用Handlebars語法進行個人化。 Token在傳送時會取代為每個收件者設定檔資料的值。

新增個人化&#x200B;:_(_T)

1. 選取文字元件，然後按一下工具列中的&#x200B;_新增個人化_ （![個人化圖示](../../user/assets/do-not-localize/icon-personalize.svg) ）圖示。
1. 在個人化對話方塊中，瀏覽左側的架構樹並選取設定檔屬性。 編輯器會插入對應的Handlebars運算式，例如`{{profile.firstName}}`。
1. 如有需要，新增遞補值以處理遺漏的資料，例如`{{profile.firstName | default: "there"}}`。
1. 按一下&#x200B;**[!UICONTROL 確認]**&#x200B;或&#x200B;**[!UICONTROL 插入]**。 運算式會內嵌顯示於欄位中。

如需運算式編輯器工具和語法的詳細資訊，請參閱[Personalization編輯器](./personalization-expressions.md)。

## 編輯連結的URL追蹤 {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
