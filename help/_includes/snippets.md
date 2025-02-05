---
title: 程式碼片段
description: 重複使用附註和視覺元素，以記下套用至特定版本的功能或頁面
source-git-commit: 8892aff0501a157006506663ef304be5ccc9695c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# 程式碼片段

<!-- Content authoring steps for reuse -->

## 意圖資料設定 {#intent-data-note}

>[!NOTE]
>為您的Journey Optimizer B2B edition執行個體設定意圖資料時，該資料也可包含在頁面中。 如需有關意圖偵測模型以及如何提交關鍵字的詳細資訊，請參閱[意圖資料](../user/admin/intent-data.md)。
>

## AEM assets授權注意事項 {#aem-assets-licensing-note}

>[!NOTE]
>
>AEM Assets as a Cloud Service授權和Dynamic Media授權是整合的先決條件。 您應該確定已啟用[Dynamic Media withOpen API](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media-open-apis/dynamic-media-open-apis-overview){target="_blank"}。<br/>
>根據您的合約和設定，在設計視覺內容時，可以直接從Adobe Journey Optimizer B2B edition存取Adobe Experience Manager Assets as a Cloud Service 。

## 內容製作 — 元件 — 結構步驟 {#structures-step}

1. 若要開始您的內容設計，請從&#x200B;**[!UICONTROL 結構]**&#x200B;拖曳一個專案，然後將其放到畫布上。

   視需要從&#x200B;_[!UICONTROL 結構]_&#x200B;新增任意數目的專案，並編輯右側窗格中每個專案的設定。

   >[!TIP]
   >
   >選取&#x200B;_[!UICONTROL n：n欄]_&#x200B;元件以定義您選擇的欄數（介於3到10之間）。 您也可以移動欄下方的箭頭來定義每欄的寬度。

   ![將結構拖曳到畫布上並調整設定](../assets/content-design-shared/content-design-add-structure.png){width="800" zoomable="yes"}

   每個欄大小不能小於結構元件總寬度的10%。 只能移除空白欄。

## 內容製作 — 元件 — 內容步驟 {#contents-step}

1. 展開&#x200B;**[!UICONTROL 內容]**&#x200B;區段，並新增您所需數量的元素至一或多個結構元件。

   ![將內容元素拖曳到畫布上並調整設定](../assets/content-design-shared/content-design-add-content.png){width="800" zoomable="yes"}
   <!--
   reference to the contents elements--->

## 內容製作 — 元件 — 設定步驟 {#settings-step}

1. 如有需要，您可以在&#x200B;_[!UICONTROL 設定]_&#x200B;或&#x200B;_[!UICONTROL 樣式]_&#x200B;標籤中為每個元件進行其他自訂。

   例如，您可以變更每個元件的文字樣式、邊框間距或邊界。

## 內容製作 — 資產步驟 {#assets-step}

1. 您可以從&#x200B;_資產_&#x200B;選取器中直接選取儲存在資產庫中的資產。

   連按兩下包含資產的資料夾。 將專案拖放至結構元件中。

   如需有關使用來源型別中的資產的詳細資訊，請參閱[將資產新增至您的內容](../user/content/assets-overview.md#use-assets-for-content-authoring)。

   ![將Marketo Engage資產拖曳至畫布並調整設定](../assets/content-design-shared/content-design-add-asset.png){width="800" zoomable="yes"}

## 內容製作 — 個人化步驟 {#personalization-step}

1. 插入個人化欄位，從設定檔屬性、對象會籍、內容屬性等自訂內容。

## 內容製作 — 啟用條件內容步驟 {#dynamic-content-step}

1. 按一下&#x200B;**[!UICONTROL 啟用條件內容]**&#x200B;以新增動態內容，並根據條件規則將內容調整至目標設定檔。

## 內容製作 — 連結追蹤步驟 {#links-tracking-step}

1. 從左窗格中選取&#x200B;**[!UICONTROL 連結]**&#x200B;索引標籤，以顯示您所追蹤內容的所有URL。

   您可以修改&#x200B;_追蹤型別_&#x200B;或&#x200B;_標籤_，並視需要新增標籤。
